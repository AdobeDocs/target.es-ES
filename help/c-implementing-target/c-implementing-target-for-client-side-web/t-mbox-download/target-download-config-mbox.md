---
keywords: Implementación;Mbox;mbox.js;descargar mbox.js;configurar mbox.js
description: Obtenga información sobre la implementación de mbox.js heredada de Adobe Target. Migrar al SDK web de Adobe Experience Platform (SDK web de AEP) o a la versión más reciente de at.js.
title: ¿Cómo puedo descargar la biblioteca  [!DNL Target] mbox.js?
feature: at.js
role: Developer
exl-id: 92096b1b-a8a5-435b-8e62-24b5d15d392f
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 74%

---

# Descargar mbox.js

Target Standard y Premium usan una versión modificada del archivo mbox.js de Adobe Target.

>[!IMPORTANT]
>
>**Fin de vida útil de mbox.js**: Desde el 31 de marzo de 2021, [!DNL Adobe Target] no es compatible con la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas que se realicen desde mbox.js producirán errores y afectarán a las páginas que tengan actividades de [!DNL Target] en ejecución para las que se mostrará contenido predeterminado.
>
>Recomendamos que todos los clientes migren a la versión más reciente de la nueva [!DNL Adobe Experience Platform Web SDK] o la biblioteca JavaScript at.js antes de esta fecha para evitar cualquier problema potencial con sus sitios. Para obtener más información, consulte [Información general: Implementación de Target en sitios web del lado del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

Para usar el [!DNL Adobe Target]Compositor de experiencias visuales[!UICONTROL  de ], tiene que incluir una línea adicional de JavaScript en el archivo [!DNL mbox.js].

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Implementación]** en [!DNL Target Standard].
1. Haga clic en **[!UICONTROL Descargar mbox.js]** y siga las indicaciones para guardar el archivo.
1. (Condicional) Si usa la versión 60 o posterior de [!DNL mbox.js], puede configurar la biblioteca para que oculte automáticamente el contenido de la página de forma predeterminada hasta que se carguen los mboxes a fin de reducir el parpadeo en los sitios adaptables.

1. Cree la referencia a [!DNL mbox.js] en el sitio web.

   A partir de la versión 57 de [!DNL mbox.js], la referencia [!DNL mbox.js] se puede colocar en cualquier lugar de la sección `<head>` de la página.

   >[!IMPORTANT]
   >
   >Si usa una versión de [!DNL mbox.js] anterior a 57, la referencia debe ser el último artículo que aparezca en la sección `<head>` de las páginas. Si la referencia no es el último elemento pueden producirse problemas graves de visualización o de rendimiento.

1. Transfiera el archivo [!DNL mbox.js] guardado a la ubicación en su entorno de alojamiento que haya especificado en el código.
