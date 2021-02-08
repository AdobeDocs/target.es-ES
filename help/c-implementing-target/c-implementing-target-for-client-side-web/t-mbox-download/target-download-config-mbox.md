---
keywords: Implementación;Mbox;mbox.js;descargar mbox.js;configurar mbox.js
description: Obtenga información sobre la implementación heredada de mbox.js de Adobe Target. Migrar al SDK web de Adobe Experience Platform (AEP Web SDK) o a la versión más reciente de at.js.
title: ¿Cómo se descarga la biblioteca mbox.js de Destinatario?
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 58%

---


# Descargar mbox.js{#download-mbox-js}

Target Standard y Premium usan una versión modificada del archivo mbox.js de Adobe Target.

>[!IMPORTANT]
>
>**Fin de vida útil** de mbox.js: El 31 de marzo de 2021 ya no  [!DNL Adobe Target] admitirá la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas realizadas desde mbox.js generarán errores e impactarán en las páginas que tengan [!DNL Target] actividades ejecutándose al proporcionar contenido predeterminado.
>
>Se recomienda que todos los clientes migren a la versión más reciente de la nueva [!DNL Adobe Experience Platform Web SDK] o a la biblioteca JavaScript at.js antes de esta fecha para evitar cualquier problema potencial con sus sitios. Para obtener más información, consulte [Información general: implemente Destinatario para la Web del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

Para usar el [!DNL Adobe Target]Compositor de experiencias visuales[!UICONTROL  de ], tiene que incluir una línea adicional de JavaScript en el archivo [!DNL mbox.js].

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Implementación]** en [!DNL Target Standard].
1. Haga clic en **[!UICONTROL Descargar mbox.js]** y siga las indicaciones para guardar el archivo.
1. (Condicional) Si usa la versión 60 o posterior de [!DNL mbox.js], puede configurar la biblioteca para que oculte automáticamente el contenido de la página de forma predeterminada hasta que se carguen los mboxes a fin de reducir el parpadeo en los sitios adaptables.

   Para obtener más información, consulte “Eliminar el parpadeo en la carga de página” en la [configuración avanzada de mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/advanced-mboxjs-settings.md#reference_A9C8DAC6DF7743EDBCF1D71F8F20843C).

1. Cree la referencia a [!DNL mbox.js] en el sitio web.

   A partir de la versión 57 de [!DNL mbox.js], la referencia [!DNL mbox.js] se puede colocar en cualquier lugar de la sección `<head>` de la página.

   >[!IMPORTANT]
   >
   >Si usa una versión de [!DNL mbox.js] anterior a 57, la referencia debe ser el último artículo que aparezca en la sección `<head>` de las páginas. Si la referencia no es el último elemento pueden producirse problemas graves de visualización o de rendimiento. Consulte [Qué hace mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-technical.md) para obtener más información.

1. Transfiera el archivo [!DNL mbox.js] guardado a la ubicación en su entorno de alojamiento que haya especificado en el código.
