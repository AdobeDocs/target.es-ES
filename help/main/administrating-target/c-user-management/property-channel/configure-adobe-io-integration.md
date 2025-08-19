---
keywords: integración; funciones; permisos de usuario; admin console
description: Obtenga información sobre cómo conceder acceso a integraciones de Adobe I/O existentes a todos los espacios de trabajo con la función deseada en Adobe Target.
title: ¿Cómo concedo acceso a Adobe I/O a los espacios de trabajo y asigno funciones?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Administration & Configuration
role: Admin
exl-id: 62f6399f-c590-470c-ac3b-e0c84db63112
source-git-commit: fa11f93058b69e5e59e0ee20c65cffa4a1344ca0
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 59%

---

# Conceder acceso a las integraciones de Adobe I/O a espacios de trabajo y asignar funciones

[!UICONTROL Enterprise Permissions] permite que los clientes de [!DNL Target] usen una sola organización, pero dividirla en espacios de trabajo para diferentes equipos o flujos de trabajo.

>[!NOTE]
>
>La funcionalidad Propiedades y Permisos está disponible como parte de la solución [Target Premium](/help/main/c-intro/intro.md#premium). No están disponibles en [!DNL Target Standard] sin una licencia de [!DNL Target Premium].

La característica [!UICONTROL Enterprise Permissions] facilita la escala efectiva de los programas de optimización entre los equipos. Aunque la funcionalidad estaba disponible en la interfaz de usuario de [!DNL Target], las API de administrador no tenían la compatibilidad correspondiente hasta principios de 2019. En la versión de febrero de 2019 de [!DNL Target], Adobe actualizó las API de administrador para que se pueda utilizar la cuenta de integración para acceder a todos los espacios de trabajo creados en su organización. Por tanto, las API de administrador estaban restringidas únicamente al espacio de trabajo predeterminado, pero la actualización de febrero de 2019 otorgaba acceso a todos los espacios de trabajo con acceso de [!UICONTROL Approver].

Con la versión de [!DNL Target] de septiembre de 2019, [!DNL Target] [!UICONTROL Enterprise Permissions] proporciona a los clientes los siguientes controles de acceso:

* Puede elegir los espacios de trabajo a los que se puede aplicar la integración
* Puede aplicar un rol a la integración de Adobe I/O: [!UICONTROL Approver], [!UICONTROL Editor] o [!UICONTROL Observer].

Esta actualización es compatible con los siguientes ejemplos prácticos:

* Conceder acceso a la integración de Adobe I/O a todos los espacios de trabajo con el rol [!UICONTROL Observer] con fines de creación de informes sin tener derechos para crear o editar recursos.
* Conceder acceso a la integración de Adobe I/O para seleccionar espacios de trabajo con la función apropiada para permitir que un equipo central realice cambios controlados por API solo en unos pocos espacios de trabajo.
* Permitir que cada equipo propietario de su espacio de trabajo tenga su propia integración siempre que el equipo esté listo para explorar las API y elija la función correspondiente.
* Cualquier combinación de los escenarios anteriores.

**Acción necesaria**: Los clientes que actualmente aprovechan las API para operaciones de CRUD en recursos (actividades, audiencias, ofertas e informes) en todos los espacios de trabajo deben conceder su acceso de integración de Adobe I/O a todos los espacios de trabajo con la función deseada según su uso. Para ello, seleccione cada [!DNL Target] [!UICONTROL Product Profile] en [!DNL Adobe Admin Console] y agregue las integraciones en la ficha [!UICONTROL Integration]. Antes de la versión de septiembre, todas las integraciones operaban con el acceso de [!UICONTROL Approver], independientemente de la opción que se realice en la lista desplegable [!UICONTROL Product Role]. Ahora puede elegir la función que desee.

>[!NOTE]
>
>Si no se realiza esta acción, después de la versión de septiembre de 2019 de [!DNL Target], los controles de acceso se activarán y tendrá acceso solo al espacio de trabajo predeterminado (si es su configuración actual). Se pueden configurar integraciones por adelantado sin problema. Cuanto antes realice este cambio, mejor. En función del número de espacios de trabajo de su organización, este proceso tarda solo unos clics en añadir una integración existente en espacios de trabajo con la función deseada.

**Para conceder acceso a las integraciones de Adobe I/O a espacios de trabajo y asignar funciones:**

1. Abra **[Adobe Admin Console](https://adminconsole.adobe.com)**.

1. Haga clic en la ficha **[!UICONTROL Products]** y, a continuación, seleccione el nombre del producto deseado.

   ![Elija el producto en Adobe Admin Console](/help/main/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. Seleccione el espacio de trabajo (Perfil de producto) deseado.

   ![Seleccione el perfil de producto](/help/main/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. Haga clic en la ficha **[!UICONTROL Integrations]**.

   ![Pestaña Integraciones](/help/main/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. (Condicional) Para agregar una nueva integración, haga clic en **[!UICONTROL Add Integration]**, seleccione la integración que desee y haga clic en **[!UICONTROL Save]**.

1. En la lista desplegable **[!UICONTROL Product Role]**, seleccione la función que desee para ese área de trabajo:

   | Función | Descripción |
   |--- |--- |
   | Aprobador | Puede crear, editar y activar o detener actividades. |
   | Editor | puede crear y editar actividades antes de que estén activas, pero no puede aprobar el lanzamiento de una actividad. |
   | Observador | Puede ver actividades, pero no puede crearlas o editarlas. |
   | Editor | Similar a la función Observador (puede ver actividades, pero no puede crearlas o editarlas). Sin embargo, la función Publicador tiene el permiso adicional de activar actividades. |
