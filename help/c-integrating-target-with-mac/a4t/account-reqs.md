---
keywords: Analytics as reporting source;a4t;A4T;requirements
description: Requisitos de cuenta de usuario para crear una actividad basada en Adobe Analytics en Adobe Target (A4T).
title: Requisitos de permisos de usuario
feature: Analytics for Target (A4T)
solution: Target,Analytics
translation-type: tm+mt
source-git-commit: cf47b7f3625bb1c3430b9fba00c573f489efc448
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 49%

---


# Requisitos de permisos de usuario

Información sobre los requisitos de cuenta de usuario para crear una actividad basada en [!DNL Adobe Analytics] en [!DNL Adobe Target] (A4T).

Para poder seleccionar un grupo de informes al definir una actividad de [!DNL Analytics], necesita una cuenta de usuario de [!DNL Analytics] y una cuenta de usuario de [!DNL Target].

Sus cuentas de usuario deben estar configuradas tal como se describe en las secciones siguientes:

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

Complete las siguientes tareas en [!DNL Adobe Experience Cloud][Admin Console](https://adminconsole.adobe.com):

### Vincule las cuentas de las soluciones a su Adobe ID

Las cuentas de usuario de [!DNL Analytics] y de [!DNL Target] deben estar vinculadas a su Adobe ID.

Para obtener más información, consulte [Organizaciones y vinculación de cuentas](https://docs.adobe.com/help/en/core-services/interface/manage-users-and-products/organizations.html).

### Configuración de la pertenencia a grupo de Experience Cloud

Debe ser miembro de uno o más grupos de [!DNL Experience Cloud] que tengan acceso a [!DNL Analytics] y [!DNL Target].

Para obtener más información, consulte [Administración de usuarios y productos de Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

## Adobe Analytics    {#section_8F404FDE9A634534AB0AA4CB3075582B}

Configure el acceso al grupo de informes [!DNL Analytics]:

Para utilizar A4T en un grupo de informes determinado, debe tener acceso a ese grupo de informes.

1. En **[!UICONTROL Admin Console]**, haga clic en un perfil de producto [!DNL Analytics] y, a continuación, haga clic en la ficha **[!UICONTROL Permisos]**.

   Luego puede ver a qué grupos de informes tiene acceso el perfil.

1. Asegúrese de que el grupo de informes al que desee tener acceso en [!DNL Target] sea uno de los enumerados en el perfil del producto del que forma parte.

   La siguiente ilustración es un ejemplo de un perfil de producto que tiene acceso a todos los grupos de informes:

   ![Ficha Permiso de Admin Console](/help/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

## Adobe Target {#section_26BA212D8D40443E9EE2AB327091425C}

No se necesitan privilegios adicionales.
