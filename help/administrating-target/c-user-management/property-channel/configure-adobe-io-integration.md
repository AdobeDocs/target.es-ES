---
description: Información sobre la concesión de integraciones de Adobe I/O a todos los espacios de trabajo con la función deseada.
keywords: integración; roles; permisos de usuario; admin console
seo-description: Información sobre la concesión de integraciones de Adobe I/O a todos los espacios de trabajo con la función deseada en Adobe Target
seo-title: Conceda acceso a las integraciones de Adobe I/O a espacios de trabajo y asigne funciones en Adobe Target
solution: Target
subtopic: Primeros pasos
title: Otorgar acceso a las integraciones de Adobe I/O a espacios de trabajo y asignar funciones
translation-type: tm+mt
source-git-commit: e1174aacc5610878c8671e88fbd20d51fedffe6c

---


# ![PREMIUM](/help/assets/premium.png) Concesión de integraciones de Adobe I/O a espacios de trabajo y asignación de funciones

[!UICONTROL Los permisos de Enterprise] permiten [!DNL Target] a los clientes utilizar una sola organización, pero dividirlo en espacios de trabajo para distintos equipos o flujos de trabajo.

>[!NOTE]
>
>La funcionalidad Propiedades y Permisos está disponible como parte de la solución [Target Premium](/help/c-intro/intro.md#premium). No están disponibles en [!DNL Target Standard] sin una licencia de [!DNL Target Premium].

The [!UICONTROL Enterprise Permissions] feature facilitates effective scaling of optimization programs across teams. Although the feature was available in the [!DNL Target] UI, the Admin APIs lacked the corresponding support until earlier in 2019. In the [!DNL Target] February 2019 release, Adobe updated the Admin APIs so that you can use the integration account to access all workspaces created in your organization. So, while earlier, Admin APIs were restricted to just the default workspace, the February 2019 update granted access to all workspaces with [!UICONTROL Approver] access.

With the upcoming [!DNL Target] September 2019 release, [!DNL Target] [!UICONTROL Enterprise Permissions] will provide customers with the following access controls:

* Puede elegir los espacios de trabajo a los que se puede aplicar la integración
* You can apply a role to the Adobe I/O integration: [!UICONTROL Approver], [!UICONTROL Editor], or [!UICONTROL Observer].

Esta actualización admite los siguientes casos de uso:

* Grant the Adobe I/O integration access to all workspaces with the [!UICONTROL Observer] role for reporting purposes with no rights to create or edit resources.
* Conceda a la integración de Adobe I/O el acceso para seleccionar espacios de trabajo con la función apropiada para permitir que un equipo central realice cambios controlados por API en solo unos pocos espacios de trabajo.
* Permita que cada equipo propietario de su espacio de trabajo tenga su propia integración siempre que el equipo esté listo para explorar las API y elija la función correspondiente.
* Combina y coincide con cualquiera de los escenarios anteriores.

**Acción necesaria**: Los clientes que actualmente aprovechan las API para operaciones de CRUD en recursos (actividades, audiencias, ofertas e informes) en todos los espacios de trabajo deben conceder su acceso de integración de Adobe I/O a todos los espacios de trabajo con la función deseada según su caso de uso. You can do so by selecting each [!DNL Target] [!UICONTROL Product Profile] in the [!DNL Adobe Admin Console] and adding the integration(s) in the [!UICONTROL Integration] tab. Prior to the September release, all integrations operated using [!UICONTROL Approver] access, regardless of choice made from the [!UICONTROL Product Role] drop-down list. Ahora puede elegir la función que desee.

This action should be performed during the month of **August 2019** to not face any disruption on your end. If this action is not performed, after the [!DNL Target] September 2019 release, the access controls will activate and you will observe access to just the default workspace if that's how you are currently set up. No hay reacciones adversas para configurar integraciones por adelantado. Cuanto antes realice este cambio, mejor. Se requiere poco tiempo para configurar esto, según el número de espacios de trabajo de su organización. Este proceso solo toma unos pocos clics para agregar una integración existente en espacios de trabajo con la función deseada.

**Para otorgar acceso a las integraciones de Adobe I/O a espacios de trabajo y asignar funciones:**

1. Open the **[Adobe Admin Console](https://adminconsole.adobe.com)**.

1. Click the **[!UICONTROL Products]** tab, then select the name of the desired product.

   ![Elija el producto en Adobe Admin Console](/help/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. Seleccione el espacio de trabajo deseado (perfil de producto).

   ![Seleccione el perfil de producto](/help/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. Click the **[!UICONTROL Integrations]** tab.

   ![Ficha Integraciones](/help/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. (Conditional) To add a new integration, click **[!UICONTROL Add Integration]**, select the desired integration, then click **[!UICONTROL Save]**.

1. From the **[!UICONTROL Product Role]** drop-down list, select the desired role for that workspace:

   * [!UICONTROL Aprobador]
   * [!UICONTROL Editor]
   * [!UICONTROL Observador]
   ![Elija la función Perfil de producto](/help/administrating-target/c-user-management/property-channel/assets/product-profile-role.png)
