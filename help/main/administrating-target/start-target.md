---
keywords: Administración;función de aprobador;aprobador
description: Realizar las primeras tareas que  [!DNL Adobe Target] deben realizar los administradores después de recibir por correo electrónico la invitación para  [!DNL Adobe Experience Cloud].
title: ¿Dónde Empiezo A Administrar  [!DNL Target]?
feature: Administration & Configuration
role: Admin
exl-id: b60236da-20ae-4bab-b261-6a33d2f70e23
TQID: https://experienceleague.adobe.com/GfadY-knTwzXCB-n1AZ9u3PtoAyJokn1OXu3elRhgXk
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 473
ht-degree: 30%

---

# Primeros pasos del administrador

Este artículo contiene los primeros pasos que deben realizar los administradores de [!DNL Adobe Target] tras recibir por correo electrónico la invitación de [!DNL Adobe Experience Cloud].

## Obtener invitación para [!DNL Target] {#task_3E0817630774431983FAA3D2CB2E75BD}

Un administrador del sistema de [!DNL Adobe Admin Console] debe agregarle como usuario de [!DNL Target] para invitarle a unirse. A continuación, el administrador del sistema debe agregarle a uno o varios perfiles de producto específicos de funciones (grupos de usuarios). Ambas tareas se realizan en [Adobe Admin Console](https://adminconsole.adobe.com).

Para obtener más información, consulte [Administrar grupos de usuarios](https://helpx.adobe.com/enterprise/using/users.html).

Recibirá un correo electrónico de invitación después de que el administrador del sistema haya realizado estos pasos.

## Aceptar la invitación {#task_24FE66659E634B24AB61DB8497772E17}

Cuando reciba la invitación para unirse a [!DNL Adobe Experience Cloud], acéptela, inicie sesión y acepte el [!UICONTROL Acuerdo de licencia del usuario final] (EULA).

1. Acepte la invitación a [!DNL Adobe Experience Cloud].
1. Si todavía no dispone de un Adobe ID, se le solicitará que lo cree.

   Si tiene una Adobe ID, se reconocerá su Adobe ID y se le pedirá que inicie sesión.
1. Acepte las [!UICONTROL Condiciones de uso].
1. Revise el resumen de lo que ha hecho hasta el momento y haga clic en **[!UICONTROL Continuar a Experience Cloud]**.
1. Inicie sesión en [!DNL Adobe Experience Cloud] y haga clic en **[!UICONTROL Vincular cuenta]**.

   >[!NOTE]
   >
   >Si no vincula la cuenta, no podrá acceder a [!DNL Target].

   Todos los productos de [!UICONTROL Experience Cloud] aparecen en la página de vinculación. Haga clic en `Link Target` e introduzca su nombre de usuario y contraseña de [!DNL Target] para acceder a [!DNL Target].
1. Haga clic en **[!UICONTROL Continuar a Experience Cloud]**.

   En este punto, todavía no dispone de ningún grupo configurado con concesiones para su vínculo.
1. Si lo desea, vea el vídeo de presentación de [!DNL Adobe Experience Cloud].
1. Para ver sus nuevos privilegios y acceder al producto, cierre la sesión de [!DNL Adobe Experience Cloud] y vuelva a iniciarla.
1. Continúe con el paso siguiente. [Asignarse a sí mismo la función de aprobador](/help/main/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7).

## Asignarse a usted mismo la función de aprobador {#task_15CAA437A71444E2932B333D5E66A3C7}

Después de aceptar la invitación para unirse a [!DNL Adobe Experience Cloud] e iniciar sesión, confirme que [!DNL Target] se ha agregado a su cuenta de [!DNL Experience Cloud] y, a continuación, asígnese a usted mismo la función de [!UICONTROL Aprobador] para [!DNL Target].

Si su organización tiene una licencia [de Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905), consulte [Especificar funciones y permisos](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) en *Usuarios*.

Si su organización tiene una licencia de [Target Premium](/help/main/c-intro/intro.md#premium), consulte el [Paso 6: Especificar funciones y permisos](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_8C425E43E5DD4111BBFC734A2B7ABC80) en *Configurar permisos de Enterprise*.

El siguiente paso debe ser configurar usuarios en [!DNL Target Standard] y [!DNL Target Premium]. Para obtener más información, consulte [Administración de usuarios](/help/main/administrating-target/c-user-management/user-management.md).

## Permisos necesarios para editar la configuración de [!UICONTROL Administración] {#admin-permissions}

**Antes del 22 de abril de 2025**: Los usuarios con derechos de [!UICONTROL Aprobadores] en [!DNL Adobe Admin Console] pueden editar o cambiar toda la configuración en la página [[!UICONTROL Administración]](/help/main/administrating-target/administrating-target.md) de [!DNL Target], independientemente de su rol de [!DNL Target].

**A partir del 22 de abril de 2025**: Solo los administradores de [!UICONTROL productos] y [!UICONTROL soluciones] podrán actualizar la configuración en las secciones de [[!UICONTROL Administración]](/help/main/administrating-target/administrating-target.md), independientemente de sus roles en [!DNL Target] espacios de trabajo. Los usuarios sin este permiso tendrán acceso de solo lectura a las secciones [!UICONTROL Administración].

Esta actualización mejora el control de la organización sobre las configuraciones de instancia de [!DNL Target], lo que evita actualizaciones accidentales que podrían afectar a la entrega de la actividad en varios equipos de prueba y personalización.
