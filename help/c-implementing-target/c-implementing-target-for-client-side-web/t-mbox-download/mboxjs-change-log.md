---
keywords: cambios de mbox.js;versiones de mbox.js
description: Obtenga información sobre la implementación de mbox.js heredada de Adobe Target. Migrar al SDK web de Adobe Experience Platform (SDK web de AEP) o a la versión más reciente de at.js.
title: ¿Qué se incluye en cada versión de mbox.js?
feature: 'at.js '
role: Developer
exl-id: 4e95de13-2848-497a-9d06-41e9cbd98b42
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '2410'
ht-degree: 81%

---

# Detalles de la versión de mbox.js

Esta página muestra cambios realizados a cada versión de mbox.js.

>[!IMPORTANT]
>
>**Fin de vida útil de mbox.js**: Desde el 31 de marzo de 2021,  [!DNL Adobe Target] no es compatible con la biblioteca mbox.js . Después del 31 de marzo de 2021, todas las llamadas realizadas desde mbox.js producirán errores y afectarán a las páginas que tengan actividades [!DNL Target] ejecutándose al servir contenido predeterminado.
>
>Migrar a la versión más reciente de la nueva [!DNL Adobe Experience Platform Web SDK] o la biblioteca JavaScript at.js antes de esta fecha para evitar problemas potenciales con sus sitios. Para obtener más información, consulte [Información general: implementar Target para la web del lado del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

>[!NOTE]
>
>Adobe recomienda que todos los usuarios de mbox.js actualicen a la versión 57 o posterior. Algunos usuarios han experimentado problemas de tiempo de espera al no cargar `target.js`. La versión 57 ha corregido ese problema. Sin embargo, si utiliza el servicio [!DNL Experience Cloud Visitor ID], se requiere la versión 58 o posterior.

La forma en la que Target responde a las llamadas provenientes de su página depende de la versión de la biblioteca de Target que esté usando, si está presente la implementación de ID de visitante y si existe el ID de visitante. Para obtener información, consulte   [Respuestas de llamadas de Target por versión de biblioteca](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/call-responses-library-version.md#concept_A95A4758A1E7405D947E9B4BCB5D62F0).

>[!NOTE]
>
>La biblioteca mbox.js ya no está en desarrollo. Todos los clientes deberían migrar de mbox.js a at.js. Para obtener más información, consulte [Migrar a at.js desde mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

## Versión 63 de mbox.js {#section_ED8EFCF653A845ED8927F759578C4A33}

**Versión de Target:** 17.7.1

Ya está disponible la versión 63 de [!DNL mbox.js]. Para obtener más información, consulte [Descargar mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/target-download-config-mbox.md).

En la versión 63 de [!DNL mbox.js] se incluyen las siguientes mejoras y correcciones:

* Corrige un problema con la generación de SDID al utilizar `mboxDefine()` y `mboxUpdate()`. Este problema solo afecta a los clientes que tienen la API de visitante en la página.

## Versión 62 de mbox.js {#section_723A9119FE204183847D3B0929A99B41}

* Se han solucionado los problemas de parpadeo en actividades redirigidas al visualizarlas en navegadores de Google Chrome.
* Se ha añadido la opción de configuración `secureOnly` que indica si mbox.js debería utilizar solo HTTPS o se le debería permitir alternar entre HTTP y HTTPS según el protocolo de la página. Este ajuste es un ajuste avanzado que se establece en False de manera predeterminada.

## Versión 61 de mbox.js {#section_F3B59C5578B64883AE013B9342151193}

**Versión de Target:** 16.7.2

**Fecha de publicación:** 28 de julio de 2016

La versión 61 de mbox.js presenta las siguientes mejoras:

* El algoritmo de generación de ID de mboxSession que existe en la API de fecha de JavaScript genera una cadena aleatoria en lugar de usar una marca de tiempo más una cadena aleatoria.
* La información siguiente solo se refiere a cuando se tiene la API de visitante en la página:

   * La versión 61 de [!DNL mbox.js] no anula la propiedad `loadTimeout` de la API de visitante. Los clientes pueden usar `visitorApiTimeout` + `visitorApiPageDisplayTimeout` para controlar la integración de la API de visitante.
   * Se ha añadido la configuración `optoutEnabled` para respaldar la futura función de exclusión de Adobe Experience Cloud. El valor predeterminado es false. Si esta propiedad está habilitada, todas las solicitudes se ejecutan de manera asíncrona en el extremo [!DNL /ajax], como en la versión 60.
   * La ocultación del cuerpo está deshabilitada de forma predeterminada. Target usa la ocultación del cuerpo solo cuando la opción de creación automática de mbox global está habilitada.
   * Si no hay cookies de ID de visitante de Experience Cloud, todas las solicitudes se ejecutan asíncronamente en [!DNL /ajax] la primera vez que se carga la página. En la segunda carga de página, Target sigue el flujo normal porque los valores de ID de visitante ya están presentes.
   * Si usa Adobe Analytics como fuente de informes de la actividad, no es necesario que especifique un servidor de seguimiento durante la creación de la actividad en las versiones 61 (o posterior) de mbox.js y 0.9.1 (o posterior) de at.js. La biblioteca mbox.js o at.js envía automáticamente los valores del servidor de seguimiento a [!DNL Target]. Durante la creación de la actividad, puede dejar vacío el campo [!UICONTROL Servidor de seguimiento] de la página [!UICONTROL Objetivos y configuración].

## Versión 60 de mbox.js {#section_3BDAB885FA13444A8D35940A4BFF5825}

**Versión de Target:** 16.4.1

**Fecha de publicación:** 21 de abril de 2016

De forma predeterminada, el contenido de la página no se oculta. La versión 60 oculta contenido de la página solo cuando la opción “Crear automáticamente mbox global” está activada. Esta utiliza la propiedad CSS `opacity:0` para ocultar la página, en lugar de `display:none`. Esta propiedad garantiza un envío adecuado para los sitios adaptables y se ajusta a [!DNL at.js].

Puede habilitar la ocultación del cuerpo con dos configuraciones:

* `bodyHidingEnabled` El valor predeterminado es false, lo cual significa que el BODY de HTML no se oculta.

* bodyHiddenStyle

   El valor predeterminado es `body{opacity:0}`. Este valor se puede cambiar por otro, por ejemplo, `body{display:none}`.

Estas configuraciones se pueden anular incluyendo algo así:

```
<script> 
window.targetGlobalSettings = { 
 bodyHidingEnabled: true, 
 bodyHiddenStyle: "body{opacity:0}", 
 visitorApiPageDisplayTimeout: 2000 
}; 
</script>
```

La técnica de ocultación de página utiliza etiquetas de estilo para agregar y eliminar estilos. Esta técnica garantiza que los estilos del sitio permanezcan sin cambios después de ejecutar el código de ocultación de página.

**Usuarios de DTM:** esta técnica evita que utilice la opción de importación automática, ya que no hay forma de guardar la configuración anterior en la interfaz de usuario de Target. Debe utilizar las instrucciones anteriores y luego pegar el contenido en el cuadro de código de la opción de alojamiento personalizado.

Además, en la versión 60, si el archivo [!DNL visitorAPI.js] está presente para el servicio de ID de visitante de Experience Cloud, todos los mboxes se solicitan mediante un extremo de AJAX. Este proceso es necesario porque los métodos de API de visitante son asincrónicos. Una de las ventajas de este enfoque es que el tiempo de inicio de procesamiento disminuye drásticamente, puesto que las peticiones de mbox no bloquean el procesamiento. Sin embargo, este enfoque también significa que todo contenido de oferta [!DNL Target] se ejecuta asincrónicamente, por lo que todo el código de oferta debe escribirse de manera acorde. Las ofertas que contienen `document.write` y otro código que supone que se ejecuta al cargar la página por primera vez no se ejecutan según lo esperado.

* Llamadas asincrónicas de la versión 60

   Al usar la versión 60 con el servicio de ID de visitante, todas las llamadas de mbox se hacen asincrónicamente. Esto supone un cambio en el funcionamiento habitual de los mboxes. Tenga cuidado si actualiza a esta versión. Consulte la sección [Consideraciones asincrónicas](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-limitations.md#section_B586360A3DD34E2995AE25A18E3FB953) de la documentación de [!DNL at.js] ([!DNL at.js] también emplea llamadas asincrónicas) para informarse sobre algunos de los riesgos.
* Los casos de visitantes nuevos podrían presentar parpadeo

   Cuando se usan las versiones 58 a 60 con el servicio de id de visitante, las llamadas de mbox esperan a que se establezca el id de visitante antes de activarse (o hasta que se agote el tiempo de espera). Esto sucede en la primera carga de página de un visitante nuevo.

## Versión 59 de mbox.js {#section_FF0E70C4C17E402D8374DE428C5D996E}

**Versión de Target:** 16.2.1

**Fecha de publicación:** 17 de febrero de 2016

La versión 59 de mbox presenta las siguientes mejoras:

* El tiempo de desactivación de mbox se ha reducido a 30 minutos.
* Se ha corregido un problema relacionado con la ocultación/revelación de una página.

   En lugar de usar `display:none` para ocultar la página, como en la versión 58, se utiliza el código `opacity:0`. De esta forma, se solucionan los problemas relacionados con los sitios interactivos provocados por el anterior método de ocultación de la página.

## mbox.js versión 58    {#section_5070B0D1C87F4937BB97727923DD36C7}

**Versión de Target:** 15.7.1

**Fecha de publicación:** 30 de julio de 2015

Esta versión de mbox.js es obligatoria si usa Analytics como la fuente de informes para Target y se recomienda encarecidamente para Perfiles y audiencias.

La versión 58 de mbox.js garantiza que el ID de visitante de Experience Cloud vuelva con un ID de visitante antes de que se realicen llamadas de Target. Así los datos de audiencia que se comparten a través del servicio principal de Perfiles y Audiencias están disponibles para la primera llamada de Target en la sesión del visitante. Para evitar que el contenido predeterminado parpadee antes de que se devuelva el contenido de la prueba, Target oculta `<BODY>` hasta que se devuelve el servicio de ID de visitante. Se utiliza el código `display:none` para ocultar la página.

Esta actualización también corrige un problema cuando se usa Analytics como fuente de informes para Target que hacía que se informara de un número elevado de visitantes en Analytics para visitas que solo incluían una página.

Mbox.js establece valores de tiempo de espera si el servicio de ID de visitante no devuelve valores. El tiempo de espera predeterminado del servicio de ID de visitante es de 500 ms (0,5 segundos). Un tiempo de espera adicional establece el límite superior para mantener oculta la etiqueta `<BODY>`. El valor predeterminado es de 500 ms (0,5 segundos). Estos tiempos de espera se pueden cambiar. Solo tiene que insertar el código siguiente antes de la referencia a mbox.js en cada página:

```
<script> 
window.targetGlobalSettings = { 
 visitorApiTimeout: 500, 
 visitorApiPageDisplayTimeout: 500 
}; 
</script> 
```

Las versiones 58 y posteriores de mbox.js ejecutan contenido que no es de JavaScript para el mbox global inmediatamente después de la etiqueta `BODY` de HTML. El contenido de JavaScript que está dentro de las etiquetas `<script>` para el mbox global se ejecuta una vez activado el evento `DOMContentLoaded`. Este orden en la entrega de contenido garantiza que el contenido de JavaScript para el mbox global se entregue y represente adecuadamente.

## Versión 57 de mbox.js {#section_6BA1CDBF75B14A94B59E8624ACF583D4}

**Versión de Target:** 15.4.1

**Fecha de publicación:** 21 de abril de 2015

Se han realizado los siguientes cambios en esta versión:

* La respuesta de mbox global creada automáticamente para Target Standard ya no usa document.write() ni crea un `<div>` element.

   Este cambio elimina el requisito de que el archivo mbox.js sea el último elemento en la `<head>` página. Se recomienda un exhaustivo control de calidad al actualizar a esta nueva versión.

   Este cambio podría modificar el comportamiento a la hora de entregar algunos tipos de ofertas. Estas son las condiciones específicas que deben tenerse en cuenta:

   * El contenido HTML devuelvo como parte de una “oferta de complemento” no se representa correctamente, pero JavaScript dentro de las ofertas se ejecuta tal como se espera.
   * Las ofertas JavaScript que se devuelven al mbox global pueden tener el código JavaScript incorporado en la etiqueta `<script>` o pueden tener una referencia de un atributo `src`.

      Para ello, añada el atributo `async` en la llamada al script de la siguiente manera:

      `<script src='external-url' async='true'></script>`

      El atributo `async` tiene compatibilidad limitada en Internet Explorer (detalles en: [https://developer.mozilla.org/en/docs/Web/HTML/Element/script#Browser_compatibility](https://developer.mozilla.org/en/docs/Web/HTML/Element/script#Browser_compatibility)), de modo que debería excluir de las pruebas que incluyen scripts de terceros a los visitantes que usan versiones más antiguas de IE.

* Se han corregido problemas informados en la Versión 56 debido a cambios en la sección Extra JavaScript de mbox.js. Todo código en la sección Extra JavaScript está disponible nuevamente en el alcance global.

La siguiente funcionalidad no está admitida en mbox.js versión 57:

* Un mbox global creado automáticamente en Target Standard no funciona con tipos de ofertas alojados desde Target Classic. Los tipos de ofertas alojados incluyen “oferta en su sitio” y “oferta fuera de Test&amp;Target”.

   Esto significa que en Target Classic, no debe seleccionar el mbox global creado automáticamente desde Target Standard cuando se requiere una de estas ofertas.
* Solo se admiten los complementos de JavaScript.

   Si la oferta de un complemento combina código JavaScript, y HTML, el código JavaScript se ejecuta pero no se muestra el contenido HTML.

Mbox.js versión 57 también incluye correcciones importantes:

* Se ha corregido un problema que impedía que el complemento de SiteCatalyst funcione en mbox.js v56.
* Se ha corregido un problema que provocaba errores JavaScript extra debido a cambio de alcance.
* Se han revertido cambios al constructor de mboxFactory.

## Versión 56 de mbox.js {#section_C4F4A53584B741FF9FD907D81CB7E164}

**Versión de Target:** 15.1.2

**Fecha de publicación:** 17 de febrero de 2015

>[!NOTE]
>
>Algunos usuarios han experimentado problemas de tiempo de espera al no cargar `target.js`. La versión 57 ha corregido ese problema. Sin embargo, si utiliza el servicio [!DNL Experience Cloud Visitor ID], se requiere la versión 58 o posterior.

Se han realizado los siguientes cambios en esta versión:

* Cambios para Recommendations Premium para admitir el traspaso de parámetros a mbox global.
* Agrega un tiempo de espera de 5 segundos a la llamada de carga de target.js. En el improbable caso de que el archivo no se cargue, la página se procesa y no se muestra ninguna actividad de Target Standard.
* Se ha movido “JavaScript extra” para ejecutarlo antes del mbox global.

   Todos los ajustes en V56+ tienen espacio de nombres. Si hay funciones declaradas en la sección “JavaScript extra”, debe añadirse el prefijo `window` a cada una de ellas.

   Por ejemplo:

   `function foo {`

   `}`

   Se convierte en:

   `window.foo = function() {`

   `}`

   El prefijo `window` debe añadirse también a cualquier variable a la que se deba acceder globalmente.

* Se ha añadido una cookie llamada “em-disabled” que mbox.js proporciona al usuario si target.js no se puede cargar durante la entrega. Esta cookie impide que las ofertas creadas con el Compositor de experiencias visuales se procesen en el sitio. Los usuarios con esta cookie no ven el contenido de prueba ni se cuentan en esos informes de actividades. Todo el demás contenido de ofertas (de campañas en Target Classic, por ejemplo) sigue cargándose. La cookie tiene una vida útil de 30 minutos desde el momento del error en la carga.

## Versión 55 de mbox

**Versión de Target:** 15.1

**Fecha de versión:** 19 de enero de 2015

Se modifica la versión 53 con correcciones de IE.

## Versión 54 de mbox

**Versión de Target:** 14.9.2

**Fecha de versión:** 30 de septiembre de 2014

Se cambia la implementación del mbox global a AJAX desde document.write. Este cambio elimina el requisito de que el archivo mbox.js sea el último elemento de la sección `<head>` de la página. Esta versión solo está disponible a través de la API. Los clientes pueden descargar y utilizar este archivo mbox.js. Con esta implementación, en algunos sitios se produce un desplazamiento del contenido, así que le recomendamos que valide la integración en su sitio.

## Versión 53 de mbox

**Versión de Target:** 14.9.1

**Fecha de versión:** 14 de septiembre de 2014

Se corrigió un problema en los parámetros de página de Target no se activan correctamente en Internet Explorer.

## Versión 52 de mbox

**Versión de Target:** 14.8

**Fecha de versión:** 14 de agosto de 2014

La función mboxParameter ahora funciona en Target Standard y Premium.

Se corrigió un problema que impedía que Analytics funcione en IE 9 y 11. Este cambio afecta solamente a usuarios de Analytics.

Ahora puede [pasar parámetros](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md) como una matriz, como un objeto JSON o como una lista delimitada por comas (previamente compatible) a target-global-mbox mediante la función targetPageParams().

Se ha cambiado el nombre de M2PcId y todo lo relacionado con VisitorId.

Permite que se borre el defaultDiv de un mbox registrado.

## Versión 51 de mbox

**Versión de Target:** 14.6

**Fecha de la versión:** 25 de junio de 2014

Se ha corregido un problema que establecía una cookie incorrecta en los sitios con dos caracteres en el dominio de nivel superior.

Se ha corregido un problema leve en mbox.js que provocaba la devolución de los valores de hashtag.

## Versión 50 de mbox

Se ha mejorado la sincronización entre Target Standard y Target Classic.

## Versión 49 de mbox

Se ha mejorado la compatibilidad con Internet Explorer 10 para los mbox anidados.

## Versión 48 de mbox

Se ha añadido compatibilidad con Adobe Analytics como fuente de informes para Target.

## Versión 47 de mbox

mbox.js ahora puede usarse con un nombre de mbox global para Target Standard.

## Versión 46 de mbox

Se ha añadido compatibilidad total con el servicio de ID de visitante de Experience Cloud para implementación de una sola línea de código de Target Standard. Esto habilita la integración de Adobe Analytics del lado del servidor y el perfil compartido de Experience Cloud.

Se ha corregido un problema con la entrega de contenido en IE10 en modo de documento.

## Versión 45 de mbox

Se ha añadido la compatibilidad con el servicio de ID de visitante de Experience Cloud. Esto habilita la integración de Adobe Analytics del lado del servidor y el perfil compartido de Experience Cloud.

## Versión 44 de mbox

Se ha añadido un nuevo parámetro en la dirección URL mediante mboxVizTarget:

mboxDOMLoaded

## Versión 43 de mbox

Se ha añadido la compatibilidad con Target Standard.

## Versión 42 de mbox

Se ha añadido compatibilidad con el servicio de ID de visitante de Experience Cloud.

## Versión 41 de mbox

* Incluso con la configuración x-solamente, deshabilitar las cookies de origen para mejorar el tiempo de carga y evitar actualizaciones constantes de la página

   Se define una cookie de tiempo de espera si la llamada a Target no vuelve a tiempo. Este método es más rápido que si se usa solo la cookie de terceros. Si solo se usa una cookie de terceros, la página se actualiza continuamente mientras se espera una respuesta adecuada de los servidores de Target.

* Se ha corregido la limitación de tráfico que se da únicamente cuando se activa mbox.js

   Este problema se producía si un cliente tenía una limitación de tráfico en su mbox.js, lo que provocaba que el ajuste de tiempo de espera no funcionara. Como resultado, la página se actualizaba mientras esperaba una buena respuesta de los servidores de Target.

* Se ha corregido el complemento de SiteCatalyst para que siempre utilice el mensajero de Ajax.

   Antes de este cambio, los usuarios del complemento Test&amp;Target para SiteCatalyst podían experimentar situaciones en las que se activaba un document.write que borraba la página, en función de cuándo se cargaba el complemento.

## Versión 38 de mbox

Se ha añadido la compatibilidad para la integración de SiteCatalyst con Test&amp;Target basada en páginas (debe activarse).

## Versión 37 de mbox

Se han codificado las claves de la dirección URL

## Versión 36 de mbox

Se ha cambiado mbox para que utilice tt.omtrdc.net

## Versión 35 de mbox

* La depuración de mbox ahora siempre es remota
* Se ha añadido el parámetro mboxTime. Este parámetro es la hora tal y como la ve el usuario, en ms a partir de la época, GMT. Esto solo se calcula una vez.

## Versión 34 de mbox

* Intente obtener siempre la última versión de div predeterminada en lugar de hacer referencia a una versión en caché.

   Esto soluciona un problema con el contenido predeterminado en caché en el que div no está en DOM debido a un mboxUpdate, el cual ha proporcionado el contenido para el div predeterminado.

* mbox.getDefaultDiv cuenta con un parámetro booleano nuevo. Si es true, devuelve el div predeterminado actual. Si es false, devuelve el div almacenado en caché por última vez.
* Se ha actualizado mbox.loaded para admitir la carga de Ajax
* El parámetro mboxURL ahora está codificado mediante encodeURIComponent en lugar de escape
* Pruebe si encodeURIComponent es compatible con el navegador y muestre el contenido predeterminado en caso contrario. También se han eliminado las opciones de configuración de mbox.js siguientes:
   * encode\_mbox\_parameters
   * mbox\_signal\_support
