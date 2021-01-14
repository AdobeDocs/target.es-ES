---
keywords: global mbox;customize global mbox;edit at.js;at.js;implement at.js
description: Información útil para personalizar un mbox global para at.js.
title: Personalizar un mbox global
feature: at.js
translation-type: tm+mt
source-git-commit: 88f6e4c6ad168e4f9ce69aa6618d8641b466e28a
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 59%

---


# Personalizar un mbox global

Información útil para personalizar un mbox global para at.js.

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Implementación]**.

1. Deshabilite **[!UICONTROL Carga de página habilitada (Crear automáticamente mbox global)]**, luego agregue el nombre del mbox global personalizado que desee usar para enviar actividades desde [!DNL Target].

   Este mbox global personalizado también se usa para el rastreo de clics.

   ![custom-global-mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/assets/custom-global-mbox.png)

1. Haga clic en **[!UICONTROL Guardar]** cuando termine.

1. Implementar la biblioteca [!DNL at.js] en el sitio.

   Consulte [Cómo implementar at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md) para obtener más información.

1. Programe la transición según su versión.

   Cuando esté listo para que [!DNL Target] empiece a usar el mbox global en todas las actividades futuras, proceda con este paso.

   Actualice el nombre del mbox global personalizado para que coincida con el nombre usado en el paso 2 anterior.

   >[!IMPORTANT]
   >
   >Cuando se guarda, todas las actividades de la cuenta se sincronizan con este mbox. Si este mbox no está en su sitio, todas las actividades dejarán de funcionar.

