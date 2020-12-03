---
keywords: known issues;resolved issues;release notes;bugs;issues;fixes
description: Información sobre problemas conocidos con esta versión de Adobe Target. También incluye información sobre problemas que ya se han resuelto.
title: Problemas conocidos y problemas resueltos   en Adobe Target
feature: known issues
translation-type: tm+mt
source-git-commit: 16a626878cab97dd81b22d3d2a170df80a025afb
workflow-type: tm+mt
source-wordcount: '4327'
ht-degree: 70%

---


# Problemas conocidos y problemas resueltos  

Información sobre problemas conocidos de [!DNL Adobe Target]. También incluye información sobre problemas que ya se han resuelto.

>[!NOTE]
>
>Los números entre paréntesis de los problemas son para uso interno de Adobe.

## Problemas conocidos {#section_AEDC98B67CF24C9F8E0CF0D2EB9ACAEF}

En las secciones siguientes se enumeran los problemas conocidos de [!DNL Target]:

### Métricas de Analytics para Destinatario (A4T) para la asignación automática y actividades de Destinatario automático

Existe un problema conocido actual en la interfaz de usuario que permite a los usuarios seleccionar métricas de participación e ingresos no admitidas como métrica de objetivo principal para la optimización en actividades de asignación [!DNL Target] [!UICONTROL automática y Destinatario]  automático. Se admiten las métricas de conversión; las métricas de participación e ingresos *no son* compatibles. Si selecciona métricas de objetivo de participación o de ingresos, no se generará un modelo de optimización (aunque la interfaz de usuario actualmente le permita seleccionar métricas de objetivo no admitidas). [!DNL Target]

Para obtener una lista de las métricas de objetivo admitidas y no admitidas, consulte Métricas [de objetivo](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa) admitidas en *Crear una actividad que utilice Analytics como fuente* de sistema de informes. (TNT-38409)

### Entrega de página {#page-delivery}

Si agrega una regla de plantilla, como contenidos de una URL (/checkout, /cart) en la entrega [de](/help/c-activities/t-experience-target/t-xt-create/xt-activity-url.md) página, se añadirán espacios adicionales a las reglas. Se trata de un problema estético que no afecta la creación de definiciones de audiencia ni la entrega de ofertas. (TGT-35920)

### Vínculos de previsualización de control de calidad

Es posible que los vínculos de Vista previa de control de calidad de la actividad para las actividades guardadas no se carguen si hay demasiadas guardadas en su cuenta. Volver a intentar los vínculos de vista previa debería funcionar. Archivar actividades guardadas que ya no se utilizan activamente para evitar que este problema continúe. (TNT-37294)

### Modo de control de calidad para actividades de Recommendations

Un problema conocido impide la previsualización si los criterios utilizados en la actividad están basados en elementos o en categorías. (TNT-37455)

### Ofertas de redireccionamiento {#redirect}

Los siguientes son problemas conocidos de las ofertas de redireccionamiento:

* En algunas condiciones, un número limitado de clientes ha informado de grados de variación más altos en la distribución del tráfico al utilizar una oferta de redireccionamiento en actividades configuradas con Analytics para Target (A4T). Los ingenieros de Adobe están trabajando en este problema.
* Las actividades de redirección en las implementaciones de at.js hacen que la dirección URL de vista previa entre en bucle (la oferta se suministra repetidamente). Puede utilizar el [Modo de control de calidad](/help/c-activities/c-activity-qa/activity-qa.md) para llevar a cabo la vista previa y el control de calidad. Este problema no afecta al suministro real de la oferta. (TGT-23019)

### Cancelación de la carga de una página dentro del VEC {#cancel}

* El siguiente problema conocido aparece al cancelar la carga de una [!UICONTROL prueba A/B] o de [!UICONTROL segmentación de experiencias] (XT) dentro del VEC que contiene una dirección URL de redireccionamiento.

   En el primer paso del flujo de trabajo guiado en tres partes dentro del VEC, al cancelar la carga de la página, se muestra el panel [!UICONTROL Modificaciones] del VEC y se aplica la redirección a la plantilla URL en la experiencia (por ejemplo, &quot;Experiencia B&quot;). Cuando avanza hacia los pasos dos o tres y, después, regresa al paso uno, se produce la siguiente situación.

   De forma predeterminada, en la &quot;Experiencia B&quot;, se representa la plantilla de carga del sitio web cancelado y el panel [!UICONTROL Modificaciones] es accesible, lo cual no debería ser el caso porque esta experiencia tiene una redirección a la plantilla URL aplicada. Debería aparecer el redireccionamiento a la plantilla URL.

   Para mostrar el estado correcto de la experiencia en el VEC:

   Si cambia a otra experiencia y vuelve a la Experiencia B, [!DNL Target] muestra la redirección a la plantilla URL aplicada a esta experiencia y el panel [!UICONTROL Modificaciones] no es accesible. (TGT-32138)

* Para los sitios web de aplicación de una sola página, la cancelación de la carga no permite editar acciones en el panel [!UICONTROL Modificaciones].

### Recommendations

Los siguientes son problemas conocidos de las actividades de Recommendations:

* Las entidades caducan correctamente después de 60 días de no recibir ninguna actualización a través de la fuente o la API; sin embargo, las entidades caducadas no se eliminan del índice de búsqueda en el catálogo después del vencimiento. (IRI-857)
* Las superposiciones &quot;Información de uso&quot; para criterios y diseños no reflejan su uso en actividades A/B y de segmentación de experiencias (TGT-34331)
* Las ofertas de Recommendations en las actividades A/B y de segmentación de experiencias no muestran una previsualización concreta de la bandeja de Recommendations (TGT-33426)
* Las colecciones, las exclusiones, los criterios y los diseños creados mediante API no están visibles en la interfaz de usuario de Target y solo se pueden editar mediante API. (TGT-35777)
* Las actividades de Recommendations creadas mediante API se pueden ver en la interfaz de usuario, pero solo se pueden editar mediante API.
* El estado de la fuente de criterios personalizados que se muestra en la lista de criterios (tarjeta) se actualiza cada diez minutos, y es posible que pasen más de diez minutos de la fecha en circunstancias excepcionales. El estado que se muestra en la vista de edición de criterios personalizados se obtiene en tiempo real y siempre está actualizado. (TGT-35896, TGT-36173)
* Los criterios y las tarjetas de diseño no muestran el número correcto de actividades en las que se utilizan. Si los criterios o el diseño se utilizan en una actividad A/B, es posible que la tarjeta muestre incorrectamente que el diseño o los criterios no se utilizan, incluso cuando el diseño o los criterios se utilizan en la actividad.

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

### Métricas de éxito

Las métricas de éxito con la opción avanzada “Cómo se incrementará el recuento” establecida en “con cada impresión” o en “con cada impresión (excluyendo actualizaciones)” no se pueden utilizar como métricas de suceso de las que dependa otra métrica.

Cuando una métrica de éxito se establece para que se incremente con cada impresión, Target vuelve a contar el visitante cada vez que visita esa métrica de éxito. A continuación, Target restablece la métrica de éxito “abono” a 0 para que pueda contar de nuevo la siguiente impresión. Por lo tanto, si otra métrica requiere que esta métrica se haya visto primero, Target no reconocerá nunca que el usuario ha visto la métrica primero.

### Analytics for Target (A4T)

Cuando utilice impresiones y conversiones de actividad de Destinatario en Analysis Workspace, aplique el modelo de Attribution IQ de &quot;mismo toque&quot; a las métricas para garantizar una contabilización precisa. Para aplicar un modelo [de atribución](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html)no predeterminado, haga clic con el botón derecho en la métrica para **modificar la Configuración de columna > activar Usar modelo de atribución no predeterminado > seleccionar el modelo** de mismo toque. Sin este modelo aplicado, las métricas se sobrevaloran.

Todos los paquetes actuales de Analytics pueden añadir este modelo con Attribution IQ. Si no tiene acceso a Attribution IQ, confíe en los datos de A4T en Informes y análisis.

### API de Target

Los clientes no pueden realizar operaciones de CRUD en actividades de asignación automática a través de la versión v3 de la API de actividades A/B en Adobe I/O.

### Objetivo geográfico

El 10 de mayo de 2020 actualizamos nuestros archivos de proveedores de GEO, lo que introdujo algunas inconsistencias. Por ejemplo, se agregaron algunos valores que contenían comas; aunque los valores de las audiencias existentes no tenían coma. Este cambio no afectó a todos nuestros servidores de envío. Como resultado, es posible que las audiencias que utilizan estos valores no hayan calificado todos los visitantes correctos entre el 10 de mayo y el 22 de julio de 2020.

### Ofertas de imagen que muestran la etiqueta &quot;Procesamiento&quot;

Las ofertas de imagen de la página Ofertas a veces conservan la etiqueta de &quot;procesamiento&quot; durante varias horas después de cargar las imágenes. En la mayoría de los casos, este es un problema solo con la etiqueta: las ofertas de imagen pueden seguir utilizándose en actividades y entregarse. En algunos casos, sin embargo, es posible que una oferta de imagen no esté disponible para la acción Reemplazar contenido > Imagen. Si esto sucede, debe cargar la oferta de imagen de nuevo y comprobar después de unas horas si la oferta de imagen está disponible para su sustitución. (TGT-37458)

### Sistema de informes: datos incoherentes en el informe .csv descargable frente al informe mostrado en la interfaz de usuario de Destinatario. {#csv}

Los informes generados para la descarga como archivos .csv son incoherentes si la actividad utiliza más de una métrica. El informe descargable se genera solo en función de la configuración del informe y considera el mismo valor para cualquier otra métrica utilizada.

La fuente de la verdad es siempre el informe que se muestra en la [!DNL Target] interfaz de usuario.

## Problemas resueltos {#section_FD2FC86E7C734D60B1EDC9DEF60E1014}

A medida que se resuelvan los problemas conocidos que hemos mencionado, pasarán a las siguientes secciones y, si es necesario, se añadirán notas adicionales.

### Creación de informes en Analytics for Target (A4T)

Se han resuelto los siguientes problemas relacionados con A4T:

* Problema que afectaba a las actividades de A4T mediante una métrica de [!DNL Analytics] objetivos que hacía que los informes de A4T mostraran una división de tráfico inesperada o conversiones infladas artificialmente.

   Este problema afectaba al sistema de informes de A4T en las siguientes condiciones:

   * La actividad se creó o guardó entre el 15 de septiembre y el 5 de noviembre de 2020 (4 a.m. PST), y
   * La actividad tenía una [!DNL Analytics] métrica seleccionada como métrica de objetivo.

   [!DNL Target] dividir correctamente el tráfico durante este tiempo. Sin embargo, podría aparecer una división 50/50 en la configuración de actividad, por ejemplo, como una división 90/10 en los informes de A4T.

   Para las actividades afectadas, la división de tráfico correcta es visible para los visitantes nuevos en la actividad después del 5 de noviembre (4 a.m. PST). Las nuevas actividades creadas o guardadas después de esta hora informarán correctamente la división del tráfico.

* Problema que afectaba a las actividades de A4T con una métrica de [!DNL Target] objetivos que hacía que los informes de A4T informaran de conversiones bajas o sin ellas.

   >[!NOTE]
   >
   >Este problema solo afectaba al sistema de informes de A4T. No afectó al envío de la actividad.

   Este problema afectaba al sistema de informes de A4T en las siguientes condiciones:

   * La actividad de A4T estuvo activa entre el 22 de septiembre y el 11 de noviembre de 2020 (2:30 p.m. PST), y
   * La actividad tenía una [!DNL Target] métrica seleccionada como métrica de objetivo y
   * Cuando un visitante alcanzó el evento de objetivo de la actividad (por ejemplo, [!UICONTROL hizo clic en un elemento]), también hubo una actividad de prioridad menor que no es de A4T que coincidió con el evento de conversión. Esto podría suceder si la actividad que no es de A4T se configuró con la misma métrica que la actividad de A4T o si se configuró con la métrica &quot;cualquier mbox&quot;.

   Este problema afectó al sistema de informes de actividades de A4T que estuvieron activas entre el 22 de septiembre y el 11 de noviembre de 2020 (2:30 p.m. PST). El sistema de informes de las actividades de A4T afectadas mostrará correctamente las conversiones fuera de este intervalo de fechas. El sistema de informes para actividades que no son de A4T no se vio afectado.

Si tiene más preguntas, póngase en contacto con el administrador de éxito del cliente (CSM) o con el servicio de atención al cliente de [Adobe](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C). (CSO 20201110016)

### Sistema de informes de Destinatario automático {#at-metrics}

Se ha solucionado un problema que afectaba al sistema de informes de Destinatario [!DNL Adobe Target Premium] [!UICONTROL automático de] los usuarios desde el 15 de septiembre a las 2:30 p.m. (PDT) hasta el 6 de octubre, 9:25 a.m. (PDT). Al ver los informes de las métricas de conversión afectadas (configurados con la opción &quot;[!UICONTROL Visualizó una página]&quot; o &quot;[!UICONTROL Se hizo clic en el mbox]&quot;), las tasas de conversión se registran de manera incorrecta. No se conoce ningún problema de envío en este momento.

Para volver a sincronizar y corregir el sistema de informes:

1. Copie y guarde las actividades de Destinatario  automático afectadas.
1. Active las actividades recién guardadas (si las actividades afectadas estaban activas).
1. Elimine las actividades originales (afectadas).

(TGT-38522, CSO 20201006007)

### Creación de informes{#conversions-audiences}

Actualmente, las conversiones se incrementan de forma diferente en función de la audiencia utilizada.

Por ejemplo, para el mismo visitante, si el recuento de conversiones está configurado para aumentar &quot;Una vez por participante:&quot;

* Audiencia: &quot;Todos los Visitantes cualificados&quot; para conversiones de nivel de visita solo aumentan una vez. Este es el comportamiento esperado.
* Audiencia: Los &quot;nuevos Visitantes&quot; para las conversiones de nivel de visita aumentan incorrectamente cada vez, en lugar de incrementarse solo una vez. Este no es el comportamiento esperado.

Si el recuento de conversiones está configurado para incrementar &quot;En cada impresión:&quot;

* Audiencia: &quot;Todos los Visitantes cualificados&quot; para conversiones de nivel de visitante se incrementan incorrectamente una sola vez, en lugar de incrementarse cada vez. Este no es el comportamiento esperado.
* Audiencia: Los &quot;nuevos Visitantes&quot; para las conversiones de nivel de visitante aumentan cada vez. Este es el comportamiento esperado.

Tenga en cuenta que este problema solo está relacionado con el [!DNL Target] sistema de informes. No se trata de un problema al usar el sistema de informes [!UICONTROL Analytics para Destinatario] (A4T).

Se ha resuelto este problema.

### Páginas que no se cargan en el Compositor de experiencias visuales (VEC) o en el Compositor de experiencias mejorado (EEC) al usar Google Chrome versión 80+

Este problema conocido tiene que ver con la decisión de Google de cambiar el comportamiento predeterminado de las cookies sin el atributo SameSite a partir de la versión 80 de Chrome. Antes del cambio, Chrome establecía de forma predeterminada todas las cookies sin el atributo SameSite como &quot;SameSite=None&quot; y ahora se establece de forma predeterminada como &quot;SameSite=Lax&quot;, lo que cambia la forma en que se envían las cookies en las solicitudes del GET y del POST. Consulte [Actualizaciones](https://www.chromium.org/updates/same-site)del mismo sitio.

Para obtener más información y una corrección, consulte &quot;¿Cómo afectan las políticas de aplicación de cookies de Google Chrome SameSite a los VEC y EEC anunciados recientemente?&quot; in [Troubleshooting Issues Related to the Visual Experience Composer and Enhanced Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

### No se puede procesar el informe de gráfico de una actividad de Segmentación automática al utilizar una experiencia personalizada como control

El informe gráfico de una actividad de segmentación automática no se puede procesar para modos “diferenciales” (Alza media y Alza diaria) si no hay datos (0 visitas) en ninguna experiencia. Esta situación puede suceder durante la etapa inicial de una actividad si la experiencia de control está definida como personalizada. Para los demás modos (Control medio de ejecución y segmentaciones, Control diario y segmentaciones y Visitas) funciona correctamente. Tan pronto como hay algunos datos (visitas que no sean cero), el informe se procesa según lo esperado.

Este problema se solucionó en la versión 19.7.1 de Target.

### mbox.js

La biblioteca mbox.js no admite los lenguajes de plantilla en el lado del cliente, como Handlebars y Mustache. La biblioteca at.js *sí* admite estos lenguajes.

**Nota**: La biblioteca mbox.js ya no está en desarrollo. Todos los clientes deberían migrar de mbox.js a at.js. Para obtener más información, consulte [Migrar a at.js desde mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

### Implementación: Crear mbox global automáticamente

On the Implementation tab ([!UICONTROL Administration > Implementation]) the [!UICONTROL Global Mbox Auto Create] field will be &quot;false&quot; by default for a newly provisioned tenant.

Cuando se descarga mbox.js por primera vez después del aprovisionamiento, el campo [!UICONTROL Creación automática de Global Mbox] se establece en “true” en el archivo mbox.js descargado y en el back-end de [!DNL Target], pero seguirá mostrándose como “false” en la página [!UICONTROL Implementación] de la interfaz de usuario hasta que se actualice la página (una vez hecho, el estado será “true”).

at.js se descargará con `global_mbox_autocreate = false` para un inquilino recién aprovisionado. Si mbox.js se descarga primero, global_mbox_autocreate se establece en “true” y at.js también se descarga con `global_mbox_autocreate = true`. (TGT-15929)

### Compatibilidad con permisos de Enterprise en las API de Target {#api}

Es posible que las ofertas de código creadas desde la interfaz de usuario de Target en la biblioteca de ofertas se muestren en el espacio de trabajo predeterminado si se recupera la lista de ofertas mediante las API de GET. Este problema se solucionará en la primera semana de marzo de 2019. Una vez solucionado el problema, las ofertas de código se mostrarán en el espacio de trabajo apropiado cuando se extraigan de las API. Este problema *no* afecta a las ofertas creadas a partir de las API. Por ejemplo, las ofertas de código creadas a partir de las API se muestran en el espacio de trabajo en el que fueron creadas, ya sea mediante la API de GET o desde la interfaz de usuario de Target.

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

### at.js  {#at-js-2}

Los mboxes no se activan en los navegadores Microsoft Explorer 11 después de actualizar a at.js versión 1.0 debido a la interacción entre at.js y la API de visitante 2.2.0. Este problema afecta a la versión 0.9.6 y posteriores de at.js. (TNT-27600)

Se corrigió en la versión 2.3.0 de API o posteriores.

### Segmentación geográfica

La búsqueda de una cadena que contiene caracteres especiales (como un espacio o una coma) actualmente no funciona al crear audiencias de segmentación geográfica. Este problema surge, por ejemplo, al crear audiencias basadas en ciudades, estados, países, etc. Por ejemplo, cuando se busca “Nueva York”, la búsqueda no devuelve resultados válidos.

Corregido en noviembre de 2018.

### at.js  {#at-js-3}

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

### at.js  {#at-js-4}

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

### at.js  {#at-js-5}

Desde la publicación de Target 17.4.1 (27 de abril de 2017), el uso de la acción Insertar imagen en el Compositor de experiencias visuales (VEC) provoca que el contenido de la oferta no se envíe al usar la biblioteca at.js.

En la versión 0.9.7 de at.js, publicada el 22 de mayo de 2017, se incluyó una solución para este problema.

### Creación de informes: actividades A/B y de segmentación de experiencias (XT)

Entre las 21:00 (PST) del 27 de abril y las 6:00 (PST) del 5 de mayo, las actividades A/B y XT creadas o editadas con cualquier métrica usando la acción de conversión “Visualizó una página” (no basadas en otras métricas) podrían contener conversiones incorrectamente registradas. Este problema ya está resuelto, pero la acción de conversión “Visualizó una página” para estas actividades durante el tiempo en que duró el problema podría no ser precisa y, por desgracia, no se puede corregir. Recomendamos que, para cualquier decisión basada en las acciones de conversión “Visualizó una página” para estas actividades, confíe únicamente en los datos registrados antes o después del periodo afectado.

Pueden utilizarse los datos de otras métricas porque no se vieron afectados.

Este problema se corrigió en la versión 17.4.3 de Target.

### Ofertas: actividades A/B y de segmentación de experiencias (XT)

El envío y la vista previa se vieron afectados para las ofertas de actividades A/B y XT con al menos dos experiencias y creadas o editadas empleando el Compositor de experiencias basadas en formularios entre las 21:00 (PT) del viernes 28 de abril y las 21:15 (PT) del lunes 1 de mayo. Solo se mostraban las ofertas con contenido predeterminado.

Este problema se corrigió en la versión 17.4.3 de Target.

### at.js  {#at-js-6}

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

### at.js  {#at-js-7}

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
