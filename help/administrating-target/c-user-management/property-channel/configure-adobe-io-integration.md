---
description: Información sobre la concesión de integraciones de Adobe I/O a todos los espacios de trabajo con la función deseada.
keywords: integración; roles; permisos de usuario; admin console
seo-description: Información sobre la concesión de integraciones de Adobe I/O a todos los espacios de trabajo con la función deseada en Adobe Target
seo-title: Conceda acceso a las integraciones de Adobe I/O a espacios de trabajo y asigne funciones en Adobe Target
solution: Target
subtopic: Primeros pasos
title: Otorgar acceso a las integraciones de Adobe I/O a espacios de trabajo y asignar funciones
translation-type: tm+mt
source-git-commit: 13ad42da73dd3fcbf4e07be1de646e0eac8c991e

---


# ![PREMIUM](/help/assets/premium.png) Concesión de integraciones de Adobe I/O a espacios de trabajo y asignación de funciones

[!UICONTROL Los permisos de Enterprise] permiten [!DNL Target] a los clientes utilizar una sola organización, pero dividirlo en espacios de trabajo para distintos equipos o flujos de trabajo.

>[!NOTE]
>
>La funcionalidad Propiedades y Permisos está disponible como parte de la solución [Target Premium](/help/c-intro/intro.md#premium). No están disponibles en [!DNL Target Standard] sin una licencia de [!DNL Target Premium].

La función [!UICONTROL Permisos] de Enterprise facilita la escala efectiva de los programas de optimización entre los equipos. Aunque la función estaba disponible en [!DNL Target] la interfaz de usuario, las API de administración no tenían la compatibilidad correspondiente hasta principios de 2019. En la versión [!DNL Target] de febrero de 2019, Adobe ha actualizado las API de administración para que pueda utilizar la cuenta de integración para acceder a todos los espacios de trabajo creados en su organización. Por lo tanto, si bien las API de administración estaban restringidas a solo el espacio de trabajo predeterminado, la actualización de febrero de 2019 otorgaba acceso a todos los espacios de trabajo con [!UICONTROL acceso de aprobador] .

Con la versión [!DNL Target] de septiembre de 2019, los permisos [!DNL Target][!UICONTROL de Enterprise] proporcionan a los clientes los siguientes controles de acceso:

* Puede elegir los espacios de trabajo a los que se puede aplicar la integración
* Puede aplicar una función a la integración de Adobe I/O: [!UICONTROL Aprobador], [!UICONTROL Editor]o [!UICONTROL Observador].

Esta actualización admite los siguientes casos de uso:

* Conceda acceso a la integración de Adobe I/O a todos los espacios de trabajo con [!UICONTROL la] función Observador con fines de creación de informes sin tener derechos para crear o editar recursos.
* Conceda a la integración de Adobe I/O el acceso para seleccionar espacios de trabajo con la función apropiada para permitir que un equipo central realice cambios controlados por API en solo unos pocos espacios de trabajo.
* Permita que cada equipo propietario de su espacio de trabajo tenga su propia integración siempre que el equipo esté listo para explorar las API y elija la función correspondiente.
* Combina y coincide con cualquiera de los escenarios anteriores.

**Acción necesaria**: Los clientes que actualmente aprovechan las API para operaciones de CRUD en recursos (actividades, audiencias, ofertas e informes) en todos los espacios de trabajo deben conceder su acceso de integración de Adobe I/O a todos los espacios de trabajo con la función deseada según su caso de uso. Para ello, seleccione cada perfil [!DNL Target][!UICONTROL de producto] en la [!DNL Adobe Admin Console] y agregue las integraciones en la ficha [!UICONTROL Integración] . Antes de la versión de septiembre, todas las integraciones operaban usando el acceso [!UICONTROL de aprobador] , independientemente de la opción que se realice en la [!UICONTROL lista desplegable Función] del producto. Ahora puede elegir la función que desee.

>[!NOTE]
>
>Si no se realiza esta acción, después de [!DNL Target] la versión de septiembre de 2019, los controles de acceso se activarán y observará el acceso a solo el espacio de trabajo predeterminado, si está configurado actualmente. No hay reacciones adversas para configurar integraciones por adelantado. Cuanto antes realice este cambio, mejor. Según el número de espacios de trabajo de su organización, este proceso solo toma unos pocos clics para agregar una integración existente en espacios de trabajo con la función deseada.

**Para otorgar acceso a las integraciones de Adobe I/O a espacios de trabajo y asignar funciones:**

1. Abra **[Adobe Admin Console](https://adminconsole.adobe.com)**.

1. Click the **[!UICONTROL Products]** tab, then select the name of the desired product.

   ![Elija el producto en Adobe Admin Console](/help/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. Seleccione el espacio de trabajo deseado (perfil de producto).

   ![Seleccione el perfil de producto](/help/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. Click the **[!UICONTROL Integrations]** tab.

   ![Ficha Integraciones](/help/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. (Condicional) Para agregar una nueva integración, haga clic **[!UICONTROL en Agregar integración]**, seleccione la integración que desee y haga clic **[!UICONTROL en Guardar]**.

1. En la lista **[!UICONTROL desplegable Función]** del producto, seleccione la función que desee para ese espacio de trabajo:

   * [!UICONTROL Aprobador]
   * [!UICONTROL Editor]
   * [!UICONTROL Observador]
   ![Elija la función Perfil de producto](/help/administrating-target/c-user-management/property-channel/assets/product-profile-role.png)
