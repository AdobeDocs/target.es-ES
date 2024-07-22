---
keywords: interfaz de usuario de target;interfaz de usuario;iu;anuncios;eventos;notificaciones
description: Familiarícese con la interfaz de usuario y encuentre vínculos a información más detallada para ayudarle a sacar el máximo provecho de  [!DNL Target].
title: ¿Cómo se utiliza la IU de  [!DNL Target] ?
feature: Overview
exl-id: ce4c72b2-b635-406b-9830-650816445a64
source-git-commit: 6bef27637c06f39ffc0e755f19e8a0870ec749e5
workflow-type: tm+mt
source-wordcount: '1312'
ht-degree: 31%

---

# Información sobre la IU de [!DNL Target]

La interfaz de usuario está organizada en un formato lógico y fácil de usar para ayudarle a sacar el máximo partido a [!DNL Adobe Target]. La siguiente descripción general breve le ayudará a familiarizarse con [!DNL Target] y le proporcionará vínculos para obtener información más detallada e instrucciones paso a paso.

El encabezado de la parte superior de la interfaz de usuario de [!DNL Target] contiene fichas y opciones que le ayudarán a navegar por las diferentes capacidades de la solución. También puede cambiar de organización y [!DNL Adobe Experience Cloud] soluciones, obtener ayuda y notificaciones, administrar su perfil de [!DNL Adobe] y cerrar la sesión de [!DNL Target].

![Encabezado de Target](/help/main/c-intro/assets/target-header.png)

Las pestañas del lado izquierdo le permiten acceder a las distintas funcionalidades de [!DNL Target], que se describen más adelante. Empecemos por hablar de las opciones del lado derecho antes de saltar a las pestañas.

## Organizaciones

Una *organización* es la entidad que habilita un administrador a fin de configurar grupos y usuarios, y para controlar el inicio de sesión único en [!DNL Adobe Experience Cloud]. La organización funciona como una empresa de inicio de sesión que abarca todos los productos y soluciones de [!DNL Experience Cloud]. La mayoría de las veces, la organización es el nombre de empresa. Sin embargo, una empresa puede tener muchas organizaciones.

Seleccione la organización que desee en la lista desplegable [!UICONTROL Organization] si su compañía tiene varias organizaciones:

![Lista desplegable Organización](/help/main/c-intro/assets/organizations.png)

## Aplicaciones

El conmutador Aplicaciones le permite acceder rápidamente a las soluciones de [!DNL Adobe Experience Cloud] a las que tiene acceso.

![Conmutador de aplicaciones](/help/main/c-intro/assets/apps.png)

## Ayuda

El icono Ayuda le permite acceder a información, vídeos, blogs y mucho más para ayudarle a utilizar [!DNL Target] de forma más eficaz. Puede crear un vale de soporte, encontrar números de teléfono de soporte, hacer preguntas por Twitter o proporcionar comentarios sobre [!DNL Target] para que sepamos cómo está el equipo [!DNL Target].

![Ayuda](/help/main/c-intro/assets/help.png)

## Notificaciones y anuncios {#notifications-announcements}

Los paneles [!UICONTROL Notifications] y [!UICONTROL Announcements] le ayudan a estar al día acerca de todas las cosas de [!DNL Adobe Target]. Las notificaciones dinámicas ayudan a mantenerle al día del estado de las soluciones [!DNL Adobe Experience Cloud] y los eventos [!DNL Target]. Las notificaciones proactivas le avisan sobre eventos de interrupción y eventos de mantenimiento.

Haga clic en el icono de campana del encabezado para ver las notificaciones:

![Icono de campana para notificaciones y anuncios](assets/bell-icon.png)

El panel contiene fichas para [!UICONTROL Notifications] y [!UICONTROL Announcements].

![ Notificaciones ](assets/notifications.png)

Las secciones siguientes contienen información sobre cada pestaña y cómo configurar las notificaciones y los anuncios:

### Notificaciones {#notifications}

[!DNL Target] notificaciones de eventos incluyen lo siguiente:

* **Actividades**: notificaciones para todos los tipos de actividades cuando se aprueba o desactiva una actividad, ya sea manualmente o cuando llega a su fecha de inicio o de finalización. La notificación incluye el nombre de la actividad con un vínculo a la página de información general de la actividad.

  Las notificaciones se pueden configurar y las reciben, de forma predeterminada, los administradores de productos, los editores y los aprobadores en el área de trabajo de la actividad para las cuentas de [!DNL Target Premium]. Para las cuentas de [!DNL Target Standard], las notificaciones se reciben por todos los editores y aprobadores.

  Las notificaciones tienen el formato de los siguientes ejemplos:

   * `Activity {target.activity.name} has been activated`

   * `Activity {target.activity.name} has been deactivated`

* **Scripts de perfil**: notificaciones cuando se activa o desactiva un script de perfil, ya sea manualmente o por [!DNL Target].

  Las notificaciones se pueden configurar y las reciben, de forma predeterminada, los administradores y aprobadores de productos tanto para las cuentas de [!DNL Target Premium] como para las de [!DNL Target Standard].

  Las notificaciones tienen el formato de los siguientes ejemplos:

   * `Profile Script {target.profileScript.name} has been activated`
   * `Profile Script {target.profileScript.name} has been deactivated`

* **Fuentes de Recommendations**: notificaciones cuando se activa o desactiva una fuente de [!DNL Recommendations], ya sea de forma manual o por parte de [!DNL Target]. Las notificaciones también se envían cuando falla una fuente [!DNL Recommendations].

  Las notificaciones se pueden configurar y las reciben, de forma predeterminada, los administradores de productos y los aprobadores de las cuentas de [!DNL Target Premium]. [!DNL Recommendations] es una característica de [!DNL Target Premium] y no está disponible en [!DNL Target Standard].

  Las notificaciones tienen el formato de los siguientes ejemplos:

   * `Feed  {target.feed.name} has been activated`
   * `Feed {target.feed.name} has been deactivated`
   * `Feed {target.feed.name} has failed`
   * `Feed {target.feed.name} has failed to import from source`

Puede marcar las notificaciones individuales como leídas pasando el puntero sobre la notificación deseada y haciendo clic en la marca de verificación. Puede marcar todas las notificaciones como leídas o ver todas las notificaciones haciendo clic en [!UICONTROL "Mark as Read"] o [!UICONTROL "View All"] en la parte inferior del panel.

También puede configurar un recordatorio para que se le notifique de nuevo pasando el puntero sobre una notificación, haciendo clic en el icono &quot;[!UICONTROL Remind me]&quot; y seleccionando cuándo desea que se le notifique: 5 minutos, 15 minutos, una hora o mañana.

### Anuncios

Las notificaciones proactivas le avisan sobre eventos de interrupción y eventos de mantenimiento.

Encontrará información más detallada en la página [Estado de Adobe](https://status.adobe.com/es).

### Configuración de notificaciones y anuncios

Para editar las preferencias de notificaciones:

1. Haga clic en el icono de engranaje y luego en **[!UICONTROL Notifications]**.
1. En **[!UICONTROL Target]**, haga clic en **[!UICONTROL Customize]**.
1. Seleccione o anule la selección de las categorías para las que desea recibir notificaciones:

   * Solicitudes: Cuando alguien le envía una solicitud para aprobar un objeto u otorgar acceso a un objeto. No puede cancelar la suscripción a esta categoría.
   * Asignado a mí: cuando alguien le asigna un objeto.
   * Menciones: Cuando alguien te menciona en un comentario.
   * Nuevas versiones: Cuando hay una nueva versión disponible para un producto o servicio al que tiene acceso.
   * Compartido conmigo: Cuando alguien comparte un objeto con usted.
   * Actualizaciones de contenido: cuando alguien edita, elimina o comenta un objeto que usted creó o siguió.
   * Otros:

   >[!NOTE]
   >
   >&quot;Nuevas versiones&quot; y &quot;Actualizaciones de contenido&quot; son las únicas categorías de notificación aplicables a [!DNL Target]. Las otras categorías se aplican a otras soluciones de Adobe.


1. Seleccione las categorías que desea que se consideren de alta prioridad.
1. Seleccione las notificaciones de las que desea ver alertas en el explorador.

   Estas alertas aparecen en la esquina superior derecha del explorador durante unos segundos. Puede elegir ver las categorías de prioridad alta, todas las categorías u ocultar todas las ventanas emergentes de notificación. También puede configurar si desea que las notificaciones permanezcan visibles hasta que las descarte o hasta que pueda configurar la duración de la notificación.

1. Seleccione la frecuencia con la que desea recibir correos electrónicos de notificación:

   * No enviar correos electrónicos
   * Notificaciones inmediatas
   * Resumen diario
   * Resumen semanal

## Perfil

Haga clic en el avatar de su perfil para editar sus preferencias de [!DNL Adobe Experience Cloud] o para cerrar sesión de [!DNL Target]. También puede acceder o editar su perfil de [!DNL Adobe].

![Avatar de perfil](/help/main/c-intro/assets/change-language.png)

Ahora analicemos las pestañas a la izquierda del encabezado [!DNL Target].

## Actividades

La lista **[!UICONTROL Activities]** es la vista predeterminada al abrir [!DNL Target]. Puede crear actividades desde esta página y administrar las actividades existentes.

![lista de actividades](/help/main/c-intro/assets/activities-list.png)

Consulte [Actividades](/help/main/c-activities/activities.md) para obtener información detallada acerca de los tipos de actividades disponibles en [!DNL Target] y para obtener más información acerca de la interfaz de usuario de la lista [!UICONTROL Activity].

## Audiencias

Haga clic en la ficha **[!UICONTROL Audiences]** para mostrar la lista [!UICONTROL Audiences], donde puede crear audiencias y administrar las existentes.

![Lista de audiencias](/help/main/c-intro/assets/audience-list.png)

Una audiencia es un grupo de participantes con características similares en una actividad a los se les dirige una actividad. Una audiencia es un grupo de personas con las mismas características, como un visitante nuevo, un visitante habitual o un visitante habitual de la zona oeste. La característica [!UICONTROL Audience] le permite segmentar contenido y experiencias diferentes para optimizar el marketing digital mostrando los mensajes adecuados para la persona adecuada y en el momento adecuado. Si un visitante se identifica como parte de una audiencia objetivo, [!DNL Target] determina qué experiencia se mostrará según los criterios definidos durante la creación de la actividad.

Consulte [Crear audiencias](/help/main/c-target/c-audiences/create-audience.md) para obtener información detallada acerca de los tipos de audiencia en [!DNL Target] y para obtener más información acerca de la interfaz de usuario de la lista [!UICONTROL Audience].

## Ofertas

Haga clic en la ficha **[!UICONTROL Offers]** para mostrar la lista [!UICONTROL Offers], donde puede crear experiencias y ofertas y administrar las experiencias y ofertas existentes.

![Lista de ofertas](/help/main/c-intro/assets/offers.png)

Una experiencia puede ser una oferta, imagen, texto, botón, vídeo, una combinación de estos elementos en una página, una página web completa o un conjunto de páginas que quizás forman un canal de compras o cualquier otra secuencia lógica de páginas. También puede ser la respuesta de un ayudante de voz, un script de servicio al cliente o incluso un sabor personalizado de una máquina de bebidas. Las experiencias se prueban o personalizan en actividades de [!DNL Target].

Consulte [Ofertas](/help/main/c-experiences/c-manage-content/manage-content.md) para obtener información detallada acerca de los tipos de ofertas en [!DNL Target] y para obtener más información acerca de la interfaz de usuario de la lista [!UICONTROL Offer].

## Recommendations

Haga clic en la ficha **[!UICONTROL Recommendations]** para tener acceso a [!DNL Target Recommendations].

>[!NOTE]
>
>Las actividades de Recommendations están disponibles como parte de la solución [!DNL Target Premium]. No están disponibles en [!DNL Target Standard] sin una licencia de [!DNL Target Premium]. Para obtener más información, consulte [Target Premium](/help/main/c-intro/intro.md#premium) en *Introducción a Target*.

![Recomendaciones](/help/main/c-intro/assets/recommendations.png)

Las actividades de [!UICONTROL Recommendations] muestran automáticamente productos o contenido que podría interesar a sus clientes, en función de la actividad previa del usuario u otros algoritmos. Recommendations le ayuda a dirigir a los clientes hacia artículos relevantes que es posible que no conozcan de otra manera.

Consulte [Recommendations](/help/main/c-recommendations/recommendations.md) para obtener información detallada sobre [!UICONTROL Recommendations] en [!DNL Target] y para obtener más información sobre la interfaz de usuario de [!UICONTROL Recommendations].

## Administración

Haga clic en la ficha **[!UICONTROL Administration]** para tener acceso a las páginas de [!UICONTROL Administration].

![Páginas de administración](/help/main/c-intro/assets/administration.png)

Las páginas de [!UICONTROL Administration] le permiten administrar [!DNL Target], incluidos los ajustes de configuración de [!UICONTROL Visual Experience Composer] (VEC), informes, configuración de [!DNL Scene7], implementación, hosts, entornos, tokens de respuesta y usuarios.

Consulte [Información general sobre la administración de Target](/help/main/administrating-target/administrating-target.md) para obtener información detallada y obtener más información acerca de la interfaz de usuario.
