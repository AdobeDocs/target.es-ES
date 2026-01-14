---
keywords: espacios de trabajo;administrar propiedad;permisos;configuración de producto;perfil de producto;roles;proyecto;observador;editor;aprobador;publicador
description: Obtenga información sobre cómo crear espacios de trabajo (perfiles de producto) independientes y, a continuación, asignar a los usuarios diferentes funciones y permisos para páginas, propiedades o sitios web individuales.
title: ¿Qué son los permisos de usuario de Enterprise y cómo se utilizan?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Administration & Configuration
role: Admin
exl-id: 838abe87-dba7-4274-97b4-31a7905846dc
source-git-commit: 122484056e73f8f679312a3e776e623d905701d5
workflow-type: tm+mt
source-wordcount: '3166'
ht-degree: 48%

---

# Permisos de usuario de Enterprise

Los permisos de usuario de Enterprise son un medio para administrar formalmente el acceso de usuarios de nivel Enterprise a [!DNL Adobe Target]. Agregue usuarios a [!DNL Target], asigne permisos según sus funciones y cree espacios de trabajo para equipos en función de diferentes departamentos, ubicaciones globales, canales y otras agrupaciones lógicas. Puede asignar a los usuarios los roles de [!UICONTROL Observer], [!UICONTROL Editor], [!UICONTROL Approver] o [!UICONTROL Publisher].

{{permissions-update}}

## Determine si tiene acceso a los permisos de usuario de Enterprise

>[!NOTE]
>
>La funcionalidad [!UICONTROL Properties and Permissions] está disponible como parte de la solución [!DNL Target] Premium. No están disponibles en [!DNL Target] Estándar sin una licencia de [!DNL Target] Premium.
>
>Su implementación de [!DNL Target] puede utilizar cualquier versión de at.js o [!DNL Adobe Experience Platform Web SDK].

Puede comprobar si su organización dispone de una licencia Standard o Premium haciendo clic en el vínculo [!UICONTROL Administration] en la parte superior de la interfaz de usuario de [!DNL Target].

* **[!DNL Target Standard]clientes**: Si ve la ficha [!UICONTROL Users] ([!UICONTROL Administration > Users]) (y no la ficha [!UICONTROL Properties]), su organización dispone de una licencia de [!DNL Target Standard]. Los clientes de [!DNL Target Standard] deben seguir las instrucciones de [Usuarios](/help/main/administrating-target/c-user-management/c-user-management/user-management.md) para agregar usuarios y asignar permisos en [!DNL Adobe Admin Console].

* **[!DNL Target Premium]clientes**: Si ve la ficha [!UICONTROL Properties] ([!UICONTROL Administration > Properties]) y la ficha [!UICONTROL Users], su organización dispone de una licencia de [!DNL Target Premium]. Los clientes de [!DNL Target Premium] deben seguir las instrucciones de este artículo y de [Configurar los permisos de Enterprise](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md).

## Antes de empezar a usar los permisos de Enterprise

>[!IMPORTANT]
>
>Asegúrese de leer la sección [Advertencias](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#section_9714311B1CD9497A86F4910F8AE635E2) a continuación antes de continuar con los permisos de Enterprise.

## Términos y definiciones utilizados en esta sección {#section_F8D229544FEA41C3BC2EFD1F95AA0116}

En esta sección se usan los siguientes términos, que pueden ser nuevos para los usuarios que desean usar la funcionalidad Propiedades y Permisos en [!DNL Target] Premium.

### Propiedad

Las propiedades son similares a las propiedades de [!DNL Adobe Experience Platform], ya que utilizan un único fragmento de código para diferenciarlas.

Una propiedad web es una biblioteca de reglas y un código incrustado. Una propiedad web puede ser cualquier conjunto de uno o varios dominios y subdominios.

Las propiedades se habilitan agregando un par nombre/valor específico como parámetro con cualquier llamada (llamada de Target, llamada de API, etc.) a [!DNL Target].

Las propiedades pertenecen a canales específicos (web, móvil, correo electrónico o API/otros).

### Espacio de trabajo (perfil de producto) {#workspace}

Un espacio de trabajo permite que una organización asigne un conjunto de usuarios específico a un conjunto de propiedades concretas. En muchos aspectos, un espacio de trabajo es parecido a un grupo de informes en [!DNL Adobe Analytics].

Nota: Los espacios de trabajo se conocen como [!UICONTROL Product Profiles] en [!DNL Adobe Admin Console for Enterprise].

Si forma parte de una organización multinacional, puede tener un espacio de trabajo para sus páginas web, propiedades o sitios europeos y otro para sus páginas web, propiedades o sitios estadounidenses. Si forma parte de una organización de varias marcas, puede contar con un espacio de trabajo independiente para cada una.

Los usuarios pueden formar parte de varios espacios de trabajo y pueden incluso tener diferentes roles en cada uno de ellos.

Los usuarios pueden tener diferentes vistas de [!DNL Adobe Target] si se mueven entre espacios de trabajo, de manera similar a como los usuarios de [!DNL Analytics] tienen diferentes vistas de [!DNL Analytics] si se mueven entre grupos de informes.

Los espacios de trabajo pueden incluir audiencias, ofertas de código y actividades completamente diferentes.

Todas las audiencias y actividades creadas antes de la migración al modelo de permisos de Enterprise se agrupan en la sección &quot;Workspace predeterminado&quot; que se trata a continuación.

Todas las actividades creadas a través de [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] y [!DNL Adobe Target Classic] forman parte de la &quot;Workspace predeterminada&quot;.

### Workspace predeterminado

Todos los espacios de trabajo existentes (perfiles de producto) dentro de [!DNL Admin Console] se combinan en uno solo denominado &quot;Workspace predeterminado&quot; durante la migración de su organización al nuevo modelo de permisos de Enterprise.

>[!IMPORTANT]
>
>No elimine el espacio de trabajo predeterminado.

Todos los roles de usuario y el acceso a todas las funcionalidades de [!DNL Target] siguen siendo los mismos que antes de la migración al nuevo modelo de permisos de Enterprise.

### Grupos de usuarios

Puede crear grupos de usuarios, como desarrolladores, analistas, especialistas en marketing y ejecutivos. A continuación, puede asignar privilegios en varios productos y espacios de trabajo de Adobe. Asignar todos los privilegios apropiados en diferentes productos de Adobe a un nuevo miembro del equipo puede ser tan fácil como añadirlos a un grupo de usuarios específico.

### Funciones y permisos {#roles-permissions}

Las funciones y los permisos determinan los niveles de acceso que tienen los usuarios para crear y administrar actividades en su implementación de [!DNL Target]. En [!DNL Target], los roles incluyen lo siguiente:

| Función | Descripción |
|--- |--- |
| [!UICONTROL Approver] | Puede crear, editar y activar o detener actividades. |
| [!UICONTROL Editor] | Puede crear y editar actividades antes de que estén activas, pero no puede aprobar el lanzamiento de una actividad. |
| [!UICONTROL Observer] | Puede ver actividades, pero no puede crearlas o editarlas. |
| [!UICONTROL Publisher] | Similar al rol [!UICONTROL Observer] (puede ver actividades, pero no puede crearlas o editarlas). Sin embargo, el rol [!UICONTROL Publisher] tiene el permiso adicional de activar actividades. |

### Canal

El canal se refiere al tipo de contenido desde donde se entregan sus actividades [!DNL Target]: páginas web, aplicaciones móviles, mensajes de correo electrónico, etc.

Al crear una actividad, esta se crea en el espacio de trabajo seleccionado. Verá las opciones de selección de canales en el primer cuadro de diálogo que le permite elegir el canal deseado para la actividad: web, aplicación móvil, correo electrónico o API/otro.

## Resumen de permisos {#section_DC2172520DA84605B218A5E9FB6D187A}

La siguiente información explica cómo se aplicaban los permisos anteriormente en [!DNL Target] y cómo se aplican usando la funcionalidad [!UICONTROL Properties] y [!UICONTROL Permissions].

La nueva funcionalidad [!UICONTROL Permissions] le permite crear diferentes proyectos (llamados &quot;perfiles de producto&quot; en [!DNL Adobe Admin Console for Enterprise]). Los proyectos le permiten asignar a un único usuario diferentes permisos que dictan sus derechos de acceso a cada proyecto. Estos proyectos independientes pueden compararse con el modo en el que funcionan los grupos de informes en [!DNL Adobe Analytics]. Cada proyecto tiene usuarios específicos con funciones específicas que se aplican a un conjunto de propiedades. El resultado es que los clientes pueden restringir el acceso de visualización, edición y aprobación a sus usuarios en función de la región, el entorno (dev/stage/prod), el canal u otros criterios personalizados, como se muestra a continuación:

![imagen de permisos](assets/permissions.png)

Por ejemplo, un usuario determinado puede tener el acceso de aprobación en los sitios web de América, pero solo el acceso de visualización en la aplicación móvil europea. Ese mismo usuario puede no tener acceso ni siquiera a la visualización de las actividades ofrecidas en propiedades web y móviles en la región Asia-Pacífico.

El modelo [!DNL Target] [!UICONTROL Permissions] tiene las siguientes funciones de permiso (Observador, Editor, Aprobador y Observador). La función de observador no aparece en las ilustraciones de este artículo.

![permisos_1 imagen](assets/permissions_1.png)

Cada función tiene diferentes niveles de permisos:

| Función | Descripción |
|--- |--- |
| Aprobador | Puede crear, editar y activar o detener actividades. |
| Editor | puede crear y editar actividades antes de que estén activas, pero no puede aprobar el lanzamiento de una actividad. |
| Observador | Puede ver actividades, pero no puede crearlas o editarlas. |
| Editor | Similar a la función Observador (puede ver actividades, pero no puede crearlas o editarlas). Sin embargo, la función Publicador tiene el permiso adicional de activar actividades. |

Es importante tener en cuenta que la función de cada usuario se aplica a cada página, propiedad o sitio de su cuenta que incluya etiquetas de [!DNL Target] como se muestra a continuación:

![imagen permissions_2](assets/permissions_2.png)

El nuevo modelo [!DNL Target] [!UICONTROL Permissions] tiene las mismas funciones de permiso (Observador, Editor y Aprobador); sin embargo, puede asignar las funciones de permiso de un usuario por separado para páginas, propiedades o sitios individuales, como se muestra a continuación:

![imagen permissions_3](assets/permissions_3.png)

En este ejemplo, Jan tiene permisos de aprobador en la página principal y el sitio de EE. UU. y permisos de observador en el sitio de Francia.

Además, Jan no puede ver páginas, propiedades ni sitios en [!DNL Target] para los que no tiene permiso, como se muestra a continuación:

![imagen permissions_4](assets/permissions_4.png)

En este ejemplo, Jan no ve las páginas de producto, el sitio de Rusia ni el sitio de ofertas de empleo.

## Casos de uso {#section_F3CE8576959E4F4CB13BEEED38311DD8}

En los siguientes casos de uso, trataremos de explicar cómo lograr los objetivos de marketing con ayuda de las propiedades, los proyectos y las funciones de [!DNL Target]:

### Organización multinacional

Si forma parte de una organización multinacional, puede tener un espacio de trabajo para sus páginas web, propiedades o sitios europeos y otro para sus páginas web, propiedades o sitios estadounidenses. 
Usando los personajes de las ilustraciones anteriores, tras una reorganización, podría configurar los espacios de trabajo y permisos de este modo:

* **Jan:** Jan es la jefa de optimización del Centro de excelencia para las páginas web, las propiedades y los sitios estadounidenses de la organización. Es muy probable que tenga derechos de administración del sistema en Adobe Experience Cloud.

  Con su función, tiene permisos de aprobación en la página principal y el sitio de EE. UU. Con el permiso de Aprobador, puede crear, editar y activar o detener actividades.

  Jan también realiza consultas al equipo de optimización de Francia, por lo que tiene permisos de observación en el sitio francés que le otorgan acceso de solo lectura a las actividades. Jan puede ver actividades, pero no puede crearlas o editarlas.

  Como no tiene ninguna función que le exija ver las páginas de productos, el sitio de Rusia ni el sitio de ofertas de empleo, no ve las actividades relacionadas con estos sitios.

* **Ernie:** Ernie trabaja como administrador de marketing en la organización que se encarga del marketing de EE. UU.

  Como Ernie lleva poco tiempo en la organización y no tiene experiencia con Target, tiene permisos de edición en la página principal y el sitio de EE. UU. y en las páginas de productos. Con permisos de editor, Ernie puede crear y editar actividades antes de que estén activas. No puede aprobar el lanzamiento de una actividad: alguien con permiso de aprobación, como Jan, debe aprobar la actividad antes de que se pueda poner en producción.

  Como no tiene ninguna función que le exija ver el sitio de Rusia, el sitio de Francia ni el sitio de ofertas de empleo, no ve las actividades relacionadas con estos sitios.

* **Diana:** Diana trabaja como analista en la organización y se le han concedido permisos de observación en la página principal y el sitio de EE. UU., las páginas de producto, el sitio de Rusia y el sitio de Francia. Con estos permisos tiene acceso de solo lectura a las actividades. Diana puede ver actividades, pero no puede crearlas o editarlas.

  Como no tiene ninguna función que le exija ver el sitio de ofertas de empleo, no ve las actividades relacionadas con este sitio.

### Organización de varias marcas

Si forma parte de una organización de varias marcas, puede contar con un espacio de trabajo independiente para cada página web, propiedad o sitio de la marca.

Usando los personajes de las ilustraciones anteriores, tras una reorganización podría configurar los proyectos y permisos de este modo:

* **Jan:** Jan es la jefa de optimización del Centro de excelencia de una organización sanitaria que trabaja en el ámbito de productos para hospitales y consumidores. Es muy probable que tenga derechos de administración del sistema en Adobe Experience Cloud.

  Con su función, tiene permisos de aprobación en el sitio del hospital. Con el permiso de Aprobador, puede crear, editar y activar o detener actividades.

  Jan también realiza consultas al equipo de optimización en el ámbito de productos para consumidores, por lo que tiene permisos de observación en el sitio correspondiente que le otorgan acceso de solo lectura a las actividades. Jan puede ver actividades, pero no puede crearlas o editarlas.

* **Ernie:** Ernie trabaja como administrador de marketing en la organización que se encarga del marketing en el ámbito de productos para consumidores.

  Como Ernie lleva poco tiempo en la organización y no tiene experiencia con Target, tiene permiso de edición en el sitio para consumidores. Con permisos de editor, Ernie puede crear y editar actividades antes de que estén activas. No puede aprobar el lanzamiento de una actividad: alguien con permisos de aprobación para el sitio del consumidor, pero no Jan en este caso, debe aprobar la actividad antes de que se pueda poner en producción.

  Como no tiene ninguna función que le exija ver el sitio del hospital, no ve las actividades relacionadas con estos sitios.

* **Diana:** Diana trabaja como analista en la organización y se le han concedido permisos de observación en el sitio del hospital y el sitio para consumidores. Con estos permisos tiene acceso de solo lectura a las actividades. Diana puede ver actividades, pero no puede crearlas o editarlas.

## Puntos de contacto de propiedad y permisos de IU de Target {#section_3414371393BB42999A268628B5456EC9}

La nueva funcionalidad Permisos puede verse en diferentes sitios de la interfaz de usuario de [!DNL Target].

* **Lista desplegable de Workspace (Perfil de producto):** La lista desplegable de Workspace se muestra en la parte superior de las páginas [!UICONTROL Activities], [!UICONTROL Audiences] y [!UICONTROL Offers]. Seleccione el espacio de trabajo deseado para filtrar la lista y mostrar únicamente los elementos de dicho espacio de trabajo.

* **Creación de actividades:** Al crear una actividad, esta se crea en el área de trabajo seleccionada actualmente. Verá las opciones de selección de canales en el primer cuadro de diálogo que le permite elegir el canal deseado para la actividad: web, aplicación móvil, correo electrónico o API/otro.

* **Creación de audiencias:** Al crear una audiencia, esta se crea en el área de trabajo seleccionada actualmente.
* **Lista de audiencias:** Puede mover audiencias entre espacios de trabajo mediante la opción [!UICONTROL More Actions] > [!DNL Move] en la página [!UICONTROL Audiences].
* **Creación de oferta:** Al crear una oferta, esta se crea en el área de trabajo seleccionada actualmente.
* **Página Propiedades (Administración > Propiedades):** Puede usar el cuadro [!UICONTROL Search] para buscar en la lista [!UICONTROL Property].

## Advertencias  {#section_9714311B1CD9497A86F4910F8AE635E2}

Tenga en cuenta lo siguiente al utilizar o configurar propiedades y permisos en [!DNL Target] Premium:

* **Importante**: No elimine espacios de trabajo con actividades. Si elimina un espacio de trabajo con actividades, trabaje con Atención al cliente para recuperar esas actividades.
* Al utilizar la vista Todos mis espacios de trabajo:

   * Puede ver las actividades, audiencias y ofertas de todos los espacios de trabajo para los que tenga el rol adecuado y permiso de acceso.
   * Al seleccionar la vista [!UICONTROL All My Workspaces], se agrega una nueva columna a la página Actividades, Audiencias y Ofertas. En esta columna se muestra el espacio de trabajo del elemento y los permisos de usuario asociados a dicho elemento (Observador, Editor o Aprobador).
   * Al crear una actividad, público u oferta en la vista Todos mis espacios de trabajo, debe seleccionar el espacio de trabajo donde se creará el elemento. Solo podrá seleccionar los espacios de trabajo para los que disponga del permiso Editor o Aprobador.
   * Al copiar una actividad, público u oferta en la vista Todos mis espacios de trabajo, debe seleccionar el espacio de trabajo donde se copiará el elemento. Solo podrá seleccionar los espacios de trabajo para los que disponga del permiso Editor o Aprobador.

* Cualquier configuración en las siguientes páginas de [!UICONTROL Administration] puede ser controlada por cualquier [!UICONTROL Approver] en cualquier espacio de trabajo:

   * Compositor de experiencias visuales
   * Creación de informes
   * Configuración de Scene7
   * Implementación
   * Propiedades
   * Hosts
   * Entornos
   * Tokens de respuesta
   * Usuarios

* Los usuarios no pueden mover recursos de un espacio de trabajo (perfil de producto) a otro. Sin embargo, sí se permite la copia.
* Si visualiza los públicos desde la página [!DNL Audiences], la página carga más lento de lo esperado. Si interactúa con la barra de búsqueda de cualquier forma, las audiencias se muestran más rápido. Este problema se conoce y se solucionará en una actualización próxima. Este problema no afecta a la selección de audiencias durante el flujo de trabajo de creación de actividades.
* Los siguientes recursos son parte del nuevo modelo de permisos de Enterprise:

   * Las actividades, audiencias y ofertas de código creadas en [!DNL Target Standard/Premium] están disponibles para su uso una vez que el cliente haya habilitado los permisos. (Nota: los clientes deben tener derecho a [!DNL Target Premium].)
   * Las propiedades se pueden añadir a las actividades existentes en la Workspace predeterminada; sin embargo, este método está sujeto a cambios.
   * Solo los nuevos recursos (como actividades, ofertas de código y audiencias) creados en Target Premium (una vez habilitados los permisos de Enterprise) se pueden restringir mediante permisos.
   * Los recursos externos solo están disponibles para los usuarios en el espacio de trabajo predeterminado. El rol de un usuario en el espacio de trabajo predeterminado se aplica globalmente (a todas las solicitudes y recursos de Target).

* Los siguientes recursos *no* son parte del nuevo modelo de permisos de Enterprise:

   * Ofertas de imágenes
   * Todos los recursos de Recommendations, incluidos la Biblioteca de criterios, Biblioteca de diseños, Catálogo, Configuración de Recommendations.
   * Los recursos existentes (como actividades, ofertas de código y audiencias) creados en Target Premium antes de habilitar los permisos de Enterprise se pueden copiar, pero no se pueden mover a otros espacios de trabajo.
   * Las actividades, audiencias, ofertas de código, ofertas de imágenes o cualquier otro recurso creado con las siguientes soluciones o métodos no se pueden controlar mediante el modelo de permisos de Enterprise, pero forman parte de la Workspace predeterminada: Target Classic, Adobe Experience Manager (AEM), Adobe Mobile Services y recursos creados mediante API. Recursos creados mediante API (incluidas actividades, públicos, ofertas de código y ofertas de imagen).
   * Actualmente, las ofertas de imagen (recursos almacenados en `https://[tenantName].marketing.adobe.com/content/mac/[tenantName]/target/offers.html#image-library`) no se pueden controlar mediante el modelo de permisos de Enterprise.
   * clickTracking y las redirecciones funcionan cuando el vínculo de destino o la página de destino son parte de una propiedad incluida en la actividad. Además, es posible que clickTracking no funcione al utilizar la función `targetPageParams()`. La función recomendada es `targetPageParamsAll()`.

  [!DNL Target] requiere actualmente un token `at_property` en cualquier página donde se realice un seguimiento. Si el token (1) no está presente, (2) no se detecta a la hora de configurar la actividad (en el VEC) o (3) no se pasa a la llamada de Target de rastreo de clics a través de la función `targetPageParamsAll()`, la métrica no se incrementa y aparece como &quot;0&quot;.

  Lo mismo se aplica a las actividades que usan redirecciones. La página de destino debe tener un token `at_property` y se debe reconocer cuando se configura en el VEC.

  En una versión futura, Target funcionará en páginas donde no haya presente un token `at_property`, o donde exista un token `at_property` distinto.

* La funcionalidad Permisos de usuario de Enterprise no se admite en las llamadas a la API de Adobe Developer.

## Preguntas frecuentes {#faqs}

Las preguntas más frecuentes sobre permisos de Enterprise incluyen las siguientes:

### ¿Qué sucede si un usuario tiene varias funciones y permisos? {#multiple-roles}

Si un usuario tiene varias funciones y varios permisos, se aplica la función con los permisos de contratante. Por ejemplo, si un usuario tiene los roles [!UICONTROL Observer] y [!UICONTROL Approver], se aplica el rol [!UICONTROL Approver].

### ¿Puedo trasladar una actividad de un espacio de trabajo a otro?

Por desgracia, las actividades no se pueden trasladar de un espacio de trabajo a otro. Sin embargo, puede copiar una actividad en cualquier espacio de trabajo sabiendo que los datos de los informes no se transfieren. Para obtener más información, consulte “Copiar/editar una actividad al utilizar espacios de trabajo” en [Copiar/Editar una actividad al usar espacios de trabajo.](/help/main/c-activities/edit-activity.md#section_45A92E1DD3934523B07E71EF90C4F8B6)

Las actividades creadas antes de la migración se siguen ejecutando del mismo modo en el espacio de trabajo predeterminado, a menos que se editen y se les asignen propiedades. Las actividades bajo una propiedad de honor de espacio de trabajo específica asignada a ese espacio de trabajo y, por lo tanto, el comportamiento podría no ser el mismo que antes de la migración.

### ¿Puedo trasladar un público de un espacio de trabajo a otro? {#move-audience}

Sí, puede mover audiencias entre espacios de trabajo mediante la opción [!UICONTROL More Actions] en la página [!UICONTROL Audiences].

1. Haga clic en el botón **[!UICONTROL More Actions]** (los tres puntos suspensivos) y luego haga clic en **[!UICONTROL Move]**.

   ![Más acciones > Mover](/help/main/administrating-target/c-user-management/property-channel/assets/move-audience.png)

1. Seleccione el área de trabajo que desee en la lista desplegable **[!UICONTROL Workspace]** y luego haga clic en **[!UICONTROL Move]**.

   ![Seleccione la audiencia que desee para pasar al nuevo espacio de trabajo](/help/main/administrating-target/c-user-management/property-channel/assets/workspace-move.png)

>[!NOTE]
>
>Debe tener los derechos adecuados para editar una audiencia. Además, la audiencia no debe utilizarse en otras actividades. Si la audiencia se está utilizando en otras actividades y desea trasladarla a otro lugar de trabajo, elimine la audiencia de las demás actividades en las que se esté utilizando.

### ¿Por qué aparece un mensaje de error que indica que no hay ninguna propiedad asociada con esta actividad, aunque haya una propiedad asignada?

Si ha implementado [!DNL Target] con etiquetas en [!DNL Adobe Experience Platform] y ha obtenido un mensaje de error que indica que no hay ninguna propiedad asociada con la actividad, pase el parámetro `at_property` con la función `targetPageParams`.

### ¿Se registran conversiones de rastreo de clics si una página redirigida y la dirección URL de actividad pertenecen a propiedades diferentes?

El rastreo de clics no se registra en páginas en las que la URL de la página y de la actividad pertenecen a propiedades diferentes.

Imagine la siguiente situación:

* Página1 pertenece a Propiedad1.
* Página2 pertenece a Propiedad2.
* En la actividad, Página1 redirige a Página2, que contiene los rastreos de clics.

Cuando un visitante abre Página1 en un explorador, se redirige al visitante a Página2. Debido a que Página2 no cumple los requisitos para entregar la actividad, su llamada de Target no contiene rastreos de clics en su respuesta.

Si la página de redirección y la dirección URL de la actividad pertenecen a la misma propiedad, los rastreos de clics funcionan según lo esperado. Para obtener más información, consulte [Rastreo de clics](/help/main/c-activities/r-success-metrics/click-tracking.md).

## Vídeos de formación

Los siguientes vídeos contienen más información sobre los conceptos mencionados en este artículo.

### Vídeo de formación: Permisos de Enterprise Vídeo de formación ![Distintivo de información general](/help/main/assets/overview.png)

Objetivos de aprendizaje:

* Los tres roles que pueden tener los usuarios de Adobe Target
* Los conceptos de propiedad y espacio de trabajo, y cómo operan estos límites y agrupamientos para permitir controlar el nivel de acceso de los usuarios
* Diferentes ejemplos de propiedades para la consideración de su organización

>[!VIDEO](https://video.tv.adobe.com/v/19042/)

### Horario de oficina: [!DNL Target] espacios de trabajo Premium

Este vídeo es una grabación de “Horario de oficina”, una iniciativa dirigida por el equipo de atención al cliente de Adobe.

* Creación de un espacio de trabajo (perfil de producto)
* Creación de propiedades
* Adición de usuarios
* Actualización de la implementación

>[!NOTE]
>
>La interfaz de usuario del menú [!DNL Target] [!UICONTROL Administration] (anteriormente [!UICONTROL Setup]) se ha rediseñado para proporcionar un rendimiento mejorado, reducir el tiempo de mantenimiento necesario al lanzar nuevas características y mejorar la experiencia del usuario en todo el producto. La información del siguiente vídeo es correcta; sin embargo, las opciones pueden estar en ubicaciones ligeramente diferentes.

>[!VIDEO](https://video.tv.adobe.com/v/23643/)
