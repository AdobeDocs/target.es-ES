---
keywords: atributos de entidad de varios valores;atributos de entidad personalizados;JSON válido;valor de atributo de entidad;matriz de JSON;varios valores;valores múltiples
description: Aprenda a utilizar atributos de entidad personalizados de uno o varios valores para definir información adicional sobre los elementos del catálogo de Adobe [!DNL Target] Recommendations.
title: ¿Cómo utilizo los atributos de entidad personalizados?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
mini-toc-levels: 3
exl-id: d7d0b04a-0f50-4d30-9cbe-c0347a3d3715
TQID: 'https://experienceleague.adobe.com/eFeg78-PswBCwtpzMR7j5c8FJ03MyQVcSdzo6ctZt3Q'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 5ed511322cc9f04c349471f8ad84a17526d4925f
workflow-type: tm+mt
source-wordcount: '1347'
ht-degree: 55%
---
# Atributos de entidad personalizados {#custom-entity-attributes}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a definir, enviar y utilizar atributos de entidad personalizados de uno o varios valores que describan los elementos del catálogo [!DNL Adobe Target Recommendations].

>[!ENDSHADEBOX]

Use atributos de entidad personalizados de uno o varios valores en [!DNL Adobe Target Recommendations] para definir información adicional sobre los elementos del catálogo. Esta información se puede utilizar en reglas de inclusión de algoritmos, reglas de catálogo y reglas de exclusión, y se puede mostrar en diseños de.

## Límites {#limits}

Puede incluir hasta 100 atributos de entidad personalizados para definir información adicional sobre los artículos de su catálogo. Por ejemplo, puede crear un atributo personalizado llamado `entity.genre` para definir un libro o una película. O un vendedor de entradas podría crear atributos del lugar de celebración para incluir un actor secundario, como un equipo visitante en un evento deportivo o un acto de apertura en un concierto.

La longitud máxima de los atributos personalizados de entidad de un solo valor es de 15 000 caracteres (para idiomas con codificación UTF-8 de uno y dos bytes, como inglés y otros alfabetos latinos) o 10 000 caracteres (para lenguajes con codificación UTF-8 de tres bytes, como chino, japonés y coreano).

Los atributos personalizados de entidad de varios valores no pueden contener más de 500 valores. Cada valor individual está limitado a 100 caracteres. El número total de caracteres en todos los valores debe cumplir las limitaciones de la longitud máxima de atributos personalizados de entidad de un solo valor (ver arriba).

## Valores de atributo de entidad personalizados {#section_313331A9F8194A89B5EDD89363018651}

Los atributos de entidad personalizados pueden contener uno o varios valores. Los valores de los atributos de entidad se muestran en la vista del producto.

![imagen multi-value_product](assets/multi-value_product.png)

Un atributo de entidad personalizado con un solo valor tiene el mismo formato que un atributo de entidad predefinido de un solo valor:

`entity.genre=genre1`

Un atributo de entidad personalizado con varios valores se debe enviar como una matriz de JSON válida:

`entity.genre=["genre1", "genre2"]`

Estos son ejemplos de matrices de JSON válidas compatibles con [!DNL Recommendations]:

* `["AB","BC"]` todos los valores son cadenas
* `[1,2]` todos los valores son numéricos

>[!NOTE]
>
>[!DNL Recommendations] no admite mezclas de tipos de valores en los atributos de entidad de varios valores. Por ejemplo, `["AB",1,true, [1,2,3]]` es una matriz de JSON válida, pero [!DNL Recommendations] no la admite porque incluye una mezcla de tipos de valores (cadena, número, booleano, objeto).

Cuando un atributo personalizado se envía como matriz de JSON válida, se trata como un atributo de varios valores en todos los productos del catálogo.

>[!NOTE]
>
>Para cambiar un atributo de varios valores a otro que sea de un valor, tiene que eliminar el catálogo y cargar los datos de los productos corregidos. Al eliminar el catálogo, no se eliminan los datos históricos asociados con los identificadores de los productos. Consulte [Eliminar todos los artículos del sistema](/help/main/assets/adobe-recommendations-classic.pdf) en la documentación de *Adobe Recommendations Classic* para obtener más información.

**Restricciones**:

* No se pueden usar nombres de atributos de entidad predefinidos para atributos de entidad personalizados. (Consulte [Atributos de entidad](/help/main/c-recommendations/c-products/entity-attributes.md#entity-attributes)).
* El atributo `entity.environment` se reserva para el sistema y no se puede usar en atributos de entidad personalizados. Se hará caso omiso de los intentos de pasar `entity.environment` usando `targetPageParams`, fuentes o API.
* Las matrices deben contener un solo tipo de valor. Las matrices con valores mezclados (`["AB",1,true]`) no se admiten.
* Un atributo de varios valores que incluye una matriz de JSON anidada (`[10,12,[1,2,3]]`) se trata como un atributo de un valor.

## Implementación de atributos de varios valores {#section_80FEFE49E8AF415D99B739AA3CBA2A14}

Los atributos de entidad personalizados de varios valores se admiten al usar fuentes (CSV), `targetPageParams` y la API de entrega para cargar productos. Los valores nuevos reemplazan a los actuales, no se adjuntan. Las matrices vacías ( []) se tratan como si no tuvieran valores.

Las comillas dobles se deben escapar. Por ejemplo, `"[""test"", ""value""]"` es una matriz JSON válida que se pueden usar en CSV.

### Uso de targetPageParams

El siguiente ejemplo muestra cómo usar `targetPageParams`:

```javascript
function targetPageParams() { 
  return { 
    'entity.id':                   '123', 
    'entity.categoryId':            '["A", "A:B", "A:B:C", "A:B:C:D"]',        
    'entity.MultiValueAttribute':   '["X", "Y", "Z"]', 
    'entity.event.detailsOnly':     'true', 
    'excludedIds':                  '[123, 3232, 2323, 4344]', 
    'orderId':                      '123456', 
    'orderTotal':                   '195.32', 
    'productPurchaseId':            '[001,002,003]' 
  }; 
}
```

### Uso del CSV

Puede administrar los archivos CSV sin procesar mediante un editor de texto o usar un programa de hojas de cálculo.

El CSV sin procesar tendrá este aspecto:

![imagen multi-value_example_raw](assets/multi-value_example_raw.png)

El mismo catálogo se verá del modo siguiente en una hoja de cálculo:

![imagen multi-value_example_excel](assets/multi-value_example_excel.png)

Al convertir al formato .csv, el programa de hojas de cálculo encierra entre comillas dobles el contenido de las celdas para evitar que las comas de la celda funcionen como separadores de columnas. También encierra entre comillas dobles los valores de las cadenas JSON que se incluyen en los atributos personalizados de varios valores. Esto puede hacer que trabajar directamente con el archivo sin procesar sea un poco complicado. Por ejemplo:

* Hoja de cálculo: `["1","2","3"]`
* Sin procesar: `"[""1"",""2"",""3""]"`

Tenga cuidado al editar directamente un archivo CSV de catálogo sin procesar.

### Uso de API

Puede pasar atributos de varios valores utilizando la API de entrega en un parámetro de mbox como un valor de cadena que contiene una matriz JSON de escape.

```javascript
"execute": {
    "mboxes": [
      {
        "index": 0,
        "name": "first-mbox",
        "parameters": {
          "entity.id": "32323",
          "entity.categoryId": "My Category",
          "entity.MultiValueAttribute": "[\"X\", \"Y\", \"Z\"]"
        }
      }
    ]
  }
```

Consulte la [documentación de la API de Adobe Recommendations](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=es){target=_blank} para obtener información sobre el uso de las API Entrega y Guardar entidades.

## Uso de operadores con atributos de varios valores {#section_83C2288A805242D9A02EBC4F07DEE945}

Al aplicar operadores a atributos personalizados de varios valores en reglas de inclusión de algoritmos, reglas de catálogo y reglas de exclusión, el resultado es *true* si al menos un valor de la lista cumple el criterio de la operación (booleano *OR*).

En el ejemplo siguiente, la regla es `message contains abc`.

* Caso 1: `entity.genre = ["ab", "bc", "de"]`. El resultado es false porque ningún valor contiene `abc`.
* Caso 2: `entity.genre = ["abcde","de","ef"]`. El resultado es true porque un valor contiene `abc`.

En el caso de los operadores negativos, todos los valores de atributo deben cumplir el criterio (booleano *AND*). Por ejemplo, si el operador es `notEquals`, el resultado será *false* si algún valor coincide.

En la tabla siguiente se resume el comportamiento de cada operador y se proporcionan los casos de cada regla de ejemplo.

| Operador | El resultado es verdadero cuando | Regla de ejemplo | Valor de atributo | Resultado | Motivo |
|---|---|---|---|---|---|
| Es igual a | Cualquier valor de atributo es igual al valor de entrada. | `genre equals abc` | `["ab", "bc", "de"]` | Falso | Ningún valor es igual a `abc`. |
|  |  |  | `["abc", "de", "ef"]` | True | Un valor es igual a `abc`. |
|  |  |  | `["abcde", "de", "ef"]` | Falso | `abc` no es igual a ningún elemento de la lista. |
| No es igual a | Ningún valor de atributo es igual al valor de entrada. | `genre not equals abc` | `["ab", "bc", "de"]` | True | Ningún valor es igual a `abc`. |
|  |  |  | `["abc", "de", "ef"]` | Falso | Un valor es igual a `abc`. |
|  |  |  | `["abcde", "de", "ef"]` | True | `abc` no es igual a ningún elemento de la lista. |
| Contiene | Cualquier valor de atributo contiene el valor de entrada. | `genre contains abc` | `["ab", "bc", "de"]` | Falso | Ningún valor contiene `abc`. |
|  |  |  | `["abcde", "de", "ef"]` | True | Un valor contiene `abc`. |
| No contiene | Ningún valor de atributo contiene el valor de entrada. | `genre does not contain abc` | `["ab", "bc", "de"]` | True | Ningún valor contiene `abc`. |
|  |  |  | `["abcde", "de", "ef"]` | Falso | Un valor contiene `abc`. |
| Comienza con | Cualquier valor de atributo comienza con el valor de entrada. | `genre starts with abc` | `["ab", "bc", "de"]` | Falso | Ningún valor comienza con `abc`. |
|  |  |  | `["abcde", "de", "ef"]` | True | Un valor comienza con `abc`. |
|  |  |  | `["ab", "de", "abc"]` | True | Un valor comienza por `abc` (no necesariamente el primer elemento de la lista). |
| Finaliza con | Cualquier valor de atributo termina con el valor de entrada. | `genre ends with abc` | `["ab", "bc", "de"]` | Falso | Ningún valor termina en `abc`. |
|  |  |  | `["deabc", "de", "ef"]` | True | Un valor termina con `abc`. |
| Es mayor o igual que (solo valores numéricos) | Cualquier valor de atributo es mayor o igual que el valor de entrada. Cada valor se convierte en el doble y los valores que no se pueden convertir se omiten mientras se ejecuta la regla. | `price greater than or equal to 100` | `["10", "20", "45", "de"]` | Falso | Ningún valor es mayor o igual que 100. El valor `de` se pasa por alto porque no se puede convertir en el doble. |
|  |  |  | `["100", "101", "90", "80"]` | True | Dos valores son mayores o iguales que 100. |
| Es menor o igual que (solo valores numéricos) | Cualquier valor de atributo es menor o igual que el valor de entrada. Cada valor se convierte en el doble y los valores que no se pueden convertir se omiten mientras se ejecuta la regla. | `price less than or equal to 100` | `["101", "200", "141", "de"]` | Falso | Ningún valor es menor o igual que 100. El valor `de` se pasa por alto porque no se puede convertir en el doble. |
|  |  |  | `["100", "101", "90", "80"]` | True | Dos valores son menores o iguales a 100. |
| Coincide dinámicamente (solo disponible en algoritmos de artículos) | Cualquier valor de atributo coincide con el valor de entrada. | `genre matches abc` | `["ab", "bc", "de"]` | Falso | Ningún valor coincide con `abc`. |
|  |  |  | `["abc", "de", "ef"]` | True | Un valor coincide con `abc`. |
| No coincide dinámicamente (solo disponible en algoritmos de artículos) | Ningún valor de atributo coincide con el valor de entrada. El resultado es false si algún valor de atributo coincide. | `genre does not match abc` | `["ab", "bc", "de"]` | True | Ningún valor coincide con `abc`. |
|  |  |  | `["abc", "de", "ef"]` | Falso | Un valor coincide con `abc`. |
| Se incluye dinámicamente en el rango (solo disponible en algoritmos de artículos y solo valores numéricos) | Cualquier valor de atributo numérico se encuentra dentro del rango especificado. | `price dynamically ranges in 80% to 120% of 100` | `["101", "200", "125", "de"]` | True | `101` está en el rango del 80% al 120% de 100. El valor `de` se pasa por alto porque no se puede convertir en el doble. |
|  |  |  | `["130", "191", "60", "75"]` | Falso | Ningún valor está en el rango del 80 % al 120 % de 100. |

>[!NOTE]
>
>*Doble* es un tipo de datos de Java. Con los operadores que requieren valores numéricos, convertir en doble elimina los valores no numéricos de los resultados, ya que no se tienen en cuenta.

## Atributos de varios valores en diseños {#section_F672E4F6E1D44B3196B7ADE89334ED4A}

Los atributos de varios valores aparecen como una lista separada por comas cuando se hace referencia a ellos en un diseño.

Ejemplo:

Cuando se hace referencia a `entity.genre=["genre1","genre2"]` en un diseño como `$entity<N>.genre`, el resultado es `genre1, genre2`.

## Temas relacionados

* [Atributos de entidad](/help/main/c-recommendations/c-products/entity-attributes.md#entity-attributes)
