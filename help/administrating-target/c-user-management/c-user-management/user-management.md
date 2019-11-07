---
keywords: agregar usuario;administrar usuario;permisos de usuario
description: Puede añadir usuarios y gestionar sus permisos en Adobe Admin Console.
title: Usuarios
subtopic: Primeros pasos
topic: Standard
uuid: 9b311dd3-b8fa-483d-aedd-96761cfcd67e
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Usuarios{#users}

Puede añadir usuarios y gestionar sus permisos en Adobe Admin Console.

>[!NOTE]
>
>La funcionalidad [!UICONTROL Propiedades] y [!UICONTROL Permisos] está disponible como parte de la [!DNL Target]solución Premium. No están disponibles en [!DNL Target] Standard sin una licencia de [!DNL Target] Premium.
>Puede comprobar si su organización dispone de una licencia Standard o Premium haciendo clic en el vínculo [!UICONTROL Configuración] en la parte superior de la interfaz de usuario de.[!DNL Target]
>
>**[!DNL Target]Clientes de Standard**: si ve la pestaña [!UICONTROL Usuarios] ([!UICONTROL Configuración &gt; Usuarios]), su organización dispone de una [!DNL Target] licencia de Standard. [!DNL Los clientes de Target Standard deben seguir las instrucciones descritas en este artículo para agregar usuarios y asignar permisos en [!DNL Adobe Admin Console].
>
>**Clientes de[!DNL Target]Premium**: si ve la pestaña [!UICONTROL Propiedades] ([!UICONTROL Configuración &gt; Propiedades]), su organización dispone de una [!DNL Target] licencia Premium. [!DNL Target] Los clientes Premium deben seguir las instrucciones de [Permisos de usuario de Enterprise](/help/administrating-target/c-user-management/property-channel/property-channel.md) y [Configuración de permisos de Enterprise](/help/administrating-target/c-user-management/property-channel/properties-overview.md) para agregar usuarios y asignar permisos en [!DNL Adobe Admin Console].

Solo los usuarios administradores del sistema pueden agregar usuarios y administrar sus permisos. La función de administrador del sistema se asigna en el nivel de [!DNL Experience Cloud]. Las funciones de [!DNL Experience Cloud] están separadas de las funciones administradas en cada solución.

Al comenzar a usar [!DNL Adobe Target], encontrará identificadores (terminados en Adobe.com) ya rellenados en su cuenta de [!DNL Adobe Experience Cloud]. Estos identificadores son para miembros de equipos de Adobe, para que puedan ayudarle con su nueva cuenta y a usar [!DNL Adobe Target] si es necesario. Para obtener ayuda, póngase en contacto con los equipos de Adobe de la forma habitual.

No verá el nombre del usuario nuevo en la página [!UICONTROL Usuarios] hasta que el usuario inicie sesión con la cuenta de Adobe Experience Cloud y luego inicie sesión en [!DNL Target Standard/Premium] haciendo clic en la tarjeta [!DNL Target].

De forma predeterminada, todos los usuarios de [!DNL Target] empiezan con permisos de observador.

Los usuarios administradores del sistema se señalan en la lista de usuarios de Contacte con uno de los usuarios administradores del sistema si necesita que cambien su nivel de acceso.

## Acceso a Adobe Admin Console {#access}

Para tareas realizadas en Adobe Admin Console, acceda a la consola siguiendo estos pasos:

1. Vaya a [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/) &gt; inicie sesión con su Adobe ID si todavía no ha iniciado sesión.

   O

   Si ya inició sesión en Experience Cloud, vaya a [https://www.experiencecloud.adobe.com](https://experiencecloud.adobe.com), luego haga clic en el icono [!UICONTROL Aplicación] en la barra de navegación superior &gt; haga clic en **[!UICONTROL Admin]** a la derecha.

1. (Condicional) Si tiene acceso a [!DNL Admin Console for Enterprise] para más de una organización, haga clic en el avatar del usuario en la esquina derecha o en la barra de navegación superior y, a continuación, seleccione la organización que quiera.

## Agregar usuarios {#add-users}

Toda la administración de usuarios debe realizarse en [!DNL Adobe Admin Console for Enterprise]. Sin embargo, todos los usuarios existentes en [!DNL Target] se migrarán de [!DNL Target] a [!DNL Admin Console for Enterprise].

1. [En Admin Console](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), haga clic en **[!UICONTROL Usuarios]** &gt; **[!UICONTROL Usuarios]** para crear usuarios nuevos o editar los existentes.
1. Siga las instrucciones de [Administrar usuarios y grupos en Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) en la *Guía del usuario de Enterprise*.

## Crear grupos de usuarios {#user-groups}

Puede crear grupos de usuarios, como Desarrolladores, Analistas, Especialistas en marketing, Ejecutivos, etc., y luego asignar privilegios en varios productos y espacios de trabajo de Adobe. Asignar todos los privilegios apropiados en diferentes productos de Adobe a un nuevo miembro del equipo puede ser tan fácil como añadirlos a un grupo de usuarios específico.

1. [En Admin Console](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), haga clic en **[!UICONTROL Usuarios]** &gt; **[!UICONTROL Grupos de usuarios]** para crear grupos de usuarios nuevos o editar los existentes.
1. Siga las instrucciones de [Administrar usuarios y grupos en Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) en la *Guía del usuario de Enterprise*.

## Especificar roles y permisos {#roles-permissions}

Solo los administradores del sistema pueden establecer roles de usuario en [!DNL Target]. Por ejemplo, un usuario aprobador de Standard no puede cambiar un observador a un aprobador si no dispone también de permisos de administrador de Experience Cloud.

Los usuarios administradores del sistema deben agregar usuarios al sistema. Los usuarios no se agregan automáticamente. Reciben una invitación por correo electrónico desde Experience Cloud y deben confirmar su dirección de correo electrónico para que se registre su cuenta.

1. [En Admin Console](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), haga clic en **[!UICONTROL Productos]** y, a continuación, seleccione el nombre del producto deseado.

   ![Pestaña Productos](/help/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. Haga clic en el nombre de la configuración deseada.
1. Haga clic en **[!UICONTROL Usuarios]**.

   La pestaña [!UICONTROL Usuarios] muestra todos los usuarios de un espacio de trabajo.

   ![usuarios de configuración](/help/administrating-target/c-user-management/c-user-management/assets/configuration_users-new.png)

1. Seleccione el rol de permisos deseado (Observador, Editor o Aprobador) utilizando la lista desplegable de cada usuario en la columna [!UICONTROL Rol del producto].

   | Función | Descripción |
   |--- |--- |
   | Observador | Puede ver actividades, pero no puede crearlas o editarlas. |
   | Editor | puede crear y editar actividades antes de que estén activas, pero no puede aprobar el lanzamiento de una actividad. |
   | Aprobador | Puede crear, editar y activar o detener actividades. |

Para obtener más información, consulte [Administrar permisos y roles de producto en Admin Console](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html) en la *Guía del usuario de Enterprise*.

## Vídeo de capacitación: Cómo configurar espacios de trabajo de Target

Objetivos de aprendizaje:

* Acceso a Adobe Admin Console desde la interfaz de Adobe Target (tres métodos)
* Configuración de un espacio de trabajo en Adobe Admin Console
   * Agregación de usuarios a espacios de trabajo
   * Agregación de propiedades a espacios de trabajo
* Explicación de los espacios de trabajo predeterminados

>[!VIDEO](https://video.tv.adobe.com/v/19463/?captions=spa)
