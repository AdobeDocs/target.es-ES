---
keywords: known issues;resolved issues;release notes;bugs;issues;fixes
description: Información sobre problemas conocidos con esta versión de Adobe Target. También incluye información sobre problemas que ya se han resuelto.
title: Problemas conocidos y problemas resueltos   en Adobe Target
uuid: f8e8e057-1842-4922-ab7f-4d5441048573
translation-type: tm+mt
source-git-commit: 3edb13b196240bb1918fc66edcc653936e32d3ef
workflow-type: tm+mt
source-wordcount: '3201'
ht-degree: 95%

---


# Problemas conocidos y problemas resueltos {#known-issues-and-resolved-issues}

Información sobre problemas conocidos con esta versión de Target. También incluye información sobre problemas que ya se han resuelto.

>[!NOTE]
>
>Los números entre paréntesis de los problemas son para uso interno de Adobe.

## Problemas conocidos {#section_AEDC98B67CF24C9F8E0CF0D2EB9ACAEF}

En las secciones siguientes se enumeran los problemas conocidos de [!DNL Target]:

### Entrega de página {#page-delivery}

Si agrega una regla de plantilla, como contenidos de una URL (/checkout, /cart) en la entrega [de](/help/c-activities/t-experience-target/t-xt-create/xt-activity-url.md) página, se añadirán espacios adicionales a las reglas. Se trata de un problema estético que no afecta la creación de definiciones de audiencia ni la entrega de ofertas. (TGT-35916)

### Vínculos de vista previa de control de calidad de la actividad {#preview}

Es posible que los vínculos de [Vista previa de control de calidad de la actividad](/help/c-activities/c-activity-qa/activity-qa.md) para las actividades guardadas no se carguen si hay demasiadas guardadas en su cuenta. Volver a intentar los vínculos de vista previa debería funcionar. Para evitar que esto siga ocurriendo, archive las actividades guardadas que ya no se usan de forma activa. (TNT-32697)

### Ofertas de redireccionamiento {#redirect}

Los siguientes son problemas conocidos de las ofertas de redireccionamiento:

* En algunas condiciones, un número limitado de clientes ha informado de grados de variación más altos en la distribución del tráfico al utilizar una oferta de redireccionamiento en actividades configuradas con Analytics para Target (A4T). Los ingenieros de Adobe están trabajando en este problema.
* Las actividades de redirección en las implementaciones de at.js hacen que la dirección URL de vista previa entre en bucle (la oferta se suministra repetidamente). Puede utilizar el [Modo de control de calidad](../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40) para llevar a cabo la vista previa y el control de calidad. Este problema no afecta al suministro real de la oferta. (TGT-23019)

### No se puede procesar el informe de gráfico de una actividad de Segmentación automática al utilizar una experiencia personalizada como control

El informe gráfico de una actividad de segmentación automática no se puede procesar para modos “diferenciales” (Alza media y Alza diaria) si no hay datos (0 visitas) en ninguna experiencia. Esta situación puede suceder durante la etapa inicial de una actividad si la experiencia de control está definida como personalizada. Para los demás modos (Control medio de ejecución y segmentaciones, Control diario y segmentaciones y Visitas) funciona correctamente. Tan pronto como hay algunos datos (visitas que no sean cero), el informe se procesa según lo esperado.

### Cancelación de la carga de una página dentro del VEC {#cancel}

* El siguiente problema conocido aparece al cancelar la carga de una [!UICONTROL prueba A/B] o de [!UICONTROL segmentación de experiencias] (XT) dentro del VEC que contiene una dirección URL de redireccionamiento.

   En el primer paso del flujo de trabajo guiado en tres partes dentro del VEC, al cancelar la carga de la página, se muestra el panel [!UICONTROL Modificaciones] del VEC y se aplica la redirección a la plantilla URL en la experiencia (por ejemplo, &quot;Experiencia B&quot;). Cuando avanza hacia los pasos dos o tres y, después, regresa al paso uno, se produce la siguiente situación.

   De forma predeterminada, en la &quot;Experiencia B&quot;, se representa la plantilla de carga del sitio web cancelado y el panel [!UICONTROL Modificaciones] es accesible, lo cual no debería ser el caso porque esta experiencia tiene una redirección a la plantilla URL aplicada. Debería aparecer el redireccionamiento a la plantilla URL.

   Para mostrar el estado correcto de la experiencia en el VEC:

   Si cambia a otra experiencia y vuelve a la Experiencia B, [!DNL Target] muestra la redirección a la plantilla URL aplicada a esta experiencia y el panel [!UICONTROL Modificaciones] no es accesible. (TGT-32138)

* Para los sitios web de aplicación de una sola página, la cancelación de la carga no permite editar acciones en el panel [!UICONTROL Modificaciones].

### Compatibilidad con permisos de Enterprise en las API de Target {#api}

Es posible que las ofertas de código creadas desde la interfaz de usuario de Target en la biblioteca de ofertas se muestren en el espacio de trabajo predeterminado si se recupera la lista de ofertas mediante las API de GET. Este problema se solucionará en la primera semana de marzo de 2019. Una vez solucionado el problema, las ofertas de código se mostrarán en el espacio de trabajo apropiado cuando se extraigan de las API. Este problema *no* afecta a las ofertas creadas a partir de las API. Por ejemplo, las ofertas de código creadas a partir de las API se muestran en el espacio de trabajo en el que fueron creadas, ya sea mediante la API de GET o desde la interfaz de usuario de Target.

### Recommendations

Los siguientes son problemas conocidos de las actividades de Recommendations:

* Las entidades caducan correctamente después de 60 días de no recibir ninguna actualización a través de la fuente o la API; sin embargo, las entidades caducadas no se eliminan del índice de búsqueda en el catálogo después del vencimiento. (IRI-857)
* Las superposiciones &quot;Información de uso&quot; para criterios y diseños no reflejan su uso en actividades A/B y de segmentación de experiencias (TGT-34331)
* Las ofertas de Recommendations en las actividades A/B y de segmentación de experiencias no muestran una previsualización concreta de la bandeja de Recommendations (TGT-33426)
* Las colecciones, las exclusiones, los criterios y los diseños creados mediante API no están visibles en la interfaz de usuario de Target y solo se pueden editar mediante API. (TGT-35777)
* Las actividades de Recommendations creadas mediante API se pueden ver en la interfaz de usuario, pero solo se pueden editar mediante API.
* El estado de la fuente de criterios personalizados que se muestra en la lista de criterios (tarjeta) se actualiza cada diez minutos, y es posible que pasen más de diez minutos de la fecha en circunstancias excepcionales. El estado que se muestra en la vista de edición de criterios personalizados se obtiene en tiempo real y siempre está actualizado. (TGT-35896, TGT-36173)

### Actividades de prueba multivariable (MVT)

En una actividad MVT, el ganador que se muestra en la tabla y en el gráfico no concuerdan al comprobar métricas. Esto ocurre si un usuario cambia de la vista Resumen a la Visualización de gráfico, después regresa a Resumen, modifica una métrica y vuelve a cambiar a Visualización de gráfico. Cuando se produce este problema, la vista Resumen siempre muestra el ganador correcto. Si el usuario no cambia entre Visualización de gráfico y la vista Resumen, la Visualización de gráfico muestra al ganador correcto.

### at.js  {#atjs}

A continuación, detallamos los problemas conocidos de at.js:

* Si se utilizan las versiones de at.js anteriores a la 2.2.0, el rastreo de clics no informa de las conversiones en Analytics para Target (A4T) si el código de Adobe Analytics no está presente en los elementos de la página (como los botones). Se ha introducido una corrección para este problema en at.js 2.2.0. [Actualice a la última versión de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) si experimenta este problema.
* Si crea una experiencia sin modificaciones con at.js 2.1.1 o versiones anteriores (por ejemplo, una experiencia predeterminada), es posible que la experiencia no se contabilice en informes, Analytics for Target (A4T), Adobe Analytics ni Google Analytics. Además, es posible que el [complemento](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-plugins.md) ttMeta no funcione correctamente.

   Como solución alternativa, utilice un espacio en blanco en el contenido de la experiencia. (TNT-33366)

   >[!NOTE]
   >
   >Se ha incluido una corrección para este problema en at.js 2.2.0. Debe actualizar a la versión [más reciente o a at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) o usar la solución mencionada anteriormente solo para las versiones de at.js anteriores a la 2.2.0.

* Cuando se carga una página en el Compositor de experiencias visuales (VEC), Target debe determinar si la configuración de mbox global está habilitada o deshabilitada, y si entityID o categoryID están presentes en la ubicación donde el usuario intenta aplicar las recomendaciones del VEC. La lista de criterios se filtra en función de esta información. La lista predeterminada tiene filtrados algunos algoritmos, pero la [casilla Compatible](/help/c-recommendations/t-create-recs-activity/algo-select-recs.md) le permite ver la lista de algoritmos completa.

   Al usar at.js, la casilla Compatibilidad queda oculta, por lo que no puede ver los algoritmos no compatibles.

   Este problema se aplica solo a actividades de Recommendations que usan el VEC.

   **Solución alternativa**: en [!UICONTROL Recommendations > Configuración], desactive la opción [!UICONTROL Filtrar los criterios no compatibles]. Después de desactivar este ajuste, el selector de criterios los muestra todos, compatibles y no compatibles. (TGT-25949)

* Los mboxes no se activan en los navegadores Microsoft Explorer 11 después de actualizar a at.js versión 1.0 debido a la interacción entre at.js y la API de visitante 2.2.0. Este problema afecta a la versión 0.9.6 y posteriores de at.js. (TNT-27600)
* Es posible que at.js no funcione con aplicaciones Cordova o híbridas porque no admiten las cookies de origen. (TNT-26166)

   **Solución alternativa**: configure at.js con la opción “solo x” habilitada y transfiera `mboxThirdPartyId` en llamadas para administrar usuarios.

### mbox.js

La biblioteca mbox.js no admite los lenguajes de plantilla en el lado del cliente, como Handlebars y Mustache. La biblioteca at.js *sí* admite estos lenguajes.

**Nota**: La biblioteca mbox.js ya no está en desarrollo. Todos los clientes deberían migrar de mbox.js a at.js. Para obtener más información, consulte [Migrar a at.js desde mbox.js](../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

### Implementación: Crear mbox global automáticamente

On the Implementation tab ([!UICONTROL Administration > Implementation]) the [!UICONTROL Global Mbox Auto Create] field will be &quot;false&quot; by default for a newly provisioned tenant.

Cuando se descarga mbox.js por primera vez después del aprovisionamiento, el campo [!UICONTROL Creación automática de Global Mbox] se establece en “true” en el archivo mbox.js descargado y en el back-end de [!DNL Target], pero seguirá mostrándose como “false” en la página [!UICONTROL Implementación] de la interfaz de usuario hasta que se actualice la página (una vez hecho, el estado será “true”).

at.js se descargará con `global_mbox_autocreate = false` para un inquilino recién aprovisionado. Si mbox.js se descarga primero, global_mbox_autocreate se establece en “true” y at.js también se descarga con `global_mbox_autocreate = true`. (TGT-15929)

### Métricas de éxito

Las métricas de éxito con la opción avanzada “Cómo se incrementará el recuento” establecida en “con cada impresión” o en “con cada impresión (excluyendo actualizaciones)” no se pueden utilizar como métricas de suceso de las que dependa otra métrica.

Cuando una métrica de éxito se establece para que se incremente con cada impresión, Target vuelve a contar el visitante cada vez que visita esa métrica de éxito. A continuación, Target restablece la métrica de éxito “abono” a 0 para que pueda contar de nuevo la siguiente impresión. Por lo tanto, si otra métrica requiere que esta métrica se haya visto primero, Target no reconocerá nunca que el usuario ha visto la métrica primero.

### Analytics for Target (A4T)

Las impresiones y conversiones de la actividad de destino actualmente se cuentan incorrectamente en Analysis Workspace.

Como solución alternativa, confíe en los datos de A4T en Reports &amp; Analytics hasta que este problema se resuelva.

### API de Target

Los clientes no pueden realizar operaciones de CRUD en actividades de asignación automática a través de la versión v3 de la API de actividades A/B en Adobe I/O.

## Problemas resueltos {#section_FD2FC86E7C734D60B1EDC9DEF60E1014}

A medida que se resuelvan los problemas conocidos que hemos mencionado, pasarán a las siguientes secciones y, si es necesario, se añadirán notas adicionales.

### Sistemas de informes y pedidos extremos

Desde el 25 de noviembre de 2019 hasta el 26 de abril de 2020, un servidor de Destinatario experimentó un problema que hacía que los valores de pedidos extremos se contaran en las métricas de informes basadas en ingresos (AOV, RPV). Desde el 19 de diciembre de 2019 hasta el 23 de abril de 2020, otro servidor experimentó el mismo problema. Este problema no afectaba a todos los servidores de Destinatario ni a todos los clientes de Destinatario.

Usted *no se vio* afectado si:

* La implementación de Destinatario utiliza diferentes servidores.
* Los informes no excluyeron pedidos extremos.
* Ha utilizado una métrica de conversión para medir sus actividades.
* Las actividades de Destinatario utilizan Analytics para Destinatario (A4T).
* Está ubicado en la región de Asia-Pacífico (APAC).

Para determinar si este problema afectó a su sistema de informes de Destinatario, póngase en contacto con [Client Care](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB).

### Recommendations

* El índice de fuentes de Recommendations puede mostrar “Esperando índice” si los elementos de la fuente son los mismos que en la ejecución anterior. La ingesta del producto para la entrega no se ve afectada. (RECS-6663)

   Este problema se solucionó en la versión 19.4.2 de Target.

* Las fuentes de Recommendations tardan más de lo esperado en procesarse. (COR-2836)

   Este problema se corrigió en la versión 16.10.1 de Target.

* La interfaz de usuario de fuentes de Recommendations no muestra el estado de indexación correcto. Las tareas de back-end funcionan correctamente, pero la interfaz de usuario no puede recuperar ni mostrar el estado actual.

   Se corrigió en la versión 17.10.1.

### Ofertas de redireccionamiento

Una condición de carrera en la página puede provocar que se cuenten las vistas de página en la página original y en la página de redirección. Hay actualizaciones previstas para la implementación de at.js para garantizar que se pueda evitar esta condición de carrera.

Este problema se solucionó en at.js 1.6.3.

### Grupos de exclusión

* Cuando se aplica la deduplicación automática después de crear grupos de exclusión, el recuento del diagrama de la actividad en la interfaz de usuario podría ser incorrecto.
* Cuando se edita una actividad existente con grupo de exclusión, las inclusiones manuales pueden no reflejarse correctamente en la interfaz.

Se han resuelto estos problemas.

### API de Target

La versión v1 de las API de oferta en Adobe I/O trata todas las ofertas creadas a través de Target para que estén en el espacio de trabajo predeterminado. (TTTEAM-41957)

Se ha resuelto este problema.

### at.js

Los mboxes no se activan en los navegadores Microsoft Explorer 11 después de actualizar a at.js versión 1.0 debido a la interacción entre at.js y la API de visitante 2.2.0. Este problema afecta a la versión 0.9.6 y posteriores de at.js. (TNT-27600)

Se corrigió en la versión 2.3.0 de API o posteriores.

### Segmentación geográfica

La búsqueda de una cadena que contiene caracteres especiales (como un espacio o una coma) actualmente no funciona al crear audiencias de segmentación geográfica. Este problema surge, por ejemplo, al crear audiencias basadas en ciudades, estados, países, etc. Por ejemplo, cuando se busca “Nueva York”, la búsqueda no devuelve resultados válidos.

Corregido en noviembre de 2018.

### at.js

Al utilizar la versión 1.6.0 de at.js, se produce el redireccionamiento de Analytics for Target (A4T), pero sin calificación de la actividad.

Se corrigió en la versión 1.6.2 de at.js.

### Actividades, Workspaces y eliminación de API de actividad

Las actividades en el espacio de trabajo predeterminado eliminadas a través de la API siguen mostrándose en la IU de Target. Como solución alternativa, elimine todas las actividades en el espacio de trabajo predeterminado utilizando la IU de Target. (TGT-31315)

Se corrigió el 25 de octubre de 2018.

### Creación de informes de nivel de oferta de Personalización automatizada (AP)

Cuando hace clic en la experiencia específica en un informe de actividad de Personalización automatizada (AP) para ver los informes de nivel de oferta, actualmente ve resultados vacíos, un mensaje de error o un icono giratorio. (TNT-30695)

Se corrigió el 27 de septiembre de 2018.

### Editor de código

Si vuelve a cargar el VEC en el paso 1 del flujo de trabajo guiado de tres pasos mientras trabaja con el Editor de código en Firefox e Internet Explorer, la pestaña Modificaciones no se procesa correctamente; sin embargo, la funcionalidad del VEC no se ve afectada. (TGT-28730)

Se corrigió en la versión 18.9.1.

### Actividad de Recommendations que utiliza una regla de promoción de atributos

Cuando edita o copia una actividad de Recommendations que usa una regla de promoción de atributos, el error “Le faltan campos” se muestra al hacer clic en Guardar.

Se corrigió en la versión 17.8.1.

### Recomendaciones de copia de seguridad

Las recomendaciones de copias de seguridad muestran erróneamente “Habilitado” en las tarjetas de Elementos visualizados recientemente en la IU de Target. (TGT-29308)

Se corrigió en la versión de 18.4.1, por lo que se muestra “Deshabilitado”.

### Actividades de segmentación automática y audiencias de informes

Cuando se cambia el nombre de una audiencia de informes utilizado en una actividad de segmentación automática, cualquier actualización posterior de la actividad desde Target podía fallar y provocar un mensaje de error.

Este problema se corrigió en la versión 18.5.1 (22 de mayo de 2018).

### at.js

El algoritmo para extraer el dominio de nivel superior que debería usarse al guardar cookies ha cambiado en la versión 0.9.6 de at.js. Debido a ello, no es posible guardar cookies en direcciones que utilicen IP. La mayoría de las veces, las direcciones IP se utilizan con fines de prueba, pero como solución alternativa se pueden utilizar entradas DNS, ajustar el archivo de host en un cuadro local o utilizar la función targetGlobalSettings() de at.js para insertar un fragmento de código para admitir direcciones IP.

Este problema se corrigió en la versión 1.2 de at.js.

### Permisos de usuario de Enterprise para Target Premium

Como parte de la migración de permisos de Enterprise, toda la administración de usuarios de Target Premium se trasladó de la interfaz de Adobe Target a Adobe Admin Console.

Esta migración ha provocado dos posibles problemas de los que debe tener constancia:

* Los usuarios no administradores recibieron un correo electrónico donde se indicaba que ya tenían acceso a Adobe Target. Esto indica que la migración se completó para su organización. Este mensaje puede ignorarse.
* Tras la migración se han producido algunos informes de usuarios previamente desactivados que reaparecen en Adobe Admin Console. El que usuarios desactivados en Adobe Admin Console sigan apareciendo en la lista de usuarios de Target antes de la migración puede suponer un problema para su organización. Recomendamos que los administradores revisen la lista de usuarios en Admin Console para validar el acceso.

Este problema se corrigió el 30 de agosto de 2017.

### Creación de actividades

Un problema en la versión 17.6.2 puede haber afectado a las actividades creadas o actualizadas entre el 22 y el 29 de junio de 2017. Se vieron afectadas las siguientes actividades:

* Cualquier experiencia reordenada en segmentación de experiencias (XT) habrá retomado al orden original.
* Cualquier regla de segmentación local respecto a la actividad (no guardada dentro de una audiencia) se habrá perdido: audiencias combinadas, refinamientos de ubicación y cualquier regla con métricas de éxito.

No se vio afectada ninguna otra actividad.

**Importante**: Este problema no se arregla automáticamente. Para ello, debe volver a guardar cualquier actividad afectada.

Este problema se corrigió el 29 de junio de 2017.

### Compositor de experiencias basadas en formularios

Se ha informado de los siguientes problemas conocidos al utilizar el Compositor de experiencias basadas en formularios:

* Si usa el Compositor de experiencias basadas en formularios con un mbox que no sea el mbox global creado automáticamente (target-global-mbox) y luego elige una métrica de participación como métrica de éxito, la métrica solo se incrementa en las páginas que tienen el mbox usado en la actividad. Por ejemplo, si el mbox es homepage\_mbox, la métrica Páginas por visita es el número de peticiones al servidor realizadas a homepage\_mbox durante esa visita. (TGT-22789)
* Se produce una excepción de JavaScript cuando se elimina una experiencia en una actividad de segmentación de experiencias (XT) al usar durante el paso 1 del proceso el Compositor de experiencias basadas en formularios. (TGT-24366)

El primer problema se corrigió en la versión de Target 17.3.1 (marzo de 2017).

El segundo problema se corrigió en la versión de Target 17.6.1 (junio de 2017).

### at.js

Desde la publicación de Target 17.4.1 (27 de abril de 2017), el uso de la acción Insertar imagen en el Compositor de experiencias visuales (VEC) provoca que el contenido de la oferta no se envíe al usar la biblioteca at.js.

En la versión 0.9.7 de at.js, publicada el 22 de mayo de 2017, se incluyó una solución para este problema.

### Creación de informes: actividades A/B y de segmentación de experiencias (XT)

Entre las 21:00 (PST) del 27 de abril y las 6:00 (PST) del 5 de mayo, las actividades A/B y XT creadas o editadas con cualquier métrica usando la acción de conversión “Visualizó una página” (no basadas en otras métricas) podrían contener conversiones incorrectamente registradas. Este problema ya está resuelto, pero la acción de conversión “Visualizó una página” para estas actividades durante el tiempo en que duró el problema podría no ser precisa y, por desgracia, no se puede corregir. Recomendamos que, para cualquier decisión basada en las acciones de conversión “Visualizó una página” para estas actividades, confíe únicamente en los datos registrados antes o después del periodo afectado.

Pueden utilizarse los datos de otras métricas porque no se vieron afectados.

Este problema se corrigió en la versión 17.4.3 de Target.

### Ofertas: actividades A/B y de segmentación de experiencias (XT)

El envío y la vista previa se vieron afectados para las ofertas de actividades A/B y XT con al menos dos experiencias y creadas o editadas empleando el Compositor de experiencias basadas en formularios entre las 21:00 (PT) del viernes 28 de abril y las 21:15 (PT) del lunes 1 de mayo. Solo se mostraban las ofertas con contenido predeterminado.

Este problema se corrigió en la versión 17.4.3 de Target.

### at.js

Las siguientes acciones provocaban que la oferta no se enviara al utilizar el Compositor de experiencias visuales (VEC) y at.js: Mover y Reorganizar.

Este problema se corrigió en la versión 0.9.6 at.js.

### Informes

La posibilidad de ver varias métricas en un informe, incluida en la versión 17.3.1 de Target (30 de marzo de 2017), se ha eliminado debido a un comportamiento inesperado. Esta característica volverá a estar disponible en una próxima versión.

La capacidad para ver múltiples métricas en un informe se incluyó en la versión de Target 17.4.1 (27 de abril de 2017).

### Ofertas

Las imágenes eliminadas de la biblioteca Ofertas de imágenes (Ofertas > Ofertas de imágenes) siguen visibles en la interfaz de usuario. En una próxima versión, las imágenes eliminadas dejarán de verse. Mientras tanto, estas imágenes se verán en la interfaz de usuario con el estado Eliminada. (TGT-23793)

Este problema se corrigió en la versión 17.4.1 de Target (27 de abril de 2017).

### Ofertas de redireccionamiento

Para los criterios visualizados recientemente, las reglas dinámicas basadas en entidades no llevarán a ninguna recomendación si el parámetro entity.id no se pasa en la solicitud de mbox. (RECS-6241)

Este problema se corrigió después de la publicación de Recommendations (22 de marzo de 2018). Después de la publicación de Recommendations, Target omite las reglas dinámicas basadas en entidad si entity.id no se pasa en la solicitud de mbox.

### at.js

Cuando los usuarios intentan descargar at.js desde la página de detalles de Implementaciones después de actualizar la configuración de at.js, se descarga mbox.js en lugar de at.js. (TGT-23069)

Este problema se corrigió en la versión 17.3.1 de Target (30 de marzo de 2017).

### Reglas de exclusión globales

Las reglas de exclusión globales tardan entre 10 y 20 minutos en propagarse al borde para Recommendations Premium. (RECS-5270)

Este problema se corrigió en la versión 17.2.2.0 de Recommendations (6 de marzo de 2017).

### Creación de informes en Analytics for Target (A4T)

Los informes no se actualizan cuando se cambia la métrica para la creación de informes. Este es un problema de la interfaz de usuario. Esto no repercute en la recopilación ni en el suministro de datos para la creación de informes. (TGT-22970)

Este problema se corrigió en la versión 17.2.2.0 de Target (24 de febrero de 2017).

### Informes de CSV

Los informes descargados no respetan la opción de configuración Excluir pedidos extremos. (TGT-21871)

Este problema se corrigió en la versión 17.2.1.0 de Target.
