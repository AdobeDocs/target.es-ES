---
keywords: preguntas frecuentes;faq sobre at.js;preguntas frecuentes sobre at.js;parpadeo;cargador;cargador de páginas;dominios cruzados;dominio cruzado;tamaño de archivo;dominio x;at.js y mbox.js;solo x;safari;una sola página;aplicación de una sola página;spa;selectores desaparecidos;selectores;tt.omtrdc.net;Adobe Experience Manager;AEM;dirección ip;solo http;solo Http;ip;segura;dominio de cookie
description: Respuestas a las preguntas frecuentes acerca de la biblioteca de JavaScript de Adobe  [!DNL Target]  at.js.
title: ¿Cuáles son las preguntas y respuestas comunes acerca de at.js?
feature: at.js
role: Developer
exl-id: 937f880a-1842-4655-be44-0a5614c2dbcc
source-git-commit: f4b490c489427130e78d84b573b2d290a8a60585
workflow-type: ht
source-wordcount: '2521'
ht-degree: 100%

---

# Preguntas más frecuentes de at.js

Respuestas a las preguntas frecuentes acerca de la biblioteca JavaScript de [!DNL Adobe Target] at.js.

## ¿Cuáles son las ventajas de usar at.js en lugar de mbox.js? {#section_FE30D01A577C46ACB0F787B85F5E0F6B}

La biblioteca [!DNL at.js] reemplaza a [!DNL mbox.js]. La biblioteca [!DNL mbox.js] ya no es compatible. Sin embargo, para la mayoría de las personas, [!DNL at.js] proporciona ventajas con respecto a [!DNL mbox.js].

Entre otros beneficios, [!DNL at.js] mejora los tiempos de carga de página en implementaciones web, mejora la seguridad y proporciona mejores opciones de implementación en aplicaciones de una sola página.

El diagrama siguiente compara el rendimiento de carga de página de mbox.js y at.js.

![](assets/atjs_vesus_mboxjs.png)

Como se observa en la ilustración, al usar mbox.js, el contenido de la página no empieza a cargarse hasta que no se completa la llamada a [!DNL Target]. Con at.js, el contenido de la página empieza a cargarse cuando se inicia la llamada a [!DNL Target] y no espera hasta que ha finalizado.

## ¿Cuál es el impacto de at.js y mbox.js en el tiempo de carga de página?  {#page-load}

Muchos clientes y consultores quieren conocer el impacto de [!DNL at.js] y [!DNL mbox.js] en el tiempo de carga de página, especialmente en el contexto de los nuevos usuarios frente a los que regresan. Lamentablemente, es difícil medir y ofrecer números concretos sobre la influencia de [!DNL at.js] o [!DNL mbox.js] en el tiempo de carga, ya que cada cliente dispone de una implementación diferente.

No obstante, si la API de visitante está presente en la página, [!DNL Target] puede comprender mejor cómo influyen [!DNL at.js] y [!DNL mbox.js] en este tiempo de carga.

>[!NOTE]
>
>La API de visitante y [!DNL at.js] o [!DNL mbox.js] solo afectan al tiempo de carga de página cuando utiliza el mbox global (debido a la técnica de ocultación del cuerpo). Los mboxes regionales no se ven afectados por la integración del API de visitante.

La siguiente tabla describe la secuencia de acciones para los visitantes nuevos y los habituales:

### Visitantes nuevos

1. El API de visitante se carga, se analiza y se ejecuta.
1. at.js/mbox.js se carga, se analiza y se ejecuta.
1. Si la creación automática de mbox global está habilitada, la biblioteca JavaScript de Target:

   * Crea una instancia del objeto Visitante.
   * La biblioteca de [!DNL Target] intenta recuperar los datos de [!DNL Experience Cloud Visitor ID].
   * Como se trata de un nuevo visitante, la API de visitante activa una solicitud entre dominios dirigida a demdex.net.
   * Una vez recuperados los datos de [!DNL Experience Cloud Visitor ID], se activa una solicitud a [!DNL Target].

### Visitantes que regresan

1. El API de visitante se carga, se analiza y se ejecuta.
1. at.js/mbox.js se carga, se analiza y se ejecuta.
1. Si la creación automática de mbox global está habilitada, la biblioteca JavaScript de [!DNL Target]:

   * Crea una instancia del objeto Visitante.
   * La biblioteca de [!DNL Target] intenta recuperar los datos de [!DNL Experience Cloud Visitor ID].
   * La API de visitante recupera datos de las cookies.
   * Una vez recuperados los datos de [!DNL Experience Cloud Visitor ID], se activa una solicitud a [!DNL Target].

>[!NOTE]
>
>Para los nuevos visitantes, cuando la API de visitante está presente, [!DNL Target] debe actuar varias veces para garantizar que las solicitudes de [!DNL Target] contengan datos de ID de visitante de [!DNL Experience Cloud Visitor ID]. Para los visitantes habituales, [!DNL Target] actúa únicamente para que [!DNL Target] recupere el contenido personalizado.

## ¿Por qué parece que se obtienen tiempos de respuesta más lentos después de actualizar desde una versión anterior de at.js a la versión 1.0.0? {#section_DFBA5854FFD142B49AD87BFAA09896B0}

[!DNL at.js] 1.0.0 y las versiones posteriores activan todas las solicitudes en paralelo. Las versiones anteriores ejecutan las solicitudes de forma secuencial, lo que significa que se ponen en cola y que [!DNL Target] espera a que la primera se complete antes de pasar a la siguiente.

El modo en que versiones anteriores de [!DNL at.js] ejecutan las solicitudes es susceptible al llamado “bloqueo de cabeza de línea”. En [!DNL at.js] 1.0.0 y versiones posteriores, cambió a la ejecución de solicitudes en paralelo.[!DNL Target]

Por ejemplo, si se comprueba el esquema de etiquetas de red de [!DNL at.js] 0.9.1, se ve que no se comienza una solicitud de hasta que la anterior ha finalizado. [!DNL Target] Este no es el caso de [!DNL at.js] 1.0.0 y posterior, donde todas las solicitudes comienzan básicamente al mismo tiempo.

Desde la perspectiva del tiempo de respuesta, matemáticamente, esta secuencia se puede resumir así

<ul class="simplelist"> 
 <li> at.js 0.9.1: tiempo de respuesta de todas las solicitudes de [!DNL Target] = suma del tiempo de respuesta de cada solicitud </li> 
 <li> at.js 1.0.0 y posteriores: tiempo de respuesta de todas las solicitudes de [!DNL Target] = el mayor valor de todos los tiempos de respuesta </li> 
</ul>

La versión 1.0.0 de la biblioteca [!DNL at.js] completa las solicitudes más rápido. Además, las solicitudes de [!DNL at.js] son asíncronas, de modo que no bloquea la representación de páginas. [!DNL Target] Aunque las solicitudes tarden segundos en completarse, se verá la página procesada; no obstante, algunas partes pueden quedar en blanco hasta que [!DNL Target] obtenga una respuesta del perímetro de [!DNL Target].

## ¿Puedo cargar la biblioteca de [!DNL Target] de forma asíncrona? {#section_AB9A0CA30C5440C693413F1455841470}

La versión de at.js 1.0.0 permite cargar la biblioteca de [!DNL Target] de forma asíncrona.

Para cargar at.js de forma asíncrona:

* El método recomendado es mediante etiquetas en [!DNL Adobe Experience Platform].
* También puede cargar at.js de forma asíncrona añadiendo el atributo async a la etiqueta de script que carga at.js. Utilice algo similar a esto:

   ```
   <script src="<URL to at.js>" async></script>
   ```

* También puede cargar at.js de forma asíncrona utilizando este código:

   ```
   var script = document.createElement('script'); 
   script.async = true; 
   script.src = "<URL to at.js>"; 
   document.head.appendChild(script);
   ```

Cargar at.js de forma asíncrona es un modo excelente de evitar el bloqueo de presentación por parte del navegador; sin embargo, esta técnica puede producir parpadeos en la página web.

Puede evitar el parpadeo utilizando un fragmento de ocultamiento previo que oculta la página (o partes especificadas) y luego lo revela después de que at.js y la solicitud global se hayan cargado. El fragmento debe añadirse antes de cargar at.js.

Si va a implementar at.js a través de una implementación asíncrona de [!DNL Adobe Experience Platform], asegúrese de incluir el fragmento de ocultamiento previo directamente en las páginas, antes de implementar [!DNL Target] mediante código incrustado de [!DNL Adobe Experience Platform].

Si implementa at.js a través de una implementación sincrónica de DTM, el fragmento de ocultamiento previo se puede añadir a través de una regla de carga de página activada en la parte superior de la misma.

Para obtener más información, consulte [Cómo gestiona at.js el parpadeo](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md).

## ¿at.js es compatible con la integración de [!DNL Adobe Experience Manager] (Experience Manager)? {#section_6177AE10542344239753764C6165FDDC}

Ahora, [!DNL Adobe Experience Manager] 6.2 con FP-11577 (o posterior) es compatible con las implementaciones de [!DNL at.js] mediante su integración [!UICONTROL Servicios de nube de Adobe Target]. 

## ¿Cómo puedo evitar el parpadeo en la carga de la página al utilizar at.js? {#section_4D78AAAE73C24E578C974743A3C65919}

Target ofrece varias maneras de prevenir el parpadeo en la carga de la página. Para obtener más información, consulte [Prevención de parpadeo con at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md#concept_AA168574397D4474B993EEAB90865EBA).

## ¿Cuál es el tamaño de archivo de at.js? {#section_6A25C9A14C66441785A7635FEF5C4475}

El archivo at.js pesa aproximadamente 109 kB cuando se descarga. Sin embargo, como la mayoría de los servidores comprimen los archivos automáticamente para reducir el tamaño, el at.js pesa unos 34 kB cuando se comprime (mediante GZIP u otro método) en el servidor y se carga con las visitas de los usuarios a su sitio web. La configuración de compresión definida en el servidor donde instaló at.js determina su tamaño comprimido real.

## ¿Por qué at.js es más grande que mbox.js? {#section_AA1C43897E46448FA3E26EEC10ED7E51}

Las implementaciones de at.js utilizan una sola biblioteca ([!DNL at.js]), mientras que las de mbox.js utilizan dos bibliotecas ([!DNL mbox.js] y [!DNL target.js]). Así pues, una comparación más justa sería de at.js con mbox.js *y* `target.js`. Comparando los tamaños comprimidos en formato gzip de las dos versiones, la versión 1.2 de at.js ocupa 34 kB y la versión 63 de mbox.js, 26,2 kB. ``

at.js tiene un tamaño mayor porque realiza mucho más análisis de DOM en comparación con mbox.js. Esto es necesario porque at.js obtiene datos “sin procesar” en la respuesta de JSON y tiene que darle sentido. mbox.js utiliza `document.write()` y todo el análisis lo realiza el explorador.

A pesar del mayor tamaño de archivo, nuestra prueba determina que las páginas se cargan más rápido con at.js en comparación con mbox.js. Además, at.js es superior desde el punto de vista de la seguridad, porque no carga archivos adicionales de forma dinámica ni utiliza `document.write`.

## ¿at.js incluye jQuery? ¿Puedo eliminar esta parte de at.js porque ya cuento con jQuery en mi sitio web? {#section_E4604E46E7B34460B8DD6A78D9B476F9}

En estos momentos, at.js utiliza partes de jQuery y, por lo tanto, podrá ver la notificación de licencia de MIT en la parte superior de at.js. jQuery no se expone y no interfiere con la biblioteca jQuery que ya tenga en su página, cuya versión es posible que difiera. No admite la eliminación del código jQuery en at.js.

## ¿at.js permite definir Safari y el dominio cruzado en x-solamente? {#section_114EC271A6E045E1B2183B66F1B71285}

No, si el dominio cruzado se define en x-solamente y Safari tiene deshabilitadas las cookies de terceros, tanto [!DNL mbox.js] como at.js definirán una cookie deshabilitada y no se ejecutará ninguna solicitud de mbox para el dominio de este cliente.

Para permitir el acceso desde Safari, habría que “deshabilitar” (solo establece una cookie de origen) o “habilitar” (solo establece una cookie de origen en Safari, pero establece cookies de origen y de terceros en otros navegadores) un mejor dominio x.

## ¿Puedo usar el Compositor de experiencias visuales (VEC) de [!DNL Target] en mis aplicaciones de una sola página? {#section_459C1BEABD4B4A1AADA6CF4EC7A70DFB}

Sí, puede utilizar el VEC para su SPA si usa at.js 2.x. Para obtener más información, consulte [Compositor de experiencias visuales de una sola página (SPA)](/help/c-experiences/spa-visual-experience-composer.md).

## ¿Puedo usar el Debugger de [!DNL Adobe Experience Cloud] con implementaciones de at.js? {#section_FF3CF4C5FD2F4DB1BF1A6B39DA161637}

Sí. También puede utilizar mboxTrace con fines de depuración, o puede usar las herramientas de desarrollo de su navegador para inspeccionar las solicitudes de red y filtrar “mbox”, aislando así las llamadas a mbox.

## ¿Puedo utilizar caracteres especiales en nombres de mbox con at.js? {#section_8E31D2E8A27642098934D7DACFB2A600}

Sí, igual que con mbox.js.

## ¿Por qué no se activan los mboxes en mis páginas web? {#section_4BA5DA424B734324AAB51E4588FA50F5}

Los clientes de [!DNL Target] utilizan en ocasiones instancias basadas en la nube con [!DNL Target] para realizar pruebas o simplemente exponer conceptos. Estos dominios, y muchos otros, son parte de la [Lista pública de sufijos](https://publicsuffix.org/list/public_suffix_list.dat).

Los exploradores modernos no guardan las cookies si se utilizan estos dominios, a no ser que se personalice el ajuste `cookieDomain` mediante targetGlobalSettings(). Para obtener más información, consulte [Uso de instancias basadas en la nube con Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/targeting-using-cloud-based-instances.md).

## ¿Pueden usarse direcciones IP como el dominio de la cookie al utilizar at.js? {#section_8BEEC91A3410459D9E442840A3C88AF7}

Compruebe que está utilizando la [versión 1.2 o posterior de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A). Sin embargo, [!DNL Adobe] recomienda encarecidamente mantenerse actualizado con la versión más reciente.

>[!NOTE]
>
>Los siguientes ejemplos no son necesarios si utiliza la versión 1.2 o posterior de at.js.

Según la forma en que use [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md), es posible que tenga que realizar más modificaciones en el código tras descargar at.js. Por ejemplo, si necesita emplear unas configuraciones que difieran un poco para las implementaciones de [!DNL Target] en varios sitios web y no puede definirlas de forma dinámica mediante JavaScript personalizado, haga las personalizaciones manualmente después de descargar el archivo y antes de cargarlo en el sitio web correspondiente.

Los siguientes ejemplos le permiten utilizar la función `targetGlobalSettings()` de at.js para insertar un fragmento de código para admitir las direcciones IP:

Este ejemplo es para una dirección IP única:

```
if (window.location.hostname === '123.456.78.9') { 
    window.targetGlobalSettings = window.targetGlobalSettings || {}; 
    window.targetGlobalSettings.cookieDomain = window.location.hostname; 
}
```

Este ejemplo es para un intervalo de direcciones IP:

```
if (/^123\.456\.78\..*/g.test(window.location.hostname)) { 
    window.targetGlobalSettings = window.targetGlobalSettings || {}; 
    window.targetGlobalSettings.cookieDomain = window.location.hostname; 
}
```

## ¿Por qué veo mensajes de aviso como “acciones con selectores ausentes”?  {#section_C36BED5B16634361A1BA46FCB731489D}

Estos mensajes no están relacionados con la funcionalidad de [!DNL at.js]. La biblioteca [!DNL at.js] intenta informar de todo lo que no pueda encontrarse en el DOM.

Las siguientes son posibles causas para que aparezca este mensaje de advertencia:

* La página se está creando dinámicamente y at.js no puede encontrar el elemento.
* La página se está creando lentamente (debido a una red lenta) y at.js no puede encontrar el selector en el DOM.
* La estructura de la página en la que se ejecuta la activida[!UICONTROL d ha cambiado. Si vuelve a abrir la actividad en el ]Compositor de experiencias visuales (VEC), debería recibir un mensaje de advertencia. Actualice la actividad de modo que se encuentren todos los elementos necesarios.
* La página subyacente es parte de una [!UICONTROL aplicación de una sola página] (SPA) o la página contiene elementos que aparecen más adelante y el “mecanismo de sondeo selector” de [!DNL at.js] no puede encontrar dichos elementos. Aumentar el valor de `selectorsPollingTimeout` podría ser de ayuda. Para obtener más información, consulte [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).
* Cualquier métrica de seguimiento de clics intenta añadirse a todas las páginas, independientemente de la dirección URL en la que se estableciera dicha métrica. Aunque es algo inofensivo, esta situación provoca la aparición de muchos de estos mensajes.

   Para obtener los mejores resultados, descargue y utilice la versión más reciente de [!DNL at.js]. Para obtener más información, consulte [Detalles de versión de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) y [Descargar at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md).

## ¿Cuál es el dominio tt.omtrdc.net al cual se dirigen las llamadas del servidor de [!DNL Target]? {#section_999C29940E8B4CAD8A957A6B1D440317}

[!DNL tt.omtrdc.net] es el nombre de dominio de la red EDGE de Adobe, que se utiliza para recibir todas las llamadas de servidor para Target.

## ¿Por qué at.js no siempre utiliza los indicadores de cookies HttpOnly y Secure? {#section_74527E3B41B54B0A83F217C3E664ED1F}

HttpOnly solo se puede establecer mediante código del lado del servidor. [!DNL Target]Las cookies de, como mbox, se crean y guardan mediante código JavaScript, de modo que no puede utilizar el indicador de [!DNL Target] cookie HttpOnly. [!DNL Target] utiliza establecer HttpOnly para cookies de terceros establecidas del lado del servidor cuando el dominio cruzado está habilitado.

Secure se puede establecer mediante JavaScript solo cuando la página se carga mediante HTTPS. Si la página se carga inicialmente mediante HTTP, JavaScript no puede establecer este indicador. Además, si se utiliza el indicador Secure, la cookie estará disponible solo en páginas HTTPS. Para las páginas cargadas mediante HTTPS, [!DNL Target] establece los atributos Secure y SameSite=None.

Para asegurarse de que [!DNL Target] puede rastrear correctamente a los usuarios y porque las cookies se generan en el lado del cliente, [!DNL Target] no utiliza ninguno de estos indicadores excepto en las situaciones mencionadas anteriormente.

## ¿Con qué frecuencia inicia at.js una solicitud de red?  {#section_57C5235DF7694AF093A845D73EABADFD}

[!DNL Target] ejecuta todas sus decisiones en el servidor. Esto significa que at.js inicia una solicitud de red cada vez que la página se vuelve a cargar o se invoca una API pública at.js.

## En el mejor de los casos, ¿podemos esperar que el usuario no experimente ningún efecto visible en la carga de la página relacionada con ocultar, reemplazar y mostrar contenido? {#section_CB3C566AD61F417FAC0EC5AC706723EB}

at.js intenta evitar la ocultación previa de los elementos BODY de HTML u otros elementos DOM durante un periodo prolongado de tiempo, pero esto depende de las condiciones de la red y la configuración de la actividad. at.js proporciona [ajustes](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) que puede utilizar para personalizar el estilo del CSS oculto de BODY, de modo que, en lugar de borrar todo el BODY de HTML, puede ocultar solo algunas partes de la página. La expectativa es que esas partes contengan elementos DOM que deben ser “personalizados”.

## ¿Cuál es la secuencia de eventos en un escenario promedio donde un usuario califica para una actividad?  {#section_56E6F448E901403FB77DF02F44C44452}

La solicitud at.js es una solicitud `XMLHttpRequest` asincrónica, por lo que realizamos los pasos siguientes:

1. La página se carga.
1. at.js oculta previamente BODY de HTML. Hay una configuración para ocultar previamente un contenedor en particular en lugar de BODY de HTML.
1. at.js solicita activaciones.
1. Una vez recibida la respuesta de [!DNL Target], [!DNL Target] extrae los selectores de CSS.
1. Al utilizar selectores de CSS, [!DNL Target] crea etiquetas de STYLE para ocultar previamente los elementos DOM que se personalizarán.
1. Se elimina STYLE de ocultamiento previo de BODY de HTML.
1. [!DNL Target] comienza a sondear los elementos DOM.
1. Si se encuentra un elemento DOM, [!DNL Target] aplica los cambios de DOM y el elemento de ocultamiento previo STYLE se elimina.
1. Si no se encuentran elementos DOM, un tiempo de espera global no oculta los elementos para evitar tener una página rota.

## ¿Con qué frecuencia el contenido de la página está completamente cargado y es visible cuando at.js no oculta finalmente el elemento que está cambiando la actividad? {#section_01AFF476EFD046298A2E17FE3ED85075}

Teniendo en cuenta el escenario anterior, ¿con qué frecuencia el contenido de la página está completamente cargado y es visible cuando at.js no oculta finalmente el elemento que está cambiando la actividad? En otras palabras, la página es totalmente visible, excepto por el contenido de la actividad, que luego se revela ligeramente después del resto del contenido.

at.js no bloquea el procesamiento de la página. Un usuario puede ver que [!DNL Target] personalizará algunas regiones en blanco de la página que representan elementos. Si el contenido que se va a aplicar no contiene muchos recursos remotos, como SCRIPT o IMG, todo debería procesarse rápidamente.

## ¿Cómo afectaría una página en caché completa al escenario anterior? ¿Sería más probable que el contenido de la actividad se hiciera visible después de que se cargara el resto del contenido de la página?  {#section_CE76335A3E0B41CB8253DEE5E060FCDA}

Si una página se almacena en caché en una red de distribución de contenido (CDN) que está cerca de la ubicación del usuario, pero no cerca del perímetro de [!DNL Target], ese usuario puede ver algunos retrasos. Los perímetros de [!DNL Target] están bien distribuidos en todo el mundo, por lo que no es un problema la mayor parte del tiempo.

## ¿Es posible que se muestre una imagen a pantalla completa y cambie después de un breve retraso?  {#section_C25B07B25B854AAE8DEE1623D0FA62A3}

Si tenemos en cuenta el escenario siguiente:

El tiempo de espera de [!DNL Target] es de cinco segundos. Un usuario carga una página que tiene una actividad para personalizar una imagen a pantalla completa. at.js envía la solicitud para determinar si hay una actividad para aplicar, pero no hay una respuesta inicial. Suponga que el usuario ve el contenido normal de la imagen a pantalla completa, porque no se recibió respuesta de [!DNL Target] con respecto a si hay una actividad asociada. Después de cuatro segundos, [!DNL Target] devuelve una respuesta con el contenido de la actividad.

En este momento, ¿sería posible mostrar la versión alternativa? Entonces, después de cuatro segundos, ¿podría cambiar la imagen a pantalla completa y podría el usuario notar este cambio de imagen?

Inicialmente, el elemento DOM de la imagen a pantalla completa está oculto. Después de recibir una respuesta por parte de [!DNL Target], at.js aplica los cambios de DOM, como reemplazar el IMG y mostrar la imagen a pantalla completa personalizada.

## ¿Qué tipo de documento HTML requiere at.js?

at.js requiere el tipo de documento HTML 5.

Esta sintaxis es:

`<!DOCTYPE html>`

El tipo de documento HTML 5 garantiza que la página se carga en modo estándar. Cuando se carga en modo quirks, algunas API de JS de las que depende at.js están desactivadas. [!DNL Target] deshabilita at.js en modo quirks.
