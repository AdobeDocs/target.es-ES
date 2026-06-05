---
keywords: personalización automatizada;ap
description: Aprenda a crear una actividad [!UICONTROL Automated Personalization] (AP) con [!UICONTROL Compositor de experiencias visuales].
title: ¿Cómo creo una actividad [!UICONTROL Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Automated Personalization
exl-id: eadc2bbc-310b-479f-b75b-253e8d7aa812
TQID: https://experienceleague.adobe.com/5eUFwob4BekIJP4SM2lrSDQam4h1AXIByJjM7-1RNL8
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: c467f629596b37c334276d6f095f19b639a8518d
workflow-type: tm+mt
source-wordcount: 2032
ht-degree: 23%

---

# Crear una actividad [!UICONTROL Automated Personalization]

Cree una actividad [!UICONTROL Automated Personalization] (AP) en [!DNL Adobe Target] con el [!UICONTROL Compositor de experiencias visuales] (VEC).

El flujo de trabajo de la actividad [!UICONTROL Automated Personalization] (AP) en [!DNL Target] varía con respecto al flujo de trabajo de los otros tipos de actividad.

Este procedimiento sigue el flujo de trabajo guiado de tres pasos del [!UICONTROL Compositor de experiencias visuales]:

1. [Paso 1: Crear experiencias](#build-experiences)
1. [Paso 2: Establecer el objetivo](#set-targeting)
1. [Paso 3: Configurar los objetivos y la configuración](#configure-goals-and-settings)

## Paso 1: Crear experiencias {#build-experiences}

Defina el grupo de variaciones de contenido con las que [!UICONTROL Automated Personalization] puede personalizar. Cuanto más enriquecidas y distintas sean sus experiencias y ofertas, mejor podrá el algoritmo hacer coincidir el contenido adecuado con cada visitante.

1. En la lista [!DNL Target] [!UICONTROL Actividades], haga clic en **[!UICONTROL Crear actividad]** > **[!UICONTROL Automated Personalization]**.

1. Para usar el [!UICONTROL Compositor de experiencias visuales] (VEC), haz clic en **[!UICONTROL Visual]**.

   Para usar [!UICONTROL Compositor de experiencias basadas en formularios], seleccione [!UICONTROL Formulario]. Consulte [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md) para obtener más información.

   >[!NOTE]
   >
   >Además del VEC y [!UICONTROL Compositor de experiencias basadas en formularios], [!DNL Target] ofrece el [!UICONTROL VEC de aplicaciones de una sola página]. Para obtener más información sobre los distintos compositores, consulte [Experiencias y ofertas](/help/main/c-experiences/experiences.md).
   >
   >Para obtener información de solución de problemas acerca del VEC, consulte [Solución de problemas del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Condicional) [Elija un área de trabajo](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. En el cuadro **[!UICONTROL Introducir URL de actividad]**, especifique la [URL de actividad](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md).

   Si la cuenta se [configura con una dirección URL predeterminada](/help/main/administrating-target/visual-experience-composer-set-up.md) esa dirección URL aparece de manera predeterminada. Puede cambiar la dirección URL predeterminada por otra dirección si es necesario.

   [!DNL Target] no diferencia entre los protocolos de URL ([!DNL https] y [!DNL http]). Como resultado, [!DNL `http://www.adobe.com`] y [!DNL `https://wwww.adobe.com`] coinciden.

1. Haga clic en **[!UICONTROL Crear]**.

   Se abre la página con la dirección URL especificada en el VEC.

1. Para asignar un nombre a la actividad, haz clic en el icono **[!UICONTROL Editar]** ( ![Editar icono](/help/main/assets/icons/Edit.svg) ) junto a &quot;[!UICONTROL Actividad sin título]&quot;, especifica un nombre descriptivo para la actividad y haz clic en **[!UICONTROL Guardar]**.

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

1. Haga clic en el icono **[!UICONTROL Administrar contenido]** ( ![Icono Administrar contenido](/help/main/assets/icons/Experience.svg) ) para configurar las combinaciones disponibles.

   Aparece un cuadro de diálogo con dos fichas: [!UICONTROL Experiencias] y [!UICONTROL Ofertas]. La ficha [!UICONTROL Experiencias] enumera cada fragmento de contenido y la ubicación a la que está asignado. Para excluir una o más experiencias, selecciona las casillas correspondientes y haz clic en el icono [!UICONTROL Excluir]. Para obtener más opciones, consulte [Administración de exclusiones](/help/main/c-activities/t-automated-personalization/managing-exclusions.md).

   >[!IMPORTANT]
   >
   >Para obtener un rendimiento óptimo, limite las actividades de [!UICONTROL Automated Personalization] y [!UICONTROL Segmentación automática] a entre 4 y 6 ubicaciones con entre 4 y 6 ofertas por ubicación. El número total de experiencias crece a partir de la combinación cartesiana de ubicaciones y ofertas. Las configuraciones más grandes pueden provocar una carga o edición lentas en [!UICONTROL Compositor de experiencias visuales]. Mantener el total por debajo de 5000 experiencias para obtener mejores resultados; el límite estricto es de 30 000 (el mismo límite se aplica cuando la opción [!UICONTROL No permitir duplicados] está habilitada).

1. (Condicional) Haga clic en **[!UICONTROL Ofertas]** para seleccionar elementos de contenido y asignarlos a grupos de informes o para permitir que solo determinados visitantes vean determinadas ofertas con segmentación.

   Para obtener más información sobre los grupos de informes, consulte [Grupos de informes de ofertas en Automated Personalization](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md).

<!--
1. (Conditional) Click **[!UICONTROL Exclusion Groups]** to choose any combination of elements that you want to exclude from the activity.

   ![Exclusion Groups tab of Manage Content dialog box](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   Although you can create up to 30,000 experiences in an AP test, the algorithm performs its best when fewer than 10,000 distinct experiences are used. This same limit is applied even when the activity has enabled the [!UICONTROL Disallow Duplicates] option.

   If you do not currently have any exclusion groups included in your activity, click **Create Exclusion Group**. You can filter to create a list that shows only the combinations you want to exclude. Name your exclusion group, then click **Save**.

   To edit an existing exclusion group, hover over the group you want to edit, then click the pencil icon.
-->

1. Haga clic en **[!UICONTROL Listo]** cuando haya terminado de configurar el contenido de su actividad.

## Paso 2: Establecer el objetivo {#set-targeting}

Decida qué visitantes entran en la actividad y cuánto de su tráfico está expuesto. Emparejarlos con un grupo de control para que [!DNL Target] pueda medir el alza que ofrece la personalización.

1. Haga clic en **[!UICONTROL Segmentación]** en la parte superior de [!UICONTROL Compositor de experiencias visuales] para pasar al siguiente paso en el flujo de trabajo guiado de tres pasos.

   El paso **Segmentación** le resultará familiar si ha utilizado otros tipos de actividad de [!DNL Target]. Aquí puede seleccionar una audiencia y especificar el porcentaje de visitantes que ven cada experiencia.

1. El diagrama de flujo le guía durante el procedimiento para asignar una audiencia y su porcentaje de tráfico, seleccionar el método de asignación de tráfico y especificar la asignación de tráfico para cada experiencia en la actividad.

   ![Paso de segmentación de pruebas AP](/help/main/c-activities/t-automated-personalization/assets/ap-traffic-flow.png)

1. (Condicional) Haga clic en el control **[!UICONTROL Todos los visitantes]** para [seleccionar otra audiencia](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) para la actividad y establecer su porcentaje de visitantes.

   La audiencia [!UICONTROL Todos los visitantes] está establecida como predeterminada. Si selecciona otra audiencia, su nombre se muestra en el control situado más a la izquierda. Por ejemplo, puede limitar las entradas al 50 % de todos los visitantes o al 45 % de la audiencia de California.

1. Haga clic en el control **[!UICONTROL Asignación del tráfico]** para elegir entre las siguientes opciones:

   ![Opciones del objetivo de asignación de tráfico](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap-new.png)

   * **[!UICONTROL Evaluar el algoritmo de Personalization (50/50)]:** Si su objetivo es probar el algoritmo, utilice una división del 50/50 por ciento de los visitantes entre el control y el algoritmo de destino. Esta división proporciona la estimación más precisa del alza. Se sugiere usar con &quot;experiencias aleatorias&quot; como control.
   * **[!UICONTROL Maximización del tráfico de Personalization (90/10)]:** Si su objetivo es crear una actividad &quot;siempre activada&quot;, ponga el 10% de los visitantes en el control. Esta opción garantiza que haya suficientes datos para que los algoritmos continúen aprendiendo a lo largo del tiempo. La compensación aquí es que, a cambio de personalizar una mayor proporción de su tráfico, tiene menos precisión en la estimación del alza. Independientemente del objetivo, esta opción es la división de tráfico recomendada al utilizar una experiencia específica como control.
   * **[!UICONTROL Asignación personalizada]:**: divida manualmente el porcentaje como desee.

1. (Condicional) En la lista desplegable [!UICONTROL Control], [seleccione una experiencia específica para utilizarla como control](/help/main/c-activities/t-automated-personalization/experience-as-control.md) o seleccione [!UICONTROL Experiencia aleatoria.]

   La experiencia de control ofrece una comparación para determinar cuánta alza se proporciona con la prueba automatizada.

   [!UICONTROL Automated Personalization] siempre mide el rendimiento con respecto a un grupo de control. Lo mejor es colocar al menos el 10 % de los participantes en el grupo de control. Si su objetivo es probar si el algoritmo de personalización de los datos que se le proporcionan tiene un mejor rendimiento que el de ninguna personalización (por ejemplo, el control servido aleatoriamente), una división del tráfico del 50/50 por ciento entre el control y el algoritmo de personalización es la forma más rápida y precisa de lograr este objetivo. Si desea maximizar la cantidad de tráfico personalizado y no le interesa comprender el alza exacta que está generando su actividad, una división del tráfico del 10/90 por ciento entre el control y el algoritmo de personalización es la manera más rápida y precisa de lograr este objetivo.

   >[!NOTE]
   >
   >En las actividades [!UICONTROL Automated Personalization], los criterios de entrada (segmentación por URL, reglas de plantilla y objetivos de audiencia) se evalúan en cada solicitud. En las versiones anteriores, los criterios de entrada se evaluaban una vez por sesión.

## Paso 3: Configurar los objetivos y la configuración {#configure-goals-and-settings}

Indique a [!DNL Target] la apariencia del éxito. El objetivo de optimización que elija es la métrica con la que se entrena el algoritmo de personalización, por lo que debe elegir el resultado que más importe para esta actividad.

1. Haga clic en **[!UICONTROL Siguiente]** para mostrar la página de **[!UICONTROL Objetivos y configuración]**.
1. Configure la actividad con las siguientes opciones y luego haga clic en **[!UICONTROL Guardar y cerrar]**.

   | Configuración | Descripción |
   |--- |--- |
   | [!UICONTROL Nombre] | Asigne un nombre a la actividad. Asigne a la actividad un nombre que sea lo suficientemente descriptivo como para que los integrantes del equipo puedan reconocerlo en la lista [!UICONTROL Actividades]. Consulte la tabla anterior para ver los caracteres que no están permitidos en el nombre de la actividad. |
   | [!UICONTROL Objetivo] | (Opcional) Escriba el objetivo de la prueba. El objetivo le ayuda a recordar la finalidad de la actividad. |
   | [!UICONTROL Prioridad] | Según la configuración, la interfaz de usuario de [!DNL Target] y las opciones de [!UICONTROL Prioridad] varían. Puede usar la configuración heredada de [!UICONTROL Low], [!UICONTROL Medium] o [!UICONTROL High], o bien habilitar prioridades específicas de 0 a 999.<P>La prioridad se utiliza si se asignan varias actividades a la misma ubicación con el mismo público. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta.<P>Si esta opción no está habilitada en [!UICONTROL Administración] > [!UICONTROL Informes] (la predeterminada), especifique una prioridad: [!UICONTROL Baja], [!UICONTROL Medium] o [!UICONTROL Alta].<P>Para habilitar prioridades específicas, haga clic en [!UICONTROL Administración] > [!UICONTROL Informes] y luego coloque la opción [!UICONTROL Habilitar prioridades específicas] en la posición &quot;Activado&quot;.<P>Si esta opción está habilitada, especifique un valor de 0 a 999:<ul><li>0 = Bajo</li><li>999 = Alto</li></ul>Para las actividades creadas en versiones anteriores de [!DNL Target Standard/Premium], la prioridad [!UICONTROL Low] se convierte en 0, la prioridad [!UICONTROL Medium] se convierte en 5 y la prioridad [!UICONTROL High] se convierte en 10. Si lo necesita, puede ajustar estos valores.<P>**Nota**: para deshabilitar esta opción después de usar las prioridades específicas, hay que volver a fijar todas las prioridades en 0, 5 y 10. |
   | [!UICONTROL Duración] | Defina las fechas de inicio y finalización de la actividad. Puede seleccionar [!UICONTROL Al activarlo] o especificar una fecha y hora específicas. |
   | [!UICONTROL Objetivo de optimización] | Especifique el objetivo de optimización, que consta de dos parámetros:<ul><li>Qué quiere medir con la actividad</li><li>La acción realizada por el participante de una actividad que muestra que se ha logrado el objetivo.</li></ul>Puede elegir nombrar el objetivo de optimización seleccionando los tres puntos a la derecha de [!UICONTROL Mi objetivo principal]. Las actividades de [!UICONTROL Automated Personalization] pueden medir [!UICONTROL Conversión] o [!UICONTROL Ingresos]. La conversión se puede realizar viendo una página o un mbox. También se realiza un seguimiento de los clics.<P>El objetivo principal también se convierte en la métrica de modelado que utiliza el sistema de modelado para calcular el éxito de la experiencia.<P>Los visitantes pueden continuar en la actividad con fines de seguimiento después de alcanzar el objetivo de modelado. Por ejemplo, a menudo se usa una actividad [!UICONTROL Automated Personalization] para mejorar las tasas de clics, y eso se establece como objetivo de modelado. Sin embargo, es importante ver cómo las tasas de clics incrementadas llevan a conversión final, por lo que resulta esencial el seguimiento a través de la conversión final.<P>Dispone de dependencia respecto a varias métricas y tiene la posibilidad de elegir si una métrica debe alcanzarse o no para que su contador aumente.<P>Debe definir ambas (o varias) métricas de éxito antes de poder hacer una dependiente de la otra.<P>La opción [!UICONTROL Añadir dependencia] permite que la métrica de éxito aumente si se alcanza otra métrica de éxito (o todo lo contrario, si no se alcanza).<P>Para agregar una dependencia:<ol><li>Después de agregar métricas adicionales, haz clic en **[!UICONTROL Configuración avanzada]** en el menú de tres puntos a la derecha de [!UICONTROL Objetivo adicional].</li><li>Haga clic en la opción **[!UICONTROL Agregar dependencia]** en la parte inferior de la sección [!UICONTROL Configuración de informes].</li><li>Arrastre y suelte las métricas deseadas del panel izquierdo al panel derecho y, a continuación, haga clic en [!UICONTROL Alcanzado] para alternar el valor entre [!UICONTROL Alcanzado] y [!UICONTROL No alcanzado].</li></ol>Puede editar o eliminar dependencias después de añadirlas. |
   | [!UICONTROL Métrica de conversión] | De forma predeterminada, la métrica de conversión es la misma que la métrica de objetivo de optimización. Sin embargo, puede definir una métrica de conversión independiente desmarcando la opción [!UICONTROL Igual que el objetivo de optimización]. |
   | [!UICONTROL Métricas adicionales] | Añada las métricas adicionales de creación de informes que desee utilizar. Puede agregar métricas de conversión, participación o ingresos.<P>**Nota**: La métrica [!UICONTROL Participación] no se admite como métrica adicional. Es posible que la interfaz de usuario [!DNL Target] le permita seleccionar la métrica [!UICONTROL Participación], pero los datos no se muestran con precisión en los informes. |
   | [!UICONTROL Audiencias para informes] | Añada audiencias para habilitar el filtrado por audiencias en los informes. De manera predeterminada, el informe muestra los resultados para todos los visitantes que cumplen los criterios. Añada audiencias para filtrar los resultados para subconjuntos de visitantes más específicos.<P>**Nota**: a diferencia de otros tipos de actividades, [!UICONTROL Automated Personalization] no puede usar [!UICONTROL Adobe Analytics] como fuente de informes (A4T). |
   | [!UICONTROL Notas] | Escriba cualquier información sobre la actividad que sea útil para usted o para otros integrantes del equipo. Se puede cambiar el tamaño del panel [!UICONTROL Notas]. |

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

Después de hacer clic en **[!UICONTROL Guardar y cerrar]**, se muestra la página [!UICONTROL Información general] de la actividad. Haga clic en **Previsualizar experiencias** para obtener una vista previa del aspecto que tendrán las experiencias cuando se entreguen. Aparece un elemento emergente que puede usar para ver y compartir vínculos a sus experiencias AP en su sitio para obtener una &quot;auténtica vista previa&quot; de las experiencias fuera del [!UICONTROL Compositor de experiencias visuales] de [!UICONTROL Target] (VEC). Debe compartir los vínculos del mensaje para compartir la vista previa. No funciona hacer clic en un vínculo y copiar la dirección URL directamente desde el explorador. Si se copia el vínculo, la dirección URL contiene un parámetro que muestra la página correctamente solo cuando se accede a la página desde el vínculo del mensaje.

Para obtener información sobre los informes, consulte [Informes de Personalización automatizada](/help/main/c-reports/personalization-reports/reports-ap.md).
