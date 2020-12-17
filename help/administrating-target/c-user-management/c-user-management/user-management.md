---
keywords: add user;manage user;user permissions
description: Puede agregar usuarios a Adobe Target y administrar sus permisos en Adobe Admin Console.
title: Usuarios
feature: Administration & Configuration
translation-type: tm+mt
source-git-commit: 9b57d5554884b06d278c3baef3b2c1d5f37bdeb5
workflow-type: tm+mt
source-wordcount: '896'
ht-degree: 45%

---


# Usuarios{#users}

Puede agregar usuarios y administrar sus permisos en [!DNL Adobe Admin Console].

>[!NOTE]
>
>La funcionalidad [!UICONTROL Propiedades] y [!UICONTROL Permisos] está disponible como parte de la [!DNL Target]solución Premium. No están disponibles en [!DNL Target] Standard sin una licencia de [!DNL Target] Premium.
>Puede saber si su organización tiene una licencia Standard o Premium haciendo clic en el vínculo [!UICONTROL Administración] en la parte superior de la [!DNL Target] interfaz de usuario.
>
>* **[!DNL Target]Clientes** estándar: Si ve la ficha   Userstab ([!UICONTROL Administración > Usuarios]) (y no la ficha  **** Propiedades), su organización tiene una licencia  [!DNL Target] estándar. [!DNL Target] Los clientes estándar deben seguir las instrucciones de este artículo para agregar usuarios y asignar permisos en el  [!DNL Adobe Admin Console].
   >
   >
* **[!DNL Target]Clientes** Premium: Si ve la   ficha Userstab y la ficha   Propiedades ([!UICONTROL Administración > Propiedades]), su organización tiene una licencia  [!DNL Target] Premium. [!DNL Target] Los clientes Premium deben seguir las instrucciones de [Permisos de usuario de Enterprise](/help/administrating-target/c-user-management/property-channel/property-channel.md) y [Configuración de permisos de Enterprise](/help/administrating-target/c-user-management/property-channel/properties-overview.md) para agregar usuarios y asignar permisos en [!DNL Adobe Admin Console].
>
>
Para obtener información detallada sobre cómo administrar usuarios y permisos, consulte [Administrar productos y perfiles](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) en la *Guía del usuario de Enterprise &amp; Teams*.

Al comenzar a usar [!DNL Adobe Target], encontrará identificadores (terminados en Adobe.com) ya rellenados en su cuenta de [!DNL Adobe Experience Cloud]. Estos ID son para miembros de equipos [!DNL Adobe] para que puedan ayudarle con su nueva cuenta y con el uso de [!DNL Adobe Target], en caso de necesitar ayuda. Para obtener ayuda, póngase en contacto con los equipos de Adobe de la forma habitual.

No verá el nuevo usuario enumerado en la página [!UICONTROL Usuarios] hasta que el usuario inicie sesión con su cuenta [!DNL Adobe Experience Cloud] y luego inicie sesión en [!DNL Target Standard/Premium].

De forma predeterminada, todos los usuarios de [!DNL Target] empiezan con permisos de observador.

Los usuarios administradores se identifican en la lista [!UICONTROL Usuarios]. Póngase en contacto con uno de los usuarios administradores del sistema si necesita cambiar el nivel de acceso.

## Vista de información de usuario desde Destinatario

Puede realizar la vista de una lista de los usuarios actuales en el entorno de Destinatario, incluidas sus funciones por espacio de trabajo y las direcciones de correo electrónico directamente desde el Destinatario.

Para vista de la página Usuarios, haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Usuarios]**.

![Lista del usuario desde Destinatario](/help/administrating-target/c-user-management/c-user-management/assets/user-list-target.png)

>[!NOTE]
>
>Para administrar un usuario existente o agregar nuevos usuarios, debe utilizar el [!UICONTROL Adobe Admin Console], como se explica a continuación.

## Acceso a Adobe Admin Console {#access}

Para tareas realizadas en Adobe Admin Console, acceda a la consola siguiendo estos pasos:

1. Desde [!DNL Target], haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Usuarios]** > **[!UICONTROL Administración de usuarios]**.

   O

   Vaya a [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/) e inicie sesión con su Adobe ID si aún no ha iniciado sesión.

1. (Condicional) Si tiene acceso a [!DNL Admin Console for Enterprise] para más de una organización, haga clic en el avatar del usuario en la esquina derecha o en la barra de navegación superior y, a continuación, seleccione la organización que quiera.

## Añadir usuarios {#add-users}

Toda la administración de usuarios debe realizarse en [!DNL Adobe Admin Console for Enterprise]. Sin embargo, todos los usuarios existentes en [!DNL Target] se migrarán de [!DNL Target] a [!DNL Admin Console for Enterprise].

1. [En el Admin Console](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), haga clic en  **[!UICONTROL Usuarios]** >  **** Usuarios para crear nuevos usuarios o editar los existentes.
1. Siga las instrucciones de [Administrar usuarios y grupos en Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) en la *Guía del usuario de Enterprise*.

## Crear grupos de usuarios {#user-groups}

Puede crear grupos de usuarios, como Desarrolladores, Analistas, Especialistas en marketing, Ejecutivos, etc., y luego asignar privilegios en varios productos y espacios de trabajo de Adobe. Asignar todos los privilegios apropiados en diferentes productos de Adobe a un nuevo miembro del equipo puede ser tan fácil como añadirlos a un grupo de usuarios específico.

1. [En el Admin Console](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), haga clic en  **[!UICONTROL Usuarios]** >  **[!UICONTROL Grupos]** de usuarios para crear nuevos grupos de usuarios o editar los existentes.
1. Siga las instrucciones de [Administrar usuarios y grupos en Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) en la *Guía del usuario de Enterprise*.

## Especificar funciones y permisos {#roles-permissions}

Solo los administradores del sistema pueden establecer roles de usuario en [!DNL Target]. Por ejemplo, un usuario aprobador estándar no puede cambiar un observador a aprobador sin tener también [!DNL Experience Cloud] derechos de administrador.

Los usuarios administradores del sistema deben agregar usuarios al sistema. Los usuarios no se agregan automáticamente. Se les invita por correo electrónico desde [!DNL Experience Cloud] y deben confirmar sus direcciones de correo electrónico antes de que se registren sus cuentas.

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
   | Editor | Similar a la función Observador (puede vista de actividades, pero no puede crearlas o editarlas). Sin embargo, la función Editor tiene el permiso adicional para activar actividades. |

Para obtener más información, consulte [Administrar permisos y roles de producto en Admin Console](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html) en la *Guía del usuario de Enterprise*.

## Vídeo de capacitación: Cómo configurar espacios de trabajo de Destinatario ![distintivo de tutorial](/help/assets/tutorial.png)

Objetivos de aprendizaje:

* Acceso a Adobe Admin Console desde la interfaz de Adobe Target (tres métodos)
* Configuración de un espacio de trabajo en Adobe Admin Console
   * Agregación de usuarios a espacios de trabajo
   * Agregación de propiedades a espacios de trabajo
* Explicación de los espacios de trabajo predeterminados

>[!NOTE]
>
>La interfaz de usuario del menú [!DNL Target] [!UICONTROL Administración] (anteriormente [!UICONTROL Configuración]) se ha rediseñado para proporcionar un rendimiento mejorado, reducir el tiempo de mantenimiento necesario al lanzar nuevas funciones y mejorar la experiencia del usuario en todo el producto. La información del siguiente vídeo es, en general, correcta; sin embargo, las opciones pueden estar en ubicaciones ligeramente diferentes. Los vídeos actualizados se publicarán pronto.

>[!VIDEO](https://video.tv.adobe.com/v/19463/)
