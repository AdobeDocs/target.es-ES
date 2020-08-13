---
keywords: Analytics as reporting source;a4t;A4T
description: Requisitos de cuenta de usuario para crear una actividad basada en Adobe Analytics en Adobe Target (A4T).
title: Requisitos de permisos de usuario
feature: a4t implementation
solution: Target,Analytics
topic: Reports and analytics
uuid: cf359bcd-547e-4f8f-bcf6-e646245bb9ce
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 63%

---


# Requisitos de permisos de usuario {#user-permission-requirements}

Información sobre los requisitos de cuenta de usuario para crear una actividad basada en [!DNL Adobe Analytics] en [!DNL Adobe Target] (A4T).

Para poder seleccionar un grupo de informes al definir una actividad de [!DNL Analytics], necesita una cuenta de usuario de [!DNL Analytics] y una cuenta de usuario de [!DNL Target].

Sus cuentas de usuario deben estar configuradas tal como se describe en las secciones siguientes:

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

Complete las siguientes tareas en [!DNL Adobe Experience Cloud][Admin Console](https://adminconsole.adobe.com):

### Vincule las cuentas de las soluciones a su Adobe ID

Las cuentas de usuario de [!DNL Analytics] y de [!DNL Target] deben estar vinculadas a su Adobe ID.

For more information, see [Organizations and account linking](https://docs.adobe.com/help/en/core-services/interface/manage-users-and-products/organizations.html).

### Configuración de la pertenencia a grupo de Experience Cloud

Debe ser miembro de uno o más grupos de [!DNL Experience Cloud] que tengan acceso a [!DNL Analytics] y [!DNL Target].

For more information, see [Manage Experience Cloud users and products](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html).

## Adobe Analytics   {#section_8F404FDE9A634534AB0AA4CB3075582B}

Complete las siguientes tareas en [!DNL Adobe Analytics]:

### Configuración del acceso al grupo de informes de Analytics

Before creating or viewing reports for an [!DNL Analytics]-powered activity, you must be a member of the **[!UICONTROL All Report Access]** group, or a member of a group that has access to at least one report in the report suite that you want to use. Si no puede ver informes, asegúrese de que es miembro de uno de estos grupos.

Para obtener más información, consulte perfiles y grupos [de productos](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html#section_AB50558124D541CF80A0D3D76D35A4BF).

### Configuración del acceso al grupo de acceso a servicios web

Para poder usar [!DNL Analytics] como la fuente de informes para [!DNL Target], debe pertenecer al grupo de acceso a servicios web de [!DNL Analytics].

## Adobe Target {#section_26BA212D8D40443E9EE2AB327091425C}

No se necesitan privilegios adicionales.
