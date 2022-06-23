---
keywords: mbox global;personalizar mbox global;editar at.js;at.js;implementar at.js
description: Obtenga información sobre cómo personalizar un mbox global para at.js en la página Administration-Implementation de Adobe Target.
title: ¿Cómo personalizo un mbox global?
feature: at.js
role: Developer
exl-id: 6d3eab89-818c-405c-81af-90dfbede7390
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 17%

---

# Personalización de un mbox global

Información para ayudarle a personalizar y [!DNL Adobe Target] mbox global para at.js.

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Implementación]**.

1. Deshabilitar **[!UICONTROL Carga de página habilitada (Creación automática de mbox global)]** y, a continuación, añada el nombre del mbox global personalizado que desea usar para publicar actividades desde [!DNL Target].

   >[!IMPORTANT]
   >
   >El cambio se guarda automáticamente al seleccionar un mbox global diferente.

   Este mbox global personalizado también se usa para el rastreo de clics.

   ![custom-global-mbox](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/assets/custom-global-mbox.png)

1. Implementación de [!DNL at.js] biblioteca en el sitio.

   Consulte [Cómo implementar at.js](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/how-to-deployatjs/) para obtener más información.

1. Programe la transición según su versión.

   Cuando esté listo para [!DNL Target] para empezar a usar el mbox global en todas las actividades futuras, siga este paso.

   Actualice el nombre del mbox global personalizado para que coincida con el nombre usado en el paso 2 anterior.

   >[!IMPORTANT]
   >
   >Todas las actividades de la cuenta se sincronizan con este mbox. Asegúrese de que el mbox global esté presente en el sitio para que las actividades sigan funcionando. Asegúrese de editar y volver a guardar las actividades afectadas que se crearon con el Compositor de experiencias visuales (VEC) que se sincronizan con este mbox. No es necesario volver a guardar las actividades creadas en el Compositor de experiencias basadas en formularios o mediante API.

