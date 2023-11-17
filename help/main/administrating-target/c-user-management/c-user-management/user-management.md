---
keywords: agregar usuario;administrar usuario;permisos de usuario
description: Aprenda a utilizar el [!DNL Adobe Admin Console] para administrar usuarios y sus permisos y derechos en [!DNL Adobe Target Standard].
title: Cómo se agregan usuarios y se administran permisos para un [!DNL Target Standard] ¿Cuenta?
feature: Administration & Configuration
role: Admin
exl-id: 535c28c7-179d-4edc-b140-880b9dfe1d59
source-git-commit: d40c25f75103327e749ad864b17df926cb323be0
workflow-type: tm+mt
source-wordcount: '897'
ht-degree: 73%

---

# Usuarios

Agregue usuarios y administre sus permisos en [!DNL Adobe Admin Console] para un [!DNL Target Standard] cuenta.

>[!NOTE]
>
>La funcionalidad [!UICONTROL Propiedades] y [!UICONTROL Permisos] está disponible como parte de la [!DNL Target Premium] solución. No están disponibles en [!DNL Target] Standard sin una licencia de [!DNL Target] Premium.
>
>Puede comprobar si su organización dispone de un [!UICONTROL Standard] o [!UICONTROL Premium] al hacer clic en el botón [!UICONTROL Administration] en la parte superior del [!DNL Target] IU.
>
>* **[!DNL Target]Clientes de  Standard**: Si ve la pestaña [!UICONTROL Usuarios] ([!UICONTROL Administración > Usuarios]) (y no la pestaña **[!UICONTROL Propiedades]**), su organización tiene una licencia de [!DNL Target] Standard.  [!DNL Target]Los clientes de  Standard deben seguir las instrucciones de este artículo para agregar usuarios y asignar permisos en [!DNL Adobe Admin Console]
>
>* Clientes de **[!DNL Target]Premium**: si ve la pestaña [!UICONTROL Usuarios] y la pestaña [!UICONTROL Propiedades] ([!UICONTROL Administración > Propiedades]), su organización tiene una licencia de [!DNL Target] Premium. [!DNL Target] Los clientes Premium deben seguir las instrucciones de [Permisos de usuario de Enterprise](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) y [Configuración de permisos de Enterprise](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md) para agregar usuarios y asignar permisos en [!DNL Adobe Admin Console].
>
>Para obtener información detallada sobre cómo administrar usuarios y permisos, consulte [Administración de productos y perfiles](https://helpx.adobe.com/es/enterprise/using/manage-products-and-profiles.html) en la *Guía del usuario de Enterprise &amp; Teams*.

Al comenzar a usar [!DNL Adobe Target], encontrará identificadores (terminados en Adobe.com) ya rellenados en su cuenta de [!DNL Adobe Experience Cloud]. Estos identificadores son para miembros de equipos de [!DNL Adobe], para que puedan ayudarle con su nueva cuenta y a usar [!DNL Adobe Target] si es necesario. Para obtener ayuda, póngase en contacto con los equipos de Adobe de la forma habitual.

No verá nuevos usuarios en la lista de [!UICONTROL Usuarios] hasta que inicien sesión con su [!DNL Adobe Experience Cloud] y luego inicie sesión en [!DNL Target].

De forma predeterminada, todas [!DNL Target] Los usuarios de empiezan con [!UICONTROL Observador] permisos.

Los usuarios administradores se señalan en la lista de [!UICONTROL usuarios]. Póngase en contacto con el usuario administrador del sistema si necesita que cambien su nivel de acceso.

## Ver información de usuario desde [!DNL Target]

Puede ver una lista de los usuarios actuales en la [!DNL Target] IU, incluidas sus funciones por espacio de trabajo y direcciones de correo electrónico.

Para ver la [!UICONTROL Usuarios] página, haga clic en **[!UICONTROL Administration]** > **[!UICONTROL Usuarios]**.

![Lista de usuarios desde Target](/help/main/administrating-target/c-user-management/c-user-management/assets/user-list-target.png)

>[!NOTE]
>
>Para administrar un usuario existente o agregar nuevos usuarios, debe usar [!UICONTROL Adobe Admin Console], tal como se explica más abajo.

## Acceda a la [!DNL Adobe Admin Console] {#access}

Para tareas realizadas en [!DNL Adobe Admin Console], acceda a la consola siguiendo estos pasos:

1. Desde [!DNL Target], haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Usuarios]** > **[!UICONTROL Administración de usuarios]**.

   O

   Vaya a [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/) e inicie sesión con su Adobe ID si todavía no ha iniciado sesión.

1. (Condicional) Si tiene acceso a [!DNL Admin Console for Enterprise] para más de una organización, haga clic en el avatar del usuario en la esquina derecha o en la barra de navegación superior y, a continuación, seleccione la organización que quiera.

## Agregar usuarios {#add-users}

Toda la administración de usuarios debe realizarse en [!DNL Adobe Admin Console for Enterprise]. Sin embargo, todos los usuarios existentes en [!DNL Target] se migrarán de [!DNL Target] a [!DNL Admin Console for Enterprise].

1. [En Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), haga clic en **[!UICONTROL Usuarios]** > **[!UICONTROL Usuarios]** para crear usuarios nuevos o editar los existentes.
1. Siga las instrucciones de [Administrar usuarios y grupos en Experience Cloud](https://helpx.adobe.com/es/enterprise/using/users.html) en la *Guía del usuario de Enterprise*.

## Crear grupos de usuarios {#user-groups}

Puede crear grupos de usuarios, como desarrolladores, analistas, especialistas en marketing, ejecutivos, etc., y luego asignar privilegios entre varios [!DNL Adobe] productos y espacios de trabajo. Asignar un nuevo miembro del equipo a todos los privilegios adecuados entre diferentes [!DNL Adobe] los productos pueden ser tan fáciles como agregarlos a un grupo de usuarios específico.

1. [En Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), haga clic en **[!UICONTROL Usuarios]** > **[!UICONTROL Grupos de usuarios]** para crear grupos de usuarios nuevos o editar los existentes.
1. Siga las instrucciones de [Administrar usuarios y grupos en Experience Cloud](https://helpx.adobe.com/es/enterprise/using/users.html) en la *Guía del usuario de Enterprise*.

## Especificar funciones y permisos {#roles-permissions}

Solo los administradores del sistema pueden establecer roles de usuario en [!DNL Target]. Por ejemplo, una [!UICONTROL Standard] el usuario aprobador no puede cambiar un observador a un aprobador si no tiene [!DNL Experience Cloud] Derechos de administrador.

Los usuarios administradores del sistema deben agregar usuarios al sistema. Los usuarios no se agregan automáticamente. Reciben una invitación por correo electrónico desde [!DNL Experience Cloud] y deben confirmar su dirección de correo electrónico para que se registre su cuenta.

1. [En Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), haga clic en **[!UICONTROL Productos]** y, a continuación, seleccione el nombre del producto deseado.

   ![Pestaña Productos](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. Haga clic en el espacio de trabajo deseado (por ejemplo, Espacio de trabajo predeterminado).

   ![Espacio de trabajo predeterminado](/help/main/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

   La pestaña [!UICONTROL Usuarios] muestra todos los usuarios de un espacio de trabajo.

   ![usuarios de configuración](/help/main/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Seleccione la función de permisos deseada ([!UICONTROL Aprobador], [!UICONTROL Editor], [!UICONTROL Observador] o [!UICONTROL Editor]) mediante la lista desplegable de cada usuario en la [!UICONTROL Función del producto] columna.

   ![Lista desplegable Función del producto](/help/main/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | Función | Descripción |
   |--- |--- |
   | [!UICONTROL Aprobador] | Puede crear, editar y activar o detener actividades. |
   | [!UICONTROL Editor] | puede crear y editar actividades antes de que estén activas, pero no puede aprobar el lanzamiento de una actividad. |
   | [!UICONTROL Observador] | Puede ver actividades, pero no puede crearlas o editarlas. |
   | [!UICONTROL Editor] | Similar a la [!UICONTROL Observador] función (puede ver actividades, pero no puede crearlas o editarlas). Sin embargo, la función [!UICONTROL Publicador] tiene el permiso adicional de activar actividades. |

Para obtener más información, consulte [Administrar permisos y roles de producto en Admin Console](https://helpx.adobe.com/es/enterprise/help/manage-permissions-and-roles.html) en la *Guía del usuario de Enterprise*.

## Vídeo de formación: Cómo configurar espacios de trabajo de Adobe Target ![Distintivo del tutorial](/help/main/assets/tutorial.png)

Objetivos de aprendizaje:

* Acceso a Adobe Admin Console desde la interfaz de Adobe Target (tres métodos)
* Configuración de un espacio de trabajo en Adobe Admin Console
   * Agregación de usuarios a espacios de trabajo
   * Agregación de propiedades a espacios de trabajo
* Explicación de los espacios de trabajo predeterminados

>[!NOTE]
>
>La interfaz del menú [!UICONTROL Administración] de [!DNL Target] (anteriormente [!UICONTROL Configuración]) se ha rediseñado para proporcionar un rendimiento mejorado, reducir el tiempo de mantenimiento necesario al lanzar nuevas funciones y mejorar la experiencia del usuario en todo el producto. La información que aparece en el siguiente vídeo es, en general, correcta; sin embargo, las opciones pueden estar en ubicaciones ligeramente diferentes. Los vídeos actualizados se publicarán próximamente.

>[!VIDEO](https://video.tv.adobe.com/v/19463/)
