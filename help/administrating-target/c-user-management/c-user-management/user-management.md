---
keywords: add user;manage user;user permissions
description: Puede añadir usuarios y gestionar sus permisos en Adobe Admin Console.
title: Usuarios
feature: user management
subtopic: Getting Started
topic: Standard
uuid: 9b311dd3-b8fa-483d-aedd-96761cfcd67e
translation-type: tm+mt
source-git-commit: 8d0faeb83e7fe854dcf99c89081fb656cf16c4c0
workflow-type: tm+mt
source-wordcount: '893'
ht-degree: 46%

---


# Usuarios{#users}

You can add users and manage their permissions in the [!DNL Adobe Admin Console].

>[!NOTE]
>
>La funcionalidad [!UICONTROL Propiedades] y [!UICONTROL Permisos] está disponible como parte de la [!DNL Target]solución Premium. No están disponibles en [!DNL Target] Standard sin una licencia de [!DNL Target] Premium.
>You can tell whether your organization has a Standard or Premium license by clicking the [!UICONTROL Administration] link at the top of the [!DNL Target] UI.
>
>* **[!DNL Target]Clientes** estándar: Si ve la ficha [!UICONTROL Usuarios] ([!UICONTROL Administración > Usuarios]) (y no la ficha **[!UICONTROL Propiedades]** ), su organización tiene una licencia [!DNL Target] estándar. [!DNL Target] Los clientes estándar deben seguir las instrucciones de este artículo para agregar usuarios y asignar permisos en el [!DNL Adobe Admin Console].
   >
   >
* **[!DNL Target]Clientes** Premium: Si ve la ficha [!UICONTROL Usuarios] y la ficha [!UICONTROL Propiedades] ([!UICONTROL Administración > Propiedades]), su organización dispone de una licencia [!DNL Target] Premium. [!DNL Target] Los clientes Premium deben seguir las instrucciones de [Permisos de usuario de Enterprise](/help/administrating-target/c-user-management/property-channel/property-channel.md) y [Configuración de permisos de Enterprise](/help/administrating-target/c-user-management/property-channel/properties-overview.md) para agregar usuarios y asignar permisos en [!DNL Adobe Admin Console].
>
>
Para obtener información detallada sobre cómo administrar usuarios y permisos, consulte [Administrar productos y perfiles](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) en la Guía *del usuario de* Enterprise &amp; Teams.

Al comenzar a usar [!DNL Adobe Target], encontrará identificadores (terminados en Adobe.com) ya rellenados en su cuenta de [!DNL Adobe Experience Cloud]. These IDs are for members of [!DNL Adobe] teams so that they can assist you with your new account and with your use of [!DNL Adobe Target], should you need help. Para obtener ayuda, póngase en contacto con los equipos de Adobe de la forma habitual.

You will not see the new user listed on the [!UICONTROL Users] page until the user logs in using his or her [!DNL Adobe Experience Cloud] account and then logs in to [!DNL Target Standard/Premium].

De forma predeterminada, todos los usuarios de [!DNL Target] empiezan con permisos de observador.

Admin users are identified in the [!UICONTROL Users] list. Póngase en contacto con uno de los usuarios administradores del sistema si necesita cambiar el nivel de acceso.

## Vista de información de usuario desde Destinatario

Puede realizar la vista de una lista de los usuarios actuales en el entorno de Destinatario, incluidas sus funciones por espacio de trabajo y las direcciones de correo electrónico directamente desde el Destinatario.

Para vista de la página Usuarios, haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Usuarios]**.

![Lista del usuario desde Destinatario](/help/administrating-target/c-user-management/c-user-management/assets/user-list-target.png)

>[!NOTE]
>
>Para administrar usuarios existentes o agregar usuarios nuevos, debe utilizar el [!UICONTROL Adobe Admin Console], tal como se explica a continuación.

## Acceso a Adobe Admin Console {#access}

Para tareas realizadas en Adobe Admin Console, acceda a la consola siguiendo estos pasos:

1. Desde dentro [!DNL Target], haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Usuarios]** > Administración de **[!UICONTROL usuarios]**.

   O

   Go to [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/), then sign in using your Adobe ID, if you have not already logged in.

1. (Condicional) Si tiene acceso a [!DNL Admin Console for Enterprise] para más de una organización, haga clic en el avatar del usuario en la esquina derecha o en la barra de navegación superior y, a continuación, seleccione la organización que quiera.

## Add users {#add-users}

Toda la administración de usuarios debe realizarse en [!DNL Adobe Admin Console for Enterprise]. Sin embargo, todos los usuarios existentes en [!DNL Target] se migrarán de [!DNL Target] a [!DNL Admin Console for Enterprise].

1. [En el Admin Console](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), haga clic en **[!UICONTROL Usuarios]** > **[!UICONTROL Usuarios]** para crear nuevos usuarios o editar los existentes.
1. Siga las instrucciones de [Administrar usuarios y grupos en Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) en la *Guía del usuario de Enterprise*.

## Create user groups {#user-groups}

Puede crear grupos de usuarios, como Desarrolladores, Analistas, Especialistas en marketing, Ejecutivos, etc., y luego asignar privilegios en varios productos y espacios de trabajo de Adobe. Asignar todos los privilegios apropiados en diferentes productos de Adobe a un nuevo miembro del equipo puede ser tan fácil como añadirlos a un grupo de usuarios específico.

1. [En el Admin Console](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), haga clic en **[!UICONTROL Usuarios]** > Grupos **** de usuarios para crear nuevos grupos de usuarios o editar los existentes.
1. Siga las instrucciones de [Administrar usuarios y grupos en Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) en la *Guía del usuario de Enterprise*.

## Especificar funciones y permisos {#roles-permissions}

Solo los administradores del sistema pueden establecer roles de usuario en [!DNL Target]. For example, a Standard approver user cannot change an observer to an approver, without also having [!DNL Experience Cloud] Admin rights.

Los usuarios administradores del sistema deben agregar usuarios al sistema. Los usuarios no se agregan automáticamente. They are invited by email from the [!DNL Experience Cloud] and must confirm their email addresses before their accounts are registered.

1. [En Admin Console](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), haga clic en **[!UICONTROL Productos]** y, a continuación, seleccione el nombre del producto deseado.

   ![Pestaña Productos](/help/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. Haga clic en el espacio de trabajo deseado (por ejemplo, Espacio de trabajo predeterminado).

   ![Espacio de trabajo predeterminado](/help/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

   La pestaña [!UICONTROL Usuarios] muestra todos los usuarios de un espacio de trabajo.

   ![usuarios de configuración](/help/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Seleccione la función de permisos deseada (Aprobador, Editor u Observador) utilizando la lista desplegable de cada usuario en la columna [!UICONTROL Función del producto].

   ![Lista desplegable Función del producto](/help/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | Función | Descripción |
   |--- |--- |
   | Aprobador | Puede crear, editar y activar o detener actividades. |
   | Editor | puede crear y editar actividades antes de que estén activas, pero no puede aprobar el lanzamiento de una actividad. |
   | Observador | Puede ver actividades, pero no puede crearlas o editarlas. |
   | Editor | Similar a la función Observador (puede vista de actividades, pero no puede crearlas o editarlas). Sin embargo, la función Editor tiene el permiso adicional para activar actividades. |

Para obtener más información, consulte [Administrar permisos y roles de producto en Admin Console](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html) en la *Guía del usuario de Enterprise*.

## Training video: How to Configure Target Workspaces ![Tutorial badge](/help/assets/tutorial.png)

Objetivos de aprendizaje:

* Acceso a Adobe Admin Console desde la interfaz de Adobe Target (tres métodos)
* Configuración de un espacio de trabajo en Adobe Admin Console
   * Agregación de usuarios a espacios de trabajo
   * Agregación de propiedades a espacios de trabajo
* Explicación de los espacios de trabajo predeterminados

>[!NOTE]
>
>La interfaz de usuario del menú [!DNL Target] Administración [!UICONTROL (anteriormente] Ajustes ) se ha rediseñado para proporcionar un rendimiento mejorado, reducir el tiempo de mantenimiento necesario al lanzar nuevas funciones y mejorar la experiencia del usuario en todo el producto. La información del siguiente vídeo es, en general, correcta; sin embargo, las opciones pueden estar en ubicaciones ligeramente diferentes. Los vídeos actualizados se publicarán pronto.

>[!VIDEO](https://video.tv.adobe.com/v/19463/)
