---
keywords: integration;roles;user permissions;admin console
description: Otorgar a las integraciones de Adobe I/O existentes acceso a todos los espacios de trabajo con la función deseada en Adobe Target
title: Conceder acceso a las integraciones de Adobe I/O a espacios de trabajo y asigne funciones en Adobe Target
feature: Administration & Configuration
translation-type: tm+mt
source-git-commit: 1c5fd1062da5f90f24720fc3deb67f7f3b05aee9
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 85%

---


# ![PREMIUM](/help/assets/premium.png) Concesión de acceso a integraciones de Adobe I/O a espacios de trabajo y asignación de funciones

Los [!UICONTROL Permisos de Enterprise] permiten [!DNL Target] a los clientes utilizar una sola organización, pero dividirla en espacios de trabajo para distintos equipos o flujos de trabajo.

>[!NOTE]
>
>La funcionalidad Propiedades y Permisos está disponible como parte de la solución [Target Premium](/help/c-intro/intro.md#premium). No están disponibles en [!DNL Target Standard] sin una licencia de [!DNL Target Premium].

La funcionalidad de [!UICONTROL Permisos de Enterprise] facilita la escala efectiva de los programas de optimización entre los equipos. Aunque la funcionalidad estaba disponible en la interfaz de usuario de [!DNL Target], las API de administrador no tenían la compatibilidad correspondiente hasta principios de 2019. En la versión de febrero de 2019 de [!DNL Target], Adobe actualizó las API de administrador para que se pueda utilizar la cuenta de integración para acceder a todos los espacios de trabajo creados en su organización. Por tanto, las API de administrador estaban restringidas únicamente al espacio de trabajo predeterminado, pero dicha actualización de febrero de 2019 ha permitido el acceso a todos los espacios de trabajo con acceso de [!UICONTROL Aprobador].

Con la versión de [!DNL Target] septiembre de 2019, [!DNL Target] [!UICONTROL Enterprise Permissions] proporciona a los clientes los siguientes controles de acceso:

* Puede elegir los espacios de trabajo a los que se puede aplicar la integración
* Puede aplicar una función a la integración de Adobe I/O: [!UICONTROL Aprobador], [!UICONTROL Editor] u [!UICONTROL Observador].

Esta actualización es compatible con los siguientes ejemplos prácticos:

* Conceder acceso a la integración de Adobe I/O a todos los espacios de trabajo con la función [!UICONTROL Observador] con fines de creación de informes sin tener derechos para crear o editar recursos.
* Conceder acceso a la integración de Adobe I/O para seleccionar espacios de trabajo con la función apropiada para permitir que un equipo central realice cambios controlados por API solo en unos pocos espacios de trabajo.
* Permitir que cada equipo propietario de su espacio de trabajo tenga su propia integración siempre que el equipo esté listo para explorar las API y elija la función correspondiente.
* Cualquier combinación de los escenarios anteriores.

**Acción necesaria**: Los clientes que actualmente aprovechan las API para operaciones de CRUD en recursos (actividades, audiencias, ofertas e informes) en todos los espacios de trabajo deben conceder su acceso de integración de Adobe I/O a todos los espacios de trabajo con la función deseada según su uso. Para ello, seleccione cada [!DNL Target] [!UICONTROL Perfil de producto] en [!DNL Adobe Admin Console] y agregue las integraciones en la pestaña [!UICONTROL Integración]. Antes de la versión de septiembre, todas las integraciones operaban con el acceso de [!UICONTROL Aprobador], independientemente de la opción que se realice en la lista desplegable [!UICONTROL Función] del producto. Ahora puede elegir la función que desee.

>[!NOTE]
>
>Si no se realiza esta acción, después de la versión de septiembre de 2019 de [!DNL Target], los controles de acceso se activarán y tendrá acceso solo al espacio de trabajo predeterminado (si es su configuración actual). Se pueden configurar integraciones por adelantado sin problema. Cuanto antes realice este cambio, mejor. En función del número de espacios de trabajo de la organización, este proceso requiere sólo unos pocos clics para agregar una integración existente a espacios de trabajo con la función deseada.

**Para conceder acceso a las integraciones de Adobe I/O a espacios de trabajo y asignar funciones:**

1. Abra el **[Adobe Admin Console](https://adminconsole.adobe.com)**.

1. Haga clic en la pestaña **[!UICONTROL Productos]** y luego seleccione el nombre del producto deseado.

   ![Elija el producto en Adobe Admin Console](/help/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. Seleccione el espacio de trabajo (Perfil de producto) deseado.

   ![Seleccione el perfil de producto](/help/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. Haga clic en la pestaña **[!UICONTROL Integraciones]**.

   ![Pestaña Integraciones](/help/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. (Condicional) Para agregar una nueva integración, haga clic en **[!UICONTROL Agregar integración]**, seleccione la integración que desee y haga clic en **[!UICONTROL Guardar]**.

1. En la lista desplegable **[!UICONTROL Función del producto]**, seleccione la función que desee para ese espacio de trabajo:

   | Función | Descripción |
   |--- |--- |
   | Aprobador | Puede crear, editar y activar o detener actividades. |
   | Editor | puede crear y editar actividades antes de que estén activas, pero no puede aprobar el lanzamiento de una actividad. |
   | Observador | Puede ver actividades, pero no puede crearlas o editarlas. |
   | Editor | Similar a la función Observador (puede vista de actividades, pero no puede crearlas o editarlas). Sin embargo, la función Editor tiene el permiso adicional para activar actividades. |
