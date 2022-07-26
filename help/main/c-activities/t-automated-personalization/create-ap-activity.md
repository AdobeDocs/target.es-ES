---
keywords: personalización automatizada;ap;audiencias;ensamblado;bosque aleatorio;variación residual;variación de error;valor de duración
description: Obtenga información sobre cómo crear una [!UICONTROL Automated Personalization] actividad (AP) en [!DNL Adobe Target] usando la variable [!UICONTROL Compositor de experiencias visuales].
title: ¿Cómo creo un [!UICONTROL Automated Personalization] ¿Actividad?
feature: Automated Personalization
exl-id: eadc2bbc-310b-479f-b75b-253e8d7aa812
source-git-commit: 3a11b368838adb4a6b4f99249db260da8f3f423b
workflow-type: tm+mt
source-wordcount: '1855'
ht-degree: 62%

---

# ![PREMIUM](/help/main/assets/premium.png) Creación de una actividad de Personalización automatizada

Cree un [!UICONTROL Automated Personalization] actividad (AP) en [!DNL Adobe Target] usando la variable [!UICONTROL Compositor de experiencias visuales] (VEC).

La variable [!UICONTROL Automated Personalization] Flujo de trabajo de la actividad (AP) en [!DNL Adobe Target] difiere del flujo de trabajo de los otros tipos de actividad.

1. En el [!DNL Target] [!UICONTROL Actividades] lista, haga clic en **[!UICONTROL Crear actividad]** > **[!UICONTROL Automated Personalization]**.

   ![Crear actividad: Automated Personalization](/help/main/c-activities/t-automated-personalization/assets/ap-create-new.png)

1. Para utilizar el VEC, haga clic en **[!UICONTROL Visual (predeterminado)]**.

   ![Cuadro de diálogo Crear actividad de Automated Personalization](/help/main/c-activities/t-automated-personalization/assets/ap_url-new.png){width="300"}

   Para usar la variable [!UICONTROL Compositor de experiencias basadas en formularios], seleccione [!UICONTROL Formulario]. Consulte [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md) para obtener más información.

   >[!NOTE]
   >
   >Además del VEC y [!UICONTROL Compositor de experiencias basadas en formularios], [!DNL Target] ofrece la variable [!UICONTROL Aplicación de una sola página VEC]. Para obtener más información sobre los distintos compositores, consulte [Experiencias y ofertas](/help/main/c-experiences/experiences.md).
   >
   >Para obtener información sobre la solución de problemas del VEC, consulte [Solución de problemas del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Condicional) [Elegir un espacio de trabajo](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Compruebe o escriba la dirección URL de la actividad y haga clic en **[!UICONTROL Siguiente]**.

   >[!NOTE]
   >
   >[!DNL Target] no diferencia entre los protocolos URL ([!DNL https] y [!DNL http]). Esto quiere decir que tanto [!DNL `http://www.adobe.com`] como [!DNL `https://wwww.adobe.com`] coinciden.

   La página con la dirección URL especificada se abre en el VEC.

1. Para asignar un nombre a la actividad, haga clic en el botón **[!UICONTROL Nombre]** y escriba el nombre de la actividad.

   ![Campo Nombre](/help/main/c-activities/t-automated-personalization/assets/ap-new-name.png)

   El nombre de la actividad no puede comenzar con ninguno de los siguientes caracteres:

   | Carácter | Descripción |
   |--- |--- |
   | `=` | Igual a |
   | `+` | Más |
   | `-` | Menos |
   | `@` | Arroba |

   Además, el nombre de la actividad no puede contener ninguna de las siguientes secuencias de caracteres: &#39;;=&#39;, &#39;;+&#39;, &#39;;-&#39;, &#39;;@&#39;, &#39;,=&#39;, &#39;,+&#39;, &#39;,-&#39;, &#39;,@&#39;, &#39;[&quot;&#39;, &#39;&quot;]&#39;, &#39;[&#39;&#39;, &#39;&#39;]&#39;.

1. Modifique los elementos de página tal como se explica en [las opciones del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   Puede seleccionar varias imágenes a la vez desde el administrador de recursos. De este modo, puede ver rápidamente la página con cada una de las imágenes configuradas en la actividad. También puede editar fácilmente los elementos de texto en sus ofertas. Cuando edite un elemento, aparecen barras en ese elemento para indicar que lo ha cambiado.

1. Haga clic en **[!UICONTROL Gestionar contenido]** para configurar las combinaciones disponibles.

   ![Opción Administrar contenido](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   Aparece un cuadro de diálogo con tres opciones en la parte superior de la pantalla: [!UICONTROL Experiencias], [!UICONTROL Ofertas]y [!UICONTROL Grupos de exclusión].

   ![Cuadro de diálogo Administrar contenido](/help/main/c-activities/t-automated-personalization/assets/ap_content-new.png)

   >[!NOTE]
   >
   >Aunque se pueden crear hasta 30 000 experiencias en una actividad AP, el rendimiento de la actividad es mejor cuando se utilizan menos de 5000. Este mismo límite se aplica incluso cuando la actividad tiene habilitada la opción [!UICONTROL No permitir duplicados].

   La variable [!UICONTROL Experiencias] muestra cada parte de contenido seleccionada para la actividad y la ubicación que se le asigna.

   Puede excluir experiencias específicas pasando el puntero sobre la experiencia deseada y luego haciendo clic en el botón [!UICONTROL Excluir] icono.

   ![Icono Excluir al pasar el ratón por encima](/help/main/c-activities/t-automated-personalization/assets/icon-exclude.png)

   Puede excluir/incluir experiencias por lotes seleccionando la casilla de las experiencias relevantes y luego haciendo clic en el botón [!UICONTROL Excluir] en la esquina superior derecha del cuadro de diálogo.

   ![Opciones de exclusión por lotes](/help/main/c-activities/t-automated-personalization/assets/batch-exclude.png)

   Puede filtrar esta vista de lista para ver solo actividades excluidas o incluidas haciendo clic en la lista desplegable [!UICONTROL Estado].

1. (Condicional) Haga clic en **[!UICONTROL Ofertas]** para seleccionar elementos de contenido y asignarlos a grupos de informes o para permitir que solo determinados visitantes vean determinadas ofertas con segmentación.

   Para obtener más información sobre los grupos de informes, consulte [Grupos de informes de ofertas en Automated Personalization](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md).

1. (Condicional) Haga clic en **[!UICONTROL Grupos de exclusión]** para elegir cualquier combinación de elementos que desee excluir de la actividad.

   ![Pestaña Grupos de exclusión del cuadro de diálogo Administrar contenido](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   Aunque puede crear hasta 30 000 experiencias en una prueba AP, el algoritmo funciona mejor cuando se usan menos de 10 000 experiencias distintas. Este mismo límite se aplica incluso cuando la actividad tiene habilitada la opción [!UICONTROL No permitir duplicados].

   Si actualmente no tiene grupos de exclusión incluidos en su actividad, haga clic en **Crear grupo de exclusión**. Puede filtrar para crear una lista que muestre solo las combinaciones que desea excluir. Asigne un nombre a su grupo de exclusión y haga clic en **Guardar**.

   Para editar un grupo de exclusión existente, desplace el cursor sobre el grupo que desea editar y luego haga clic en el icono del lápiz.

1. Haga clic en **[!UICONTROL Listo]** cuando haya terminado de configurar el contenido de su actividad.

1. La variable **Segmentación** el paso parece familiar si ha utilizado otros [!DNL Target] tipos de actividades. Aquí puede seleccionar una audiencia y especificar el porcentaje de visitantes que ven la experiencia de control haciendo clic en el **[!UICONTROL Asignación personalizada]** lista desplegable y haga clic en **Siguiente**.

   La lista desplegable [!UICONTROL Asignación personalizada] le permite elegir entre las siguientes opciones:

   ![Lista desplegable Objetivo de asignación de tráfico](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap.png)

   * **[!UICONTROL Evaluar el algoritmo de personalización (50/50)]:** Si su objetivo es probar el algoritmo, utilice una división del 50/50 por ciento de los visitantes entre el control y el algoritmo segmentado. Esta división proporciona la estimación más precisa del alza. Se sugiere usar con &quot;experiencias aleatorias&quot; como control.
   * **[!UICONTROL Maximización del tráfico de personalización (90/10)]:** Si su objetivo es crear una actividad &quot;siempre activada&quot;, ponga el 10 % de los visitantes en el control. Esta opción garantiza que haya suficientes datos para que los algoritmos continúen aprendiendo a lo largo del tiempo. Tenga en cuenta que la compensación aquí es que a cambio de personalizar una mayor proporción de su tráfico, tiene menos precisión en cuál es exactamente el alza. Independientemente del objetivo, esta es la división de tráfico recomendada al usar una experiencia específica como control.
   * **[!UICONTROL Asignación personalizada]:** Divida manualmente el porcentaje como desee.

1. (Condicional) En la lista desplegable [!UICONTROL Control][, seleccione una experiencia específica para utilizarla como control](/help/main/c-activities/t-automated-personalization/experience-as-control.md) o seleccione [!UICONTROL Experiencia aleatoria.]

   La experiencia de control ofrece una comparación para determinar cuánta alza se proporciona con la prueba automatizada.

   [!UICONTROL Personalización automatizada siempre mide el rendimiento con respecto al grupo de control. ] Lo mejor es colocar al menos el 10 % de los participantes en el grupo de control. Si su objetivo es probar si el algoritmo de personalización en los datos que se ofrece tiene mejor rendimiento que la no personalización (es decir, el control servido aleatoriamente), entonces una división de tráfico del 50/50 por ciento entre el control y el algoritmo de personalización sería el más rápido y la forma más precisa para lograr este objetivo. Si desea maximizar la cantidad de tráfico que se personaliza y le preocupa menos comprender el alza exacta que está generando su actividad, entonces una división de tráfico del 10/90 por ciento entre el control y el algoritmo de personalización sería la manera más rápida y precisa para alcanzar esta meta.

   >[!NOTE]
   >
   >En [!UICONTROL Automated Personalization] las actividades de , los criterios de entrada (segmentación por URL, reglas de plantilla y segmentaciones de audiencia) se evalúan en cada solicitud. En las versiones anteriores, los criterios de entrada se evaluaban una vez por sesión.

1. Haga clic en **[!UICONTROL Siguiente]** para mostrar la página de **[!UICONTROL Objetivos y configuración]**.
1. Configure la actividad con las siguientes opciones y, a continuación, haga clic en **[!UICONTROL Guardar y cerrar]**.

   | Configuración | Descripción |
   |--- |--- |
   | [!UICONTROL Nombre] | Asigne un nombre a la actividad. Asigne a la actividad un nombre lo suficientemente descriptivo como para que los integrantes del equipo puedan reconocerlo en la variable [!UICONTROL Actividades] lista. Consulte la tabla anterior para ver los caracteres que no están permitidos en el nombre de la actividad. |
   | [!UICONTROL Objetivo] | (Opcional) Escriba el objetivo de la prueba. El objetivo le ayuda a recordar la finalidad de la actividad. |
   | [!UICONTROL Prioridad] | La interfaz de usuario y las opciones de [!UICONTROL Prioridad] varían en función de la configuración. Puede usar la configuración heredada de bajo, medio o alto, o habilitar prioridades específicas de 0 a 999.<br>La prioridad se utiliza si se asignan varias actividades a la misma ubicación con la misma audiencia. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta.<br>Si esta opción no está habilitada en [!UICONTROL Administración] > [!UICONTROL Informes] (predeterminado), especifique una prioridad: Bajo, Medio o Alto.<br>Para habilitar prioridades específicas, haga clic en [!UICONTROL Administración] > [!UICONTROL Informes]y, a continuación, cambie la [!UICONTROL Habilitar prioridades específicas] a la posición &quot;Activado&quot;.<br>Si esta opción está habilitada, indique un valor entre 0 y 999:<ul><li>0 = Bajo</li><li>999 = Alto</li></ul>En las actividades creadas en versiones anteriores de [!DNL Target Standard/Premium], el nivel bajo de prioridad se convierte en 0; el medio, en 5; y el alto, en 10. Si lo necesita, puede ajustar estos valores.<br>**Nota:** para deshabilitar esta opción después de usar las prioridades específicas, hay que volver a fijar todas las prioridades en 0, 5 y 10. |
   | [!UICONTROL Duración] | Defina las fechas de inicio y finalización de la actividad. Puede seleccionar [!UICONTROL Cuando se activa] o puede especificar una fecha y hora específicas. |
   | [!UICONTROL Objetivo de optimización] | Especifique el objetivo de optimización, que consta de dos parámetros:<ul><li>Qué quiere medir con la actividad</li><li>La acción realizada por el participante de una actividad que muestra que se ha logrado el objetivo.</li></ul>Puede elegir asignar un nombre al objetivo de optimización seleccionando los tres puntos a la derecha de [!UICONTROL Mi objetivo principal]. [!UICONTROL Las actividades de Personalización automatizada pueden medir la conversión, los ingresos por visitante y el valor de pedido promedio. ] La conversión se puede conseguir visualizando una página o visualizando un mbox. También se realiza un seguimiento de los clics.<br>El objetivo principal también se convierte en la métrica de modelado, que el sistema de modelado utiliza para calcular el éxito de la experiencia.<br>Los visitantes pueden continuar en la actividad con fines de seguimiento después de alcanzar el objetivo de modelado. Por ejemplo, a menudo un [!UICONTROL Automated Personalization] actividad se usa para mejorar las tasas de clics, y se establece como objetivo de modelado. Sin embargo, es importante ver cómo las tasas de clics incrementadas llevan a conversión final, por lo que resulta esencial el seguimiento a través de la conversión final.<br>Dispone de dependencia respecto a varias métricas y tiene la posibilidad de elegir si una métrica debe alcanzarse o no para que su contador aumente.<br>Debe definir ambas (o varias) métricas de éxito antes de poder hacer una dependiente de la otra.<br>La opción Añadir dependencia permite que la métrica de éxito aumente si se alcanza otra métrica de éxito (o todo lo contrario, si no se alcanza).  <br>Para agregar una dependencia:<ol><li>Después de agregar métricas adicionales, haga clic en **[!UICONTROL Configuración avanzada]**[!UICONTROL  en el menú de tres puntos que hay a la derecha de Objetivo adicional].</li><li>Haga clic en la opción **[!UICONTROL Agregar dependencia]** en la parte inferior de la sección [!UICONTROL Configuración de informes].</li><li>Arrastre y suelte las métricas deseadas del panel izquierdo al panel derecho y, a continuación, haga clic en [!UICONTROL Alcanzado] para alternar el valor entre [!UICONTROL Alcanzado] y [!UICONTROL No alcanzado]</li></ol>Puede editar o eliminar dependencias después de añadirlas. |
   | [!UICONTROL Métrica de conversión] | De forma predeterminada, la métrica de conversión es la misma que la métrica de objetivo de optimización. Sin embargo, puede definir una métrica de conversión independiente desmarcando la opción [!UICONTROL Igual que el objetivo de optimización]. |
   | [!UICONTROL Métricas adicionales] | Agregue las métricas de informes adicionales que desee usar. Puede agregar métricas de conversión, participación o ingresos.<br>**Nota:** no se puede utilizar la métrica de compromiso como métrica adicional. La interfaz de usuario puede permitirle seleccionar la variable [!UICONTROL Participación] , pero los datos no se muestran con precisión en los informes. |
   | [!UICONTROL Audiencias para los informes] | Añada audiencias para habilitar el filtrado por audiencias en los informes. De manera predeterminada, el informe muestra los resultados para todos los visitantes que cumplen los criterios. Añada audiencias para filtrar los resultados para subconjuntos de visitantes más específicos.<br>**Nota**: A diferencia de otros tipos de actividades, [!UICONTROL Automated Personalization] no se puede usar [!UICONTROL Adobe Analytics] como fuente de informes (A4T). |
   | [!UICONTROL Notas] | Escriba la información sobre la actividad que sea útil tener disponible para el equipo. La variable [!UICONTROL Notas] se puede cambiar de tamaño. |

   Cuando nombra o cambia el nombre de una métrica, no se permiten los siguientes caracteres:

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

Después de hacer clic en **[!UICONTROL Guardar y cerrar]**, la actividad [!UICONTROL Información general] se muestra. Haga clic en **Previsualizar experiencias** para previsualizar el aspecto de las experiencias cuando se entregan. Aparece un elemento emergente que puede usar para ver y compartir vínculos a sus experiencias AP en su sitio para obtener una &quot;auténtica vista previa&quot; de las experiencias fuera de [!UICONTROL Target]Compositor de experiencias visuales (VEC) de . Debe compartir los vínculos del mensaje para compartir la vista previa. Hacer clic en un vínculo y luego copiar la dirección URL directamente desde el explorador no funcionará. Si copia el vínculo, la dirección URL contendrá un parámetro que muestre la página correctamente solo cuando acceda a la página desde el vínculo del mensaje.

Para obtener información sobre los informes, consulte [Informes de Personalización automatizada](/help/main/c-reports/personalization-reports/reports-ap.md).
