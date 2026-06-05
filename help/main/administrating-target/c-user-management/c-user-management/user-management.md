---
keywords: agregar usuario;administrar usuario;permisos de usuario
description: Aprenda a utilizar  [!DNL Adobe Admin Console]  para administrar usuarios y sus permisos y derechos en  [!DNL Adobe Target Standard].
title: ¿Cómo se agregan usuarios y se administran permisos para una cuenta  [!DNL Target Standard] ?
feature: Administration & Configuration
role: Admin
exl-id: 535c28c7-179d-4edc-b140-880b9dfe1d59
TQID: https://experienceleague.adobe.com/DdNQ81TpmyIRuPkmy4OIOq43CXwaMtm-uH2HtPjdx10
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
subfeature_v2:
  - id: c011fe9c-b94b-4a88-93d8-f2acece55112
  - id: cd7b6938-5837-4ee0-9790-5840997133d9
  - id: cf6b8469-14d0-4c0e-90ee-fb54066a035e
  - id: faed1c89-faf7-4df1-910d-a88263e03b15
  - id: fc9c2184-9102-403f-bd6c-0055021e4bea
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 925
ht-degree: 60%

---

# Usuarios

Agregue usuarios y administre sus permisos en [!DNL Adobe Admin Console] para una cuenta [!DNL Target Standard].

>[!NOTE]
>
>La funcionalidad [!UICONTROL Propiedades] y [!UICONTROL Permisos] está disponible como parte de la solución [!DNL Target Premium]. No están disponibles en [!DNL Target] Estándar sin una licencia de [!DNL Target] Premium.
>
>Puede comprobar si su organización dispone de una licencia de [!UICONTROL Standard] o [!UICONTROL Premium] si hace clic en el vínculo [!UICONTROL Administración] en la parte superior de la interfaz de usuario de [!DNL Target].
>
>* **[!DNL Target]&#x200B;[!UICONTROL Clientes de Standard]**: Si ve la ficha [!UICONTROL Usuarios] ([!UICONTROL Administración > Usuarios]) (y no la ficha **[!UICONTROL Propiedades]**), su organización dispone de una licencia de [!DNL Target] [!UICONTROL Standard]. [!DNL Target] Los clientes de [!UICONTROL Standard] deben seguir las instrucciones de este artículo para agregar usuarios y asignar permisos en [!DNL Adobe Admin Console].
>
>* **[!DNL Target]clientes Premium**: Si ve la ficha [!UICONTROL Usuarios] y la ficha [!UICONTROL Propiedades] ([!UICONTROL Administración > Propiedades]), su organización dispone de una licencia de [!DNL Target] Premium. [!DNL Target] Los clientes Premium deben seguir las instrucciones de [Permisos de usuario de Enterprise](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) y [Configurar permisos de Enterprise](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md) para agregar usuarios y asignar permisos en [!DNL Adobe Admin Console].
>
>Para obtener información detallada sobre cómo administrar usuarios y permisos, consulte [Administración de productos y perfiles](https://helpx.adobe.com/es/enterprise/using/manage-products-and-profiles.html) en la *Guía del usuario de Enterprise &amp; Teams*.

Al comenzar a usar [!DNL Adobe Target], encontrará identificadores (terminados en Adobe.com) ya rellenados en su cuenta de [!DNL Adobe Experience Cloud]. Estos identificadores son para miembros de equipos de [!DNL Adobe], para que puedan ayudarle con su nueva cuenta y a usar [!DNL Adobe Target] si es necesario. Para obtener ayuda, póngase en contacto con los equipos de Adobe de la forma habitual.

No verá nuevos usuarios enumerados en la página [!UICONTROL Usuarios] hasta que inicien sesión con su cuenta de [!DNL Adobe Experience Cloud] y luego inicien sesión en [!DNL Target].

De manera predeterminada, todos los usuarios de [!DNL Target] comienzan con los permisos de [!UICONTROL Observer].

Los usuarios administradores se han identificado en la lista [!UICONTROL Usuarios]. Póngase en contacto con el usuario administrador del sistema si necesita que cambien su nivel de acceso.

## Ver información de usuario desde [!DNL Target]

Puede ver una lista de los usuarios actuales en la IU de [!DNL Target], incluidas sus funciones por espacio de trabajo y sus direcciones de correo electrónico.

Para ver la página [!UICONTROL Usuarios], haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Usuarios]**.

>[!NOTE]
>
>Para administrar un usuario existente o agregar nuevos usuarios, debes usar [!UICONTROL Adobe Admin Console], como se explica más abajo.

## Acceda a la [!DNL Adobe Admin Console] {#access}

Para tareas realizadas en [!DNL Adobe Admin Console], acceda a la consola siguiendo estos pasos:

1. En [!DNL Target], haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Usuarios]** > **[!UICONTROL Administración de usuarios]**.

   O

   Vaya a [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/) e inicie sesión con su Adobe ID si todavía no ha iniciado sesión.

1. (Condicional) Si tiene acceso a [!DNL Admin Console for Enterprise] para más de una organización, haga clic en el avatar del usuario en la esquina derecha o en la barra de navegación superior y, a continuación, seleccione la organización que quiera.

## Agregar usuarios {#add-users}

Toda la administración de usuarios debe realizarse en [!DNL Adobe Admin Console for Enterprise]. Sin embargo, todos los usuarios existentes en [!DNL Target] se migrarán de [!DNL Target] a [!DNL Admin Console for Enterprise].

1. [En Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), haga clic en **[!UICONTROL Usuarios]** > **[!UICONTROL Usuarios]** para crear usuarios nuevos o para editar los existentes.
1. Siga las instrucciones de [Administrar usuarios y grupos en Experience Cloud](https://helpx.adobe.com/es/enterprise/using/users.html) en la *Guía del usuario de Enterprise*.

## Crear grupos de usuarios {#user-groups}

Puede crear grupos de usuarios, como Desarrolladores, Analistas, Especialistas en marketing, Ejecutivos, etc., y luego asignar privilegios en varios productos y espacios de trabajo de [!DNL Adobe]. Asignar todos los privilegios apropiados en diferentes productos de [!DNL Adobe] a un nuevo miembro del equipo puede ser tan fácil como agregarlos a un grupo de usuarios específico.

1. [En Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), haga clic en **[!UICONTROL Usuarios]** > **[!UICONTROL Grupos de usuarios]** para crear grupos de usuarios nuevos o para editar los existentes.
1. Siga las instrucciones de [Administrar usuarios y grupos en Experience Cloud](https://helpx.adobe.com/es/enterprise/using/users.html) en la *Guía del usuario de Enterprise*.

## Especificar funciones y permisos {#roles-permissions}

Solo los administradores del sistema pueden establecer roles de usuario en [!DNL Target]. Por ejemplo, un usuario aprobador de [!UICONTROL Standard] no puede cambiar un observador a un aprobador sin tener también [!DNL Experience Cloud] derechos de administrador.

Los usuarios administradores del sistema deben agregar usuarios al sistema. Los usuarios no se agregan automáticamente. Reciben una invitación por correo electrónico desde [!DNL Experience Cloud] y deben confirmar su dirección de correo electrónico para que se registre su cuenta.

>[!NOTE]
>
>Para ver actividades en [!DNL Target], los usuarios deben estar asignados directamente a un área de trabajo con al menos la función [!UICONTROL Observer]. La asignación a través de grupos de usuarios por sí sola es insuficiente. En general, se recomienda otorgar a los usuarios acceso al espacio de trabajo predeterminado.

1. [En Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), haga clic en **[!UICONTROL Productos]** y, a continuación, seleccione el nombre del producto deseado.

1. Haga clic en el espacio de trabajo deseado (por ejemplo, Espacio de trabajo predeterminado).

   La ficha [!UICONTROL Usuarios] muestra todos los usuarios de ese espacio de trabajo.

1. Seleccione la función de permisos deseada ([!UICONTROL Aprobador], [!UICONTROL Editor], [!UICONTROL Observador] o [!UICONTROL Publicador]) utilizando la lista desplegable de cada usuario en la columna [!UICONTROL Función del producto].

   | Función | Descripción |
   |--- |--- |
   | [!UICONTROL Aprobador] | Puede crear, editar y activar o detener actividades. |
   | [!UICONTROL Editor] | puede crear y editar actividades antes de que estén activas, pero no puede aprobar el lanzamiento de una actividad. |
   | [!UICONTROL Observador] | Puede ver actividades, pero no puede crearlas o editarlas. |
   | [!UICONTROL Editor] | Similar a la función [!UICONTROL Observer] (puede ver actividades, pero no puede crearlas o editarlas). Sin embargo, el rol [!UICONTROL Publicador] tiene el permiso adicional de activar actividades. |

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
>La interfaz de usuario del menú [!DNL Target] [!UICONTROL Administración] (anteriormente [!UICONTROL Configuración]) se ha rediseñado para proporcionar un rendimiento mejorado, reducir el tiempo de mantenimiento necesario al lanzar nuevas características y mejorar la experiencia del usuario en todo el producto. La información que aparece en el siguiente vídeo es, en general, correcta; sin embargo, las opciones pueden estar en ubicaciones ligeramente diferentes. Los vídeos actualizados se publicarán próximamente.

>[!VIDEO](https://video.tv.adobe.com/v/3421730?captions=spa)
