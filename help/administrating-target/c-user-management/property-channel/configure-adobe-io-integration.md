---
description: Información sobre la concesión de acceso a integraciones de Adobe I/O a todos los espacios de trabajo con la función deseada.
keywords: integración;funciones;permisos de usuario;consola de administración
seo-description: Información sobre la concesión de acceso a integraciones de Adobe I/O existentes a todos los espacios de trabajo con la función deseada en Adobe Target
seo-title: Conceder a las integraciones de Adobe I/O acceso a espacios de trabajo y asignar funciones en Adobe Target
solution: Target
subtopic: Primeros pasos
title: Conceder a las integraciones de Adobe I/O acceso a espacios de trabajo y asignar funciones
translation-type: tm+mt
source-git-commit: 13ad42da73dd3fcbf4e07be1de646e0eac8c991e

---


# ![PREMIUM](/help/assets/premium.png) otorga a las integraciones de E/S de Adobe acceso a espacios de trabajo y asignación de funciones

[!UICONTROL Los permisos] de Enterprise permiten a [!DNL Target] los clientes utilizar una sola organización, pero dividirla en espacios de trabajo para sus distintos equipos o flujos de trabajo.

>[!NOTE]
>
>La funcionalidad Propiedades y Permisos está disponible como parte de la solución [Target Premium](/help/c-intro/intro.md#premium). No están disponibles en [!DNL Target Standard] sin una licencia de [!DNL Target Premium].

La función Permisos [!UICONTROL de] empresa facilita la escalada efectiva de los programas de optimización entre equipos. Aunque la función estaba disponible en la interfaz de usuario, las API de administración carecían de la compatibilidad correspondiente hasta principios de 2019. [!DNL Target] En la versión [!DNL Target] de febrero de 2019, Adobe actualizó las API de administración para que pueda utilizar la cuenta de integración para acceder a todos los espacios de trabajo creados en su organización. Por lo tanto, aunque antes las API de administración estaban restringidas solo al espacio de trabajo predeterminado, la actualización de febrero de 2019 otorgaba acceso a todos los espacios de trabajo con acceso de [!UICONTROL aprobador] .

Con la versión de [!DNL Target] septiembre de 2019, Permisos [!DNL Target] de  empresa proporciona a los clientes los siguientes controles de acceso:

* Puede elegir los espacios de trabajo a los que se puede aplicar la integración
* Puede aplicar una función a la integración de Adobe I/O: [!UICONTROL Aprobador], [!UICONTROL Editor]u [!UICONTROL Observador].

Esta actualización admite los siguientes casos de uso:

* Otorgue a la integración de Adobe I/O acceso a todos los espacios de trabajo con la función de [!UICONTROL observador] para la realización de informes sin derechos para crear o editar recursos.
* Otorgue a la integración de Adobe I/O el acceso para seleccionar espacios de trabajo con la función adecuada para permitir que un equipo central realice cambios impulsados por API en sólo unos pocos espacios de trabajo.
* Permita que cada equipo propietario de su espacio de trabajo tenga su propia integración cuando el equipo esté listo para explorar las API y elija la función en consecuencia.
* Mezclar y hacer coincidir cualquiera de los escenarios anteriores.

**Acción necesaria**: Los clientes que actualmente utilizan API para operaciones de CRUD en recursos (actividades, audiencias, ofertas e informes) en todos los espacios de trabajo deben otorgar a su integración de Adobe I/O existente acceso a todos los espacios de trabajo con la función deseada según el caso de uso. Para ello, seleccione cada perfil [!DNL Target] de [!UICONTROL producto] en la ficha [!DNL Adobe Admin Console] y agregue las integraciones en la ficha [!UICONTROL Integración] . Antes de la versión de septiembre, todas las integraciones funcionaban mediante el acceso de [!UICONTROL aprobador] , independientemente de la opción que se haya seleccionado en la lista desplegable Función [!UICONTROL del] producto. Ahora puede elegir la función deseada.

>[!NOTE]
>
>Si no se realiza esta acción, después de la versión de [!DNL Target] septiembre de 2019, los controles de acceso se activarán y observará el acceso sólo al espacio de trabajo predeterminado si así es como está configurado actualmente. No hay ninguna reacción adversa a la hora de configurar integraciones por adelantado. Cuanto antes hagas este cambio, mejor. En función del número de espacios de trabajo de la organización, este proceso requiere sólo unos pocos clics para agregar una integración existente a espacios de trabajo con la función deseada.

**Para otorgar a las integraciones de Adobe I/O acceso a espacios de trabajo y asignar funciones:**

1. Abra **[Adobe Admin Console](https://adminconsole.adobe.com)**.

1. Click the **[!UICONTROL Products]** tab, then select the name of the desired product.

   ![Elija un producto en Adobe Admin Console](/help/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. Seleccione el espacio de trabajo deseado (perfil de producto).

   ![Seleccione el perfil de producto](/help/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. Click the **[!UICONTROL Integrations]** tab.

   ![Ficha Integraciones](/help/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. (Condicional) Para agregar una nueva integración, haga clic en **[!UICONTROL Agregar integración]**, seleccione la integración que desee y haga clic en **[!UICONTROL Guardar]**.

1. En la lista desplegable Función **** del producto, seleccione la función que desee para ese espacio de trabajo:

   * [!UICONTROL Aprobador]
   * [!UICONTROL Editor]
   * [!UICONTROL Observador]
   ![Elegir función de perfil de producto](/help/administrating-target/c-user-management/property-channel/assets/product-profile-role.png)
