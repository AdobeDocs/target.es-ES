---
keywords: target documentation change log;documentation updates;new topics;edits;updates;update
description: Esta página lista los cambios importantes realizados en la documentación de Adobe Target, ordenados por versiones.
title: Cambios en la documentación de los productos de Adobe Target.
feature: release notes
topic: Standard
uuid: 6fba75e2-0a93-488d-9010-fffa423600c0
translation-type: tm+mt
source-git-commit: 61273ea3174f5b380a2d8d6b664584f4e3d7f6ff
workflow-type: tm+mt
source-wordcount: '1939'
ht-degree: 30%

---


# Cambios de la documentación{#documentation-changes}

This page lists important changes made to the [!DNL Adobe Target] product documentation.

## Adobe Target Standard/Premium 20.7.1 (27 de julio de 2020)

| Fecha | Tema | Cambios |
| --- | --- | --- |
| 24 de agosto | [Métricas de éxito](/help/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B) | Se ha actualizado la sección &quot;Configuración avanzada&quot;. |
| 21 de agosto | [Introducción al kit de bienvenida de Adobe Target](/help/c-intro/target-welcome-kit.md) | Nuevo artículo y subtemas. |
| 20 de agosto | [Resolución de problemas relacionados con el Compositor de experiencias visuales y el Compositor de experiencias mejorado](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md) | Se añadió la siguiente sección: &quot;¿Cómo afectan las políticas de aplicación de cookies de Google Chrome SameSite al VEC y al EEC?&quot; |
|  | [Rastreo de clics](/help/c-activities/r-success-metrics/click-tracking.md) | Se ha actualizado el siguiente texto: &quot;Si selecciona más de un elemento, si un participante hace clic en cualquiera de los elementos seleccionados, se contabilizará el clic. Para contar cada elemento por separado, configure métricas de éxito individuales para cualquier elemento. Para contar un elemento haciendo clic en varios elementos de una página, edite el selector de elementos CSS para que coincida con varios elementos.&quot; |
|  | [Notas de la versión de Target (versión previa)](/help/r-release-notes/target-release-notes.md) | Se ha añadido información sobre la versión Target Standard/Premium 20.9.1 (2 de septiembre de 2020). |
| 14 de agosto | [Problemas conocidos y problemas resueltos](/help/r-release-notes/known-issues-resolved-issues.md) | Se ha añadido un problema conocido sobre control de calidad en actividades de Recommendations. |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Texto añadido que indica que si está utilizando `serverState` y utilizando `<script>` etiquetas en el contenido devuelto, asegúrese de que el contenido HTML utiliza `<\/script>` en lugar de `</script>`. |
| 12 de agosto | [Comprender la IU de Destinatario](/help/c-intro/understand-the-target-ui.md) | Nuevo tema. |
|  | [Información general sobre la API de Adobe Target](/help/api/api-overview.md) | Nuevo tema. |
| 10 de agosto | [CNAME y Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Texto añadido que indica que el tamaño del encabezado de la cookie aumentará al utilizar CNAME. |
|  | [Integrar Destinatario con Adobe Audience Manager](/help/c-integrating-target-with-mac/audience-manager-target-integration.md) | Nuevo tema. |
|  | [Anuncios y eventos de destinatario](/help/r-release-notes/target-announcements.md) | Vínculo añadido a la vista del siguiente seminario web archivado: &quot;Cómo HSBC aprovecha Adobe Target y AI para optimizar rápidamente y ofrecer personalización a escala&quot;. |
| 6 de agosto | [Segmentación automática](/help/c-activities/auto-target-to-optimize.md#how-long) | Se ha actualizado el texto de las siguientes preguntas más frecuentes: &quot;¿Cuánto tiempo debo esperar a que se construyan los modelos?&quot; |
|  | [Clasificaciones: Preguntas más frecuentes sobre A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-classifications.md) | Se ha actualizado el texto del tipo de destino. |
| 5 de agosto | [Eliminar la cookie de Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cookie-deleting.md) | Se ha actualizado todo el tema. |
| 4 de agosto | [Anuncios y eventos de destinatario](/help/r-release-notes/target-announcements.md) | Se añadió la información de registro sobre el seminario web &quot;Estrategias de personalización que usan inteligencia artificial y Adobe Target&quot; programado para el 13 de agosto. |
|  | [Activación de contenido mixto en el navegador](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/mixed-content.md) | Tema actualizado. |
| 3 de agosto | [Métricas de éxito](/help/c-activities/r-success-metrics/success-metrics.md) | Nota añadida que aclara qué significan las opciones [!UICONTROL Aumentar recuento] en relación con los visitantes vs. las visitas. |
| Julio de 31 | [Problemas conocidos y problemas resueltos](/help/r-release-notes/known-issues-resolved-issues.md) | Se ha añadido un nuevo problema conocido: &quot;Ofertas de imagen que muestran la etiqueta &quot;Procesamiento&quot;.&quot; |
|  | [adobe.target.getOffers(options) - at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) | Ejemplo de código añadido que se usará `getoffers()` para realizar un pageLoad. |
|  | [Anuncios y eventos de destinatario](/help/r-release-notes/target-announcements.md) | Añadió la información de registro sobre el próximo Adobe Target Community Coffee Break el 5 de agosto. |
| Julio de 28 | [Informes](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)de perspectivas de personalización, informe<br>[de segmentos](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md)automatizados<br>y atributos [importantes](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md) | Se ha actualizado el texto de la nota en la parte superior de los temas. |
|  | [Asignación automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Se agregaron las siguientes preguntas más frecuentes:<ul><li>¿Puedo utilizar la opción Restablecer datos del informe mientras ejecuto una actividad de asignación automática?</li><li>¿Cómo genera la asignación automática modelos con respecto a los entornos?</li></ul> |
|  | [Segmentación automática](/help/c-activities/auto-target-to-optimize.md) | Se ha añadido la siguiente pregunta muy frecuente: <ul><li>¿Puedo utilizar la opción Restablecer datos del informe al ejecutar una actividad de Destinatario automático?</li></ul>Se ha actualizado el texto en la sección &quot;Consideraciones&quot;. |
|  | [Preguntas más frecuentes sobre Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization-faq.md) | Se agregaron las siguientes preguntas más frecuentes:<ul><li>¿Puedo utilizar la opción Restablecer datos del informe al ejecutar una actividad de Automated Personalization?</li><li>¿Cómo construye Automated Personalization modelos con respecto a los entornos?</li></ul> |
|  | [Navegadores admitidos](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md) | Información añadida sobre Internet Explorer y elementos desconocidos. |
|  | [Atributos del cliente](/help/c-target/c-visitor-profile/working-with-customer-attributes.md) | Updated following paragraph:<br>[!DNL Adobe] does not guarantee that 100% of customer attribute (visitor profile) data from CRM databases will be onboarded to the [!DNL Experience Cloud] and, thus, be available for use for targeting in [!DNL Target]. En nuestro diseño actual, existe la posibilidad de que un pequeño porcentaje de datos (hasta el 0,1% de los lotes de producción grandes) no se incorporen. |
| Julio de 27 | [Administración de Target](/help/administrating-target/administrating-target.md) | Se ha actualizado el texto de todos los temas vinculados de esta página para reflejar los nuevos cambios en la interfaz de usuario de las páginas de [!UICONTROL administración] . |
|  | [Anuncios y eventos de destinatario](/help/r-release-notes/target-announcements.md) | Se han implementado los siguientes cambios: <ul><li>Información de registro añadida para el siguiente seminario web: &quot;Cómo HSBC aprovecha Adobe Target y AI para optimizar rápidamente y ofrecer personalización a escala&quot;.</li><li>Se ha añadido información sobre el Adobe como Líder en el Cuadrante Mágico de Gartner para Motores de Personalización.</li></ul> |
|  | [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md) | Se ha aclarado la información en el paso 4: Seleccione una ubicación. |
| Julio de 24 | <br>[Detalles de las versiones de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Se ha añadido información sobre at.js 2.3.2. |
|  | [Notas de la versión](/help/r-release-notes/release-notes.md): 20.7.1 | Esta versión incluye mejoras y correcciones. Puede leer al respecto y consultar la documentación desde las Notas de la versión. Esta versión incorpora muchas actualizaciones de documentación en la ayuda. |

## Adobe Target Standard/Premium 20.5.1 (17 de junio de 2020). 

| Fecha | Tema | Cambios |
| --- | --- | --- |
| Julio de 17 | [Anuncios y eventos de destinatario](/help/r-release-notes/target-announcements.md) | Información añadida sobre la pausa para café de Adobe Target del 22 de julio. |
| Julio de 15 | [La asignación automática puede proporcionar resultados de prueba más rápidos y mayores ingresos que una prueba manual](/help/c-activities/automated-traffic-allocation/faster-results-higher-revenue.md) | Nuevo tema. |
| Julio de 14 | [Preguntas más frecuentes sobre asignación](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)automática, Destinatario<br>[](/help/c-activities/auto-target-to-optimize.md)automático<br><br>[y personalización automatizada](/help/c-activities/t-automated-personalization/automated-personalization-faq.md) | Preguntas más frecuentes añadidas que recomiendan que no debe cambiar la métrica de objetivos a mitad de una actividad. |
| Julio de 7 | [Anuncios y eventos de destinatario](/help/r-release-notes/target-announcements.md) | Información añadida sobre el Descanso del Café Adobe Target del 8 de julio. |
| 25 de junio | [Notas de la versión de Target (versión previa)](/help/r-release-notes/target-release-notes.md) | Información añadida sobre la versión Target Standard/Premium 20.6.1 (julio de 2020). |
|  | [Información general sobre la documentación de destinatario](/help/r-release-notes/target-documentation.md) | Nuevo tema que detalla las diferentes fuentes de [!DNL Target] documentación. |
| 23 de junio | [Anuncios y eventos de destinatario](/help/r-release-notes/target-announcements.md) | Información añadida sobre la pausa para café de Adobe Target del 24 de junio. |
|  | [Atributos de perfil](/help/c-target/c-visitor-profile/profile-parameters.md) | Se ha añadido que no se recomienda crear secuencias de comandos de perfil dependientes que utilicen el resultado de un script de perfil en otro script de perfil. |
|  | [Cómo funciona at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) | Se añadió el siguiente vídeo: Horario de oficina: Sugerencias de at.js y descripción general |
| 17 de junio | [CNAME y Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Tema actualizado. |
|  | [Tokens de respuesta](/help/administrating-target/response-tokens.md) | Se añadió información sobre los tokens de respuesta para el método de asignación de tráfico para actividades [!UICONTROL de Destinatario] automático y [!UICONTROL Automated Personalization] . |
|  | [Creación de actividad](/help/c-integrating-target-with-mac/a4t/campaign-creation.md) | Información añadida sobre la compatibilidad de Analytics para Destinatario (A4T) con actividades de asignación automática. |
|  | [Usuarios](/help/administrating-target/c-user-management/c-user-management/user-management.md) | Se añadió información sobre la nueva función de [!UICONTROL Editor] en *Especificar funciones y permisos*. |
|  | [Configuración de permisos de Enterprise](/help/administrating-target/c-user-management/property-channel/properties-overview.md) | Información añadida sobre la nueva función de [!UICONTROL Editor] en el *paso 6: Especifique funciones y permisos*. |
|  | [Permisos de usuario de Enterprise](/help/administrating-target/c-user-management/property-channel/property-channel.md) | Vínculo añadido al horario de *Office: Destinatario Premium Workspaces, sesión*. |
|  | [Notas de la versión](/help/r-release-notes/release-notes.md): 20.5.1 | Esta versión incluye mejoras y correcciones. Puede leer al respecto y consultar la documentación desde las Notas de la versión. Esta versión incorpora muchas actualizaciones de documentación en la ayuda. |

## Adobe Target Standard/Premium 20.4.1 (6 de mayo de 2020). 

| Fecha | Tema | Cambios |
| --- | --- | --- |
| 15 de junio | [Notas de la versión de Target (actual)](/help/r-release-notes/release-notes.md) | Información añadida sobre las versiones 1.8.2 y 2.3.1 de at.js. |
|  | [Detalles de las versiones de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Información añadida sobre las versiones 1.8.2 y 2.3.1 de at.js. |
|  | [Notas de la versión de Target (versión previa)](/help/r-release-notes/target-release-notes.md) | Se han actualizado las notas de la versión [!DNL Target Standard/Premium] 20.5.1 (17 de junio de 2020) para incluir información sobre la compatibilidad con A4T en [!DNL Analysis Workspace]. |
| 12 de junio | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Se ha añadido información sobre la opción de configuración `deviceIdLifetime`. |
|  | [Notas de la versión de Target (versión previa)](/help/r-release-notes/target-release-notes.md) | Información añadida sobre las versiones 1.8.2 y 2.3.1 de at.js. |
| 8 de junio | [Preguntas más frecuentes sobre destinatario para aplicaciones móviles](/help/c-target-mobile-app/target-for-mobile-apps-faq.md) | Se ha actualizado el texto de las siguientes preguntas más frecuentes: &quot;¿Es Destinatario Mobile una funcionalidad de SKU de producto de Adobe Target Premium solamente?&quot; |
|  | [Visualización de informes: preguntas más frecuentes sobre A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | Se ha actualizado todo el tema. |
| 5 de junio | [Anuncios y eventos de destinatario](/help/r-release-notes/target-announcements.md) | Información añadida sobre el Descanso del Café Adobe Target del 10 de junio. |
|  | [Alza y confianza: preguntas más frecuentes sobre A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-lift-and-confidence.md) | Se ha actualizado el texto de las siguientes preguntas más frecuentes: &quot;¿Por qué no puedo ver el alza y la confianza en las métricas calculadas?&quot; |
| 4 de junio | [Informes de A4T](/help/c-integrating-target-with-mac/a4t/reporting.md) | Se ha actualizado la sección &quot;Informes en Analytics&quot;. |
| 1 de junio | [Anuncios de destinatario](/help/r-release-notes/target-announcements.md) | Se añadió una nueva página para anunciar los próximos eventos de Destinatario. |
|  | [Ventanillas móviles para las experiencias adaptables](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md) | Se han actualizado las dimensiones y resoluciones de la ventanilla para Apple iPhone 11, Apple iPhone SE y Google Pixel 2 XL. |
| Mayo de 28 | [Preguntas más frecuentes sobre la creación de informes](/help/c-reports/reporting-frequently-asked-questions.md) | Se ha añadido la siguiente pregunta frecuente: <ul><li>¿Cómo se cuentan las métricas Nuevos Visitantes y Visitantes que regresan?</li></ul> |
| Mayo de 27 | [Notas de la versión de Target (versión previa)](/help/r-release-notes/target-release-notes.md) | Información añadida sobre la compatibilidad de Analytics para Destinatario (A4T) con actividades de asignación automática. |
| Mayo de 26 | [Atributos de perfil](/help/c-target/c-visitor-profile/profile-parameters.md) | Se añadió la siguiente información: &quot;El parámetro permanece en el perfil después de desactivar la secuencia de comandos. Los usuarios cuyos perfiles ya contengan un parámetro que se utilice en la audiencia de una actividad se clasificarán en esa actividad&quot;. |
| Mayo de 21 | [Nodos de borde de Destinatario de lista de permitidos](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md) | Añadido `mboxedge30.tt.omtrdc.net` a la lista. |
| Mayo de 20 | [Notas de la versión de Target (versión previa)](/help/r-release-notes/target-release-notes.md) | Se ha añadido información sobre la próxima versión de Target Standard/Premium 20.6.1 (10 de junio de 2020). |
|  | [Hosts](/help/administrating-target/hosts.md) | Nota añadida a la sección &quot;Prácticas recomendadas de seguridad&quot;. |
| Mayo de 14 | [Notas de la versión de Target (actual)](/help/r-release-notes/release-notes.md) | Se añadió información sobre los cambios de la API v2 de estado de lote de Perfil. |
| Mayo de 13 | [CNAME y Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Sección &quot;Limitaciones conocidas&quot; añadida. |
| Mayo de 11 | [Hosts](/help/administrating-target/hosts.md) | Información añadida sobre el uso de la funcionalidad ubox con redirecciones y listas de permitidos. |
|  | [Trabajar con redirectores](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) | Información añadida sobre el uso de hosts para evitar vulnerabilidades de redireccionamiento abierto. |
|  | [Integrar Recommendations con el correo electrónico](/help/c-recommendations/c-recommendations-faq/integrating-recs-email.md) | Información añadida sobre el uso de hosts para evitar vulnerabilidades de redireccionamiento abierto. |
|  | [Correo electrónico: implementación de Target](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md) | Información añadida sobre el uso de hosts para evitar vulnerabilidades de redireccionamiento abierto. |
|  | [Control de calidad de la actividad](/help/c-activities/c-activity-qa/activity-qa.md) | Se ha actualizado la sección &quot;Consideraciones&quot;. |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Se ha actualizado la fila &quot;overrideMboxEdgeServer&quot; en &quot;Configuración&quot;. |
| Mayo de 6 | [Prevención inteligente del seguimiento de Apple (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md) | Información añadida sobre ITP 2.3. |
|  | [Notas de la versión](/help/r-release-notes/release-notes.md): 20.4.1 | Esta versión incluye mejoras y correcciones. Puede leer al respecto y consultar la documentación desde las Notas de la versión. Esta versión incorpora muchas actualizaciones de documentación en la ayuda. |

## Adobe Target Standard/Premium 20.2.1 (19 de febrero de 2020)

| Fecha | Tema | Cambios |
| --- | --- | --- |
| Mayo de 4 | [Preguntas más frecuentes sobre la creación de informes](/help/c-reports/reporting-frequently-asked-questions.md#uneven) | Nuevas preguntas más frecuentes añadidas: &quot;¿Por qué el tráfico se divide entre mis experiencias de forma desigual en mi actividad A/B o MVT?&quot; |
| Abril de 29 | [Problemas conocidos y problemas resueltos](/help/r-release-notes/known-issues-resolved-issues.md) | Se ha añadido un problema conocido para el sistema de informes de pedidos extremos. |
| Abril de 28 | [Glosario de perfiles y variables](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md) | Se ha eliminado la información sobre el uso `user.header('x-forwarded-for')` con bordes AWS más recientes para recuperar las direcciones IP de los usuarios. Este comando ahora funciona con los bordes AWS más recientes. |
|  | [Notas de la versión de Target (versión previa)](/help/r-release-notes/target-release-notes.md) | Se ha cambiado la fecha de la versión de Target Standard/Premium (20.4.1) al 6 de mayo. |
| Abril de 23 | [CNAME y Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Tema actualizado. |
| Abril de 22 | [Notas de la versión de Target (versión previa)](/help/r-release-notes/target-release-notes.md) | Nueva sección añadida: *Cambios en la API de estado de lote de perfil v2 (4 de mayo de 2020).* |
| Abril de 14 | [Hosts perimetrales de Destinatario de lista de permitidos](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md) | Nuevo tema. |
| Abril de 10 | [Implementación de aplicación de página única](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md#bp) | Nueva sección añadida: &quot;Prácticas recomendadas de implementación&quot;. |
| Abril de 7 | [Alza y confianza: preguntas más frecuentes sobre A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-lift-and-confidence.md#lift-condidence) | Texto actualizado para &quot;¿Por qué no puedo ver el alza y la confianza en las métricas calculadas?&quot; |
| Abril de 2 | [Glosario de perfiles y variables](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md) | Información añadida sobre el uso `user.header('x-forwarded-for')` con los bordes AWS más recientes para recuperar las direcciones IP de los usuarios. |
|  | [Actualización de at.js 1.*x* a at.js 2.*x*](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md) | Se ha añadido la nota siguiente:<ul><li>Después de instalar la biblioteca ECID 4.3.0+ y at.js 2.,*x*, podrá crear actividades que abarquen dominios únicos y rastrear usuarios. Es importante tener en cuenta que esta funcionalidad solo funciona después de que caduque la sesión.</li></ul> |
| Marzo de 30 | [Problemas conocidos y problemas resueltos](/help/r-release-notes/known-issues-resolved-issues.md#atjs) | Se han añadido problemas conocidos que afectan a las versiones de at.js anteriores a at.js 2.2.0. Este problema provocaba que el rastreo de clics no informara de las conversiones en Analytics para Destinatario (A4T) cuando el código de Adobe Analytics no estaba presente en los elementos de página. |
|  | [Detalles de las versiones de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Se añadió la siguiente información en los detalles de la versión 2.2.0 de at.js:<ul><li>Se ha corregido un problema que provocaba que el rastreo de clics no informara de las conversiones en Analytics para Destinatario (A4T) cuando el código de Adobe Analytics no estaba presente en los elementos de página.</li></ul> |
| Marzo de 25 | [Detalles de las versiones de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Información añadida sobre las siguientes nuevas versiones de at.js:<ul><li>Versión 2.3.0 de at.js</li><li>Versión 1.8.1 de at.js</li></ul> |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Se han añadido las siguientes filas nuevas en la sección &quot;Configuración&quot;:<ul><li>cspScriptNonce</li><li>cspStyleNonce</li></ul>Se ha añadido esta nueva sección:<ul><li>Directiva de seguridad del contenido</li></ul> |
| Marzo de 24 | [Prevención inteligente del seguimiento de Apple (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md#impact) | Información añadida sobre los impactos para lo siguiente:<ul><li>Secuencias de comandos de perfil basadas en 3rdPartyID</li><li>Direcciones URL de control de calidad/Previsualización en dispositivos iOS</li></ul> |
| Marzo de 20 | [Notas de la versión (actual)](/help/r-release-notes/release-notes.md) | Se indica que la versión de Target Standard/Premium 20.2.1 será el 23 de marzo de 2020. |
| Marzo de 13 | [Límites](/help/r-troubleshooting-target/target-limits.md) | Se ha actualizado el número de &quot;Audiencias, reutilizables por cuenta&quot;. |
| Marzo de 12 | [Notas de la versión (actual)](/help/r-release-notes/release-notes.md#summit) | Información de registro añadida para el acceso gratuito a la conferencia digital en línea de la Cumbre. |
| Marzo de 9 | [Privacidad](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md) | Se añadió más información en la sección &quot;Sustitución del último octeto de direcciones IP&quot;. |
|  | [Trabajar con atributos de varios valores](/help/c-recommendations/c-algorithms/work-with-multi-value-attributes.md) | Se ha actualizado el ejemplo de código en *Pasar un parámetro de varios valores en JavaScript*. |
|  | [Atributos de entidad personalizados](/help/c-recommendations/c-products/custom-entity-attributes.md) | Ejemplo de código añadido en *Uso de API* en *Implementación de atributos* de varios valores. |
| Marzo de 4 | [Atributos de perfil](/help/c-target/c-visitor-profile/profile-parameters.md) | Se ha actualizado todo el tema con amplias revisiones a la sección &quot;Prácticas recomendadas&quot;. |
| 21 de febrero | [Notas de la versión (actual)](/help/r-release-notes/release-notes.md) | Información añadida sobre la nueva navegación de Adobe Experience Cloud. |
| 20 de febrero | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Updated the description for the `enabled` setting. Información añadida para la siguiente configuración: `pageLoadEnabled` y `viewsEnabled`. |
|  | [Ubicación geográfica](/help/c-target/c-audiences/c-target-rules/geo.md) | Nota añadida que `mboxOverride.browserIp` se admite en at.js 1.Solamente *x.* |
|  | [Detalles de las versiones de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Se ha aclarado el texto que explica qué versiones de at.js admite el equipo de Destinatario. |
|  | [Notas de la versión](/help/r-release-notes/release-notes.md): 20.2.1 | Esta versión incluye mejoras y correcciones. Puede leer al respecto y consultar la documentación desde las Notas de la versión. Esta versión incorpora muchas actualizaciones de documentación en la ayuda. |

## Adobe Target Standard/Premium 20.1.1 (4 de febrero de 2020)

| Fecha | Tema | Cambios |
| --- | --- | --- |
| 4 de febrero | [Notas de la versión](/help/r-release-notes/release-notes.md): 20.1.1 | Esta versión incluye mejoras y correcciones. Puede leer al respecto y consultar la documentación desde las Notas de la versión. Esta versión incorpora muchas actualizaciones de documentación en la ayuda. |
