---
keywords: control de calidad;modo control de calidad; control de calidad de la actividad;url de control de calidad;url de control de calidad;url de vista previa;url de vista previa
description: Aprenda a utilizar Adobe [!DNL Target] Direcciones URL de control de calidad para realizar sencillos controles de calidad de las actividades de extremo a extremo con vínculos de vista previa invariables, segmentación opcional de audiencias e informes de control de calidad que permanecen segmentados a partir de datos de actividades activas.
title: ¿Cómo Se Hacen Evaluaciones De Las Actividades?
feature: Activities
exl-id: 5c606d61-6d13-4a9b-9a23-4840f1754d3c
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '1832'
ht-degree: 39%

---

# Control de calidad de la actividad

Use direcciones URL de control de calidad en [!DNL Adobe Target] para realizar sencillos controles de calidad de las actividades de extremo a extremo con vínculos de vista previa invariables, segmentación opcional de audiencias e informes de control de calidad que permanecen segmentados a partir de datos de actividades activas.

[!UICONTROL Control de calidad de la actividad] permite probar completamente el [!DNL Target] antes de lanzarlas en directo. La variable [!UICONTROL Control de calidad de la actividad] incluye:

* Vínculos que nunca cambian ni requieren regeneración, independientemente de las actualizaciones realizadas en las experiencias o actividades, para compartir con los integrantes del equipo. Esta función le permite probar completamente sus actividades en todo el recorrido del usuario.
* Respeto opcional a las condiciones a audiencia, de forma que los expertos en marketing puedan probar o ignorar criterios de segmentación con el fin de evaluar el aspecto de las experiencias sin necesidad de cumplir sus condiciones de audiencia.
* La realización de informes de control de calidad se captura; de este modo, los expertos en marketing pueden confirmar si las métricas aumentan del modo esperado y es posible mantener los datos de informes de control de calidad separados de los informes de producción (para la creación de informes ajenos a A4T).
* La capacidad de obtener una vista previa de una experiencia de forma aislada o con otras actividades activas que cumplan los criterios de entrega (página/solicitud de Target/audiencia).
* La capacidad para realizar un control de calidad del viaje del usuario completo. Puede acceder a su sitio una vez con el vínculo de control de calidad y, a continuación, examinar el sitio entero durante el control de calidad de la actividad. Permanecerá en el control de calidad de la actividad hasta que termine la sesión o hasta que utilice el  [bookmarklet QA Target](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879)[!UICONTROL  para forzar su salida de dicho control de calidad]. Esta función es útil si tiene una actividad que abarca varias páginas web.

   >[!NOTE]
   >
   >Esta funcionalidad se aplica a las implementaciones de at.js con la versión 2.*x* o posterior. Para at.js 1.*x* , esta funcionalidad solo es verdadera si el explorador del visitante no bloquea las cookies de terceros.

## Acceso y uso compartido de una URL de control de calidad {#section_1C59BAA247B247BDB125D1BE8EAD4547}

1. Desde el [!UICONTROL Información general] , haga clic en el botón **[!UICONTROL Control de calidad de la actividad]** vínculo.

   ![Vínculo de control de calidad de la actividad](assets/qa_link.png)

1. Configure los siguientes ajustes:

   ![Opciones de configuración de vínculo de control de calidad](assets/qa_link_config.png)

   * **[!UICONTROL Hacer coincidir reglas de audiencia con las experiencias]:** A veces, se quiere confirmar que la coincidencia de audiencias funcione. Otras veces desea comprobar el aspecto de la actividad. Si esta opción está activada, los analistas deben cumplir los requisitos de segmentación para poder ver las experiencias. En el caso de actividades de Segmentación de experiencias (XT), se proporciona una única URL de actividad. La experiencia que se ve la determina el cumplimiento de alguna de las reglas de segmentación.

      Si esta opción está desactivada, al hacer clic en los vínculos se mostrarán las experiencias independientemente de si se cumplen los requisitos o no. Al realizar el control de calidad, puede cambiar repetidamente entre un ajuste y otro.

   * **Mostrar el contenido predeterminado para todas las demás actividades:** Si esta opción está activada, se muestra el contenido predeterminado para todas las demás actividades. Por ejemplo, la vista previa se muestra de forma aislada sin tener en cuenta las demás actividades activas en la misma página/[!DNL Target] solicitud.

      Si el ajuste está desactivado, tenga en cuenta lo siguiente:

      * En caso de conflicto entre la actividad que está probando y otras actividades en curso, se aplicarán  [reglas de prioridad normales](/help/main/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F). Debido a los conflictos, es posible que no pueda ver la actividad que desea realizar un control de calidad.
      * Las métricas aumentan para las actividades vistas, pero solo en el entorno de realización de informes de control de calidad.

1. Haga clic en **[!UICONTROL Hecho]** para guardar los cambios.
1. Comparta las URL de vínculos de actividad con miembros de su organización para realizar pruebas.

   Los vínculos de actividad nunca caducan y no es necesario volver a enviarlos si alguien cambia una actividad o experiencia. Sin embargo, si aplica una audiencia diferente a la del [!UICONTROL Biblioteca de audiencias], en lugar de simplemente editar la actividad, se genera un nuevo vínculo que debe volver a compartir.

   Cada URL de vínculo de actividad (para la experiencia A, la experiencia B, etc.) le permite iniciar el recorrido del usuario desde la experiencia correspondiente. Haga clic en la URL generada para una experiencia y, a continuación, continúe con la exploración normal del sitio para ver las experiencias en varias páginas (si existen varias páginas). Se genera una única URL por experiencia, aunque esta abarque múltiples páginas (prueba de plantilla o prueba multipágina).

   Puede navegar por el sitio para ver las otras páginas porque la variable [!UICONTROL Control de calidad de la actividad] es fijo. Esta situación se da en las implementaciones de at.js con la versión 2.*x* o posterior. Para at.js 1.*x* , esta situación solo ocurre si el explorador del visitante no bloquea las cookies de terceros.

1. Para ver los informes generados a partir de las URL de vínculos de actividad, haga clic en el **[!UICONTROL Informes]** , haga clic en el botón **[!UICONTROL Configuración]** icono (  ![icon_engrane image](assets/icon_gear.png) ) y, a continuación, seleccione **[!UICONTROL Tráfico de modo de control de calidad]** de la variable **[!UICONTROL Entorno]** lista desplegable.

## Consideraciones {#section_B256EDD7BFEC4A6DA72A8A6ABD196D78}

* La variable [!UICONTROL Control de calidad de la actividad] el vínculo aparece en la [!UICONTROL Información general] página de todos los tipos de actividades excepto [!UICONTROL Segmentación automática] y [!UICONTROL Automated Personalization] (AP).
* [!UICONTROL Es posible que los vínculos de Vista previa de control de calidad de la actividad para las actividades guardadas no se carguen si hay demasiadas guardadas en su cuenta. ] Volver a intentar los vínculos de vista previa debería funcionar. Para evitar que esta situación siga ocurriendo, archive las actividades guardadas que ya no se utilizan activamente.
* [!UICONTROL Las URL de control de calidad de la actividad están disponibles con actividades que tienen Analytics como fuente de informes (A4T). ] Visitas generadas al realizar el control de calidad mediante [!UICONTROL Control de calidad de la actividad] flujo al mismo grupo de informes en el que fluyen los datos de la actividad incluso después de que la actividad se haya activado.
* [!UICONTROL El control de calidad de la actividad no muestra contenido para actividades archivadas o ya caducadas. ] Si desactiva una actividad finalizada, debe guardar de nuevo la actividad para [!UICONTROL Control de calidad de la actividad] para trabajar.
* Actividades importadas en [!DNL Target Standard/Premium] (de [!DNL Target Classic], por ejemplo) no admiten direcciones URL de control de calidad.
* En [!UICONTROL Asignación automática] y [!UICONTROL Recommendations] , el modelo no se ve afectado por las visitas capturadas en [!UICONTROL Control de calidad de la actividad].
* [!UICONTROL Control de calidad de la actividad] es pegajoso. Después de examinar un sitio web en [!UICONTROL Control de calidad de la actividad], su [!DNL Target] la sesión debe caducar o debe [!DNL Target] liberarlo de [!UICONTROL Control de calidad de la actividad] antes de poder ver el sitio como lo vería un visitante. Use el [bookmarklet de control de calidad de Target](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879)[!UICONTROL  para forzar su salida de dicho control de calidad de la actividad].

   También puede forzar la salida manual cargando una página en su sitio con un valor en blanco en el parámetro `at_preview_token` (por ejemplo, `https://www.mysite.com/?at_preview_token=`).

* Si especificó &quot;URL es&quot; al crear la actividad [refinamientos en el Compositor basado en formularios](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) o [opciones de envío de página en el Compositor de experiencias visuales)](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81), la URL de control de calidad no funciona porque [!UICONTROL Control de calidad de la actividad] adjunta parámetros de URL. Para solucionar este problema, haga clic en la URL de control de calidad para ir a su sitio, elimine los parámetros añadidos a la URL y cargue la nueva dirección.
* Si tiene at.js 1.*x*, [!UICONTROL Control de calidad de la actividad] no es persistente si utiliza Safari u otro explorador que bloquee cookies de terceros. En estos casos, debe añadir los parámetros de vista previa a cada URL a la que navegue. Lo mismo ocurre si ha implementado [CNAME](https://developer.adobe.com/target/before-implement/implement-cname-support-in-target/){target=_blank}.
* Si una actividad utiliza varias audiencias de experiencia (por ejemplo, un sitio de EE. UU. y Reino Unido que están incluidos en la misma actividad), no se generan vínculos de control de calidad para las cuatro combinaciones (Experiencia A/EE. UU., Experiencia A/Sitio RU, Experiencia B/Sitio EE. UU., Experiencia B/Sitio RU). Se crean solo dos vínculos de QA (Experiencia A y Experiencia B) y los usuarios deben cumplir las condiciones de audiencia apropiadas para ver la página. Una persona de control de calidad del Reino Unido no puede ver el sitio de EE. UU.
* Todos los parámetros y valores de `at_preview` ya están codificados en la URL. La mayoría de las veces, todo funciona según lo esperado. Sin embargo, algunos clientes deben cargar equilibradores o servidores web que intenten codificar de nuevo los parámetros de cadena de consulta.

   Debido a esta doble codificación, cuando [!DNL Target] intenta decodificar la variable `at_preview_token`, [!DNL Target] no se puede extraer el valor del token correcto, lo que hace que la vista previa no funcione.

   Adobe recomienda hablar con el equipo de TI para asegurarse de que todos los parámetros de vista previa estén incluidos en la lista de permitidos, de modo que estos valores no se transformen de modo alguno.

   La siguiente tabla enumera los parámetros que pueden estar incluidos en la lista de permitidos en su dominio:

   | Parámetro | Tipo | Valor | Descripción |
   |--- |--- |--- |--- |
   | `at_preview_token` | Cadena cifrada | Obligatorio; no hay valor predeterminado | Una entidad cifrada que contiene la lista de ID de campañas que se pueden ejecutar en modo de control de calidad. |
   | `at_preview_index` | Cadena | Vacío | El formato del parámetro es `<campaignIndex>` o `<campaignIndex>_< experienceIndex>`<br>ambos índices comienzan con 1. |
   | `at_preview_listed_activities_only` | Booleano (true/false) | Valor predeterminado: false | Si es “true”, se procesan todas las campañas especificadas en los parámetros `at_preview_index`.<br>Si es “false”, se procesan todas las campañas de la página, aunque no se especificaran en el token de vista previa. |
   | `at_preview_evaluate_as_true_audience_ids` | Cadena | Vacío | Lista de segmentId separada por guiones bajos (&quot;_&quot;) que siempre (en el nivel de segmentación e informes) deben evaluarse como &quot;true&quot; en el ámbito del [!DNL Target] solicitud. |
   | `_AT_Debug` | Cadena | Ventana o consola | Registro de consola o nueva ventana. |
   | `adobe_mc_ref` |  |  | Pasa la URL de referencia de la página predeterminada a la nueva página. Cuando se utiliza con `AppMeasurement.js` versión 2.1 (o posterior), [!DNL Adobe Analytics] usa este valor de parámetro como URL de referencia en la nueva página. |
   | `adobe_mc_sdid` |  |  | Pasa el [!DNL Supplemental Data Id] (SDID) y [!DNL Experience Cloud Org Id] de la página predeterminada a la nueva página. Pasar estos ID permite [!UICONTROL Analytics para Target] (A4T) para &quot;unir&quot; el [!DNL Target] en la página predeterminada con la variable [!DNL Analytics] en la nueva página. |

* La variable [!UICONTROL Modo de control de calidad de Target] La interfaz de usuario solo muestra la primera URL de una experiencia en una actividad de varias páginas. Se supone que está creando una prueba de recorrido y se mueve de la URL1 a la URL2. Sin embargo, si desea ir a la URL 2 de forma independiente, copie todos los parámetros de la URL proporcionados con la URL 1 y aplíquelos a la URL 2 después de colocar “?” como se ve en la URL 1.
* Es posible que los vínculos de Vista previa de control de calidad de la actividad para las actividades guardadas no se carguen si hay demasiadas guardadas en su cuenta. Reinténtelo con los vínculos de previsualización. Archive las actividades guardadas que ya no se utilizan activamente para evitar que este problema siga ocurriendo.

## Compatibilidad con la biblioteca JavaScript [!UICONTROL Modo QA] de Target {#compatibility}

[!DNL Target] admite las siguientes bibliotecas JavaScript:

* [at.js 1.x](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/how-atjs-works/)
* [at.js 2.x](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/how-atjs-works/)
* [SDK web de Adobe Experience Platform](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/)

La tabla siguiente muestra los distintos tipos de actividades e indica si [!UICONTROL Control de calidad de la actividad] se admite para cada biblioteca:

| Tipo de actividad | at.js 1.x | at.js 2.x | SDK web de plataforma |
| --- | --- | --- | --- |
| [!UICONTROL Prueba A/B] | Sí | Sí | Sí |
| [!UICONTROL Asignación automática] | Sí | Sí | Sí |
| [!UICONTROL Segmentación automática] | No | No | No |
| [!UICONTROL Automated Personalization] (AP) | No | No | No |
| [!UICONTROL Segmentación de experiencias] (XT) | Sí | Sí | Sí |
| [!UICONTROL Prueba multivariable] (MVT) | Sí | Sí | Sí |
| [!UICONTROL Recommendations] | Sí | Sí | Sí |

## Vista previa de direcciones URL {#preview}

Las direcciones URL de vista previa de la experiencia se pueden generar para todos [!DNL Target] tipos de actividades. Las direcciones URL de vista previa permiten ver el contenido de la experiencia directamente en el sitio antes de que la actividad esté activa para su vista previa y control de calidad. Las direcciones URL de vista previa de experiencias evitan la segmentación para forzar la visualización de una experiencia en particular.

Para obtener información sobre cómo funcionan las direcciones URL de vista previa con [!UICONTROL Automated Personalization] actividades (AP), consulte [Vista previa de actividades de Automated Personalization con direcciones URL de vista previa de experiencias](/help/main/c-activities/t-automated-personalization/experience-preview.md).

Para acceder y compartir una dirección URL de vista previa, desde la **[!UICONTROL Información general]** , haga clic en el botón **[!UICONTROL Control de calidad de la actividad]** vínculo.

>[!NOTE]
>
>La variable [!UICONTROL Control de calidad de la actividad] y la dirección URL de vista previa son iguales para todas las actividades que no sean [!DNL Target] Actividades AP.

La tabla siguiente muestra los distintos tipos de actividades e indica si la función de vista previa de direcciones URL es compatible con cada biblioteca o API:

| Tipo de actividad | at.js 1.x | at.js 2.x | SDK web de plataforma |
| --- | --- | --- | --- |
| [!UICONTROL Prueba A/B] | Sí | Sí | Sí |
| [!UICONTROL Asignación automática] | Sí | Sí | Sí |
| [!UICONTROL Segmentación automática] | Sí | Sí | Sí |
| [!UICONTROL Automated Personalization] (AP) | Sí | Sí | Sí |
| [!UICONTROL Segmentación de experiencias] (XT) | Sí | Sí | Sí |
| [!UICONTROL Prueba multivariable] (MVT) | Sí | Sí | Sí |
| [!UICONTROL Recommendations] | Sí | Sí | Sí |

