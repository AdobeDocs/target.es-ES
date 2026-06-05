---
keywords: control de calidad;modo de control de calidad; control de calidad de la actividad;url de control de calidad;url de control de calidad;url de vista previa;url de vista previa
description: Aprenda a utilizar las URL de control de calidad de Adobe [!DNL Target] para realizar sencillos controles de calidad de las actividades integrales con vínculos de vista previa invariables, segmentar audiencias de forma opcional y crear informes de control de calidad que permanecen segmentados a partir de datos de actividades activas.
title: ¿Cómo realizo actividades de control de calidad?
feature: Activities
exl-id: 5c606d61-6d13-4a9b-9a23-4840f1754d3c
TQID: https://experienceleague.adobe.com/glE1Kx2xhqagq9v-SgSkdwr6lYwpioe4DlSkLRFQ0jI
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1815
ht-degree: 27%

---

# Control de calidad de la actividad

Use direcciones URL de control de calidad en [!DNL Adobe Target] para realizar sencillos controles de calidad de las actividades de extremo a extremo con vínculos de vista previa invariables, segmentar audiencias de manera opcional y crear informes de control de calidad que permanecen segmentados a partir de datos de actividades activas.

El [!UICONTROL control de calidad de la actividad] le permite probar por completo sus actividades [!DNL Target] antes de lanzarlas en vivo. La funcionalidad [!UICONTROL Control de calidad de la actividad] incluye:

* Vínculos para compartir con integrantes del equipo que nunca cambian ni requieren regeneración, independientemente de las actualizaciones realizadas en las experiencias o actividades. Esta función le permite probar todas las actividades en todo el recorrido del usuario.
* Respeto opcional a las condiciones a público, de forma que los expertos en marketing puedan probar o ignorar criterios de segmentación con el fin de evaluar el aspecto de las experiencias sin necesidad de cumplir sus condiciones de público.
* La realización de informes de control de calidad se captura; de este modo, los expertos en marketing pueden confirmar si las métricas aumentan del modo esperado y es posible mantener los datos de informes de control de calidad separados de los informes de producción (para la creación de informes ajenos a A4T).
* La capacidad de previsualizar una experiencia de forma aislada o con otras actividades activas que satisfagan los criterios de entrega (página/[!DNL Target] solicitud/audiencia).
* La capacidad para realizar un control de calidad del viaje del usuario completo. Puede acceder a su sitio una vez con el vínculo de control de calidad y, a continuación, examinar el sitio entero durante el control de calidad de la actividad. Permanece en el control de calidad de la actividad hasta que finaliza la sesión o hasta que usa el [bookmarklet QA Target](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) para forzar su salida de [!UICONTROL control de calidad de la actividad]. Esta función es útil si tiene una actividad que abarca varias páginas web.

  >[!NOTE]
  >
  >Esta funcionalidad es verdadera para implementaciones at.js con versión 2.*x* o posterior. En implementaciones at.js 1.*x*, esta funcionalidad solo se cumple si el explorador del visitante no bloquea las cookies de terceros.

## Acceso y uso compartido de una URL de control de calidad {#section_1C59BAA247B247BDB125D1BE8EAD4547}

1. En la página [!UICONTROL Información general] de una actividad, haz clic en **[!UICONTROL Control de calidad de la actividad]**.

1. Configure los siguientes ajustes:

   * **[!UICONTROL Hacer coincidir reglas de audiencia para ver las experiencias]:** A veces se desea confirmar que la coincidencia de audiencia funcione. Otras veces, se desea comprobar el aspecto de la actividad. Si esta opción está activada, los analistas deben cumplir los requisitos de segmentación para poder ver las experiencias. En el caso de actividades de Segmentación de experiencias (XT), se proporciona una única URL de actividad. La experiencia que se ve la determina el cumplimiento de alguna de las reglas de segmentación.

     Si esta opción está desactivada, al hacer clic en los vínculos se mostrarán las experiencias independientemente de si se cumplen los requisitos o no. Al realizar el control de calidad, puede cambiar repetidamente entre un ajuste y otro.

   * **Mostrar contenido predeterminado para todas las demás actividades:** Si esta opción está activada, se mostrará el contenido predeterminado para todas las demás actividades. Por ejemplo, la vista previa se muestra aisladamente sin tener en cuenta las demás actividades activas en la misma solicitud de página/[!DNL Target].

     Si el ajuste está desactivado, tenga en cuenta lo siguiente:

      * Si hay conflictos entre la actividad que está probando y otras actividades activas, se aplican [reglas de prioridad normales](/help/main/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F). Debido a los conflictos, es posible que no pueda ver la actividad que desea realizar el control de calidad.
      * Las métricas aumentan para las actividades vistas, pero solo en el entorno de realización de informes de control de calidad.

1. Haga clic en **[!UICONTROL Hecho]** para guardar los cambios.
1. Comparta las direcciones URL de los vínculos de actividad con miembros de su organización para realizar pruebas.

   Los vínculos de actividad nunca caducan y no es necesario que vuelva a enviarlos si alguien cambia una actividad o experiencia. Sin embargo, si aplica una audiencia diferente de la [!UICONTROL Biblioteca de audiencias], en lugar de simplemente editar la actividad, se genera un nuevo vínculo que debe volver a compartir.

   Cada URL de vínculo de actividad (para la Experiencia A, Experiencia B, etc.) le permite iniciar el recorrido del usuario desde la experiencia correspondiente. Haga clic en la dirección URL generada para una experiencia y, a continuación, continúe con la exploración normal del sitio para ver experiencias en varias páginas (si existen varias). Se genera una única URL por experiencia, aunque esta abarque múltiples páginas (prueba de plantilla o prueba multipágina).

   Puede navegar por el sitio para ver las demás páginas porque el modo de control de calidad de la actividad [!UICONTROL Activity Control de calidad] es fijo. Esta situación es cierta en implementaciones de at.js con la versión 2.*x* o posterior. En implementaciones de at.js 1.*x*, esta situación solo es cierta si el explorador del visitante no bloquea las cookies de terceros.

1. Para ver los informes generados a partir de las direcciones URL de los vínculos de actividad, haga clic en la página de la actividad **[!UICONTROL Informes]**, haga clic en el icono **[!UICONTROL Configuración]** ( ![imagen icon_gear](assets/icon_gear.png) ) y, a continuación, seleccione **[!UICONTROL Tráfico en modo de control de calidad]** en la lista desplegable **[!UICONTROL Entorno]**.

## Liberarse del modo de control de calidad

[!UICONTROL El control de calidad de la actividad] es fijo. Después de examinar un sitio web en [!UICONTROL control de calidad de la actividad], tu sesión de [!DNL Target] debe caducar o debes hacer que [!DNL Target] te libere del control de calidad de la actividad [!UICONTROL 5&rbrace; para poder ver tu sitio como un visitante normal.]

### at.js 2.*x*

Si su sitio tiene implementado at.js 2.*x*, use el [bookmarklet de control de calidad de Target](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) para forzar su salida de [!UICONTROL control de calidad de la actividad]. Al cargar una página en su sitio con un valor vacío, como se describe en la siguiente viñeta, *no* elimina la cookie de control de calidad del explorador cuando se implementa at.js 2.*x*.

### at.js 1.*x*

Si su sitio tiene implementado at.js 1.*x*, además de usar el [bookmarklet de control de calidad de Target](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879), también puede forzar la salida manual cargando una página en su sitio con el parámetro `at_preview_token` con un valor vacío. Por ejemplo,

`https://www.mysite.com/?at_preview_token=`

### [!DNL Adobe Experience Platform Web SDK]

Si el sitio tiene implementado [[!UICONTROL Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=es){target=_blank}, puede forzar la salida manualmente cargando una página en el sitio con el parámetro `at_qa_mode` con un valor vacío. Por ejemplo,

`https://www.mysite.com/?at_qa_mode=`

## Consideraciones {#section_B256EDD7BFEC4A6DA72A8A6ABD196D78}

* Dado que el control de calidad de la actividad ya está disponible para todos los tipos de actividad [!DNL Target], la función &quot;Vista previa de actividades de Automated Personalization con URL de vista previa de experiencia&quot; ya no es necesaria.
* [!UICONTROL Es posible que los vínculos de vista previa del control de calidad de la actividad] para las actividades guardadas no se carguen si hay demasiadas guardadas en su cuenta. Volver a intentar los vínculos de vista previa debería funcionar. Para evitar que esta situación siga ocurriendo, archive las actividades guardadas que ya no se utilizan de forma activa.
* Las direcciones URL de [!UICONTROL control de calidad de la actividad] están disponibles con actividades con [Analytics como fuente de informes](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Las visitas generadas al realizar el control de calidad mediante [!UICONTROL control de calidad de la actividad] fluyen al mismo grupo de informes donde los datos de la actividad fluyen incluso después de que esta se active.
* [!UICONTROL El control de calidad de la actividad] no muestra el contenido de las actividades archivadas o las actividades que han pasado sus fechas de finalización. Si desactiva una actividad finalizada, debe volver a guardar la actividad para que funcione [!UICONTROL Control de calidad de la actividad].
* Las actividades importadas en [!DNL Target Standard/Premium] (desde [!DNL Target Classic], por ejemplo) no admiten direcciones URL de control de calidad.
* En las actividades [!UICONTROL Asignación automática] y [!UICONTROL Recommendations], el modelo no se ve afectado por las visitas capturadas en [!UICONTROL Control de calidad de la actividad].
* Si especificó &quot;la dirección URL es&quot; al crear la actividad [refinamientos en las opciones de Compositor basado en formularios](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) o [envío de página en el Compositor de experiencias visuales)](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81), la dirección URL de control de calidad no funciona porque [!UICONTROL Control de calidad de la actividad] adjunta parámetros de dirección URL. Para solucionar este problema, haga clic en la URL de control de calidad para ir a su sitio, elimine los parámetros añadidos a la URL y cargue la nueva dirección.
* Si tiene at.js 1.*x*, el modo de control de calidad de la actividad [!UICONTROL 3&rbrace; no es fijo si usa Safari u otro explorador que bloquee cookies de terceros. &#x200B;]En estos casos, debe agregar los parámetros de vista previa a cada dirección URL a la que vaya. Lo mismo ocurre si ha implementado [CNAME](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/implement-cname-support-in-target.html){target=_blank}.
* Si una actividad utiliza varias audiencias de experiencia (por ejemplo, un sitio con versiones para Reino Unido y Estados Unidos incluidas en la misma actividad), no se generan vínculos de control de calidad para las cuatro combinaciones (experiencia A/sitio EE. UU., experiencia A/sitio RU, experiencia B/sitio EE. UU., experiencia B/sitio RU). Se crean solo dos vínculos de QA (Experiencia A y Experiencia B) y los usuarios deben cumplir las condiciones de audiencia apropiadas para ver la página. Una persona con control de calidad del Reino Unido no puede ver el sitio de EE. UU.
* Todos los parámetros y valores de `at_preview` ya están codificados en la URL. La mayoría de las veces, todo funciona según lo esperado. Sin embargo, algunos clientes deben disponer de equilibradores de carga o servidores Web que intenten codificar de nuevo los parámetros de cadena de consulta.

  Debido a esta doble codificación, cuando [!DNL Target] intenta descodificar `at_preview_token`, [!DNL Target] no puede extraer el valor del token correcto, lo que hace que la vista previa no funcione.

  [!DNL Adobe] le recomienda que hable con su equipo de TI para asegurarse de que todos los parámetros de vista previa estén incluidos en la lista de permitidos de modo que estos valores no se transformen en modo alguno.

  En la tabla siguiente se enumeran los parámetros que se pueden ver incluidos en la lista de permitidos en el dominio:

  | Parámetro | Tipo | Valor | Descripción |
  |--- |--- |--- |--- |
  | `at_preview_token` | Cadena cifrada | Obligatorio; no hay valor predeterminado | Una entidad cifrada que contiene la lista de ID de campañas que se pueden ejecutar en modo de control de calidad. |
  | `at_preview_index` | Cadena | Vacío | El formato del parámetro es `<campaignIndex>` o `<campaignIndex>_< experienceIndex>`<br>Ambos índices comienzan con 1. |
  | `at_preview_listed_activities_only` | Booleano (true/false) | Valor predeterminado: false | Si es “true”, se procesan todas las campañas especificadas en los parámetros `at_preview_index`.<br>Si es “false”, se procesan todas las campañas de la página, aunque no se especificaran en el token de vista previa. |
  | `at_preview_evaluate_as_true_audience_ids` | Cadena | Vacío | Lista de segmentId separada por guiones bajos (&quot;_&quot;) que siempre (en los niveles de segmentación e informes) deben evaluarse como &quot;true&quot; en el ámbito de la solicitud [!DNL Target]. |
  | `_AT_Debug` | Cadena | Ventana o consola | Registro de consola o nueva ventana. |
  | `adobe_mc_ref` |  |  | Pasa la URL de referencia de la página predeterminada a la nueva página. Cuando se utiliza con `AppMeasurement.js` versión 2.1 (o posterior), [!DNL Adobe Analytics] usa este valor de parámetro como URL de referencia en la nueva página. |
  | `adobe_mc_sdid` |  |  | Pasa [!DNL Supplemental Data Id] (SDID) y [!DNL Experience Cloud Org Id] de la página predeterminada a la nueva página. Al pasar estos identificadores, [!UICONTROL Analytics for Target] (A4T) puede &quot;unir&quot; la solicitud [!DNL Target] de la página predeterminada con la solicitud [!DNL Analytics] de la nueva página. |

* La interfaz de usuario [!UICONTROL Modo de control de calidad de Target] solo muestra la primera URL de una experiencia en una actividad de varias páginas. Se supone que está creando una prueba de recorrido y pasa de la URL 1 a la URL 2. Sin embargo, si desea ir a la URL 2 de forma independiente, copie todos los parámetros de la URL proporcionados con la URL 1 y aplíquelos a la URL 2 después de colocar “?” como se ve en la URL 1.
* Es posible que los vínculos de Vista previa de control de calidad de la actividad para las actividades guardadas no se carguen si hay demasiadas guardadas en su cuenta. Reinténtelo con los vínculos de previsualización. Archive las actividades guardadas que ya no se utilizan activamente para evitar que este problema siga ocurriendo.

## Compatibilidad con la biblioteca JavaScript de destino [!UICONTROL Modo QA] {#compatibility}

[!DNL Target] admite las siguientes bibliotecas de JavaScript:

* [at.js 1.x](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html)
* [at.js 2.x](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html)
* [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=es)

En la tabla siguiente se enumeran los distintos tipos de actividades y se indica si se admite el modo [!UICONTROL Control de calidad de la actividad] para cada biblioteca:

| Tipo de actividad | at.js 1.x | at.js 2.x | Platform Web SDK |
| --- | --- | --- | --- |
| [!UICONTROL Prueba A/B] | Sí | Sí | Sí |
| [!UICONTROL Asignación automática] | Sí | Sí | Sí |
| [!UICONTROL Segmentación automática] | Sí | Sí | Sí |
| [!UICONTROL Automated Personalization] (AP) | Sí | Sí | Sí |
| [!UICONTROL Segmentación de experiencias] (XT) | Sí | Sí | Sí |
| [!UICONTROL Prueba multivariada] (MVT) | Sí | Sí | Sí |
| [!UICONTROL Recommendations] | Sí | Sí | Sí |