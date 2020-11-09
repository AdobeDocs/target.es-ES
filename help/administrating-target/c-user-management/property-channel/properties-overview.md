---
keywords: add user;project;user group;properties;workspace;manage property;property;at_property;roles;permissions
description: Información sobre las tareas necesarias para añadir usuarios a la implementación de Adobe Target; crear espacios de trabajo, grupos de usuarios y propiedades; actualizar la implementación de Target para incluir el parámetro at_property; y especificar funciones y permisos.
title: Configuración de permisos de Enterprise
feature: user management
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '1474'
ht-degree: 68%

---


# ![PREMIUM](/help/assets/premium.png) Configuración de permisos de Enterprise{#configure-enterprise-permissions}

Information about the tasks required to add users to your [!DNL Target] implementation; create workspaces, user groups, and properties; update your [!DNL Target] implementation to include the `at_property` parameter; and specify roles and permissions.

>[!NOTE]
>
>La funcionalidad Propiedades y Permisos está disponible como parte de la solución [Target Premium](/help/c-intro/intro.md#premium). No están disponibles en [!DNL Target Standard] sin una licencia de [!DNL Target Premium].

La siguiente tabla enumera las tareas que debe realizar para crear propiedades y asignar funciones de usuario y permisos. Consulte las secciones siguientes para obtener más información sobre cada tarea.

| Tarea | Realizado en |
|--- |--- |
| 1. Agregar usuarios (Opcional) | [!DNL Adobe Admin Console for Enterprise] |
| 2. Crear un espacio de trabajo (perfil de producto) | [!DNL Adobe Admin Console for Enterprise] |
| 3. Crear grupos de usuarios (Opcional) | [!DNL Adobe Admin Console for Enterprise] |
| 4. Crear propiedades | [!DNL Target] IU |
| 5. Actualizar la implementación para incluir el parámetro.`at_property` | [!DNL Target] Interfaz de usuario, funciones de at.js, [!DNL Adobe Launch] o [!DNL Dynamic Tag Management] |
| 6. Especificar roles y permisos | [!DNL Adobe Admin Console for Enterprise] |

For those tasks performed in the [!DNL Adobe Admin Console for Enterprise], access the console by following these steps:

1. En Adobe Target, haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Propiedades]** > **[!UICONTROL Asignar propiedades a espacios de trabajo]**.

   O

   Go to [https://adminconsole.adobe.com/enterprise](https://adminconsole.adobe.com/enterprise/) > sign in using your Adobe ID, if you have not already logged in.


1. (Condicional) Si tiene acceso a [!DNL Admin Console for Enterprise] para más de una organización, haga clic en el avatar del usuario en la esquina derecha o en la barra de navegación superior y, a continuación, seleccione la organización que quiera.

## Paso 1. Add users (Optional) {#section_A92AF0F921B743FEB9E9033433BD816A}

Cuando comience a utilizar la nueva funcionalidad [!UICONTROL Propiedades], toda la administración de usuarios debe realizarse en [!DNL Adobe Admin Console for Enterprise]. Sin embargo, todos los usuarios existentes en [!DNL Target] se migrarán de [!DNL Target] a [!DNL Admin Console for Enterprise].

1. [En Admin Console](/help/administrating-target/c-user-management/property-channel/properties-overview.md#section_79796E0227D048F59BAE0AB02E544EBE), haga clic en la pestaña **[!UICONTROL Usuarios]** en la parte superior de la página > **[!UICONTROL Agregar usuarios]** para crear usuarios nuevos o para editar los existentes.
1. Siga las instrucciones de [Administrar usuarios y grupos en Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) en la *Guía del usuario de Enterprise*.

## Paso 2: Create a workspace (product profile) {#section_B82EB409B67C4D9D9D20CE30E48DB1DC}

Un espacio de trabajo (perfil de productos) permite a una organización asignar un conjunto específico de usuarios a un conjunto específico de propiedades. En muchos aspectos, un espacio de trabajo es parecido a un grupo de informes en [!DNL Analytics].

Organizations can begin taking advantage of Enterprise permissions functionality by creating new workspaces within [!DNL Admin Console], assigning [!DNL Target] properties to these workspaces, and moving users from the &quot;Default Workspace&quot; configuration to these newer, limited-access workspaces.

Los clientes pueden utilizar estos espacios de trabajo para asignar a los equipos distintos accesos según su región, unidad de negocio, sección de sitio o cualquier otro método que se quiera.

Los usuarios pueden formar parte de varios espacios de trabajo y pueden incluso tener diferentes roles en cada uno de ellos.

1. En [!DNL Admin Console], haga clic en **[!UICONTROL Productos]** y, a continuación, seleccione el nombre del producto deseado.

   ![workspace](/help/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. Cree el espacio de trabajo (perfil de producto) deseado:

   * **Acceso predeterminado:** todas las actividades existentes se combinarán en un solo proyecto llamado “Acceso predeterminado”. Esto no tendrá ningún impacto en los clientes. Todas las funciones de usuario y las funcionalidades se mantendrán exactamente igual que se encontraban antes este cambio.

      Todas las actividades creadas mediante [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] y [!DNL Target Classic] también formarán parte del espacio de trabajo “Acceso predeterminado”. No está permitido mover proyectos de “Acceso predeterminado” a otro proyecto.

   * **Nuevos espacios de trabajo (perfiles de producto):** puede comenzar a sacar provecho de la nueva funcionalidad de permisos haciendo lo siguiente:

      * Creación de nuevos espacios de trabajo en [!DNL Admin Console for Enterprise].
      * Asignar propiedades de Target a los espacios de trabajo.

   Puede utilizar estos espacios de trabajo para acceder a los diferentes equipos por región, unidad de negocio, sección del sitio o mediante cualquier otro método a su elección. Los usuarios pueden formar parte de varios espacios de trabajo y pueden tener diferentes funciones en cada uno de ellos.

1. Siga las instrucciones de [Creación y administración de configuraciones de producto](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html) en la *Guía del usuario de Enterprise*.

>[!NOTE]
>Consulte el siguiente vídeo de formación para obtener más información sobre cómo configurar espacios de trabajo.

### Obtain your workspace ID {#workspace-id}

Tendrá que pasar el ID de espacio de trabajo para aprovechar los permisos de Enterprise en [las API de Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md).

1. En [Adobe Admin Console](https://adminconsole.adobe.com), haga clic en la ficha [!UICONTROL Productos] y, a continuación, haga clic en el producto en el menú izquierdo para mostrar la lista PLC (espacio de trabajo).
1. Haga clic en el PLC (espacio de trabajo) deseado y luego busque el ID de «perfiles» en la URL, como se muestra a continuación.

   ![ID de trabajo](/help/administrating-target/c-user-management/property-channel/assets/workspace-id-newest.png)

## Paso 3. Create user groups (Optional) {#section_5F5CB9AA7A9F4D26953E22016DA59605}

Puede crear grupos de usuarios, como Desarrolladores, Analistas, Especialistas en marketing, Ejecutivos, etc., y luego asignar privilegios en varios productos y espacios de trabajo de Adobe. Asignar todos los privilegios apropiados en diferentes productos de Adobe a un nuevo miembro del equipo puede ser tan fácil como añadirlos a un grupo de usuarios específico.

1. En Admin Console, haga clic en la pestaña **[!UICONTROL Usuarios]** en la parte superior de la página > **[!UICONTROL Grupos de usuarios]** para crear grupos de usuarios nuevos o para editar los grupos existentes.
1. Siga las instrucciones de [Administrar usuarios y grupos de una configuración de producto](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html) en la *Guía del usuario de Enterprise*.

## Paso 4. Crear propiedades {#section_E8F2C92BE0F4466AB87604059C9CF3FD}

Las propiedades se habilitan agregando un par nombre/valor específico como parámetro con cualquier llamada (llamada de Destinatario, llamada de API, etc.) a Target.

Las propiedades pertenecen a canales específicos (web, móvil, correo electrónico y API/otros).

**Sugerencia**: consulte el vídeo de formación siguiente para obtener más información sobre la creación de propiedades.

1. In [!DNL Target], click **[!UICONTROL Administration]** > **[!UICONTROL Properties]** to display the [!UICONTROL Properties] list.
1. Haga clic en **Crear propiedad**.

   ![Nueva propiedad, cuadro de diálogo](/help/administrating-target/c-user-management/property-channel/assets/new_property1.png)

   Rellene los campos:

   * **Nombre de propiedad (obligatorio):** Especifique un nombre descriptivo para la propiedad.
   * **Descripción:** especifique una descripción opcional para la propiedad.
   * **Canal:** Seleccione el canal deseado para esta propiedad: web, aplicación móvil, correo electrónico o API/otro (por ejemplo, un cuadro en la parte superior o una consola PlayStation).

1. Haga clic en **[!UICONTROL Copiar]** para copiar el código en el portapapeles que utilizará mientras realiza los pasos de la [5: Actualice su implementación para incluir el parámetro](/help/administrating-target/c-user-management/property-channel/properties-overview.md#section_9B17A59807A94712BE642942442EBBC8)at_property.
1. Haga clic en **[!UICONTROL Guardar]** cuando termine.

>[!NOTE]
>Consulte el vídeo de formación siguiente para obtener más información sobre la creación de propiedades.

## Step 5: Update your implementation to include the at_property parameter {#section_9B17A59807A94712BE642942442EBBC8}

To use the [!DNL Target] user-permissions functionality, you must add the `at_property` parameter to any call that is hitting [!DNL Target] (Target call, api call, etc.).

**Para obtener el código del parámetro `at_property`:**

1. (Condicional) Utilice el código de implementación que ha generado y guardado en el Portapapeles mientras realiza los pasos de [4. Crear propiedades](/help/administrating-target/c-user-management/property-channel/properties-overview.md#section_E8F2C92BE0F4466AB87604059C9CF3FD) y continuar con el paso 2.

   O

   In [!DNL Target], click **[!UICONTROL Administration]** > **[!UICONTROL Properties]** to display the [!UICONTROL Properties] list.

   1. Pase el puntero del ratón por la columna [!UICONTROL Última actualización] de la propiedad deseada para mostrar y hacer clic en el icono [!UICONTROL Código].

      ![Código de pase de propiedad](/help/administrating-target/c-user-management/property-channel/assets/code_property_new.png)

   1. Haga clic con el botón derecho sobre el código de implementación destacado para copiarlo en el Portapapeles.

      ![Código de propiedad](/help/administrating-target/c-user-management/property-channel/assets/code_property_2_new.png)

1. Update your [!DNL Target] implementation with the implementation code obtained in the previous step.

   Existen varias formas de actualizar la implementación de [!DNL Target]. Por ejemplo, puede usar los siguientes métodos para páginas web:

   * **Mediante un “Parámetro global” en [!DNL Adobe Launch]:**

      For more information, see [Add Global Target Params](https://docs.adobelaunch.com/extension-reference/web/adobe-target-extension#add-global-mbox-params) in the *Adobe Experience Platform Launch* documentation.

   * **Mediante un “Parámetro global” en [!DNL Dynamic Tag Management]:**

      ![](assets/property_token_2.png)

      Para obtener más información, consulte [Parámetros globales: Adobe Target](https://experienceleague.adobe.com/docs/dtm/using/tools-reference/target.html#global-parameters---adobe-target) en la *documentación sobre Dynamic Tag Management*.

   * **Mediante la función targetPageParams():** Coloque el siguiente código en las `<head>` etiquetas, encima de la referencia a at.js o mbox.js.

      ![](assets/property_token_1.png)

      Para obtener más información sobre la realización de esto con at.js, consulte [targetPageParams()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md).

   * **Mediante la función mboxCreate():**

      ![](assets/property_token_3.png)

      Para obtener más información sobre cómo realizar esto con at.js, consulte  [targetPageParams()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md) y  [mboxCreate(mbox,params)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxcreate-atjs.md).

## Step 6: Specify roles and permissions {#section_8C425E43E5DD4111BBFC734A2B7ABC80}

1. En Admin Console, haga clic en **[!UICONTROL Productos]** y, a continuación, seleccione el nombre del producto deseado.

   ![Workspace](/help/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. Haga clic en el nombre del perfil deseado (por ejemplo, Espacio de trabajo predeterminado).

   ![Espacio de trabajo predeterminado](/help/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

1. Haga clic en **[!UICONTROL Usuarios]**.

   La pestaña [!UICONTROL Usuarios] muestra todos los usuarios de un espacio de trabajo.

   ![usuarios de configuración](/help/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Select the desired permissions role (Approver, Editor, Observer, or Publisher) by using the drop-down list for each user in the [!UICONTROL Product Role] column.

   ![Lista desplegable Función del producto](/help/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | Función | Descripción |
   |--- |--- |
   | Aprobador | Puede crear, editar y activar o detener actividades. |
   | Editor | puede crear y editar actividades antes de que estén activas, pero no puede aprobar el lanzamiento de una actividad. |
   | Observador | Puede ver actividades, pero no puede crearlas o editarlas. |
   | Editor | Similar a la función Observador (puede vista de actividades, pero no puede crearlas o editarlas). Sin embargo, la función Editor tiene el permiso adicional para activar actividades. |

   Para obtener más información, consulte [Administrar permisos y roles de producto en Admin Console](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html) en la *Guía del usuario de Enterprise*.

## Vídeos de formación

Los siguientes vídeos contienen más información sobre los conceptos mencionados en este artículo.

>[!NOTE]
>
>La interfaz de usuario del menú [!DNL Target] Administración [!UICONTROL (anteriormente] Ajustes ) se ha rediseñado para proporcionar un rendimiento mejorado, reducir el tiempo de mantenimiento necesario al lanzar nuevas funciones y mejorar la experiencia del usuario en todo el producto. La información de los siguientes vídeos es generalmente correcta; sin embargo, las opciones pueden estar en ubicaciones ligeramente diferentes. Los vídeos actualizados se publicarán pronto.

### Insignia de ![tutorial Cómo configurar espacios de trabajo de Destinatario (6:55)](/help/assets/tutorial.png)

Este vídeo explica cómo se crean espacios de trabajo.

* Acceso a Adobe Admin Console desde la interfaz de Adobe Target (3 métodos)
* Configuración de un espacio de trabajo en Adobe Admin Console

   * Agregación de usuarios a espacios de trabajo
   * Agregación de propiedades a espacios de trabajo

* Explicación de los espacios de trabajo predeterminados

>[!VIDEO](https://video.tv.adobe.com/v/19463/)

### How to Create Properties in Adobe Target (3:05) ![Tutorial badge](/help/assets/tutorial.png)

* Cómo crear una propiedad en la interfaz de.[!DNL Adobe Target]
* Cómo se genera un token de propiedad para incluirlo en su implementación de propiedad
* Familiarícese con los tres métodos de implementación:

   * Web
   * Aplicación móvil
   * Correo electrónico, cuadro superior fijo o llamadas API

>[!VIDEO](https://video.tv.adobe.com/v/18990/)
