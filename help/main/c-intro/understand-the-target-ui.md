---
keywords: interfaz de usuario de target;interfaz de usuario;iu;anuncios;eventos;notificaciones
description: Familiarícese con la interfaz de usuario y encuentre vínculos a información más detallada para ayudarle a sacar el máximo partido de [!DNL Target].
title: ¿Cómo se utiliza la IU de  [!DNL Target] ?
feature: Overview
exl-id: ce4c72b2-b635-406b-9830-650816445a64
source-git-commit: 6bef27637c06f39ffc0e755f19e8a0870ec749e5
workflow-type: tm+mt
source-wordcount: '1345'
ht-degree: 49%

---

# Información sobre la IU de [!DNL Target]

La interfaz de usuario está organizada en un formato lógico y fácil de usar para ayudarle a sacar el máximo partido a [!DNL Adobe Target]. La siguiente descripción general breve le ayudará a familiarizarse con [!DNL Target] y proporciona vínculos para obtener información más detallada e instrucciones paso a paso.

El encabezado situado en la parte superior del [!DNL Target] La interfaz de usuario de contiene pestañas y opciones que le ayudarán a navegar por las diferentes funcionalidades de la solución. También puede cambiar de organización y [!DNL Adobe Experience Cloud] soluciones, obtener ayuda y notificaciones, administrar su [!DNL Adobe] perfil y cierre la sesión de [!DNL Target].

![Encabezado de Target](/help/main/c-intro/assets/target-header.png)

Las pestañas del lado izquierdo permiten acceder a las distintas funcionalidades de [!DNL Target], que se analiza más adelante. Empecemos por hablar de las opciones del lado derecho antes de saltar a las pestañas.

## Organizaciones

Una *organización* es la entidad que habilita un administrador a fin de configurar grupos y usuarios, y para controlar el inicio de sesión único en [!DNL Adobe Experience Cloud]. La organización funciona como una empresa de inicio de sesión que abarca todos los productos y soluciones de [!DNL Experience Cloud]. La mayoría de las veces, la organización es el nombre de empresa. Sin embargo, una empresa puede tener muchas organizaciones.

Seleccione la organización que desee en la lista desplegable [!UICONTROL Organización] si su compañía tiene varias organizaciones:

![Lista desplegable Organización](/help/main/c-intro/assets/organizations.png)

## Aplicaciones

El conmutador Aplicaciones le permite acceder rápidamente a las soluciones de [!DNL Adobe Experience Cloud] a las que tiene acceso.

![Conmutador de aplicaciones](/help/main/c-intro/assets/apps.png)

## Ayuda

El icono Ayuda le permite acceder a información, vídeos, blogs y mucho más para ayudarle a utilizar [!DNL Target] de forma más eficaz. Puede crear un ticket de asistencia, encontrar números de teléfono de asistencia, hacer preguntas a través de Twitter o proporcionar comentarios sobre [!DNL Target] para hacernos saber cómo [!DNL Target] equipo está haciendo.

![Ayuda](/help/main/c-intro/assets/help.png)

## Notificaciones y anuncios {#notifications-announcements}

Los paneles [!UICONTROL Notificaciones] y [!UICONTROL Anuncios] le ayudan a estar al día acerca de todas las cosas de [!DNL Adobe Target]. Las notificaciones dinámicas ayudan a mantenerle al día del estado de [!DNL Adobe Experience Cloud] soluciones y [!DNL Target] eventos. Las notificaciones proactivas le avisan sobre eventos de interrupción y eventos de mantenimiento.

Haga clic en el icono de campana del encabezado para ver las notificaciones:

![Icono de campana para notificaciones y anuncios](assets/bell-icon.png)

El panel contiene pestañas para [!UICONTROL Notificaciones] y [!UICONTROL Anuncios].

![ Notificaciones ](assets/notifications.png)

Las secciones siguientes contienen información sobre cada pestaña y cómo configurar las notificaciones y los anuncios:

###  Notificaciones  {#notifications}

[!DNL Target] Las notificaciones de eventos incluyen lo siguiente:

* **Actividades**: notificaciones para todos los tipos de actividades cuando se aprueba o desactiva una actividad, ya sea manualmente o cuando llega a su fecha de inicio o de finalización. La notificación incluye el nombre de la actividad con un vínculo a la página de información general de la actividad.

   Las notificaciones se pueden configurar y reciben, de forma predeterminada, los administradores de productos, los editores y los aprobadores en el espacio de trabajo de la actividad para [!DNL Target Premium] cuentas. Para [!DNL Target Standard] cuentas, las notificaciones las reciben todos los editores y aprobadores.

   Las notificaciones tienen el formato de los siguientes ejemplos:

   * `Activity {target.activity.name} has been activated`

   * `Activity {target.activity.name} has been deactivated`

* **Scripts de perfil**: notificaciones cuando se activa o desactiva un script de perfil, ya sea de forma manual o por parte de [!DNL Target].

   Las notificaciones son configurables y se reciben, de forma predeterminada, por los administradores de productos y los aprobadores para ambos [!DNL Target Premium] y [!DNL Target Standard] cuentas.

   Las notificaciones tienen el formato de los siguientes ejemplos:

   * `Profile Script {target.profileScript.name} has been activated`
   * `Profile Script {target.profileScript.name} has been deactivated`

* **Fuentes de**[!DNL Recommendations]: notificaciones cuando se activa o desactiva una fuente de Recommendations, ya sea de forma manual o por parte de [!DNL Target]. Las notificaciones también se envían cuando [!DNL Recommendations] la fuente falla.

   Las notificaciones son configurables y se reciben, de forma predeterminada, por los administradores de productos y los aprobadores de [!DNL Target Premium] cuentas. [!DNL Recommendations] es un [!DNL Target Premium] y no está disponible en [!DNL Target Standard].

   Las notificaciones tienen el formato de los siguientes ejemplos:

   * `Feed  {target.feed.name} has been activated`
   * `Feed {target.feed.name} has been deactivated`
   * `Feed {target.feed.name} has failed`
   * `Feed {target.feed.name} has failed to import from source`

Puede marcar las notificaciones individuales como leídas pasando el puntero sobre la notificación deseada y haciendo clic en la marca de verificación. Puede marcar todas las notificaciones como leídas o ver todas las notificaciones haciendo clic en [!UICONTROL &quot;Marcar como leído&quot;] o [!UICONTROL &quot;Ver todo&quot;] en la parte inferior del panel.

También puede configurar un recordatorio para que se le notifique de nuevo pasando el puntero sobre una notificación y haciendo clic en el icono &quot;[!UICONTROL Recordatorio]&quot; y, a continuación, seleccione cuándo desea recibir la notificación: 5 minutos, 15 minutos, una hora o mañana.

### Anuncios

Las notificaciones proactivas le avisan sobre eventos de interrupción y eventos de mantenimiento.

Encontrará información más detallada en la página [Adobe Status.](https://status.adobe.com/)

### Configuración de notificaciones y anuncios

Para editar las preferencias de notificaciones:

1. Haga clic en el icono de engranaje y luego en **[!UICONTROL Notificaciones]**.
1. En **[!UICONTROL Target]**, haga clic en **[!UICONTROL Personalizar]**.
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
   >Las únicas categorías de notificación aplicables a son &quot;Nuevas versiones&quot; y &quot;Actualizaciones de contenido&quot; [!DNL Target]. Las otras categorías se aplican a otras soluciones de Adobe.


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

La lista **[!UICONTROL Actividades]** es la vista predeterminada al abrir [!DNL Target]. Puede crear actividades desde esta página y administrar las actividades existentes.

![lista de actividades](/help/main/c-intro/assets/activities-list.png)

Consulte [Actividades](/help/main/c-activities/activities.md) para obtener información detallada acerca de los tipos de actividades disponibles en [!DNL Target] y para obtener más información sobre la interfaz de usuario de la lista [!UICONTROL Actividad].

## Audiencias

Haga clic en **[!UICONTROL Audiencias]** para mostrar la pestaña [!UICONTROL Audiencias] Lista donde se pueden crear audiencias y administrar las existentes.

![Lista de audiencias](/help/main/c-intro/assets/audience-list.png)

Una audiencia es un grupo de participantes con características similares en una actividad a los se les dirige una actividad. Una audiencia es un grupo de personas con las mismas características, como un visitante nuevo, un visitante habitual o un visitante habitual de la zona oeste. La funcionalidad [!UICONTROL Audiencia] le permite segmentar contenido y experiencias diferentes hacia audiencias específicas para optimizar el marketing digital mostrando los mensajes adecuados a la persona adecuada y en el momento adecuado. Si un visitante se identifica como parte de una audiencia objetivo, [!DNL Target] determina qué experiencia se mostrará según los criterios definidos durante la creación de la actividad.

Consulte [Crear audiencias](/help/main/c-target/c-audiences/create-audience.md) para obtener información detallada acerca de los tipos de audiencias en [!DNL Target] y para obtener más información sobre la interfaz de usuario de la lista [!UICONTROL Audiencia].

## Ofertas

Haga clic en **[!UICONTROL Ofertas]** para mostrar la pestaña [!UICONTROL Ofertas] lista donde puede crear experiencias y ofertas y administrar las experiencias y ofertas existentes.

![Lista de ofertas](/help/main/c-intro/assets/offers.png)

Una experiencia puede ser una oferta, imagen, texto, botón, vídeo, una combinación de estos elementos en una página, una página web completa o un conjunto de páginas que quizás forman un canal de compras o cualquier otra secuencia lógica de páginas. También puede ser la respuesta de un ayudante de voz, un script de servicio al cliente o incluso un sabor personalizado de una máquina de bebidas. Las experiencias se prueban o personalizan en actividades de [!DNL Target].

Consulte [Ofertas](/help/main/c-experiences/c-manage-content/manage-content.md) para obtener información detallada acerca de los tipos de oferta en [!DNL Target] y para obtener más información sobre la interfaz de usuario de la lista [!UICONTROL Oferta].

## Recomendaciones

Haga clic en la pestaña **[!UICONTROL Recomendaciones]** para acceder a [!DNL Target Recommendations].

>[!NOTE]
>
>Las actividades de Recommendations están disponibles como parte de la solución [!DNL Target Premium]. No están disponibles en [!DNL Target Standard] sin una licencia de [!DNL Target Premium]. Para obtener más información, consulte [Target Premium](/help/main/c-intro/intro.md#premium) en *Introducción a Target*.

![Recomendaciones](/help/main/c-intro/assets/recommendations.png)

Las actividades de [!UICONTROL Recommendations] muestran automáticamente productos o contenido que podría interesar a sus clientes en función de la actividad previa del usuario u otros algoritmos. Recommendations le ayuda a dirigir a los clientes hacia artículos relevantes que es posible que no conozcan de otra manera.

Consulte [Recomendaciones](/help/main/c-recommendations/recommendations.md) para obtener información detallada acerca de [!UICONTROL Recommendations] en [!DNL Target] y para obtener más información sobre la interfaz de usuario de [!UICONTROL Recommendations].

## Administración

Haga clic en la pestaña **[!UICONTROL Administración]** para acceder a las páginas de [!UICONTROL Administración].

![Páginas de administración](/help/main/c-intro/assets/administration.png)

Las páginas de [!UICONTROL Administración] le permiten administrar [!DNL Target], incluyendo los ajustes de configuración del [!UICONTROL Compositor de experiencias visuales] (VEC), informes, [!DNL Scene7] configuración, implementación, hosts, entornos, tokens de respuesta y usuarios.

Consulte [Información general sobre la administración de Target](/help/main/administrating-target/administrating-target.md) para obtener información detallada y obtener más información acerca de la interfaz de usuario.
