---
title: Extensión de indicadores para la guía de integración web
description: Obtenga información sobre cómo integrar la extensión Flags con Adobe Experience Platform Web SDK (Alloy) para aplicaciones web.
badge: label="Beta" type="Informative"
hide: true
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
source-git-commit: a25ca0f3ce4c9cf38a871d8193ec43250d61edb9
workflow-type: tm+mt
source-wordcount: '1241'
ht-degree: 7%
---
# Extensión de marcas para la web {#web-extension-integration-guide}

En esta guía se describe cómo integrar la extensión Flags con Adobe Experience Platform Web SDK (Alloy) para aplicaciones web. La extensión Flags permite la administración de indicadores de funciones y despliegues controlados para experiencias web.

## Requisitos previos {#prerequisites}

Antes de implementar la extensión Banderas, asegúrese de lo siguiente:

* Una propiedad web configurada en [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/#/data-collection)
* Extensión de Adobe Experience Platform Web SDK instalada
* Un ID de organización de Adobe Experience Cloud
* Acceso a los indicadores en su organización

### Permisos necesarios {#required-permissions}

Asegúrese de que tiene los siguientes derechos de propiedad:

* Desarrollar
* Administración de extensiones

## Dependencias de extensión {#extension-dependencies}

La extensión Flags requiere la siguiente extensión de Adobe Experience Platform:

| Extensión | Descripción | Requerido |
|---|---|---|
| Adobe Experience Platform Web SDK | Proporciona funcionalidad principal, incluidas comunicación de Edge Network y administración de identidades | Sí |

Asegúrese de que esta extensión esté instalada en la propiedad web de recopilación de datos antes de instalar la extensión de marcas.

## Configuración de la extensión Flags en la recopilación de datos {#configure}

### Instalación de la extensión {#install-extension}

1. Inicie sesión en [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection).

1. Seleccione la ficha **[!UICONTROL Etiquetas]** y elija su propiedad móvil.

1. Vaya a **[!UICONTROL Extensiones]** > **[!UICONTROL Catálogo]**.

1. Busque **[!DNL Adobe Flags]** y seleccione **[!UICONTROL Instalar]**.

   ![](../assets/extension-install.png)

#### Configuración de la extensión {#configure-extension-settings}

Al instalar la extensión Banderas, se le redirige a la página de configuración. Configure los siguientes ajustes:

| Configuración | Descripción | Requerido |
|---|---|---|
| ID del cliente | Un identificador único para su aplicación en Banderas. | Sí |

#### Publicación de la extensión {#publish-extension}

Siga el [proceso de publicación](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) para actualizar la configuración.

1. Añada la extensión a una biblioteca.

1. Compile en su entorno de desarrollo.

1. Validar con [Adobe Experience Platform Debugger](https://experienceleague.adobe.com/docs/experience-platform/debugger/home.html).

1. Enviar a ensayo y producción.

## Añadir el código incrustado de etiquetas en el sitio web {#embed-code}

Después de publicar la biblioteca de etiquetas, debe agregar el código incrustado al sitio web. El código incrustado es una etiqueta `<script>` que carga la biblioteca de etiquetas y todas las extensiones configuradas, incluida la extensión de marcas.

### Copiar el código de incrustación {#copy-embed-code}

1. En Recopilación de datos, vaya a la propiedad web.

1. Acceda al menú **[!UICONTROL Entornos]**.

1. Seleccione el icono de cuadro en la columna **[!UICONTROL Instalar]** del entorno seleccionado.

   ![](../assets/extension-install-2.png)

1. En el cuadro de diálogo **[!UICONTROL Instrucciones de instalación web]**, Etiquetas toma como valor predeterminado el código incrustado asincrónico.

1. Seleccione el icono **[!UICONTROL Copiar]** para copiar el código incrustado en el portapapeles.

   >[!NOTE]
   >
   >Cada entorno tiene una URL de código incrustado única. Consulte la documentación de [Entornos](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=es) para obtener más información.

   ![](../assets/extension-install-4.png)

### Implementación del código incrustado {#implement-embed-code}

>[!NOTE]
>
>Reemplace la URL `src` con su código incrustado real de la página Entornos. La dirección URL contiene el identificador de su compañía, el identificador de propiedad y el identificador de entorno (por ejemplo, `launch-EN123456789abcdef.min.js`).

Agregue el código incrustado en el elemento `<head>` de sus páginas de HTML. El código incrustado debe colocarse antes de otros scripts que dependan de la biblioteca de etiquetas:

```html
<!DOCTYPE html>
<html>
<head>
  <title>My Website</title>

  <!-- Adobe Experience Platform Tags embed code -->
  <script src="https://assets.adobedtm.com/your-company/your-property/launch-ENxxxxxxxxxxx.min.js" async></script>
</head>
<body>
  <!-- Your page content -->
</body>
</html>
```

### Evaluación de indicadores con componentes de etiquetas {#tags-components}

La extensión Flags proporciona superficies de evaluación nativas de etiquetas.

| Componente | Tipo | Descripción |
|---|---|---|
| La Función Está Activada | Condición | Devuelve si una característica está habilitada para el usuario o contexto actual |
| Marca de característica | Elemento de datos | Devuelve un objeto de característica booleano o completo |

## Inicialización de SDK {#initialize-sdk}

La extensión de marcas se inicializa automáticamente cuando se carga la biblioteca de etiquetas. La extensión expone al cliente en:

```javascript
window._flagClient
```

### Espere a que el cliente esté preparado {#client-readiness}

Las etiquetas se cargan asincrónicamente. Antes de llamar a los métodos de SDK desde el código personalizado, espere hasta que se inicialice el cliente:

```javascript
window.flagClientReady
  .then(function () {
    const enabled = window._flagClient.isFeatureEnabled('my-feature', context);
    // Use enabled to select the feature or fallback behavior.
  })
  .catch(function (error) {
    console.error('Flags initialization failed:', error);
  });
```

## Contexto de evaluación {#evaluation-context}

`FeatureEvaluationContext` incluye identidad (necesaria para evaluación, agrupación A/B y análisis) y atributos de segmentación opcionales (utilizados para coincidencia de reglas).

| Propiedad | Requerido | Descripción |
|---|---|---|
| `identityNamespace` | Sí | Área de nombres Identity (consulte [Áreas de nombres Identity de Adobe](https://experienceleague.adobe.com/es/docs/experience-platform/identity/features/namespaces)). Valores comunes: `ECID`, `Email`, `CRMId`. |
| `identityId` | Sí | Valor de identidad del usuario actual. |
| `attributes` | No | `Record<string, string[]>`. Clave es el nombre de atributo de contexto utilizado por las reglas de marcador (por ejemplo `locale`, `platform`). Valor es la lista de valores de atributos candidatos para esa clave. |

En Componentes de etiquetas, establezca los valores predeterminados de identidad en la condición o la IU del elemento de datos. El elemento de datos Feature Flag también acepta atributos de tiempo de ejecución a través de `getVar(name, attributes)` cuando el segundo argumento es un mapa de atributos plano.

### Uso {#usage}

```javascript
const context = {
  identityNamespace: 'ECID',
  identityId: 'your-visitor-ecid',
  attributes: {
    locale: ['en-US'],
    platform: ['web']
  }
};
```

## Referencia de API {#api-reference}

### Evaluación de funciones {#is-feature-enabled}

`isFeatureEnabled` devuelve si la característica Marcas está activada o desactivada en el contexto determinado. Pase `featureKey` y `FeatureEvaluationContext`. Consulte [Contexto de evaluación](#evaluation-context). Use la condición de etiquetas **La característica está habilitada** o llame a `window._flagClient.isFeatureEnabled(...)` desde el código personalizado después de la inicialización.

**Firma**

```javascript
isFeatureEnabled(featureKey: string, context: FeatureEvaluationContext): boolean
```

**Parámetros**

| Parámetro | Tipo | Descripción |
|---|---|---|
| `featureKey` | string | Clave de función a evaluar en Indicadores |
| `context` | FeatureEvaluationContext | Identidad (obligatorio) y atributos de segmentación opcionales. Consulte [Contexto de evaluación](#evaluation-context). |

## Creación de un elemento de datos de indicador de funcionalidad {#create-data-element}

Utilice un elemento de datos cuando necesite un valor de indicador disponible como `%Data Element Name%` en reglas o código personalizado.

1. En su propiedad, acceda al menú **[!UICONTROL Elementos de datos]** y seleccione **[!UICONTROL Agregar elemento de datos]**.

   ![](../assets/extension-install-5.png)

1. En la pantalla **Crear elemento de datos**, configure los campos Etiquetas:

   * **[!UICONTROL Nombre]**: un nombre descriptivo (por ejemplo `checkout flag`)
   * **[!UICONTROL Extensión]**: Indicadores
   * **[!UICONTROL Tipo de elemento de datos]**: Marca de característica

1. Configurar los campos de extensión de **Flags**:

   * **[!UICONTROL Clave de característica]**: Clave de marca única (por ejemplo `checkout_flag`), obligatoria.
   * **[!UICONTROL Tipo de devolución]**: **Booleano (verdadero/falso)** — habilitado/deshabilitado o **Objeto de característica (detalles completos)** — carga útil completa que incluye `meta`, necesaria.

     | Tipo de devolución | Se resuelve en |
     |---|---|
     | Booleano (true/false) | `true` si está habilitado, `false` en caso contrario |
     | Objeto Feature (detalles completos) | Se evaluó la carga útil de la característica cuando el indicador está habilitado y el contexto coincide con su audiencia; `null` cuando el indicador está deshabilitado, no se encuentra o el contexto no coincide |

1. Seleccione **Guardar**.

### Uso del elemento de datos {#use-data-element}

En una regla, haga referencia a por nombre, por ejemplo `%Test Flag%`.

En el código personalizado, use `_satellite.getVar`. Con atributos en tiempo de ejecución, pase un mapa de atributos plano como segundo argumento para evaluar:

```javascript
var isEnabled = _satellite.getVar('Test Flag', {
  locale: ['en-US'],
  platform: ['web']
});
```

**Código personalizado**

```javascript
var isEnabled = _satellite.getVar('Test Flag', {
  locale: ['en-US'],
  platform: ['web']
});
if (isEnabled) {
  // your custom code
} else {
  // your default code
}
```

### getFeature {#get-feature}

`getFeature` devuelve la carga útil de la característica evaluada cuando se necesitan metadatos por encima de habilitado/deshabilitado.

Use un elemento de datos **Feature Flag** con **Tipo de devolución: Feature Object (detalles completos)**, vea [Crear un elemento de datos Feature Flag](#create-data-element) o llame a `window._flagClient.getFeature(...)` desde el código personalizado después de que `flagClientReady` se resuelva.

**Firma**

```javascript
getFeature(featureKey: string, context: FeatureEvaluationContext): FeatureResult | null
```

**Parámetros**

| Parámetro | Tipo | Descripción |
|---|---|---|
| `featureKey` | string | Clave de función a evaluar en Indicadores |
| `context` | FeatureEvaluationContext | Atributos de identidad (obligatorios) y segmentación. Consulte [Contexto de evaluación](#evaluation-context). |

**Respuesta**

`getFeature` evalúa un indicador solamente cuando está habilitado y el contexto proporcionado coincide con los criterios de audiencia del indicador. En ese caso, devuelve un objeto result; de lo contrario, devuelve `null`.

*FeatureResult*

| Campo | Tipo | Descripción |
|---|---|---|
| `id` | entero | Identificador de función numérica. `-1` para centinela de control a nivel de funcionalidad. |
| `key` | `string \| null` | Tecla de función. `null` para centinela de control a nivel de funcionalidad. |
| `featureGroupKey` | `string \| null` | Tecla de grupo de funciones cuando esté disponible |
| `meta` | `string \| null` | Metadatos de funciones cuando están disponibles |
| `analyticsParam` | `AnalyticsParam \| null` | Detalles de Analytics para la función evaluada |

*Parámetro de análisis*

| Campo | Tipo | Descripción |
|---|---|---|
| `featureGroupId` | entero | Identificador del grupo de funciones numéricas |
| `featureId` | entero | Identificador de función numérica |
| `variantId` | `number \| null` | Identificador de variante (`0` si el usuario está en el grupo de control) |

**Comportamiento del grupo de control**

| Escenario | isFeatureEnabled | getFeature | El evento de Analytics está habilitado para funciones | Evento de Analytics getFeature |
|---|---|---|---|---|
| Tratamiento | `true` | Resultado normal | Sí | Sí |
| Control de nivel de funcionalidad | `false` | Centinela (`id: -1`, `key: null`) | Sí (`variantId: 0`) | Sí |
| No coinciden los criterios / no se encuentran | `false` | `null` | No | No |

**Ejemplos**

*Elemento de datos Etiquetas*

Haga referencia al elemento de datos (por ejemplo `%Test Feature%`) en una regla y búsquelo a través de `_satellite.getVar`.

*Código personalizado*

```javascript
var feature = _flagClient.getFeature('new-test-flag', {
  identityNamespace: 'ECID',
  identityId: visitorEcid,
  attributes: {
    locale: ['en-US']
  }
});

var meta = feature && feature.meta;
if (meta) {
  // your custom code
} else {
  // your default code
}
```

### extensionVersion {#extension-version}

Devuelve la cadena de versión de la extensión Flags.

**Firma**

```javascript
_flagClient.extensionVersion(): string
```

**Ejemplo**

```javascript
const version = _flagClient.extensionVersion();
console.log(`Flags extension version: ${version}`);
```

## Resumen de API {#api-summary}

| de visitante | Devuelve |
|---|---|
| Marca de característica (elemento de datos Etiquetas, booleano) | Booleano |
| Marca de característica (elemento de datos Etiquetas, objeto) | Objeto de característica para `null` |
| `window.flagClientReady` | Promise: esperar a la inicialización de la extensión |
| `window._flagClient.isFeatureEnabled(featureKey, context)` | Booleano |
| `window._flagClient.getFeature(featureKey, context)` | Objeto de característica para `null` |
| `window._flagClient.extensionVersion()` | Cadena de versión de extensión |

## Control de errores {#error-handling}

La extensión gestiona los errores correctamente:

| Escenario | Comportamiento |
|---|---|
| Red no disponible en inicialización | SDK reintenta la recuperación inicial 3 veces con desactivación y falla la inicialización. `window.flagClientReady` y `_satellite.getVar(...)` rechazos con `Failed to initialize Flag`; `window._flagClient` permanece `undefined`. |
| Falta la identidad en el contexto | La evaluación genera un error; proporcione `identityNamespace` y `identityId` |
| Función no encontrada | `getFeature` devuelve `null`; `isFeatureEnabled` devuelve `false` |

**Ejemplo**

```javascript
try {
  const isEnabled = _flagClient.isFeatureEnabled('my-feature', context);
  // Use the result
} catch (error) {
  console.error('Evaluation failed:', error.message);
  // Use default value
}
```

## Prácticas recomendadas {#best-practices}

### Proporcionar identidad coherente {#consistent-identity}

Utilice el mismo área de nombres de identidad e ID en todas las evaluaciones para un agrupamiento coherente en los despliegues porcentuales.

**Ejemplo**

```javascript
const context = {
  identityNamespace: 'ECID',
  identityId: identity,
  attributes: {
    locale: ['en-US'],
    platform: ['web']
  }
};

const isEnabled = _flagClient.isFeatureEnabled('my-feature', context);
```

### Gestión correcta de las funciones que faltan {#handle-missing}

Proporcione siempre un comportamiento de reserva cuando no se encuentre una función o cuando falle la evaluación.

```javascript
const feature = _flagClient.getFeature('new-test-flag', context);

if (feature && feature.meta) {
  // your custom code
} else {
  // Feature not enabled - use default code
}
```

### Evaluar después de cargar la página {#evaluate-after-load}

Asegúrese de que la biblioteca de etiquetas y la extensión de marcas se hayan inicializado antes de llamar a las API. Use el evento **Library Loaded** en las reglas, un elemento de datos **Feature Flag** o espere a `flagClientReady`:

```javascript
window.flagClientReady.then(function () {
  var isEnabled = window._flagClient.isFeatureEnabled('my-feature', context);
  // Use the result
});
```

## Consulte también {#see-also}

* [Creación de la primera marca de funcionalidad](../../feature-flags/create-your-first-feature-flag.md)
* [Audiencia en indicadores y grupos de características](../../audience/audience-in-feature-flags-and-feature-groups.md)
* [Informes](../../feature-flags/reporting.md)

