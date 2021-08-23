---
keywords: Script de perfil;atributos de script de perfil;prácticas recomendadas de script de perfil;depurar;depuración;scripts;scripts de perfil;atributos;atributo;parámetro
description: Obtenga información sobre los atributos específicos del visitante que se almacenan en el perfil del visitante para proporcionar información sobre los que se pueden usar en las actividades de Adobe [!DNL Target] .
title: ¿Qué son los atributos de perfil?
feature: Audiencias
exl-id: 6c689629-bbd3-461e-9a68-5b16d4eb4250
source-git-commit: f509fca07305d72cfc3ffd99d0e9a21b19dc6521
workflow-type: tm+mt
source-wordcount: '2403'
ht-degree: 50%

---

# Atributos de perfil

Los atributos de perfil en [!DNL Adobe Target] son parámetros específicos de un visitante. Estos atributos se almacenan en el perfil del visitante para proporcionar información acerca de ese visitante que puede utilizar en sus actividades.

Un perfil de usuario contiene información demográfica y de comportamiento de un visitante de una página web. Esta información puede incluir edad, sexo, productos comprados, última vez en la visita, etc., que [!DNL Target] utiliza para personalizar el contenido que sirve al visitante.

Cuando un visitante navega por su sitio web o regresa para otra sesión, los atributos de perfil guardados en el perfil se pueden utilizar para segmentar el contenido o registrar información para filtrar segmentos.

Para configurar atributos de perfil:

1. Haga clic en **[!UICONTROL Audiencias]** > **[!UICONTROL Scripts de perfil.]**

   ![Pestaña Scripts de perfil](/help/c-target/c-visitor-profile/assets/create-script.png)

1. Haga clic en **[!UICONTROL Crear script]**.

   ![Cuadro de diálogo Crear script de perfil](/help/c-target/c-visitor-profile/assets/profile-script.png)

   Se encuentran disponibles los siguientes tipos de atributos de perfil:

   | Tipo de parámetro | Descripción |
   |--- |--- |
   | mbox | Se pasan directamente a través del código de la página cuando el mbox se crea. Consulte [Pasar parámetros a un mbox global](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md).<br>**** Nota:  tiene un límite de 50 atributos de perfil únicos por llamada de mbox. [!DNL Target] Si debe pasar más de 50 atributos de perfil a [!DNL Target], páselo con el método de API Profile Update. Para obtener más información, consulte [Profile Update in the [!DNL Adobe Target] API documentation](https://developers.adobetarget.com/api/#updating-profiles). |
   | Perfil | Definido directamente con un fragmento de código de JavaScript. Estos fragmentos pueden almacenar totales en ejecución, como el dinero total gastado por el consumidor, y se ejecutan en cada solicitud de mbox. Consulte Atributos de script de perfil a continuación. |

## Atributos de script de perfil {#concept_8C07AEAB0A144FECA8B4FEB091AED4D2}

Defina un atributo de script de perfil con su fragmento de código de JavaScript asociado.

Los scripts de perfil se pueden usar para capturar atributos de visitantes en varias visitas. Los scripts de perfil son fragmentos de código definidos dentro de [!DNL Target] utilizando una forma de JavaScript del lado del servidor. Por ejemplo, puede utilizar un script de perfil para capturar la frecuencia con la que un visitante visita su sitio y el momento en el que lo hizo por última vez.

Los scripts de perfil no son lo mismo que los parámetros de perfil. Los parámetros de perfil capturan información sobre los visitantes mediante la implementación con código de mbox de [!DNL Target].

## Creación de scripts de perfil {#section_CB02F8B97CAF407DA84F7591A7504810}

Los scripts de perfil están disponibles en la ficha [!UICONTROL Audiencias] de la interfaz de [!DNL Target].

Para agregar un script de perfil, haga clic en la pestaña **[!UICONTROL Scripts de perfil]**, **[!UICONTROL Crear script]** y, a continuación, escriba el script.

O

Para copiar un script de perfil existente, en la lista [!UICONTROL Scripts de perfil], haga clic en el icono de elipsis del script deseado y, a continuación, haga clic en **[!UICONTROL Duplicar]**.

Luego puede editar la audiencia para crear otra parecida.

Los scripts ejecutan “catchers” de atributos de perfil en cada solicitud de ubicación. Cuando se recibe una solicitud de ubicación, [!DNL Target] determina qué actividad debe ejecutarse y muestra el contenido apropiado para esa actividad y esa experiencia. [!DNL Target] también rastrea el éxito de la actividad y ejecuta cualquier script de perfil relevante. Este proceso le permite realizar un seguimiento de la información sobre la visita, como la ubicación, la hora del día, la cantidad de veces que el visitante ha estado en el sitio, si ha realizado compras con anterioridad, etc. A continuación, esta información se agrega al perfil del visitante con el objetivo de rastrear mejor su actividad en el sitio.

Los atributos de script de perfil tienen la etiqueta `user.` insertada antes del nombre de atributo. Por ejemplo:

```
if (mbox.name == 'Track_Interest') { 
    if (profile.get('model') == "A5" &&; profile.get('subcat') == "KS6") { 
        return (user.get('A5KS6') || 0) + 1; 
    } 
}
```

Tenga en cuenta la siguiente información:

* Consulte los atributos de script de perfil (incluido el que se está usando) en el código con `user.get('parameterName')`.
* Guarde las variables a las que se puede acceder la próxima vez que se ejecute el script (en la siguiente solicitud de mbox) con `user.setLocal('variable_name', 'value')`. Haga referencia a la variable con `user.getLocal('variable_name')`. Este proceso resulta útil en situaciones en las que desea hacer referencia a la fecha y hora de la última solicitud.
* Los parámetros y valores distinguen entre mayúsculas y minúsculas. Haga coincidir las mayúsculas y minúsculas de los parámetros y valores que reciba durante la actividad o prueba.
* Consulte la sección “Referencia JavaScript para parámetros de perfil de secuencia de comandos” para obtener más sintaxis de JavaScript.
* El parámetro permanece en el perfil después de deshabilitar la secuencia de comandos. Los usuarios cuyos perfiles ya contienen un parámetro que se utiliza en la audiencia de una actividad se califican en esa actividad.
* Los scripts de perfil no se pueden eliminar mientras se utilizan en una actividad.
* No se recomienda crear scripts de perfil dependientes que utilicen el resultado de un script de perfil en otro script de perfil. No se garantiza el orden de ejecución de la secuencia de comandos del perfil.

## Visualización de tarjetas de información de scripts de perfil {#section_18EA3B919A8E49BBB09AA9215E1E3F17}

Puede ver tarjetas emergentes con información sobre scripts de perfil similares a las tarjetas de información de ofertas. Estas tarjetas le permiten ver la lista de actividades que hacen referencia al script de perfil seleccionado, además de otros metadatos útiles.

Por ejemplo, se accede a la siguiente tarjeta de información de script de perfil haciendo clic en el icono [!UICONTROL Info] del script de perfil deseado en la lista ([!UICONTROL Audiencias] > [!UICONTROL Scripts de perfil]).

La pestaña [!UICONTROL Información de script] contiene la siguiente información: Nombre, Descripción y código de secuencia de comandos.

![Tarjeta de información de script de perfil](assets/profile_script_info_card.png)

Haga clic en **[!UICONTROL Ver detalles completos]** para ver las audiencias y actividades que hacen referencia al script de perfil seleccionado.

![Tarjeta de información de script de perfil > Pestaña Uso de script](assets/profile_script_info_card_usage_tab.png)

>[!NOTE]
>
>La pestaña [!UICONTROL Uso del script] no muestra las actividades que hacen referencia al script de perfil seleccionado en las siguientes situaciones:
>
> * La actividad está en el estado [!UICONTROL Borrador].
> * El contenido u oferta utilizado en la actividad emplea variables de script (una oferta en línea dentro de la actividad o una oferta de la biblioteca de ofertas).


## Target deshabilita los scripts de perfil en determinadas situaciones {#section_C0FCB702E60D4576AD1174D39FBBE1A7}

[!DNL Target] deshabilita automáticamente los scripts de perfil en determinadas situaciones, como cuando tardan demasiado en ejecutarse o tienen demasiadas instrucciones.

Cuando se deshabilita un script de perfil, aparece un icono de alerta amarillo junto al script del perfil en la interfaz de usuario de Target, como se muestra a continuación:

![](assets/profile_script_invalid.png)

Al pasar el ratón por encima, aparecen los detalles del error, como se muestra a continuación:

![](assets/profile_script_hover.png)

Estas son las razones habituales por las que el sistema deshabilita los scripts de perfil:

* Se hace referencia a una variable sin definir.
* Se hace referencia a un valor no válido. Este error suele deberse a valores de URL y a otros datos introducidos por el usuario sin la validación adecuada.
* Se están utilizando demasiadas instrucciones JavaScript. [!DNL Target] tiene un límite de 2000 instrucciones JavaScript por script, pero este límite no se puede calcular simplemente leyendo manualmente el JavaScript. Por ejemplo, Rhino trata todas las llamadas de función y “nuevas” llamadas como 100 instrucciones. Cualquier llamada a cualquier función consume 100 instrucciones. Además, el tamaño de los datos de entrada, como los valores URL, puede afectar a la contabilización de instrucciones.
* Elementos no destacados en la sección [prácticas recomendadas](/help/c-target/c-visitor-profile/profile-parameters.md#section_64AFE5D2B0C8408A912FC2A832B3AAE0) a continuación.

## Prácticas recomendadas {#best}

Las siguientes directrices pretenden ayudarle a escribir secuencias de comandos de perfil simplificadas que tengan la menor probabilidad de caer en errores mientras escribe el código que falla, por lo que se procesa sin forzar una parada de secuencia de comandos del sistema. Estas instrucciones son el resultado de las prácticas recomendadas cuya eficacia ha sido demostrada. Estas directrices se tiene que aplicar junto a los principios y recomendaciones descritos por la comunidad de desarrollo Rhino.

* Establezca el valor de la secuencia de comandos actual en una variable local de la secuencia de comandos del usuario y establezca una conmutación por error en una cadena en blanco.
* Valide la variable local y asegúrese de que no se trate de una cadena en blanco.
* Utilice funciones de manipulación basadas en cadenas en lugar de expresiones regulares.
* Utilice bucles limitados en lugar de bucles sin fin o continuos.
* No supere los 1300 caracteres o las 50 repeticiones de bucle.
* No supere las 2000 instrucciones de JavaScript. [!DNL Target] tiene un límite de 2000 instrucciones JavaScript por script, pero este límite no se puede calcular simplemente leyendo manualmente el JavaScript. Por ejemplo, Rhino trata todas las llamadas de función y “nuevas” llamadas como 100 instrucciones. Además, el tamaño de los datos de entrada, como los valores URL, puede afectar a la contabilización de instrucciones.
* Tenga en cuenta no solo el rendimiento del script, sino también el rendimiento combinado de todos los scripts. Como práctica recomendada, [!DNL Adobe] recomienda menos de 5000 instrucciones en total. El recuento del número de instrucciones no es obvio, pero lo importante es que los scripts que exceden las 2000 instrucciones se desactivan automáticamente. El número de scripts de perfil activos no debe superar los 300. Cada secuencia de comandos se ejecuta con cada llamada de mbox. Ejecute solo los scripts necesarios.
* En una regex, tener punto y asterisco al principio (por ejemplo: `/.*match/`, `/a|.*b/`) casi nunca es necesario. La búsqueda de regex comienza desde todas las posiciones en una cadena (a menos que se enlace con `^`), por lo que se asume un punto y un asterisco. La ejecución de la secuencia de comandos se puede interrumpir si este regex coincide con datos de entrada lo suficientemente largos (que pueden contener varios cientos de caracteres).
* Si falla todo, ajuste el script a un try/catch.
* Las siguientes recomendaciones pueden ayudarle a limitar la complejidad del script de perfil. Los scripts de perfil pueden ejecutar un número limitado de instrucciones.

   Como práctica recomendada:

   * Mantenga los scripts de perfil pequeños y lo más simples posible.
   * Evite las expresiones regulares o utilice solo expresiones regulares simples. Incluso las expresiones simples pueden requerir muchas instrucciones para evaluarlas.
   * Evite la recursión.
   * Los scripts de perfil deben probarse de rendimiento antes de agregarse a [!DNL Target]. Todos los scripts de perfil se ejecutan en cada solicitud de mbox. Si los scripts de perfil no se ejecutan correctamente, las solicitudes de mbox tardan más en ejecutarse, lo que puede afectar al tráfico y la conversión.
   * Si los scripts de perfil se vuelven demasiado complejos, considere la posibilidad de utilizar [tokens de respuesta](/help/administrating-target/response-tokens.md) en su lugar.

* Consulte la documentación del motor JS Rhino para obtener más información.

## Depuración de scripts de perfil {#section_E9F933DE47EC4B4E9AF2463B181CE2DA}

Se pueden utilizar los métodos siguientes para depurar scripts de perfil:

>[!NOTE]
>
>El uso de [!DNL console.log] en un script de perfil no genera el valor del perfil, ya que los scripts de perfil se ejecutan en el servidor.

* **Añada scripts de perfil como tokens de respuesta para depurar scripts de perfil:**

   En [!DNL Target], haga clic en **[!UICONTROL Administration]**, en **[!UICONTROL Response Tokens]** y, a continuación, habilite el script de perfil que desea depurar.

   Cada vez que carga una página para su sitio con [!DNL Target], parte de la respuesta de [!DNL Target] contiene el valor del script de perfil dado, como se muestra a continuación:

   ![](assets/debug_profile_script_1.png)

* **Utilice la herramienta de depuración mboxTrace para depurar scripts de perfil.**

   Este método requiere un token de autorización que puede generarse haciendo clic en **[!UICONTROL Target]** > **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!UICONTROL Generate Authorization Token]** en la sección [!UICONTROL Debugger tools].

   A continuación, agregue estos dos parámetros a la URL de su página después de &quot;?&quot;: `mboxTrace=window&authorization=YOURTOKEN`.

   Añadir estos parámetros es un poco más informativo que el token de respuesta, ya que se obtiene una instantánea del perfil anterior a la ejecución y otra posterior a la ejecución. También muestra todos los perfiles disponibles.

   ![](assets/debug_profile_script_2.png)

## Preguntas más frecuentes sobre scripts de perfil {#section_1389497BB6D84FC38958AE43AAA6E712}

**¿Es posible utilizar scripts de perfil para capturar información de una página que reside en una capa de datos?**

Los scripts de perfil no pueden leer la página directamente porque se ejecutan en el lado del servidor. Los datos se deben pasar a través de una solicitud de mbox o a través de otros  [métodos de obtención de datos en Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17). Una vez que los datos están en [!DNL Target], los scripts de perfil pueden leer los datos como un parámetro de mbox o un parámetro de perfil.

## Referencia de JavaScript para parámetros de perfil de secuencia de comandos

Se requiere conocimiento simple de JavaScript para utilizar de forma eficaz el perfil de secuencia de comandos
parámetros. Esta sección sirve como referencia rápida para aumentar su productividad con esta funcionalidad en solo unos minutos.

Los parámetros de perfil de secuencia de comandos se encuentran en la pestaña mboxes/perfiles. Puede escribir programas Javascript que devuelvan cualquier tipo de Javascript (cadena, número entero, matriz, etc.).

### Ejemplos de parámetros de perfil de secuencia de comandos {#examples}

**Nombre:** *user.recency*

```
var dayInMillis = 3600 * 24 * 1000;
if (mbox.name == 'orderThankyouPage') {
    user.setLocal('lastPurchaseTime', new Date().getTime());
}
var lastPurchaseTime = user.getLocal('lastPurchaseTime');
if (lastPurchaseTime) {
    return ((new Date()).getTime() - lastPurchaseTime) / dayInMillis;
}
```

Crea una variable por día según se mide en milisegundos. Si el nombre del mbox es `orderThankyouPage`, configure un atributo de perfil de usuario local (invisible) denominado `lastPurchaseTime` para que muestre el valor de la fecha y la hora actuales. El valor de la última compra se lee y, si se define, [!DNL Target] devuelve el tiempo que ha pasado desde la última compra, dividido por el número de milisegundos en un día (lo que resulta en el número de días desde la última compra).

**Nombre:** *user.frequency*

```
var frequency = user.get('frequency') || 0;
if (mbox.name == 'orderThankyouPage') {
    return frequency + 1;
}
```

Crea una variable llamada `frequency`, inicializándola en el valor anterior o 0, si no había ningún valor anterior. Si el nombre del mbox es `orderThankyouPage`, se devuelve el valor incrementado.

**Nombre:** *user.monetaryValue*

```
var monetaryValue = user.get('monetaryValue') || 0;
if (mbox.name == 'orderThankyouPage') {
    return monetaryValue + parseInt(mbox.param('orderTotal'));
}
```

Crea una variable llamada `monetaryValue`, buscando el valor actual para un visitante determinado (o configurándolo en 0 si no había ningún valor anterior). Si el nombre del mbox es `orderThankyouPage`, se devuelve un nuevo valor monetario sumando el valor anterior y el valor del parámetro `orderTotal` que se pasa al mbox.

**Nombre:** adobeQA

```
if (page.param("adobeQA"))
     return page.param("adobeQA");
else if (page.param("adobeqa"))
     return page.param("adobeqa");
else if (mbox.param("adobeQA"))
     return mbox.param("adobeQA");
```

Crea una variable denominada `adobeQA` para rastrear a un usuario para [Control de calidad de la actividad](/help/c-activities/c-activity-qa/activity-qa.md).

### Objetos y métodos

Los parámetros de perfil de secuencia de comandos pueden hacer referencia a las siguientes propiedades y métodos:

| Objeto o método | Detalles |
| --- | --- |
| `page.url` | La dirección URL actual |
| `page.protocol` | El protocolo usado para la página (http o https). |
| `page.domain` | El dominio URL actual (todo antes de la primera barra). Por ejemplo, `www.acme.com` en `http://www.acme.com/categories/men_jeans?color=blu e&size=small`. |
| `page.query` | La cadena de consulta de la página actual. Todo después de “?”. Por ejemplo, `blue&size=small` en `http://www.acme.com/categories/mens_jeans?color=blue&size=small`. |
| `page.param(‘<par_name>’)` | El valor del parámetro indicado por `<par_name>`. Si la dirección URL actual es la página de búsqueda de Google y había introducido `page.param('hl')`, obtendrá “en” para la dirección URL `http://www.google.com/search?hl=en& q=what+is+asdf&btnG=Google+Search`. |
| `page.referrer` | El mismo conjunto de operaciones que se aplica anteriormente se aplica al referente y al aterrizaje (es decir, referrer.url es la dirección url del referente). |
| `landing.url`, `landing.protocol`, `landing.query`, y `landing.param` | Similar a la de la página, pero para la página de aterrizaje. |
| `mbox.name` | El nombre del mbox activo. |
| `mbox.param(‘<par_name>’)` | Un parámetro de mbox por el nombre dado en el mbox activo. |
| `profile.get(‘<par_name>’)` | El parámetro de perfil de usuario creado por el cliente por el nombre `<par_name>`. Por ejemplo, si el usuario configura un parámetro de perfil denominado “gender”, el valor se puede extraer usando “profile.gender”. Devuelve el valor de “`profile.<par_name>`” configurado para el visitante actual; devuelve nulo si no se ha establecido ningún valor. Tenga en cuenta que `profile.get(<par_name>)` se califica como una llamada de función. |
| `user.get(‘<par_name>’)` | Devuelve el valor de “`user.<par_name>`” configurado para el visitante actual; devuelve nulo si no se ha establecido ningún valor. |
| `user.categoryAffinity` | Devuelve el nombre de la mejor categoría. |
| `user.categoryAffinities` | Devuelve una matriz con las mejores categorías. |
| `user.isFirstSession` | Devuelve verdadero si es la primera sesión del visitante. |
| `user.browser` | Devuelve el agente de usuario en el encabezado HTTP. Como por ejemplo, puede crear un objetivo de expresión únicamente dirigido a los usuarios de Safari: `if (user.browser != null && user.browser.indexOf('Safari') != -1) { return true; }` |

### Operadores comunes


Todos los operadores de JavaScript estándar están presentes y pueden utilizarse. Los operadores JavaScript se pueden usar en cadenas y números (y en otros tipos de datos). Una breve explicación:

| Operador | Descripción |
| --- | --- |
| `==` | Indica igualdad. Es verdadero cuando los operandos de ambos lados son iguales. |
| `!=` | Indica desigualdad. Es verdadero cuando los operandos de ambos lados no son iguales. |
| `<` | Indica que la variable a la izquierda es menor que la variable de la derecha. Evalúa a false si las variables son iguales. |
| `>` | Indica que la variable a la izquierda es mayor que la variable de la derecha. Evalúa a false si las variables son iguales. |
| `<=` | Igual que `<` excepto si las variables son iguales, que entonces se evalúa como verdadero. |
| `>=` | Igual que `>` excepto si las variables son iguales, que entonces se evalúa como verdadero. |
| `&&` | Lógicamente “Y” las expresiones a la izquierda y a la derecha de la misma, son solo verdaderas cuando ambos lados son verdaderos (falso en caso contrario). |
| `||` | Lógicamente “O” las expresiones a la izquierda y a la derecha de la misma, son solo verdaderas si uno de los lados es verdadero (falso en caso contrario). |
| `//` | Comprueba si la fuente contiene todos los elementos que el booleano de destino contiene (origen de matriz, destino de matriz).<br>`//` extrae la subcadena de destino (correspondiente a regexp) y la descodifica `Array/*String*/ decode(String encoding, String regexp, String target)`.<br>La función también es compatible con el uso de valores de cadena constantes, agrupación (`condition1 || condition2) && condition3` y expresiones regulares (`/[^a-z]$/.test(landing.referring.url)`. |

## Vídeo de formación: Scripts de perfil ![Distintivo del tutorial](/help/assets/tutorial.png)

En este vídeo se explica cómo usar y crear scripts de perfil.

* Explicar qué es un script de perfil
* Explicar en qué se diferencia un script de perfil de un parámetro de perfil
* Crear un script de perfil simple
* Usar el menú Token disponible para acceder a las opciones disponibles
* Habilitar y deshabilitar scripts de perfil

>[!VIDEO](https://video.tv.adobe.com/v/17394)
