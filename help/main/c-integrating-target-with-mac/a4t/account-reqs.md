---
keywords: Analytics como fuente de informes;a4t;A4T;requisitos
description: Aprenda a configurar los requisitos de cuenta de usuario necesarios para crear una actividad basada en Adobe Analytics en Adobe [!DNL Target] con Analytics for [!DNL Target] (A4T).
title: ¿Qué requisitos de permisos de usuario son necesarios para A4T?
feature: Analytics for Target (A4T)
solution: Target,Analytics
exl-id: f56fc525-92da-4814-86c1-18b3a2765f37
TQID: https://experienceleague.adobe.com/SGNIoARqe3yN4WvKF4JPIp0t0JCMiSgj--zrjt-ZXJQ
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 307
ht-degree: 31%

---

# Requisitos de permisos de usuario

Información sobre los requisitos de cuenta de usuario para crear una actividad basada en [!DNL Adobe Analytics] en [!DNL Adobe Target] (A4T).

Para poder seleccionar un grupo de informes al definir una actividad de [!DNL Analytics], necesita una cuenta de usuario de [!DNL Analytics] y una cuenta de usuario de [!DNL Target].

Sus cuentas de usuario deben estar configuradas tal como se describe en las secciones siguientes:

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

Complete las siguientes tareas en [!DNL Adobe Experience Cloud] [Admin Console](https://adminconsole.adobe.com):

### Vincule las cuentas de las soluciones a su Adobe ID

Las cuentas de usuario de [!DNL Analytics] y de [!DNL Target] deben estar vinculadas a su Adobe ID.

Para obtener más información, consulte [Organizaciones y vinculación de cuentas](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=es).

### Configuración del abono a grupos de Experience Cloud

Debe ser miembro de uno o más grupos de [!DNL Experience Cloud] que tengan acceso a [!DNL Analytics] y [!DNL Target].

Para obtener más información, consulte [Administrar usuarios y productos de Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=es).

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

Para utilizar A4T en un grupo de informes determinado, debe tener acceso a ese grupo de informes y conceder acceso al grupo [!DNL Web Services Access].

1. En **[!UICONTROL Admin Console]**, haga clic en un perfil de producto de [!DNL Analytics] y luego haga clic en la ficha **[!UICONTROL Permisos]**.

   A continuación, puede ver a qué grupos de informes tiene acceso el perfil.

1. Asegúrese de que el grupo de informes al que desea tener acceso en [!DNL Target] sea uno de los enumerados en el perfil de producto al que pertenece.

   La siguiente ilustración es un ejemplo de un perfil de producto que tiene acceso a todos los grupos de informes:

   ![Ficha Permiso de Admin Console](/help/main/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

1. Configure el acceso al grupo [!UICONTROL Acceso a servicios web].

   Se requiere acceso al grupo [!UICONTROL Acceso a servicios web] en [!DNL Analytics] para poder usar [!DNL Analytics] como el origen de informes para [!DNL Target].


## Adobe[!DNL Target] {#section_26BA212D8D40443E9EE2AB327091425C}

No se necesitan privilegios adicionales.
