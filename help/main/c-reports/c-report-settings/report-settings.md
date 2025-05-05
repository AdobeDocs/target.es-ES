---
keywords: Target;informes;configuración de informes;ajuste preestablecido;ajuste preestablecido de Target;métrica;audiencia;intervalo de fechas;configuración;descarga;vista de tabla;vista de gráfico;alza promedio;alza;límite de alza;intervalo de confianza;confianza;contribución de ubicación;promedio actual;metodología de recuento
description: Obtenga información sobre cómo definir la configuración de informes en Adobe Target, incluidas las métricas, las audiencias, los intervalos de fechas y mucho más.
title: ¿Cómo configuro la configuración de los informes?
feature: Reports
exl-id: 337579d1-c678-43b6-9e80-b5abe159c2d3
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '1778'
ht-degree: 48%

---

# Configuración de informes

Información para configurar los elementos que desea que aparezcan en el informe en [!DNL Adobe Target]. Las opciones de configuración de los informes se pueden guardar para usarlas posteriormente.

Para mostrar un informe:

1. Haga clic en **[!UICONTROL Activities]** y luego en una actividad de la lista.
1. Haga clic en la ficha **[!UICONTROL Reports]**.

   ![Interfaz de usuario del informe](/help/main/c-reports/c-report-settings/assets/report-ui-refresh.png)

## Ajuste preestablecido de Target {#section_51F67341465045BEB4F1A2FB638A8EB1}

Puede guardar hasta diez ajustes preestablecidos de un informe de actividad después de configurarlo a su gusto (métricas, intervalos de fechas, audiencias, configuración avanzada, etcétera). Todos los usuarios de [!DNL Target] pueden mostrar, editar y eliminar los distintos ajustes preestablecidos, independientemente de quién los haya creado.

También puede configurar un informe de actividad a su gusto y después guardar dicha configuración como su ajuste preestablecido predeterminado/favorito. Esta es la vista que se muestra cuando ve avanzar el informe de la actividad.

### Crear un ajuste preestablecido o un ajuste preestablecido predeterminado

1. Configure el informe de actividad como desee.

   A continuación se explica la configuración disponible, incluidas las métricas, los intervalos de fechas, las audiencias, la configuración avanzada, etc.

1. Junto a **[!UICONTROL Target Preset]**, haga clic en el icono **[!UICONTROL More Options]** ( ![icono de Más opciones](/help/main/assets/icons/MoreSmallListVert.svg) ) > **[!UICONTROL Save as New]**.

   Se muestra el cuadro de diálogo [!UICONTROL Create Preset].

   ![Cuadro de diálogo Nuevos ajustes preestablecidos](/help/main/c-reports/c-report-settings/assets/report_preset_dialog-new.png)

1. Revise la información de las secciones **[!UICONTROL Filters]** para asegurarse de que el informe está configurado como desea y, a continuación, especifique **[!UICONTROL Preset Name]** (hasta 50 caracteres).
1. (Condicional) Si desea que esta sea su vista de informe predeterminada/favorito, coloque el conmutador **[!UICONTROL Set as default preset]** en la posición Activado.
1. Haga clic en **[!UICONTROL Create]**.

### Seleccionar un ajuste preestablecido diferente

Seleccione el ajuste preestablecido que desee en la lista desplegable **[!UICONTROL Target Preset]**.

### Editar un ajuste preestablecido

1. Seleccione el ajuste preestablecido que desee editar.
1. Edite la configuración del informe a su gusto (métricas, intervalos de fechas, audiencias, configuración avanzada, etc.).

   Después de hacer clic en [!UICONTROL Save] después de editar la configuración del informe, aparece un asterisco ( &#42;) después del nombre del ajuste preestablecido para indicar que ha cambiado.

1. Haga clic en el icono **[!UICONTROL More Options]** ( ![icono de Más opciones](/help/main/assets/icons/MoreSmallListVert.svg) ) > **[!UICONTROL Save as New]** para crear un ajuste preestablecido nuevo.

### Eliminar un ajuste preestablecido

1. Seleccione el ajuste preestablecido que desee eliminar.
1. Haga clic en el icono **[!UICONTROL More Options]** (![icono de Más opciones](/help/main/assets/icons/MoreSmallListVert.svg) ) > **[!UICONTROL Delete]**.

1. Vuelva a hacer clic **[!UICONTROL Delete]** para confirmar la eliminación (los ajustes preestablecidos eliminados no se pueden recuperar).

### Gestión de errores preestablecidos

Si un ajuste preestablecido deja de ser válido, se indica mediante avisos y mensajes dentro de los informes. El aviso o mensaje le indica que elija otra audiencia, métrica, grupo de hosts o experiencia para crear un ajuste preestablecido válido.

La lista siguiente describe algunas de las situaciones que pueden provocar que un ajuste preestablecido deje de ser válido:

* Se elimina una audiencia de informes de la actividad, pero la definición del ajuste preestablecido sigue haciendo referencia a ella.
* Se eliminan una o más métricas, pero la definición del ajuste preestablecido sigue haciendo referencia a ellas. Por ejemplo, podría eliminar una o más métricas de la actividad y, después, agregar nuevas métricas.
* Uno o más grupos de hosts (entorno) no existen, pero la definición del ajuste preestablecido hace referencia a ellos.
* Se eliminan una o más experiencias tras la creación del ajuste preestablecido, pero la definición del ajuste sigue haciendo referencia a ellas.
* Un ajuste preestablecido no es semánticamente válido porque algunas entidades referidas siguen existiendo, pero se han actualizado de un modo que la definición del ajuste preestablecido ha cambiado semánticamente. Por ejemplo, suponga que creó un ajuste preestablecido denominado “Ingresos en Chrome”. Posteriormente actualizó la actividad para medir la métrica Conversión en vez de Ingresos. Esta actualización de la definición de actividad invalida semánticamente la definición del ajuste preestablecido.

## [!UICONTROL Report Metric] {#section_894ABD7148244806B7CE556EBBA2AD62}

Haga clic en la lista desplegable **[!UICONTROL Report Metric]** para seleccionar una [métrica de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) diferente o varias métricas que se mostrarán en el gráfico.

De manera predeterminada, la métrica principal se determina al configurar las métricas de éxito al crear la actividad. Si cambia la configuración y vuelve a guardar la actividad, se actualizará la métrica principal para informes.

Para obtener más información sobre cómo seleccionar varias métricas para verlas en los informes, consulte [Ver varias métricas en un informe](/help/main/c-reports/c-report-settings/view-multiple-metrics.md#concept_9E3C3F6F3EC1412FAF252975AC0720B7).

## [!UICONTROL Audience] {#section_70926EB4618945D9AFF2B0564FF3717B}

Haga clic en la lista desplegable **[!UICONTROL Audience]** para cambiar la audiencia mostrada en el informe.

Para obtener más información, consulte [Audiences](/help/main/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522).

## [!UICONTROL Preset Date Range]

Haga clic en la lista desplegable **[!UICONTROL Preset Date Range]** para elegir entre intervalos de fechas preestablecidos.

Seleccione nuevas fechas **[!UICONTROL Start]** y **[!UICONTROL End]** para el informe. También puede usar los rangos **[!UICONTROL Start of Activity]** y **[!UICONTROL Start of activity - End of Activity]**.

Los intervalos de fechas predefinidos incluyen: últimos 7 días, últimos 15 días o últimos 30 días. Estos intervalos de fechas predefinidos se pueden extender. Si la fecha de inicio es anterior al número de días seleccionado, el calendario muestra el intervalo desde la fecha de inicio, pero se desplaza una vez que la fecha de inicio es anterior al número de días seleccionados a medida que aumenta la duración de la actividad.

Los informes tienen las siguientes restricciones de fechas:

* La fecha de inicio del informe debe estar entre los dos últimos años.
* Los informes de grupos de ofertas están limitados a 99 días a partir del día actual.
* Los informes por horas tienen un límite de 15 días.

## Intervalo de fechas {#section_A410A768403C4E01891F95CB357E63ED}

El cuadro [!UICONTROL Date Range] muestra el intervalo de fechas actual del informe. Haga clic en el icono **[!UICONTROL Calendar]** ( ![icono de calendario](/help/main/assets/icons/Calendar.svg) ) para mostrar un calendario que le permita cambiar el intervalo de fechas del informe.

## Configuración {#section_D99CE462107D45CABE0960F820E1E972}

Para configurar los ajustes del informe:

1. Haga clic en el icono **[!UICONTROL Report Settings]** ( ![icono Configuración de informe](/help/main/assets/icons/Setting.svg) ) y realice los cambios que desee (como se explica más abajo).
1. Haga clic en **[!UICONTROL Save]** cuando termine.

Las opciones dependen del tipo de actividad que se seleccione:

### Metodología de contabilización

Seleccione la metodología que desee:

* Visitantes
* Visitas
* Impresiones de actividad

### Control

Seleccione la experiencia de control que se utilizará para calcular y comparar el alza.

### Entorno {#environment}

Seleccione el entorno (grupo de hosts) que se utilizará para el informe. Para obtener más información, consulte [Hosts](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).

>[!NOTE]
>
>Si su organización utiliza [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html){target=_blank} (AEP) para enviar datos de métricas a [!DNL Target], el entorno de la secuencia de datos de AEP debe coincidir con el entorno en la configuración del informe [!DNL Target].

### Restablecer datos del informe

Haga clic en [!UICONTROL Reset Report Data]. Restablezca los datos de informes para eliminar los datos antiguos. Los visitantes actuales permanecen en la actividad.  Esta opción solo está disponible para los que tengan permisos de [!UICONTROL Approver].

>[!IMPORTANT]
>
>Esta es una acción permanente y no se puede deshacer.

Excluir valores extremos

La opción [!UICONTROL Exclude Extreme Values] solo se aplica a las actividades con tipos de métrica de ingresos y participación. Para obtener más información, consulte [Exclusión de pedidos extremos](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA).

## Descargar   {#section_77E65C50BAAF4AB79242DB3A8778ADEF}

Haga clic en el icono **[!UICONTROL Download]** ( ![Icono de descarga](/help/main/assets/icons/Download.svg) ) para descargar datos de informe en formato [!DNL .csv] y poder importarlos rápidamente a Excel, Access o cualquier otro programa de análisis de datos.

Para obtener más información, consulte [Descarga de datos en un archivo CSV](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md).

## Actualizar {#section_E203729F2F314DF3856D2EE67C60B370}

Haga clic en el icono **[!UICONTROL Refresh]** ( ![Actualizar icono](/help/main/assets/icons/Refresh.svg) ) para actualizar la tabla y la vista de gráfico de un informe sin actualizar toda la página, su configuración o su intervalo de fechas.

## Más opciones {#section_AB1B5C695D7045A0A0AC0E2698D2E7DE}

Haga clic en el icono **[!UICONTROL More Options]** ( ![icono de Más opciones](/help/main/assets/icons/MoreSmallListVert.svg) ) para obtener acceso a las opciones [!UICONTROL Save as New] y [!UICONTROL Delete].

## Ver opciones

Puede ver el informe en varios formatos, según el tipo de actividad. Seleccione la opción que desee.

* **Vista de tabla**: haga clic en el icono **[!UICONTROL Table View]** ( ![icono de Vista de tabla](/help/main/assets/icons/Table.svg) ) para ver el informe como una tabla.
* **Visualización de gráfico**: haga clic en el icono **[!UICONTROL Graph View]** ( ![Icono de Visualización de gráfico](/help/main/assets/icons/GraphTrend.svg) ) para ver el informe como un gráfico.
* **Segmentos automatizados**:(Disponible solo para las actividades [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Auto-Target] (AT) ).) Haga clic en el icono **[!UICONTROL Automated Segments] (![icono de Segmentos automatizados](/help/main/assets/icons/AutomatedSegment.svg) ) para ver el [informe de Segmentos automatizados](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).
* **Atributos importantes**: (Disponible solamente para las actividades [!DNL Automated Personalization] (AP) y [!UICONTROL Auto-Target] (AT).) Haga clic en el icono **[!UICONTROL Important Attributes]** ( ![icono de Atributos importantes](/help/main/assets/icons/ViewList.svg) ) para ver el [informe de Atributos importantes](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).

## Alza promedio, límites de alza e intervalo de confianza {#section_0D87615B1D3344B3858BA494EEBC16FB}

Los informes incluyen varios puntos de datos y representaciones de visualización que comprenden los límites de la elevación y el nivel de confianza asociado a su actividad. Esto le ayuda a determinar un ganador con mayor precisión.

Para obtener más información, consulte [Cálculos estadísticos en Pruebas A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

Tenga en cuenta lo siguiente:

* Solo está disponible cuando se visualizan informes en [!UICONTROL Table View].
* Esta característica no está disponible para actividades que utilicen [Analytics como fuente de informes (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

## Contribución de ubicación.  {#section_5832F126AC114AE1ABFFF4D9B904393B}

Haga clic en el icono [[!UICONTROL Location Contribution]](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) ( ![icono de Contribución de ubicación](/help/main/assets/icons/LocationContribution.svg) ) para que el informe muestre la contribución por ubicación para las actividades de Prueba multivariable (MVT).

## Experiencias {#section_3A450DE1FA7E43F0AAB73165EC3D1C34}

Disponible solamente cuando se visualiza el informe en [!UICONTROL Graph View].

Seleccione o anule la selección de las experiencias en la parte izquierda de la tabla para mostrar u ocultar las experiencias correspondientes.

## Media móvil {#section_59066693158C4433B87D07402C2BC6CD}

Disponible solamente cuando se visualiza el informe en [!UICONTROL Graph View].

&quot;Promedio en curso&quot; refleja las conversiones acumuladas (desde el inicio de la ventana de creación de informes hasta la fecha representada en el gráfico) divididas por los visitantes acumulados.

Seleccione la visualización de gráfico que desee:

* Media móvil
* Alza media móvil
* Diario
* Alza diaria

El nombre de esta lista desplegable varía según la vista seleccionada, pero siempre será uno de los indicados arriba.

## Metodología de contabilización {#section_01B0ED5665C74AE1AE97259800190C3E}

Disponible solamente cuando se visualiza el informe en [!UICONTROL Graph View].

Puede elegir la metodología de contabilización para los gráficos de los informes. Tenga en cuenta que esto no es compatible con las actividades [!UICONTROL Automated Personalization] (AP).

Para acceder a la opción [!UICONTROL Counting Methodology], mientras ve un informe en modo de gráfico, haga clic en la lista desplegable **[!UICONTROL My Primary Goal]** y, a continuación, seleccione la metodología de contabilización.

La metodología de contabilización será la misma que se seleccionó en el cuadro de diálogo [!UICONTROL Settings], descrito anteriormente.

De manera predeterminada, el gráfico se traza en modo [!UICONTROL Daily].

Para cambiar el modo, haga clic en la lista desplegable [!UICONTROL Daily] y seleccione una opción acumulativa.

>[!NOTE]
>
>El nombre de esta lista desplegable varía según el modo seleccionado.

Hay cuatro modos para las actividades [!UICONTROL Auto-Target]: [!UICONTROL Daily Control], [!UICONTROL Daily Targeted], [!UICONTROL Cumulative Control] y [!UICONTROL Cumulative Targeted].

El orden predeterminado de representación del gráfico es el siguiente:

* **[!UICONTROL A/B Test] (incluidos [!UICONTROL Auto-Allocate] y [!UICONTROL Automated Personalization])**: orden descendente de creación de la experiencia.
* **[!UICONTROL Experience Targeting] (XT)**: orden de las experiencias en la actividad.
* **[!UICONTROL Multivariate Test] (MVT)**: Alfabético por nombre de experiencia.
* **[!UICONTROL Recommendations]**: orden descendente de creación de la experiencia.

Cuando trabaje con las opciones [!UICONTROL Counting Methodology], tenga en cuenta las siguientes advertencias:

* Para [[!UICONTROL Auto-Target] actividades](/help/main/c-activities/auto-target/auto-target-to-optimize.md), no hay opción para seleccionar &quot;Visitantes&quot; como metodología de conteo. [!UICONTROL Auto-Target] es el único tipo de actividad que los visitantes no pueden trazar.
* Para las actividades que usan [Analytics como fuente de informes (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md), no se puede trazar el visitante, la visita o la impresión de forma acumulativa.

## Trabajar con gráficos que tengan más de 16 experiencias en la actividad

Si una actividad tiene menos de 16 experiencias, cada una se representa en el gráfico con un color distinto.

Si una actividad tiene más de 16 experiencias, en el gráfico se muestran las líneas coloreadas para las 16 primeras. Las demás aparecen atenuadas en el panel Experiencias del lado izquierdo y sus líneas correspondientes no se representan en el gráfico. No pueden mostrarse más de 16 experiencias al mismo tiempo.

Si pasa el cursor sobre cualquiera de las experiencias en gris, en el gráfico se muestra temporalmente su correspondiente nueva línea de diagrama gris. Para representar en color la línea de diagrama de una experiencia en gris, puede anular la selección de una de las experiencias que se muestran en color haciendo clic en su nombre y, a continuación, haciendo clic en el nombre de la experiencia en gris deseada.

En el gráfico se representan las líneas de las 16 primeras experiencias (algunas se solapan, por lo que parece que hay menos de 16 líneas). El punto de color del panel Experiencias, situado la izquierda junto a cada nombre de experiencia, indica que la línea de diagrama de la experiencia se muestra en su color correspondiente.

Si se desplaza hacia abajo en el panel Experiencias, verá que los nombres de los puestos 17.º a 26.º aparecen atenuados, como se ven en esta ilustración:

Si pasa el cursor sobre una de las experiencias en gris, en el gráfico se muestra temporalmente su correspondiente nueva línea de diagrama gris.

Suponga que quiere mostrar la línea de diagrama de la Experiencia R pero no quiere ver la de la Experiencia P. Puede hacer clic en el nombre de la Experiencia P para anular su selección y, a continuación, hacer clic en el nombre de la Experiencia R para seleccionarla, como se muestra a continuación:
