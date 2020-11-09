---
keywords: global mbox;customize global mbox;edit at.js;at.js;implement at.js
description: Información útil para personalizar un mbox global para at.js.
title: Personalizar un mbox global
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 59%

---


# Personalizar un mbox global{#customize-a-global-mbox}

Información útil para personalizar un mbox global para at.js.

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Implementación]**.

1. Disable **[!UICONTROL Page load enabled (Auto create global mbox)]**, then add the name of the custom global mbox that you would like to use to deliver activities from [!DNL Target].

   Este mbox global personalizado también se usa para el rastreo de clics.

   ![custom-global-mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/assets/custom-global-mbox.png)

1. Haga clic en **[!UICONTROL Guardar]** cuando termine.

1. Implement the [!DNL at.js] library on your site.

   Consulte [Cómo implementar at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md) para obtener más información.

1. Programe la transición según su versión.

   Cuando esté listo para que [!DNL Target] empiece a usar el mbox global en todas las actividades futuras, proceda con este paso.

   Actualice el nombre del mbox global personalizado para que coincida con el nombre usado en el paso 2 anterior.

   >[!IMPORTANT]
   >
   >Cuando se guarda, todas las actividades de la cuenta se sincronizan con este mbox. Si este mbox no está en su sitio, todas las actividades dejarán de funcionar.

