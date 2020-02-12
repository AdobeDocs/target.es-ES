---
keywords: add user;manage user;user permissions
description: Puede añadir usuarios y gestionar sus permisos en Adobe Admin Console.
title: Usuarios
subtopic: Getting Started
topic: Standard
uuid: 9b311dd3-b8fa-483d-aedd-96761cfcd67e
translation-type: tm+mt
source-git-commit: 65a4fd0d05ad065c9291a83dc0b3066451f7373e

---


# Usuarios{#users}

Puede añadir usuarios y gestionar sus permisos en Adobe Admin Console.

>[!NOTE]
>
>La funcionalidad [!UICONTROL Propiedades] y [!UICONTROL Permisos] está disponible como parte de la [!DNL Target]solución Premium. No están disponibles en [!DNL Target] Standard sin una licencia de [!DNL Target] Premium.
>Puede comprobar si su organización dispone de una licencia Standard o Premium haciendo clic en el vínculo [!UICONTROL Configuración] en la parte superior de la interfaz de usuario de.[!DNL Target]
>
>**[!DNL Target]Clientes de Standard **: si ve la pestaña[!UICONTROL Usuarios]([!UICONTROL Configuración > Usuarios]), su organización dispone de una[!DNL Target]licencia de Standard. [!DNL Los clientes de Target Standard deben seguir las instrucciones descritas en este artículo para agregar usuarios y asignar permisos en[!DNL Adobe Admin Console].
>
>**[!DNL Target]Clientes de  Premium **: si ve la pestaña[!UICONTROL Propiedades]([!UICONTROL Configuración > Propiedades]), su organización dispone de una[!DNL Target]licencia Premium.[!DNL Target]Los clientes Premium deben seguir las instrucciones de[Permisos de usuario de Enterprise](/help/administrating-target/c-user-management/property-channel/property-channel.md)y[Configuración de permisos de Enterprise](/help/administrating-target/c-user-management/property-channel/properties-overview.md)para agregar usuarios y asignar permisos en[!DNL Adobe Admin Console].

Para administrar usuarios y permisos, consulte [Administrar productos y perfiles](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) en la Guía del usuario de Enterprise &amp; Teams.

Al comenzar a usar [!DNL Adobe Target], encontrará identificadores (terminados en Adobe.com) ya rellenados en su cuenta de [!DNL Adobe Experience Cloud]. Estos identificadores son para miembros de equipos de Adobe, para que puedan ayudarle con su nueva cuenta y a usar [!DNL Adobe Target] si es necesario. Para obtener ayuda, póngase en contacto con los equipos de Adobe de la forma habitual.

No verá el nombre del usuario nuevo en la página [!UICONTROL Usuarios] hasta que el usuario inicie sesión con la cuenta de Adobe Experience Cloud y luego inicie sesión en [!DNL Target Standard/Premium] haciendo clic en la tarjeta [!DNL Target].

De forma predeterminada, todos los usuarios de [!DNL Target] empiezan con permisos de observador.

Los usuarios administradores se identifican en la lista Usuarios. Póngase en contacto con uno de los usuarios administradores del sistema si necesita cambiar el nivel de acceso.

## Acceso a Adobe Admin Console {#access}

Para tareas realizadas en Adobe Admin Console, acceda a la consola siguiendo estos pasos:

1. Vaya a [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/) > inicie sesión con su Adobe ID si todavía no ha iniciado sesión.

   O

   Si ya inició sesión en Experience Cloud, vaya a [https://www.experiencecloud.adobe.com](https://experiencecloud.adobe.com), luego haga clic en el icono [!UICONTROL Aplicación] en la barra de navegación superior > haga clic en **[!UICONTROL Admin]** a la derecha.

1. (Condicional) Si tiene acceso a [!DNL Admin Console for Enterprise] para más de una organización, haga clic en el avatar del usuario en la esquina derecha o en la barra de navegación superior y, a continuación, seleccione la organización que quiera.

## Agregar usuarios {#add-users}

Toda la administración de usuarios debe realizarse en [!DNL Adobe Admin Console for Enterprise]. Sin embargo, todos los usuarios existentes en [!DNL Target] se migrarán de [!DNL Target] a [!DNL Admin Console for Enterprise].

1. [En Admin Console](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), haga clic en **[!UICONTROL Usuarios]** > **[!UICONTROL Usuarios]** para crear nuevos usuarios o editar los existentes.
1. Siga las instrucciones de [Administrar usuarios y grupos en Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) en la *Guía del usuario de Enterprise*.

## Crear grupos de usuarios {#user-groups}

Puede crear grupos de usuarios, como Desarrolladores, Analistas, Especialistas en marketing, Ejecutivos, etc., y luego asignar privilegios en varios productos y espacios de trabajo de Adobe. Asignar todos los privilegios apropiados en diferentes productos de Adobe a un nuevo miembro del equipo puede ser tan fácil como añadirlos a un grupo de usuarios específico.

1. [En Admin Console](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), haga clic en **[!UICONTROL Usuarios]** > Grupos **** de usuarios para crear nuevos grupos de usuarios o editar los existentes.
1. Siga las instrucciones de [Administrar usuarios y grupos en Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) en la *Guía del usuario de Enterprise*.

## Especificar roles y permisos {#roles-permissions}

Solo los administradores del sistema pueden establecer roles de usuario en [!DNL Target]. Por ejemplo, un usuario aprobador de Standard no puede cambiar un observador a un aprobador si no dispone también de permisos de administrador de Experience Cloud.

Los usuarios administradores del sistema deben agregar usuarios al sistema. Los usuarios no se agregan automáticamente. Reciben una invitación por correo electrónico desde Experience Cloud y deben confirmar su dirección de correo electrónico para que se registre su cuenta.

1. [En Admin Console](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), haga clic en **[!UICONTROL Productos]** y, a continuación, seleccione el nombre del producto deseado.

   ![Pestaña Productos](/help/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. Haga clic en el espacio de trabajo deseado (por ejemplo, Espacio de trabajo predeterminado).

   ![Espacio de trabajo predeterminado](/help/administrating-target/c-user-management/c-user-management/assets/default-workspace.png)

   La pestaña [!UICONTROL Usuarios] muestra todos los usuarios de un espacio de trabajo.

   ![usuarios de configuración](/help/administrating-target/c-user-management/c-user-management/assets/configuration_users-new.png)

1. Seleccione la función de permisos deseada (Aprobador, Editor u Observador) utilizando la lista desplegable de cada usuario en la columna [!UICONTROL Función del producto].

   ![Lista desplegable Función del producto](/help/administrating-target/c-user-management/c-user-management/assets/product-role.png)

   | Función | Descripción |
   |--- |--- |
   | Aprobador | Puede crear, editar y activar o detener actividades. |
   | Editor | puede crear y editar actividades antes de que estén activas, pero no puede aprobar el lanzamiento de una actividad. |
   | Observador | Puede ver actividades, pero no puede crearlas o editarlas. |

Para obtener más información, consulte [Administrar permisos y roles de producto en Admin Console](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html) en la *Guía del usuario de Enterprise*.

## Training video: How to Configure Target Workspaces ![Tutorial badge](/help/assets/tutorial.png)

Objetivos de aprendizaje:

* Acceso a Adobe Admin Console desde la interfaz de Adobe Target (tres métodos)
* Configuración de un espacio de trabajo en Adobe Admin Console
   * Agregación de usuarios a espacios de trabajo
   * Agregación de propiedades a espacios de trabajo
* Explicación de los espacios de trabajo predeterminados

>[!VIDEO](https://video.tv.adobe.com/v/19463/)
