---
keywords: personalización automatizada;ap
description: Obtenga información sobre cómo crear una actividad [!UICONTROL Automated Personalization] (AP) usando [!UICONTROL Visual Experience Composer].
title: ¿Cómo creo una actividad de [!UICONTROL Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Automated Personalization
exl-id: eadc2bbc-310b-479f-b75b-253e8d7aa812
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '1844'
ht-degree: 24%

---

# Crear una actividad [!UICONTROL Automated Personalization]

Crear una actividad [!UICONTROL Automated Personalization] (AP) en [!DNL Adobe Target] mediante el [!UICONTROL Visual Experience Composer] (VEC).

El flujo de trabajo de la actividad [!UICONTROL Automated Personalization] (AP) en [!DNL Target] varía con respecto al flujo de trabajo de los otros tipos de actividad.

1. En la lista [!DNL Target] [!UICONTROL Activities], haga clic en **[!UICONTROL Create Activity]** > **[!UICONTROL Automated Personalization]**.

1. Para usar el [!UICONTROL Visual Experience Composer] (VEC), haga clic en **[!UICONTROL Visual]**.

   Para usar [!UICONTROL Form-Based Experience Composer], seleccione [!UICONTROL Form]. Consulte [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md) para obtener más información.

   >[!NOTE]
   >
   >Además del VEC y [!UICONTROL Form-Based Experience Composer], [!DNL Target] ofrece [!UICONTROL Single Page Application VEC]. Para obtener más información sobre los distintos compositores, consulte [Experiencias y ofertas](/help/main/c-experiences/experiences.md).
   >
   >Para obtener información de solución de problemas acerca del VEC, consulte [Solución de problemas del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Condicional) [Elija un área de trabajo](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. En el cuadro **[!UICONTROL Enter Activity URL]**, especifique la [URL de actividad](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md).

   Si la cuenta se [configura con una dirección URL predeterminada](/help/main/administrating-target/visual-experience-composer-set-up.md) esa dirección URL aparece de manera predeterminada. Puede cambiar la dirección URL predeterminada por otra dirección si es necesario.

   [!DNL Target] no diferencia entre los protocolos de URL ([!DNL https] y [!DNL http]). Como resultado, [!DNL `http://www.adobe.com`] y [!DNL `https://wwww.adobe.com`] coinciden.

1. Haga clic en **[!UICONTROL Create]**.

   Se abre la página con la dirección URL especificada en el VEC.

1. Haga clic en el icono **[!UICONTROL Rename]** ( ![Cambiar nombre del icono](/help/main/assets/icons/MoreSmallListVert.svg) ), haga clic en **[!UICONTROL Rename]**, especifique un nombre para la actividad y, a continuación, haga clic en **[!UICONTROL Save]**.

   El nombre de la actividad no puede comenzar con ninguno de los siguientes caracteres:

   | Carácter | Descripción |
   |--- |--- |
   | `=` | Igual a |
   | `+` | Más |
   | `-` | Menos |
   | `@` | Arroba |

   El nombre de la actividad no puede contener ninguna de estas secuencias de caracteres:

   | Secuencia de caracteres | Descripción |
   |--- |--- |
   | ;= | Punto y coma, igual a |
   | ;+ | Punto y coma, más |
   | ;- | Punto y coma, menos |
   | ;@ | Punto y coma, signo de arroba |
   | ,= | Coma, igual a |
   | ,+ | Coma, más |
   | ,- | Coma, menos |
   | ,@ | Coma, Signo de arroba |
   | `[`&quot; | Corchete de apertura, comillas dobles |
   | &quot;`]` | Comillas tipográficas dobles, cerrar corchete |

1. Modifique los elementos de página tal como se explica en [las opciones del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   Puede seleccionar varias imágenes a la vez desde el administrador de recursos. Esto permite ver rápidamente la página con cada una de las imágenes configuradas para la actividad. También puede editar fácilmente los elementos de texto en sus ofertas. Cuando edite un elemento, aparecen barras en ese elemento para indicar que lo ha cambiado.

1. Haga clic en el icono **[!UICONTROL Manage Content]** ( ![icono Administrar contenido](/help/main/assets/icons/Experience.svg) ) para configurar las combinaciones disponibles.

   Aparece un cuadro de diálogo con dos opciones en la parte superior de la pantalla: [!UICONTROL Experiences] y [!UICONTROL Offers].

   >[!NOTE]
   >
   >Aunque se pueden crear hasta 30 000 experiencias en una actividad AP, el rendimiento de la actividad es mejor cuando se utilizan menos de 5000. Este mismo límite se aplica incluso cuando la actividad tiene habilitada la opción [!UICONTROL Disalow Duplicates].

   La lista [!UICONTROL Experiences] muestra cada fragmento de contenido seleccionado para la actividad y la ubicación a la que está asignado.

   Para excluir experiencias específicas, seleccione la casilla de verificación que hay junto a la experiencia que desee y haga clic en el icono [!UICONTROL Exclude].

   Puede excluir o incluir experiencias por lotes seleccionando la casilla de las experiencias relevantes y luego haciendo clic en el icono [!UICONTROL Exclude].

1. (Condicional) Haga clic en **[!UICONTROL Offers]** para seleccionar elementos de contenido y asignarlos a grupos de informes o para permitir que solo determinados visitantes vean determinadas ofertas con segmentación.

   Para obtener más información sobre los grupos de informes, consulte [Grupos de informes de ofertas en Automated Personalization](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md).

<!--
1. (Conditional) Click **[!UICONTROL Exclusion Groups]** to choose any combination of elements that you want to exclude from the activity.

   ![Exclusion Groups tab of Manage Content dialog box](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   Although you can create up to 30,000 experiences in an AP test, the algorithm performs its best when fewer than 10,000 distinct experiences are used. This same limit is applied even when the activity has enabled the [!UICONTROL Disalow Duplicates] option.

   If you do not currently have any exclusion groups included in your activity, click **Create Exclusion Group**. You can filter to create a list that shows only the combinations you want to exclude. Name your exclusion group, then click **Save**.

   To edit an existing exclusion group, hover over the group you want to edit, then click the pencil icon.-->

1. Haga clic en **[!UICONTROL Done]** cuando haya terminado de configurar el contenido de su actividad.

1. Haga clic en **[!UICONTROL Targeting]**, en la parte superior de [!UICONTROL Visual Experience Composer], para ir al paso siguiente en el flujo de trabajo guiado de tres pasos.

   El paso **Segmentación** le resultará familiar si ha utilizado otros tipos de actividad de [!DNL Target]. Aquí puede seleccionar una audiencia y especificar el porcentaje de visitantes que ven cada experiencia.

   Se abrirá el diagrama de flujo.

   ![Paso de segmentación de pruebas AP](/help/main/c-activities/t-automated-personalization/assets/ap-traffic-flow.png)

   El diagrama de flujo le guía durante el procedimiento para asignar una audiencia y su porcentaje de tráfico, seleccionar el método de asignación de tráfico y especificar la asignación de tráfico para cada experiencia en la actividad.

1. (Condicional) Haga clic en el control **[!UICONTROL All Visitors]** para seleccionar otra audiencia para la actividad.

   La audiencia [!UICONTROL All Visitors] está establecida como predeterminada. Si selecciona otra audiencia, su nombre se muestra en el control situado más a la izquierda.

   Se muestra el marco derecho, que le permite añadir o eliminar una audiencia y asignar el porcentaje de visitante para la actividad.

   1. Para cambiar la audiencia, haga clic en el icono **[!UICONTROL Replace]** ( ![Reemplazar icono](/help/main/assets/icons/Retweet.svg) ) en el marco derecho.
   1. En el cuadro de diálogo [!UICONTROL Add Audience], [seleccione la audiencia que desee](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) y luego haga clic en **[!UICONTROL Assign Audience]**.

      Puede hacer clic en **Combinar audiencias** para [crear una audiencia que combine varias audiencias](/help/main/c-target/combining-multiple-audiences.md).

      Si necesita crear una audiencia nueva que no esté ya en [!UICONTROL Audience Library], haga clic en **Crear audiencia**. Durante el [flujo de trabajo create-audience](/help/main/c-target/c-audiences/audiences.md), puede elegir entre las siguientes opciones:

      * **[!UICONTROL Audience Library]**: cree una audiencia bajo demanda que se guarde en [!UICONTROL Audience Library] y que pueda reutilizarse en otras actividades.
      * **[!UICONTROL This activity only]**: cree una [audiencia específica de actividad](/help/main/c-target/creating-activity-only-audience.md) que no se haya guardado en [!UICONTROL Audience Library] y que solo se pueda usar en la actividad actual.

   1. Haga clic en **[!UICONTROL Visitor Percentage]** en el cuadro derecho y, a continuación, elija el porcentaje de visitantes correspondiente que desea que participen de la actividad.

   Por ejemplo, podría limitar las entradas al 50 % de todos los visitantes o al 45 % de la audiencia de California.

1. Haga clic en el control **[!UICONTROL Traffic Allocation]** para elegir entre las siguientes opciones:

   ![Opciones del objetivo de asignación de tráfico](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap-new.png)

   * **[!UICONTROL Evaluate Personalization Algorithm (50/50)]:** Si su objetivo es probar el algoritmo, utilice una división del 50/50 por ciento de los visitantes entre el control y el algoritmo de destino. Esta división proporciona la estimación más precisa del alza. Se sugiere usar con &quot;experiencias aleatorias&quot; como control.
   * **[!UICONTROL Maximizing Personalization Traffic (90/10)]:** Si su objetivo es crear una actividad &quot;siempre activada&quot;, ponga el 10% de los visitantes en el control. Esta opción garantiza que haya suficientes datos para que los algoritmos continúen aprendiendo a lo largo del tiempo. La compensación aquí es que, a cambio de personalizar una mayor proporción de su tráfico, tiene menos precisión en la estimación del alza. Independientemente del objetivo, esta opción es la división de tráfico recomendada al utilizar una experiencia específica como control.
   * **[!UICONTROL Custom Allocation]:** Divida manualmente el porcentaje como lo desee.

1. (Condicional) En la lista desplegable [!UICONTROL Control], [seleccione una experiencia específica para utilizarla como control](/help/main/c-activities/t-automated-personalization/experience-as-control.md) o seleccione [!UICONTROL Random Experience.]

   La experiencia de control ofrece una comparación para determinar cuánta alza se proporciona con la prueba automatizada.

   [!UICONTROL Automated Personalization] siempre mide el rendimiento con respecto a un grupo de control. Lo mejor es colocar al menos el 10 % de los participantes en el grupo de control. Si su objetivo es probar si el algoritmo de personalización de los datos que se le proporcionan tiene un mejor rendimiento que el de ninguna personalización (por ejemplo, el control servido aleatoriamente), una división del tráfico del 50/50 por ciento entre el control y el algoritmo de personalización es la forma más rápida y precisa de lograr este objetivo. Si desea maximizar la cantidad de tráfico personalizado y no le interesa comprender el alza exacta que está generando su actividad, una división del tráfico del 10/90 por ciento entre el control y el algoritmo de personalización es la manera más rápida y precisa de lograr este objetivo.

   >[!NOTE]
   >
   >En [!UICONTROL Automated Personalization] actividades, los criterios de entrada (segmentación por URL, reglas de plantilla y objetivos de audiencia) se evalúan en cada solicitud. En las versiones anteriores, los criterios de entrada se evaluaban una vez por sesión.

1. Haga clic en **[!UICONTROL Next]** para mostrar la página **[!UICONTROL Goals & Settings]**.
1. Configure la actividad con las siguientes opciones y luego haga clic en **[!UICONTROL Save & Close]**.

   | Configuración | Descripción |
   |--- |--- |
   | [!UICONTROL Name] | Asigne un nombre a la actividad. Asigne a la actividad un nombre que sea lo suficientemente descriptivo como para que los integrantes del equipo puedan reconocerlo en la lista [!UICONTROL Activities]. Consulte la tabla anterior para ver los caracteres que no están permitidos en el nombre de la actividad. |
   | [!UICONTROL Objective] | (Opcional) Escriba el objetivo de la prueba. El objetivo le ayuda a recordar la finalidad de la actividad. |
   | [!UICONTROL Priority] | Según la configuración, la interfaz de usuario de [!DNL Target] y las opciones de [!UICONTROL Priority] varían. Puede usar la configuración heredada de [!UICONTROL Low], [!UICONTROL Medium] o [!UICONTROL High], o bien habilitar prioridades específicas de 0 a 999.<P>La prioridad se utiliza si se asignan varias actividades a la misma ubicación con la misma audiencia. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta.<P>Si esta opción no está habilitada en [!UICONTROL Administration] > [!UICONTROL Reporting] (la predeterminada), especifique una prioridad: [!UICONTROL Low], [!UICONTROL Medium] o [!UICONTROL High].<P>Para habilitar prioridades específicas, haga clic en [!UICONTROL Administration] > [!UICONTROL Reporting] y luego coloque la opción [!UICONTROL Enable Fine-Grained Priorities] en la posición &quot;Activado&quot;.<P>Si esta opción está habilitada, especifique un valor de 0 a 999:<ul><li>0 = Bajo</li><li>999 = Alto</li></ul>Para las actividades creadas en versiones anteriores de [!DNL Target Standard/Premium], la prioridad [!UICONTROL Low] se convierte en 0, la prioridad [!UICONTROL Medium] se convierte en 5 y la prioridad [!UICONTROL High] se convierte en 10. Si lo necesita, puede ajustar estos valores.<P>**Nota**: para deshabilitar esta opción después de usar las prioridades específicas, hay que volver a fijar todas las prioridades en 0, 5 y 10. |
   | [!UICONTROL Duration] | Establezca las fechas de inicio y finalización de la actividad. Puede seleccionar [!UICONTROL When Activated] o especificar una fecha y hora específicas. |
   | [!UICONTROL Optimization Goal] | Especifique el objetivo de optimización, que consta de dos parámetros:<ul><li>Qué quiere medir con la actividad</li><li>La acción realizada por el participante de una actividad que muestra que se ha logrado el objetivo.</li></ul>Puede elegir asignar un nombre al objetivo de optimización seleccionando los tres puntos a la derecha de [!UICONTROL My Primary Goal]. [!UICONTROL Automated Personalization] actividades pueden medir [!UICONTROL Conversion] o [!UICONTROL Revenue]. La conversión se puede realizar viendo una página o un mbox. También se realiza un seguimiento de los clics.<P>El objetivo principal también se convierte en la métrica de modelado que utiliza el sistema de modelado para calcular el éxito de la experiencia.<P>Los visitantes pueden continuar en la actividad con fines de seguimiento después de alcanzar el objetivo de modelado. Por ejemplo, a menudo se usa una actividad [!UICONTROL Automated Personalization] para mejorar las tasas de clics, y eso se establece como el objetivo de modelado. Sin embargo, es importante ver cómo las tasas de clics incrementadas llevan a conversión final, por lo que resulta esencial el seguimiento a través de la conversión final.<P>Dispone de dependencia respecto a varias métricas y tiene la posibilidad de elegir si una métrica debe alcanzarse o no para que su contador aumente.<P>Debe definir ambas (o varias) métricas de éxito antes de poder hacer una dependiente de la otra.<P>La opción [!UICONTROL Add Dependency] permite que la métrica de éxito aumente si se alcanza otra métrica de éxito (o todo lo contrario, si no se alcanza).<P>Para agregar una dependencia:<ol><li>Después de agregar métricas adicionales, haga clic en **[!UICONTROL Advanced Settings]** en el menú de tres puntos que se encuentra a la derecha de [!UICONTROL Additional Goal].</li><li>Haga clic en la opción **[!UICONTROL Add Dependency]** en la parte inferior de la sección [!UICONTROL Reporting Settings].</li><li>Arrastre y suelte las métricas deseadas del panel izquierdo al panel derecho y, a continuación, haga clic en [!UICONTROL Reached] para alternar el valor entre [!UICONTROL Reached] y [!UICONTROL Not Reached].</li></ol>Puede editar o eliminar dependencias después de añadirlas. |
   | [!UICONTROL Conversion Metric] | De forma predeterminada, la métrica de conversión es la misma que la métrica de objetivo de optimización. Sin embargo, puede definir una métrica de conversión independiente desmarcando la opción [!UICONTROL Same as Optimization Goal]. |
   | [!UICONTROL Additional Metrics] | Añada las métricas adicionales de creación de informes que desee utilizar. Puede agregar métricas de conversión, participación o ingresos.<P>**Nota**: La métrica [!UICONTROL Engagement] no se admite como métrica adicional. Es posible que la interfaz de usuario [!DNL Target] le permita seleccionar la métrica [!UICONTROL Engagement], pero los datos no se muestran con precisión en los informes. |
   | [!UICONTROL Audiences for Reporting] | Añada audiencias para habilitar el filtrado por audiencias en los informes. De manera predeterminada, el informe muestra los resultados para todos los visitantes que cumplen los criterios. Añada audiencias para filtrar los resultados para subconjuntos de visitantes más específicos.<P>**Nota**: a diferencia de otros tipos de actividades, [!UICONTROL Automated Personalization] no puede usar [!UICONTROL Adobe Analytics] como fuente de informes (A4T). |
   | [!UICONTROL Notes] | Escriba cualquier información sobre la actividad que sea útil para usted o para otros integrantes del equipo. Se puede cambiar el tamaño del panel [!UICONTROL Notes]. |

   Al asignar un nombre a una métrica o cambiarla por otro, no se permiten los siguientes caracteres:

   | Carácter | Descripción |
   |--- |--- |
   | / | Barra oblicua |
   | ? | Signo de interrogación |
   | # | Signo de número |
   | : | Dos puntos |
   | = | Igual a |
   | + | Más |
   | - | Menos |
   | @ | Arroba |

Después de hacer clic en **[!UICONTROL Save & Close]**, se muestra la página [!UICONTROL Overview] de la actividad. Haga clic en **Previsualizar experiencias** para obtener una vista previa del aspecto que tendrán las experiencias cuando se entreguen. Aparece una ventana emergente que puede usar para ver y compartir vínculos a sus experiencias AP en su sitio para obtener una &quot;auténtica vista previa&quot; de las experiencias fuera de [!UICONTROL Target] [!UICONTROL Visual Experience Composer] (VEC). Debe compartir los vínculos del mensaje para compartir la vista previa. No funciona hacer clic en un vínculo y copiar la dirección URL directamente desde el explorador. Si se copia el vínculo, la dirección URL contiene un parámetro que muestra la página correctamente solo cuando se accede a la página desde el vínculo del mensaje.

Para obtener información sobre los informes, consulte [Informes de Personalización automatizada](/help/main/c-reports/personalization-reports/reports-ap.md).
