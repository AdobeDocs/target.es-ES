---
description: Target Standard y Premium usan una versión modificada del archivo mbox.js de Adobe Target.
keywords: Implementación;Mbox;mbox.js;descargar mbox.js;configurar mbox.js
seo-description: Target Standard y Premium usan una versión modificada del archivo mbox.js de Adobe Target.
seo-title: Descargar mbox.js
solution: Target
subtopic: Primeros pasos
title: Descargar mbox.js
topic: Standard
uuid: b2a46321-cac7-4924-92dd-a80b50e27cee
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Descargar mbox.js{#download-mbox-js}

Target Standard y Premium usan una versión modificada del archivo mbox.js de Adobe Target.

Para usar el [!DNL Adobe Target]Compositor de experiencias visuales[!UICONTROL  de ], tiene que incluir una línea adicional de JavaScript en el archivo [!DNL mbox.js].

1. Haga clic en **[!UICONTROL Configuración]** &gt; **[!UICONTROL Implementación]** en [!DNL Target Standard].
1. Haga clic en **[!UICONTROL Descargar mbox.js]** y siga las indicaciones para guardar el archivo.
1. (Condicional) Si usa la versión 60 o posterior de [!DNL mbox.js], puede configurar la biblioteca para que oculte automáticamente el contenido de la página de forma predeterminada hasta que se carguen los mboxes a fin de reducir el parpadeo en los sitios adaptables.

   Para obtener más información, consulte “Eliminar el parpadeo en la carga de página” en la [configuración avanzada de mbox.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/advanced-mboxjs-settings.md#reference_A9C8DAC6DF7743EDBCF1D71F8F20843C).

1. Cree la referencia a [!DNL mbox.js] en el sitio web.

   A partir de la versión 57 de [!DNL mbox.js], la referencia [!DNL mbox.js] se puede colocar en cualquier lugar de la sección `<head>` de la página.

   >[!IMPORTANT]
   >
   >Si usa una versión de [!DNL mbox.js] anterior a 57, la referencia debe ser el último artículo que aparezca en la sección `<head>` de las páginas. Si la referencia no es el último elemento pueden producirse problemas graves de visualización o de rendimiento. Consulte [Información detallada sobre la implementación técnica](https://marketing.adobe.com/resources/help/en_US/target/ov/c_mbox_technical.html) para obtener más información.

1. Transfiera el archivo [!DNL mbox.js] guardado a la ubicación en su entorno de alojamiento que haya especificado en el código.
