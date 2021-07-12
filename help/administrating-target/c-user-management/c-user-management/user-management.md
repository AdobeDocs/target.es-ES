---
keywords: agregar usuario;administrar usuario;permisos de usuario
description: Aprenda a utilizar Adobe Admin Console para administrar usuarios y sus permisos y derechos en Adobe Target.
title: ¿Cómo puedo agregar usuarios y administrar permisos?
feature: Administración y configuración
role: Admin
exl-id: 535c28c7-179d-4edc-b140-880b9dfe1d59
source-git-commit: be7b5478006af231aae2b78e4a8c0066e3cb4a5b
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 46%

---

# Usuarios

Agregue usuarios y administre sus permisos en [!DNL Adobe Admin Console].

>[!NOTE]
>
>La funcionalidad [!UICONTROL Propiedades] y [!UICONTROL Permisos] está disponible como parte de la [!DNL Target]solución Premium. No están disponibles en [!DNL Target] Standard sin una licencia de [!DNL Target] Premium.
>Puede comprobar si su organización dispone de una licencia Standard o Premium haciendo clic en el enlace [!UICONTROL Administration] en la parte superior de la [!DNL Target] interfaz de usuario.
>
>* **[!DNL Target]Clientes** estándar: Si ve la   pestaña Userstab ([!UICONTROL Administration > Users]) (y no la  **** pestaña Properties), su organización tiene una licencia  [!DNL Target] Standard. [!DNL Target] Los clientes estándar deben seguir las instrucciones de este artículo para agregar usuarios y asignar permisos en  [!DNL Adobe Admin Console].
   >
   >
* **[!DNL Target]Clientes** Premium: Si ve la   pestaña Userstab y la   pestaña Properties ([!UICONTROL Administration > Properties]), su organización dispone de una licencia  [!DNL Target] Premium. [!DNL Target] Los clientes Premium deben seguir las instrucciones de [Permisos de usuario de Enterprise](/help/administrating-target/c-user-management/property-channel/property-channel.md) y [Configuración de permisos de Enterprise](/help/administrating-target/c-user-management/property-channel/properties-overview.md) para agregar usuarios y asignar permisos en [!DNL Adobe Admin Console].
>
>
Para obtener información detallada sobre cómo administrar usuarios y permisos, consulte [Administrar productos y perfiles](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) en la *Guía del usuario de Enterprise y equipos*.

Al comenzar a usar [!DNL Adobe Target], encontrará identificadores (terminados en Adobe.com) ya rellenados en su cuenta de [!DNL Adobe Experience Cloud]. Estos ID son para miembros de equipos [!DNL Adobe] para que puedan ayudarle con su nueva cuenta y a usar [!DNL Adobe Target] si necesita ayuda. Para obtener ayuda, póngase en contacto con los equipos de Adobe de la forma habitual.

No verá el nombre del usuario nuevo en la página [!UICONTROL Usuarios] hasta que el usuario inicie sesión con la cuenta [!DNL Adobe Experience Cloud] y luego inicie sesión en [!DNL Target Standard/Premium].

De forma predeterminada, todos los usuarios de [!DNL Target] empiezan con permisos de observador.

Los usuarios administradores se identifican en la lista [!UICONTROL Usuarios]. Póngase en contacto con uno de los usuarios administradores del sistema si necesita que su nivel de acceso cambie.

## Ver información de usuario desde Target

Puede ver una lista de los usuarios actuales en el entorno de Target, incluidas sus funciones por espacio de trabajo y las direcciones de correo electrónico directamente desde Target.

Para ver la página Usuarios, haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Usuarios]**.

![Lista de usuarios desde Target](/help/administrating-target/c-user-management/c-user-management/assets/user-list-target.png)

>[!NOTE]
>
>Para administrar un usuario existente o agregar nuevos usuarios, debe utilizar [!UICONTROL Adobe Admin Console], tal como se explica a continuación.

## Acceso a Adobe Admin Console {#access}

Para tareas realizadas en Adobe Admin Console, acceda a la consola siguiendo estos pasos:

1. Desde [!DNL Target], haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Usuarios]** > **[!UICONTROL Administración de usuarios]**.

   O

   Vaya a [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/) e inicie sesión con su Adobe ID si todavía no lo ha hecho.

1. (Condicional) Si tiene acceso a [!DNL Admin Console for Enterprise] para más de una organización, haga clic en el avatar del usuario en la esquina derecha o en la barra de navegación superior y, a continuación, seleccione la organización que quiera.

## Agregar usuarios {#add-users}

Toda la administración de usuarios debe realizarse en [!DNL Adobe Admin Console for Enterprise]. Sin embargo, todos los usuarios existentes en [!DNL Target] se migrarán de [!DNL Target] a [!DNL Admin Console for Enterprise].

1. [En el Admin Console](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), haga clic en  **[!UICONTROL Usuarios]**  >  **** Usuarios para crear usuarios nuevos o editar los existentes.
1. Siga las instrucciones de [Administrar usuarios y grupos en Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) en la *Guía del usuario de Enterprise*.

## Crear grupos de usuarios {#user-groups}

Puede crear grupos de usuarios, como Desarrolladores, Analistas, Especialistas en marketing, Ejecutivos, etc., y luego asignar privilegios en varios productos y espacios de trabajo de Adobe. Asignar todos los privilegios apropiados en diferentes productos de Adobe a un nuevo miembro del equipo puede ser tan fácil como añadirlos a un grupo de usuarios específico.

1. [En el Admin Console](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), haga clic en  **[!UICONTROL Usuarios]**  >  **[!UICONTROL Grupos de]** usuarios para crear nuevos grupos de usuarios o editar los grupos existentes.
1. Siga las instrucciones de [Administrar usuarios y grupos en Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) en la *Guía del usuario de Enterprise*.

## Especificar funciones y permisos {#roles-permissions}

Solo los administradores del sistema pueden establecer roles de usuario en [!DNL Target]. Por ejemplo, un usuario aprobador de Standard no puede cambiar un observador a un aprobador sin tener también [!DNL Experience Cloud] derechos de administrador.

Los usuarios administradores del sistema deben agregar usuarios al sistema. Los usuarios no se agregan automáticamente. Reciben una invitación por correo electrónico desde [!DNL Experience Cloud] y deben confirmar su dirección de correo electrónico antes de registrar sus cuentas.

1. [En Admin Console](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), haga clic en **[!UICONTROL Productos]** y, a continuación, seleccione el nombre del producto deseado.

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
   | Editor | Similar a la función Observador (puede ver actividades, pero no puede crearlas o editarlas). Sin embargo, la función Publicador tiene el permiso adicional de activar actividades. |

Para obtener más información, consulte [Administrar permisos y roles de producto en Admin Console](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html) en la *Guía del usuario de Enterprise*.

## Vídeo de formación: Configuración de Adobe Target Workspaces ![Distintivo de tutorial](/help/assets/tutorial.png)

Objetivos de aprendizaje:

* Acceso a Adobe Admin Console desde la interfaz de Adobe Target (tres métodos)
* Configuración de un espacio de trabajo en Adobe Admin Console
   * Agregación de usuarios a espacios de trabajo
   * Agregación de propiedades a espacios de trabajo
* Explicación de los espacios de trabajo predeterminados

>[!NOTE]
>
>La interfaz de usuario del menú [!DNL Target] [!UICONTROL Administration] (anteriormente [!UICONTROL Setup]) se ha rediseñado para proporcionar un rendimiento mejorado, reducir el tiempo de mantenimiento necesario al lanzar nuevas funciones y mejorar la experiencia del usuario en todo el producto. La información que aparece en el siguiente vídeo es, en general, correcta; sin embargo, las opciones pueden estar en ubicaciones ligeramente diferentes. Los vídeos actualizados se publicarán próximamente.

>[!VIDEO](https://video.tv.adobe.com/v/19463/)
