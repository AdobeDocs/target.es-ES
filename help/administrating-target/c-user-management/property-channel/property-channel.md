---
description: Información sobre la creación de propiedades y el uso de la funcionalidad Propiedades y Permisos, que permite a los administradores de Target crear espacios de trabajo (perfiles de producto) independientes en Target y asignar a los usuarios diferentes roles y permisos para determinadas páginas, propiedades o sitios web basados en dichos espacios de trabajo.
keywords: espacios de trabajo;administrar la propiedad;permisos;configuración de producto;perfil de producto;roles;proyecto
seo-description: Información sobre la creación de propiedades y el uso de la funcionalidad Propiedades y Permisos, que permite a los administradores de Target crear espacios de trabajo (perfiles de producto) independientes en Target y asignar a los usuarios diferentes roles y permisos para determinadas páginas, propiedades o sitios web basados en dichos espacios de trabajo.
seo-title: Permisos de usuario de Enterprise
solution: Target
subtopic: Primeros pasos
title: Permisos de usuario de Enterprise
title-outputclass: premium
topic: Premium
uuid: 1961730d-2357-406f-acac-a36b7a63bd35
badge: premium
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# ![PREMIUM](/help/assets/premium.png) Permisos de usuario de Enterprise{#enterprise-user-permissions}

Los permisos de usuario de Enterprise son un medio para administrar de forma formal el acceso de usuarios a nivel empresarial a Target. Agregue usuarios a Target, asigne permisos según sus funciones y cree espacios de trabajo para equipos en función de diferentes departamentos, ubicaciones globales, canal y otras agrupaciones lógicas. Puede asignar a los usuarios las funciones de Observador, Editor o Aprobador.

## Determinar si tiene acceso a permisos de usuario de Enterprise

>[!NOTE]
>
>La funcionalidad Propiedades y Permisos está disponible como parte de la solución Target Premium. No están disponibles en Target Standard sin una licencia de Target Premium.
>
>Su implementación de Target puede utilizar cualquier versión de at.js o mbox.js.

Puede comprobar si su organización dispone de una licencia Standard o Premium haciendo clic en el vínculo [!UICONTROL Configuración] en la parte superior de la interfaz de usuario de [!DNL Target]

* **[!DNL Target Standard]Clientes de**: si ve la pestaña [!UICONTROL Usuarios] ([!UICONTROL Configuración &gt; Usuarios]), su organización dispone de una licencia [!DNL Target Standard]. Los clientes de [!DNL Target Standard] deben seguir las instrucciones de [Usuarios](/help/administrating-target/c-user-management/c-user-management/user-management.md) para agregar usuarios y asignar permisos en Adobe Admin Console.

   [!DNL Target Standard]Los usuarios de verán el mensaje de error siguiente al hacer clic en la pestaña [!UICONTROL Propiedades]. No existe ningún problema con [!DNL Target]. Los usuarios de [!DNL Target Standard] no tienen acceso a la funcionalidad[!DNL Target Premium] [!UICONTROL Permisos de Enterprise de ].

   ![Mensaje de error](/help/administrating-target/c-user-management/property-channel/assets/sorry.png)

* Clientes de **[!DNL Target Premium]**: si ve la pestaña [!UICONTROL Propiedades] ([!UICONTROL Configuración &gt; Propiedades]), su organización dispone de una licencia de [!DNL Target Premium]. Los clientes de [!DNL Target Premium] deben seguir las instrucciones de este artículo y de [Configurar los permisos de Enterprise](/help/administrating-target/c-user-management/property-channel/properties-overview.md).

## Antes de comenzar con los permisos de Enterprise

>[!IMPORTANT]
>
>Asegúrese de leer la sección [Advertencias](../../../administrating-target/c-user-management/property-channel/property-channel.md#section_9714311B1CD9497A86F4910F8AE635E2) siguiente antes de seguir trabajando en los permisos de Enterprise.

## Términos y definiciones empleados en esta sección {#section_F8D229544FEA41C3BC2EFD1F95AA0116}

A continuación, indicamos los términos empleados en esta sección que pueden ser nuevos para los usuarios que usan la funcionalidad Propiedades y Permisos en Target Premium.

### Propiedad

Las propiedades son similares a las de la Dynamic Tag Management (Activation), en las que utilizan un único fragmento de código para diferenciarlas.

Una propiedad web es una biblioteca de reglas y un código incrustado. Una propiedad web puede ser cualquier conjunto de uno o varios dominios y subdominios.

Las propiedades se activan añadiendo un par nombre/valor específico como un parámetro con una llamada (mbox, api, etc.) a Target. 
Las propiedades pertenecen a canales específicos (web, móvil, correo electrónico o API/otros).

### Espacio de trabajo (perfil de producto)

Un espacio de trabajo permite que una organización asigne un conjunto de usuarios específico a un conjunto de propiedades concretas. En muchos aspectos, un espacio de trabajo es parecido a un grupo de informes en Adobe Analytics.

Nota: Los espacios de trabajo se denominan perfiles de producto en Adobe Admin Console for Enterprise.

Si forma parte de una organización multinacional, puede tener un espacio de trabajo para sus páginas web, propiedades o sitios europeos y otro para sus páginas web, propiedades o sitios estadounidenses. Si forma parte de una organización de varias marcas, puede contar con un espacio de trabajo independiente para cada una.

Los usuarios pueden formar parte de varios espacios de trabajo y pueden incluso tener diferentes roles en cada uno de ellos.

Los usuarios pueden tener distintas vistas en Adobe Target pasando de un espacio de trabajo a otro, de forma similar a como los usuarios de Analytics disponen de distintas vistas cambiando de grupo de informes.

Los espacios de trabajo pueden incluir audiencias, ofertas de código y actividades totalmente distintas.

Todas las audiencias y actividades creadas antes de la migración al modelo de permisos de Enterprise se agruparán en el “espacio de trabajo predeterminado” que se trata más adelante.

Todas las actividades creadas mediante Adobe Experience Manager (AEM), Adobe Mobile Services y Adobe Target Classic formarán parte del proyecto “Espacio de trabajo predeterminado”.

### Espacio de trabajo predeterminado

Todos los espacios de trabajo existentes (perfiles de producto) dentro de Admin Console se combinan en uno solo denominado “espacio de trabajo predeterminado” durante la migración de su organización al nuevo modelo de permisos de Enterprise.

>[!IMPORTANT]
>
>No elimine el espacio de trabajo predeterminado.

Todos los roles de usuario y el acceso a todas las funcionalidades de Target se mantienen exactamente igual que antes de la migración al nuevo modelo de permisos de Enterprise.

### Grupos de usuarios

Puede crear grupos de usuarios, como Desarrolladores, Analistas, Especialistas en marketing, Ejecutivos, etc., y luego asignar privilegios en varios productos y espacios de trabajo de Adobe. Asignar todos los privilegios apropiados en diferentes productos de Adobe a un nuevo miembro del equipo puede ser tan fácil como añadirlos a un grupo de usuarios específico.

### Roles y permisos

Las funciones y los permisos determinan los niveles de acceso que tienen los usuarios para crear y administrar actividades en su implementación de Target. En Target existen las funciones siguientes:

* Observador: puede ver actividades, pero no puede crearlas o editarlas.
* Editor: puede crear y editar actividades antes de que estén activas, pero no puede aprobar el lanzamiento de una actividad.
* Aprobador: puede crear, editar y activar o detener actividades.

### Canal

El canal se refiere al tipo de contenido desde donde se suministran sus actividades de Target: páginas web, aplicaciones móviles, mensajes de correo electrónico, etc.

Cuando se crea una actividad nueva, esta se crea en el espacio de trabajo que está seleccionado. Verá las opciones de selección del canal en el primer cuadro de diálogo que le permite elegir el canal deseado para la actividad: web, aplicación móvil, correo electrónico o API/otro.

## Información general sobre los permisos  {#section_DC2172520DA84605B218A5E9FB6D187A}

En esta sección explicamos cómo se aplicaban antes los permisos en [!DNL Target] y cómo se aplican usando la funcionalidad [!UICONTROL Propiedades] y [!UICONTROL permisos].

La nueva funcionalidad [!UICONTROL Permisos] permite crear diferentes proyectos (llamados “perfiles de producto” en [!DNL Adobe Admin Console for Enterprise]) para que pueda asignar a un único usuario los diferentes permisos que dictan sus derechos de acceso a cada proyecto. Estos proyectos independientes pueden compararse con el modo en el que funcionan los grupos de informes en [!DNL Adobe Analytics]. Cada proyecto tiene usuarios específicos con funciones específicas que se aplican a un conjunto de propiedades. De este modo, los clientes podrán restringir la vista, editar y aprobar el acceso de los usuarios según la región, el entorno (desarrollo/rodaje/prod.), el canal u otros criterios personalizados, como los siguientes:

![](assets/permissions.png)

Por ejemplo, un usuario determinado puede tener el acceso de aprobación en los sitios web de América, pero solo el acceso de visualización en la aplicación móvil europea. Ese mismo usuario puede no tener acceso ni siquiera a la visualización de las actividades ofrecidas en propiedades web y móviles en la región Asia-Pacífico.

El modelo actual de [!DNL Target] [!UICONTROL Permisos] de tiene tres funciones de permiso (Observador, Editor y Aprobador), como se muestra en la siguiente ilustración:

![](assets/permissions_1.png)

Cada función tiene diferentes niveles de permisos:

| Función | Descripción |
|--- |--- |
| Observador | Tiene acceso de solo lectura a las actividades. Puede ver actividades, pero no puede crearlas o editarlas. |
| Editor | puede crear y editar actividades antes de que estén activas, pero no puede aprobar el lanzamiento de una actividad. |
| Aprobador | Puede crear, editar y activar o detener actividades. |

Es importante tener en cuenta que la función de cada usuario se aplica a cada página, propiedad o sitio de su cuenta que incluya etiquetas de [!DNL Target] como se muestra a continuación:

![](assets/permissions_2.png)

El nuevo modelo de [!DNL Target] [!UICONTROL Permisos] de tiene las mismas funciones de permiso (Observador, Editor y Aprobador); sin embargo, estas funciones se pueden asignar a cada usuario por separado para páginas, propiedades o sitios concretos, como se muestra a continuación:

![](assets/permissions_3.png)

En este ejemplo, Jan tiene permisos de aprobador en la página principal y el sitio de EE. UU. y permisos de observador en el sitio de Francia.

Además, Jan no podrá ver páginas, propiedades ni sitios en [!DNL Target] para los que no tenga permisos de visualización, como se muestra a continuación:

![](assets/permissions_4.png)

En este ejemplo, Jan no ve las páginas de productos, el sitio de Rusia ni el sitio de ofertas de empleo.

## Casos de uso  {#section_F3CE8576959E4F4CB13BEEED38311DD8}

En los siguientes casos de uso, trataremos de explicar cómo lograr los objetivos de marketing con ayuda de las propiedades, los proyectos y las funciones de [!DNL Target]:

### Organización multinacional

Si forma parte de una organización multinacional, puede tener un espacio de trabajo para sus páginas web, propiedades o sitios europeos y otro para sus páginas web, propiedades o sitios estadounidenses. 
Usando los personajes de las ilustraciones anteriores, tras una reorganización, podría configurar los espacios de trabajo y permisos de este modo:

* **Jan:** Jan es la jefa de optimización del Centro de excelencia para las páginas web, las propiedades y los sitios estadounidenses de la organización. Es muy probable que tenga derechos de administración del sistema en Adobe Experience Cloud.

   Con su función, tiene permisos de aprobación en la página principal y el sitio de EE. UU. Con los permisos de aprobación, puede crear, editar y activar o detener actividades.

   Jan también realiza consultas al equipo de optimización de Francia, por lo que tiene permisos de observación en el sitio francés que le otorgan acceso de solo lectura a las actividades. Jan puede ver actividades, pero no puede crearlas o editarlas.

   Como no tiene ninguna función que le exija ver las páginas de productos, el sitio de Rusia ni el sitio de ofertas de empleo, no ve las actividades relacionadas con estos sitios.

* **Ernie:** Ernie trabaja como administrador de marketing en la organización que se encarga del marketing de EE. UU.

   Como Ernie lleva poco tiempo en la organización y no tiene demasiada experiencia con Target, tiene permisos de edición en la página principal y el sitio de EE. UU. y en las páginas de productos. Con los permisos de edición, Ernie puede crear y editar actividades antes de que estén activas, pero no puede aprobar el lanzamiento de una actividad. Alguien con permisos de aprobación, como Jan, tiene que aprobarla para que pueda pasar a la fase de producción.

   Como no tiene ninguna función que le exija ver el sitio de Rusia, el sitio de Francia ni el sitio de ofertas de empleo, no ve las actividades relacionadas con estos sitios.

* **Diana:** Diana trabaja como analista en la organización y se le han concedido permisos de observación en la página principal y el sitio de EE. UU., las páginas de productos, el sitio de Rusia y el sitio de Francia. Con estos permisos tiene acceso de solo lectura a las actividades. Diana puede ver actividades, pero no puede crearlas o editarlas.

   Como no tiene ninguna función que le exija ver el sitio de ofertas de empleo, no ve las actividades relacionadas con este sitio.

### Organización de varias marcas

Si forma parte de una organización de varias marcas, puede contar con un espacio de trabajo independiente para cada página web, propiedad o sitio de la marca.

Usando los personajes de las ilustraciones anteriores, tras una reorganización podría configurar los proyectos y permisos de este modo:

* **Jan:** Jan es la jefa de optimización del Centro de excelencia de una organización sanitaria que trabaja en el ámbito de productos para hospitales y consumidores. Es muy probable que tenga derechos de administración del sistema en Adobe Experience Cloud.

   Con su función, tiene permisos de aprobación en el sitio del hospital. Con los permisos de aprobación, puede crear, editar y activar o detener actividades.

   Jan también realiza consultas al equipo de optimización en el ámbito de productos para consumidores, por lo que tiene permisos de observación en el sitio correspondiente que le otorgan acceso de solo lectura a las actividades. Jan puede ver actividades, pero no puede crearlas o editarlas.

* **Ernie:** Ernie trabaja como administrador de marketing en la organización que se encarga del marketing en el ámbito de productos para consumidores.

   Como Ernie lleva poco tiempo en la organización y no tiene demasiada experiencia con Target, tiene permisos de edición en el sitio para consumidores. Con los permisos de edición, Ernie puede crear y editar actividades antes de que estén activas, pero no puede aprobar el lanzamiento de una actividad. Alguien con permisos de aprobación en el sitio para consumidores (que, en este caso, no es Jan) tiene que aprobarla para que pueda pasar a la fase de producción.

   Como no tiene ninguna función que le exija ver el sitio del hospital, no ve las actividades relacionadas con estos sitios.

* **Diana:** Diana trabaja como analista en la organización y se le han concedido permisos de observación en el sitio del hospital y el sitio para consumidores. Con estos permisos tiene acceso de solo lectura a las actividades. Diana puede ver actividades, pero no puede crearlas o editarlas.

## Punto de contacto de propiedad y permisos de la interfaz de usuario de Target {#section_3414371393BB42999A268628B5456EC9}

La nueva funcionalidad Permisos puede verse en diferentes sitios de la interfaz de usuario de [!DNL Target].

* **Lista desplegable Espacio de trabajo (Perfil de producto):** la lista desplegable Espacio de trabajo se muestra en la parte superior de las páginas [!UICONTROL Actividades], [!UICONTROL Audiencias] y [!UICONTROL Ofertas]. Seleccione el espacio de trabajo deseado para filtrar la lista y mostrar únicamente los elementos de dicho espacio de trabajo.

   ![](assets/workspace_drop-down.png)

* **Creación de actividad:** cuando crea una nueva actividad, esta se crea en el espacio de trabajo seleccionado actualmente. Verá las opciones de selección del canal en el primer cuadro de diálogo que le permite elegir el canal deseado para la actividad: web, aplicación móvil, correo electrónico o API/otro.

   ![](assets/channel_options.png)

* **Creación de audiencias:** cuando crea una nueva audiencia, se hace en el espacio de trabajo seleccionado.
* **Creación de ofertas:** cuando crea una nueva oferta, se hace en el espacio de trabajo seleccionado.
* **Página de propiedades (Configuración &gt; Propiedades):** puede utilizar el cuadro [!UICONTROL Buscar], la opción [!UICONTROL Canal] y la opción [!UICONTROL Perfil de producto] para filtrar la lista [!UICONTROL Propiedades].

   ![](assets/properties_list.png)

## Advertencias {#section_9714311B1CD9497A86F4910F8AE635E2}

Considere lo siguiente cuando utilice o configure propiedades y permisos en Target Premium:

* **Importante**: No elimine espacios de trabajo con actividades. Si esto sucede, trabaje con ClientCare para recuperar estas actividades.
* Al utilizar la vista Todos mis espacios de trabajo:

   * Puede ver las actividades, audiencias y ofertas de todos los espacios de trabajo para los que tenga el rol adecuado y permiso de acceso.
   * Cuando se selecciona la vista Todos mis espacios de trabajo, se agrega a las páginas Actividades, Audiencias y Ofertas una nueva columna que indica el espacio de trabajo del elemento y los permisos de usuario que tiene asociados para dicho elemento (Observador, Editor o Aprobador).
   * Al crear una actividad, audiencia u oferta en la vista Todos mis espacios de trabajo, debe seleccionar el espacio de trabajo donde se creará el elemento. Solo podrá seleccionar los espacios de trabajo para los que disponga del permiso Editor o Aprobador.
   * Al copiar una actividad, audiencia u oferta en la vista Todos mis espacios de trabajo, debe seleccionar el espacio de trabajo donde se copiará el elemento. Solo podrá seleccionar los espacios de trabajo para los que disponga del permiso Editor o Aprobador.

* Cualquier Aprobador puede controlar cualquiera de los ajustes de las páginas de configuración siguientes en cualquier espacio de trabajo:

   * Preferencias
   * Implementación
   * Configuración de Scene7
   * Hosts

* Los usuarios no pueden mover recursos de un espacio de trabajo (perfil de producto) a otro. Sin embargo, sí se permite la copia.
* Si visualiza las audiencias desde la página [!DNL Audiences], la página carga más lento de lo esperado. Si interactúa con la barra de búsqueda de cualquier forma, las audiencias se muestran más rápido. Este es un problema conocido que se solucionará en una próxima actualización. Este problema no afecta a la selección de audiencias durante el flujo de trabajo de creación de actividades.
* Los siguientes recursos son parte del nuevo modelo de permisos de Enterprise:

   * Actividades, audiencias y ofertas de código creadas en Target Standard/Premium después de que el cliente haya recibido permisos. (Nota: Los clientes deben cumplir los requisitos para el uso de Target Premium).
   * Las propiedades pueden añadirse a actividades existentes en el espacio de trabajo predeterminado; sin embargo, esto está sujeto a cambios.
   * Solo los nuevos recursos (como actividades, ofertas de código y audiencias) creados en Target Premium (una vez habilitados los permisos de Enterprise) se podrán restringir mediante permisos.
   * Los recursos externos solo están disponibles para los usuarios en el espacio de trabajo predeterminado. El rol de un usuario en el espacio de trabajo predeterminado se aplica globalmente (a todas las solicitudes y recursos de Target).

* Los siguientes recursos *no* son parte del nuevo modelo de permisos de Enterprise:

   * Ofertas de imágenes
   * Todos los recursos de Recommendations, incluidos la Biblioteca de criterios, Biblioteca de diseños, Catálogo, Configuración de Recommendations.
   * Los recursos existentes (como actividades, ofertas de código y audiencias) creados en Target Premium antes de la habilitación de los permisos de Enterprise se pueden copiar, pero no se pueden mover a otros espacios de trabajo.
   * Las actividades, audiencias, ofertas de código, ofertas de imágenes o cualquier otro recurso creado con las siguientes soluciones o métodos no se pueden controlar mediante el modelo de permisos de Enterprise, pero formarán parte del espacio de trabajo predeterminado: Target Classic, Adobe Experience Manager (AEM), Adobe Mobile Services y recursos creados mediante API. Recursos creados mediante API (incluidas actividades, audiencias, ofertas de código y ofertas de imagen).
   * Las ofertas de imagen (recursos almacenados en `https://[tenantName].marketing.adobe.com/content/mac/[tenantName]/target/offers.html#image-library`) no se pueden controlar mediante el modelo de permisos de Enterprise en este momento.
   * clickTracking y las redirecciones solo funcionan cuando el vínculo de destino o la página de destino son parte de una propiedad incluida en la actividad. Además, es posible que clickTracking no funcione al utilizar la función `targetPageParams()`. La función recomendada es `targetPageParamsAll()`.
   Actualmente, Target necesita que haya un token `at_property` en todas las páginas donde se lleve a cabo un seguimiento. En el caso de que el token (1) no esté, (2) no se detecte a la hora de configurar la actividad (en el VEC) o (3) no se pase al mbox de clickTracking por medio de la función `targetPageParamsAll()`, la métrica no se incrementará y aparecerá con el valor “0”.

   Lo mismo se aplica a las actividades que usan redirecciones. La página de destino debe tener un token `at_property` y se debe reconocer cuando se configura en el VEC.

   En una versión futura, Target funcionará en páginas donde no haya presente un token `at_property`, o donde exista un token `at_property` distinto.

* La funcionalidad Permisos de usuario de Enterprise no se admite en [llamadas a la API de Adobe I/O](https://developers.adobetarget.com)

## Preguntas frecuentes {#faqs}

Las preguntas más frecuentes sobre permisos de Enterprise incluyen las siguientes:

### ¿Puedo trasladar una actividad de un espacio de trabajo a otro?

Por desgracia, las actividades no se pueden trasladar de un espacio de trabajo a otro. Sin embargo, puede copiar una actividad a cualquier espacio de trabajo, pero los datos del informe no se guardarán. Para obtener más información, consulte “Copiar/editar una actividad al utilizar espacios de trabajo” en [Copiar/Editar una actividad al usar espacios de trabajo.](../../../c-activities/edit-activity.md#section_45A92E1DD3934523B07E71EF90C4F8B6)

Las actividades creadas antes de la migración se siguen ejecutando del mismo modo en el espacio de trabajo predeterminado, a menos que se editen y se les asignen propiedades. Las actividades que se encuentran en un espacio de trabajo responden a las propiedades asignadas a ese espacio de trabajo y, por lo tanto, puede ser que el comportamiento no sea el mismo que antes de la migración.

### ¿Por qué aparece un mensaje de error que indica que no hay ninguna propiedad asociada con esta actividad, aunque haya una propiedad asignada?

Si ha implementado [!DNL Target] con [!DNL Adobe Launch] y ha obtenido un mensaje de error indicando que no hay propiedad asociada con la actividad, pase el parámetro `at_property` con la función `targetPageParams`.

### ¿Se registran conversiones de rastreo de clics si una página redireccionada y la dirección URL de actividad pertenecen a propiedades diferentes?

El rastreo de clics no se registra en páginas en las que la URL de la página y de la actividad pertenecen a propiedades diferentes.

Considere el siguiente escenario (se aplica tanto a at.js como a mbox.js):

* Página1 pertenece a Propiedad1.
* Página2 pertenece a Propiedad2.
* En la actividad, Página1 redirige a Página2, que contiene los rastreos de clics.

Cuando un visitante abre Página1 en un explorador, se le redirige a Página2. Debido a que Página2 no cumple los requisitos para entregar la actividad, su llamada de Target no contiene rastreos de clics en su respuesta.

Si la página de redirección y la dirección URL de la actividad pertenecen a la misma propiedad, los rastreos de clics funcionan según lo esperado. Para obtener más información, consulte [Rastreo de clics](/help/c-activities/r-success-metrics/click-tracking.md).

## Vídeo de formación: Vídeo de formación de permisos de Enterprise {#section_2FA080303A064242B63FF16CFA6DB31D}

Objetivos de aprendizaje:

* Los tres roles que pueden tener los usuarios de Adobe Target
* Los conceptos de propiedad y espacio de trabajo, y cómo operan estos límites y agrupamientos para permitir controlar el nivel de acceso de los usuarios
* Diferentes ejemplos de propiedades para la consideración de su organización

>[!VIDEO](https://video.tv.adobe.com/v/19042/?captions=spa)