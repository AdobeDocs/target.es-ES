---
keywords: Administración;función de aprobador;aprobador
description: Realice las primeras tareas que los administradores de Adobe Target deben realizar después de recibir por correo electrónico la invitación de Adobe Experience Cloud.
title: ¿Dónde Empiezo A Administrar [!DNL Target]?
feature: Administration & Configuration
role: Admin
exl-id: b60236da-20ae-4bab-b261-6a33d2f70e23
TQID: 'https://experienceleague.adobe.com/GfadY-knTwzXCB-n1AZ9u3PtoAyJokn1OXu3elRhgXk'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 553aa8fb523a62f72f0e2be7d7fd1b4eb663da6b
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 9%
---
# Primeros pasos del administrador

Complete estos pasos después de recibir una invitación para unirse a [!DNL Adobe Target] a través de [!DNL Adobe Experience Cloud]. Cuando esté listo para configurar los valores predeterminados de la cuenta, consulte [¿Cómo administro Target?](/help/main/administrating-target/administrating-target.md). Para obtener ayuda para encontrar **[!UICONTROL Administration]** en la interfaz de usuario, consulte [Comprender la [!DNL Target] interfaz de usuario](/help/main/c-intro/understand-the-target-ui.md).

**Resumen del flujo de trabajo**

1. [Obtener invitación para Target](#task_3E0817630774431983FAA3D2CB2E75BD): Un administrador del sistema le agrega en [!DNL Adobe Admin Console].
1. [Acepta la invitación](#task_24FE66659E634B24AB61DB8497772E17): Inicia sesión en [!DNL Experience Cloud] y vincula tu cuenta de [!DNL Target].
1. [Asígnese a usted mismo la función de aprobador](#task_15CAA437A71444E2932B333D5E66A3C7): confirme el acceso y los permisos para su tipo de licencia.
1. [Administración de usuarios](/help/main/administrating-target/c-user-management/user-management.md): agregue usuarios y asigne roles para [!DNL Target Standard] o [!DNL Target Premium].

## Obtener invitación para [!DNL Target] {#task_3E0817630774431983FAA3D2CB2E75BD}

Un administrador del sistema de [!DNL Adobe Admin Console] debe agregarle como usuario de [!DNL Target] para invitarle a unirse. El administrador también debe agregarle a uno o varios perfiles de producto específicos de funciones (grupos de usuarios). Ambas tareas se realizaron en [Adobe Admin Console](https://adminconsole.adobe.com).

Para obtener instrucciones paso a paso, consulte [Obtenga información sobre cómo administrar usuarios y perfiles de producto](https://helpx.adobe.com/enterprise/using/users.html) en la documentación de Adobe Enterprise.

Una vez que el administrador haya completado estos pasos, recibirá un correo electrónico de invitación.

## Aceptar la invitación {#task_24FE66659E634B24AB61DB8497772E17}

Cuando reciba la invitación para unirse a [!DNL Adobe Experience Cloud], acéptela, inicie sesión y acepte el [!UICONTROL Contrato de licencia para el usuario final] (EULA).

Siga estos pasos para aceptar la invitación y vincular [!DNL Target] a su cuenta de [!DNL Experience Cloud]:

1. Acepte la invitación a [!DNL Adobe Experience Cloud].
1. Si todavía no dispone de un Adobe ID, se le solicitará que lo cree.

   Si ya tiene un Adobe ID, inicie sesión cuando se le solicite.

1. Acepte las [!UICONTROL Condiciones de uso].

1. Revise el resumen de lo que ha hecho hasta el momento y haga clic en **[!UICONTROL Continuar a Experience Cloud]**.

1. Inicie sesión en [!DNL Adobe Experience Cloud] y haga clic en **[!UICONTROL Vincular cuenta]**.

   >[!NOTE]
   >
   >Si no vincula su cuenta, no podrá obtener acceso a [!DNL Target].

   Todos los productos de [!UICONTROL Experience Cloud] aparecen en la página de vinculación. Haga clic en **[!UICONTROL Vínculo de destino]** y, a continuación, escriba su nombre de usuario y contraseña de [!DNL Target].
1. Haga clic en **[!UICONTROL Continuar a Experience Cloud]**.

   En este punto, es posible que aún no tenga perfiles de producto con derechos para vincular; el administrador del sistema puede asignarlos en [!DNL Adobe Admin Console].
1. Opcionalmente, vea el vídeo que presenta [!DNL Adobe Experience Cloud].
1. Para actualizar sus privilegios y abrir el producto, cierre la sesión de [!DNL Adobe Experience Cloud] y vuelva a iniciarla.
1. Continúe con [Asígnese a usted mismo la función de aprobador](#task_15CAA437A71444E2932B333D5E66A3C7).

## Asignarse a usted mismo la función de aprobador {#task_15CAA437A71444E2932B333D5E66A3C7}

Después de aceptar la invitación e iniciar sesión, confirme que [!DNL Target] aparece en su cuenta de [!DNL Experience Cloud] y, a continuación, asígnese la función de [!UICONTROL Aprobador] para [!DNL Target].

Elija la guía que coincida con su licencia:

* Si su organización tiene una licencia de [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905), consulte [Aprenda a especificar funciones y permisos](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) en *Usuarios*.
* Si su organización tiene una licencia de [Target Premium](/help/main/c-intro/intro.md#premium), consulte el [Paso 6: Especificar funciones y permisos](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_8C425E43E5DD4111BBFC734A2B7ABC80) en *Configurar permisos de Enterprise*.

Luego puede configurar usuarios para [!DNL Target Standard] o [!DNL Target Premium]. Consulte [Administración de usuarios](/help/main/administrating-target/c-user-management/user-management.md) para obtener información general y vínculos al flujo de trabajo correcto para su licencia.

## Permisos necesarios para editar la configuración de [!UICONTROL Administración] {#admin-permissions}

**Antes del 22 de abril de 2025**: Los usuarios con derechos de [!UICONTROL Aprobadores] en [!DNL Adobe Admin Console] podían editar o cambiar toda la configuración en las páginas de [[!UICONTROL Administración]](/help/main/administrating-target/administrating-target.md) en [!DNL Target], independientemente de su rol de [!DNL Target].

**A partir del 22 de abril de 2025**: Solo los administradores de [!UICONTROL productos] y [!UICONTROL soluciones] pueden actualizar la configuración en las secciones de [[!UICONTROL Administración]](/help/main/administrating-target/administrating-target.md), independientemente de sus roles en [!DNL Target] espacios de trabajo. Los usuarios sin este permiso tienen acceso de solo lectura a las secciones [!UICONTROL Administración].

Este cambio mejora el control de la organización sobre la configuración de la instancia [!DNL Target] y ayuda a evitar actualizaciones accidentales que podrían afectar a la entrega de la actividad en los equipos de prueba y personalización.
