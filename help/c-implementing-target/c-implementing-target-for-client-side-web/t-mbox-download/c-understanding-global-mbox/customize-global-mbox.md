---
keywords: mbox global;personalizar mbox global;editar at.js;at.js;implementar at.js
description: Obtenga información sobre cómo personalizar un mbox global para at.js en la página Administration-Implementation de Adobe Target.
title: ¿Cómo personalizo un mbox global?
feature: at.js
role: Developer
exl-id: 6d3eab89-818c-405c-81af-90dfbede7390
source-git-commit: fb0a62ecc5609e7b8ef5f6a4fb5a94f8ba025fec
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 22%

---

# Personalización de un mbox global

Información para personalizar un mbox global en at.js.

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Implementación]**.

1. Deshabilite **[!UICONTROL Page load enabled (Auto create global mbox)]** y luego añada el nombre del mbox global personalizado que desea usar para publicar actividades desde [!DNL Target].

   >[!IMPORTANT]
   >
   >El cambio se guarda automáticamente al seleccionar un mbox global diferente.

   Este mbox global personalizado también se usa para el rastreo de clics.

   ![custom-global-mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/assets/custom-global-mbox.png)

1. Implemente la biblioteca [!DNL at.js] en el sitio.

   Consulte [Cómo implementar at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md) para obtener más información.

1. Programe la transición según su versión.

   Cuando esté listo para que [!DNL Target] empiece a usar el mbox global en todas las actividades futuras, proceda con este paso.

   Actualice el nombre del mbox global personalizado para que coincida con el nombre usado en el paso 2 anterior.

   >[!IMPORTANT]
   >
   >Todas las actividades de la cuenta se sincronizan con este mbox. Si este mbox no está en su sitio, todas las actividades dejarán de funcionar.
