---
description: La manera en que Target hace y responde llamadas desde la página depende de la versión de la biblioteca de Target que está usando, de si la implementación del ID de visitante de Experience Cloud está presente y de si existe el ID de visitante.
title: Métodos de página de Target por versión de biblioteca mbox.js
feature: at.js
translation-type: tm+mt
source-git-commit: ae44c57c7b8767915fbbce4271a4b1858dd07efd
workflow-type: tm+mt
source-wordcount: '940'
ht-degree: 92%

---


# Métodos de página de Target por versión de biblioteca mbox.js{#target-page-methods-by-mbox-js-library-version}

La manera en que Target hace y responde llamadas desde la página depende de la versión de la biblioteca de Target que está usando, de si la implementación del ID de visitante de Experience Cloud está presente y de si existe el ID de visitante.

>[!IMPORTANT]
>
>**Fin de vida útil** de mbox.js: El 31 de marzo de 2021 ya no  [!DNL Adobe Target] admitirá la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas realizadas desde mbox.js generarán errores e impactarán en las páginas que tengan [!DNL Target] actividades ejecutándose al proporcionar contenido predeterminado.
>
>Se recomienda que todos los clientes migren a la versión más reciente de la nueva [!DNL Adobe Experience Platform Web SDK] o a la biblioteca JavaScript at.js antes de esta fecha para evitar cualquier problema potencial con sus sitios. Para obtener más información, consulte [Información general: implemente Destinatario para la Web del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

>[!NOTE]
>
>Si usa [!DNL at.js], todas las llamadas se realizan con JSON. Esta página proporciona detalles sobre las versiones de la biblioteca [!DNL mbox.js]. Los comportamientos que se describen en los casos siguientes no se aplican a [!DNL at.js].

En esta sección se proporciona información sobre cómo cada versión de la biblioteca de [!DNL Target] responde a la llamada de [!DNL Target] desde la página en cada uno de los casos siguientes.

Existen varios tipos de extremos, según la implementación y la versión de la biblioteca. Debe conocer cada tipo para entender cómo [!DNL Target] responde a las llamadas en cada escenario.

| Tipo/Extremo | Llamar a método | Contenido de la respuesta |
|--- |--- |--- |
| crear automáticamente mbox global: sincrónico | document.write para realizar llamada | JavaScript sin document.write() |
| crear automáticamente mbox global: asincrónico | createElement() para anexar llamada a cuerpo | JavaScript sin document.write() |
| standard | document.write para realizar llamada | JavaScript con document.write() |
| ajax | createElement() para anexar llamada a cuerpo | JavaScript sin document.write() |
| json | XMLHTTPrequest() para realizar llamada | devuelve respuesta de JSON |

>[!IMPORTANT]
>
>Para cualquier tipo, excepto estándar, todos los códigos personalizados y las ofertas deben escribirse para admitir un entorno ajax. Por ejemplo, si se usa un JavaScript que incluye `document.write()`, el script no funcionará como se espera.

## Sin implementación de ID de visitante {#section_C6F7213FDE4D48E8BBCB1A9A26310FEE}

Si usa [!DNL Target Standard] o [!DNL Premium] con [!DNL mbox.js] y habilitó [!UICONTROL Crear mbox global] para su cuenta, se realizará el tipo de llamada y respuesta **crear automáticamente mbox global sincrónico**, independientemente de la versión de [!DNL mbox.js].

Si escribe su propio código personalizado en lugar de usar las acciones del [!UICONTROL Compositor de experiencias visuales], asegúrese de que el código sea adecuado para un entorno ajax. Por ejemplo, si se usa un JavaScript que incluye `document.write()`, el script no funcionará como se espera.

>[!NOTE]
>
>Varias llamadas de mbox ajax con el mismo nombre de mbox pero parámetros diferentes no funcionarán en la misma página. Solo se realizará la primera llamada.

Si usa “crear automáticamente mbox global” pero también tiene llamadas `mboxCreate` en su página; por ejemplo, si está implementando [!DNL Target Standard] o [!DNL Premium] en una página que anteriormente usaba una implementación heredada, las llamadas de mbox global se realizan con el extremo “crear automáticamente mbox global: estándar” y las llamadas `mboxCreate` se realizan con el extremo **estándar**. El extremo **estándar** usa `document.write()` para realizar y responder la llamada. Esto bloquea la carga de la página, incluido el contenido entregado en la respuesta ajax, hasta que se descargue toda la información.

Si usa solamente mboxCreate, por ejemplo en páginas creadas con [!DNL Target Classic], la página funciona como siempre.

| Método de creación | mbox.js v57 | mbox.js v58 | mbox.js v59 | mbox.js v60 |
|---|---|---|---|---|
| crear automáticamente mbox global | crear automáticamente mbox global: sincrónico | crear automáticamente mbox global: sincrónico | crear automáticamente mbox global: sincrónico | crear automáticamente mbox global: sincrónico |
| mboxCreate | estándar | estándar | estándar | estándar |

## Con implementación de ID de visitante, pero sin ID de visitante establecido    {#section_29888A119C7A4753AD287FC845AA63F4}

Si no se estableció ningún ID de visitante, no hay ninguna cookie de visitante de [!DNL Experience Cloud] para el usuario. La página llama al servicio de ID de visitante para obtener el ID del visitante.  espera la respuesta mientras el ID realiza la llamada a [!DNL Target]Target.

>[!NOTE]
>
>Se recomienda usar la versión 58 de [!DNL Mbox.js] para garantizar que el ID de visitante se devuelva antes de realizar la llamada de Target.

Si está usando la versión 57 de [!DNL mbox.js] en este caso, todo funciona como si no hubiera implementación de ID de visitante, tal como se describió en el caso anterior. A partir de la versión 58 de [!DNL mbox.js], el servicio [!DNL Experience Cloud Visitor ID] regresa con un ID de visitante antes de realizar llamadas de [!DNL Target]. Así, los datos de audiencia que se comparten a través del servicio principal de Perfiles y Audiencias están disponibles para la primera llamada de [!DNL Target] en la sesión del visitante. Para evitar que el contenido predeterminado parpadee antes de que se devuelva el contenido de la prueba, [!DNL Target] oculta la etiqueta `<BODY>` hasta que se devuelve el servicio de ID de visitante. En la versión 58, se usa `display:none` para ocultar la página. Esto crea algunos problemas con sitios adaptables, por lo que a partir de la versión 59, se usa `opacity:0` para ocultar el contenido.

| Método de creación | mbox.js v57 | mbox.js v58 | mbox.js v59 | mbox.js v60 |
|---|---|---|---|---|
| crear automáticamente mbox global | crear automáticamente mbox global: sincrónico | crear automáticamente mbox global: asincrónico | crear automáticamente mbox global: asincrónico | crear automáticamente mbox global: asincrónico |
| mboxCreate | estándar | ajax | ajax | ajax |

## Con implementación de ID de visitante, y existe el ID de visitante    {#section_9CD4AE4C8186425D886398BC3CE6C46D}

Si existe la cookie del ID de visitante, [!DNL Target] no necesita realizar una llamada al servicio de ID de visitante. En este caso, no es necesario esperar el servicio de ID de visitante antes de mostrar el contenido. Para las versiones 57 a 59, se usa el tipo **crear automáticamente mbox global: sincrónico**, de modo que la página espera a que se devuelva la llamada a [!DNL Target] antes de seguir cargándose. Esto garantiza que no sea vean parpadeos en el contenido predeterminado. Con la versión 60, se usa el **tipo mbox global: asincrónico** para garantizar que [!DNL Target] espere a que responda el servicio de exclusión de [!DNL Experience Cloud]. El servicio de exclusión forma parte de la inclusión de datos en el otoño de 2016. Como todas las llamadas se devuelven mediante ajax, `document.write()` no debería usarse con la versión 60 de [!DNL mbox.js].

| Método de creación | mbox.js v57 | mbox.js v58 | mbox.js v59 | mbox.js v60 |
|---|---|---|---|---|
| crear automáticamente mbox global | crear automáticamente mbox global: sincrónico | crear automáticamente mbox global: sincrónico | crear automáticamente mbox global: sincrónico | crear automáticamente mbox global: asincrónico (para admitir el desarrollo de la inclusión de datos, que se lanzará más tarde en 2016) |
| mboxCreate | estándar | estándar | estándar | ajax |