---
keywords: Analytics como fuente de informes;a4t;A4T;requisitos
description: Aprenda a configurar los requisitos de cuenta de usuario necesarios para crear una actividad basada en Adobe Analytics en el Adobe  [!DNL Target] mediante Analytics for [!DNL Target] (A4T).
title: ¿Qué requisitos de permisos de usuario son necesarios para A4T?
feature: Analytics for Target (A4T)
solution: Target,Analytics
exl-id: f56fc525-92da-4814-86c1-18b3a2765f37
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 35%

---

# Requisitos de permisos de usuario

Información sobre los requisitos de cuenta de usuario para crear una actividad basada en [!DNL Adobe Analytics] en [!DNL Adobe Target] (A4T).

Para poder seleccionar un grupo de informes al definir una actividad de [!DNL Analytics], necesita una cuenta de usuario de [!DNL Analytics] y una cuenta de usuario de [!DNL Target].

Sus cuentas de usuario deben estar configuradas tal como se describe en las secciones siguientes:

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

Complete las siguientes tareas en el [!DNL Adobe Experience Cloud] [Admin Console](https://adminconsole.adobe.com):

### Vincule las cuentas de las soluciones a su Adobe ID

Las cuentas de usuario de [!DNL Analytics] y de [!DNL Target] deben estar vinculadas a su Adobe ID.

Para obtener más información, consulte [Organizaciones y vinculación de cuentas](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=es).

### Configuración de la pertenencia a grupo de Experience Cloud

Debe ser miembro de uno o más grupos de [!DNL Experience Cloud] que tengan acceso a [!DNL Analytics] y [!DNL Target].

Para obtener más información, consulte [Administrar usuarios y productos de Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=es).

## Adobe Analytics   {#section_8F404FDE9A634534AB0AA4CB3075582B}

Para utilizar A4T en un grupo de informes determinado, debe tener acceso a ese grupo de informes y conceder acceso al grupo [!DNL Web Services Access].

1. En **[!UICONTROL Admin Console]**, haga clic en un perfil de producto de [!DNL Analytics] y, a continuación, haga clic en la ficha **[!UICONTROL Permissions]**.

   A continuación, puede ver a qué grupos de informes tiene acceso el perfil.

1. Asegúrese de que el grupo de informes al que desea tener acceso en [!DNL Target] sea uno de los enumerados en el perfil de producto al que pertenece.

   La siguiente ilustración es un ejemplo de un perfil de producto que tiene acceso a todos los grupos de informes:

   ![Ficha Permiso de Admin Console](/help/main/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

1. Configure el acceso al grupo [!UICONTROL Web Services Access].

   Se requiere acceso al grupo [!UICONTROL Web Services Access] en [!DNL Analytics] para poder usar [!DNL Analytics] como el origen de informes para [!DNL Target].


## Adobe[!DNL Target] {#section_26BA212D8D40443E9EE2AB327091425C}

No se necesitan privilegios adicionales.
