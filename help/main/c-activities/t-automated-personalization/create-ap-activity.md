---
keywords: personalización automatizada;ap
description: Obtenga información sobre cómo crear un [!UICONTROL Automated Personalization] Actividad de (AP) en [!DNL Adobe Target] uso del [!UICONTROL Compositor de experiencias visuales].
title: ¿Cómo se crea un [!UICONTROL Automated Personalization] ¿Actividad?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Automated Personalization
exl-id: eadc2bbc-310b-479f-b75b-253e8d7aa812
source-git-commit: d5b24f298ae405d57c2ba639082cbe99c4e358fd
workflow-type: tm+mt
source-wordcount: '1884'
ht-degree: 43%

---

# Crear una actividad de [!UICONTROL Automated Personalization]

Crear un [!UICONTROL Automated Personalization] Actividad de (AP) en [!DNL Adobe Target] uso del [!UICONTROL Compositor de experiencias visuales] (VEC).

El [!UICONTROL Automated Personalization] Flujo de trabajo de actividad de (AP) en [!DNL Target] varía con respecto al flujo de trabajo de los demás tipos de actividades.

1. Desde el [!DNL Target] [!UICONTROL Actividades] , haga clic en **[!UICONTROL Crear actividad]** > **[!UICONTROL Automated Personalization]**.

   ![Crear actividad: Automated Personalization](/help/main/c-activities/t-automated-personalization/assets/ap-create-new.png)

1. Para usar la variable [!UICONTROL Compositor de experiencias visuales] (VEC), haga clic en **[!UICONTROL Visual]**.

   Para usar la variable [!UICONTROL Compositor de experiencias basadas en formularios], seleccione [!UICONTROL Form]. Consulte [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md) para obtener más información.

   >[!NOTE]
   >
   >Además del VEC y [!UICONTROL Compositor de experiencias basadas en formularios], [!DNL Target] ofrece el [!UICONTROL VEC de aplicación de una sola página]. Para obtener más información sobre los distintos compositores, consulte [Experiencias y ofertas](/help/main/c-experiences/experiences.md).
   >
   >Para obtener información sobre la resolución de problemas del VEC, consulte [Solución de problemas del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Condicional) [Elija un espacio de trabajo](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Compruebe o introduzca la dirección URL de la actividad y haga clic en **[!UICONTROL Crear]**.

   >[!NOTE]
   >
   >[!DNL Target] no diferencia entre los protocolos URL ([!DNL https] y [!DNL http]). Esto quiere decir que tanto [!DNL `http://www.adobe.com`] como [!DNL `https://wwww.adobe.com`] coinciden.

   Se abre la página con la dirección URL especificada en el VEC.

1. Haga clic en **[!UICONTROL Nombre]** y escriba el nombre de la actividad.

   ![Campo Nombre](/help/main/c-activities/t-automated-personalization/assets/ap-new-name.png)

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

1. Haga clic en **[!UICONTROL Gestionar contenido]** para configurar las combinaciones disponibles.

   ![Opción Administrar contenido](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   Aparece un cuadro de diálogo con tres opciones en la parte superior de la pantalla: [!UICONTROL Experiencias], [!UICONTROL Ofertas], y [!UICONTROL Grupos de exclusión].

   ![Cuadro de diálogo Administrar contenido](/help/main/c-activities/t-automated-personalization/assets/ap_content-new.png)

   >[!NOTE]
   >
   >Aunque se pueden crear hasta 30 000 experiencias en una actividad AP, el rendimiento de la actividad es mejor cuando se utilizan menos de 5000. Este mismo límite se aplica incluso cuando la actividad ha habilitado el [!UICONTROL No permitir duplicados] opción.

   El [!UICONTROL Experiencias] La lista muestra cada parte de contenido seleccionada para la actividad y la ubicación a la que está asignada.

   Puede excluir experiencias específicas pasando el puntero sobre la experiencia deseada y luego haciendo clic en [!UICONTROL Excluir] icono.

   ![Icono Excluir al pasar el ratón por encima](/help/main/c-activities/t-automated-personalization/assets/icon-exclude.png)

   Puede excluir o incluir experiencias por lotes seleccionando la casilla de las experiencias relevantes y luego haciendo clic en [!UICONTROL Excluir] en la esquina superior derecha del cuadro de diálogo.

   ![Opciones de exclusión por lotes](/help/main/c-activities/t-automated-personalization/assets/batch-exclude.png)

   Puede filtrar esta vista de lista para ver solo actividades excluidas o incluidas haciendo clic en la lista desplegable [!UICONTROL Estado].

1. (Condicional) Haga clic en **[!UICONTROL Ofertas]** para seleccionar elementos de contenido y asignarlos a grupos de informes o para permitir que solo determinados visitantes vean determinadas ofertas con segmentación.

   Para obtener más información sobre los grupos de informes, consulte [Grupos de informes de ofertas en Automated Personalization](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md).

1. (Condicional) Haga clic en **[!UICONTROL Grupos de exclusión]** para elegir cualquier combinación de elementos que desee excluir de la actividad.

   ![Pestaña Grupos de exclusión del cuadro de diálogo Administrar contenido](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   Aunque puede crear hasta 30 000 experiencias en una prueba AP, el algoritmo funciona mejor cuando se usan menos de 10 000 experiencias distintas. Este mismo límite se aplica incluso cuando la actividad ha habilitado el [!UICONTROL No permitir duplicados] opción.

   Si actualmente no tiene grupos de exclusión incluidos en su actividad, haga clic en **Crear grupo de exclusión**. Puede filtrar para crear una lista que muestre solo las combinaciones que desea excluir. Nombre el grupo de exclusión y haga clic en **Guardar**.

   Para editar un grupo de exclusión existente, desplace el cursor sobre el grupo que desea editar y luego haga clic en el icono del lápiz.

1. Haga clic en **[!UICONTROL Listo]** cuando haya terminado de configurar el contenido de su actividad.

1. El **Segmentación** Este paso le resulta familiar si ha utilizado otros [!DNL Target] tipos de actividades. Aquí puede seleccionar una audiencia y especificar el porcentaje de visitantes que ven la experiencia de control haciendo clic en **[!UICONTROL Asignación personalizada]** y haga clic en. **Siguiente**.

   La lista desplegable [!UICONTROL Asignación personalizada] le permite elegir entre las siguientes opciones:

   ![Lista desplegable Objetivo de asignación de tráfico](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap.png)

   * **[!UICONTROL Evaluar algoritmo de personalización (50/50)]:** Si su objetivo es probar el algoritmo, utilice una división del 50/50 por ciento de los visitantes entre el control y el algoritmo seleccionado. Esta división proporciona la estimación más precisa del alza. Se sugiere usar con &quot;experiencias aleatorias&quot; como control.
   * **[!UICONTROL Maximización del tráfico de personalización (90/10)]:** Si su objetivo es crear una actividad &quot;siempre activada&quot;, ponga el 10 % de los visitantes en el control. Esta opción garantiza que haya suficientes datos para que los algoritmos continúen aprendiendo a lo largo del tiempo. La compensación aquí es que, a cambio de personalizar una mayor proporción de su tráfico, tiene menos precisión en la estimación del alza. Independientemente del objetivo, esta opción es la división de tráfico recomendada al utilizar una experiencia específica como control.
   * **[!UICONTROL Asignación personalizada]:** Divida manualmente el porcentaje como desee.

1. (Condicional) En la lista desplegable [!UICONTROL Control][, seleccione una experiencia específica para utilizarla como control](/help/main/c-activities/t-automated-personalization/experience-as-control.md) o seleccione [!UICONTROL Experiencia aleatoria.]

   La experiencia de control ofrece una comparación para determinar cuánta alza se proporciona con la prueba automatizada.

   [!UICONTROL Personalización automatizada siempre mide el rendimiento con respecto al grupo de control. ] Lo mejor es colocar al menos el 10 % de los participantes en el grupo de control. Si su objetivo es probar si el algoritmo de personalización de los datos que se le proporcionan tiene un mejor rendimiento que el de ninguna personalización (por ejemplo, el control servido aleatoriamente), una división del tráfico del 50/50 por ciento entre el control y el algoritmo de personalización es la forma más rápida y precisa de lograr este objetivo. Si desea maximizar la cantidad de tráfico personalizado y no le interesa comprender el alza exacta que está generando su actividad, una división del tráfico del 10/90 por ciento entre el control y el algoritmo de personalización es la manera más rápida y precisa de lograr este objetivo.

   >[!NOTE]
   >
   >Entrada [!UICONTROL Automated Personalization] Las actividades de, los criterios de entrada (segmentación por URL, reglas de plantilla y objetivos de audiencia) se evalúan en cada solicitud. En las versiones anteriores, los criterios de entrada se evaluaban una vez por sesión.

1. Haga clic en **[!UICONTROL Siguiente]** para mostrar la página de **[!UICONTROL Objetivos y configuración]**.
1. Configure la actividad con las siguientes opciones y, a continuación, haga clic en **[!UICONTROL Guardar y cerrar]**.

   | Configuración | Descripción |
   |--- |--- |
   | [!UICONTROL Nombre] | Asigne un nombre a la actividad. Asigne a la actividad un nombre que sea lo suficientemente descriptivo como para que los integrantes del equipo puedan reconocerlo en la [!UICONTROL Actividades] lista. Consulte la tabla anterior para ver los caracteres que no están permitidos en el nombre de la actividad. |
   | [!UICONTROL Objetivo] | (Opcional) Escriba el objetivo de la prueba. El objetivo le ayuda a recordar la finalidad de la actividad. |
   | [!UICONTROL Prioridad] | Según la configuración, la variable [!DNL Target] IU y opciones de [!UICONTROL Prioridad] variar. Puede utilizar la configuración heredada de [!UICONTROL Baja], [!UICONTROL Mediana], o [!UICONTROL Alta]o puede habilitar prioridades específicas de 0 a 999.<P>La prioridad se utiliza si se asignan varias actividades a la misma ubicación con la misma audiencia. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta.<P>Si esta opción no está habilitada en [!UICONTROL Administration] > [!UICONTROL Informes] (el valor predeterminado), especifique una prioridad: [!UICONTROL Baja], [!UICONTROL Mediana], o [!UICONTROL Alta].<P>Para habilitar prioridades específicas, haga clic en [!UICONTROL Administration] > [!UICONTROL Informes]y, a continuación, active [!UICONTROL Habilitar prioridades específicas] a la posición &quot;Activado&quot;.<P>Si esta opción está habilitada, especifique un valor de 0 a 999:<ul><li>0 = Bajo</li><li>999 = Alto</li></ul>Para actividades creadas en versiones anteriores de [!DNL Target Standard/Premium], [!UICONTROL Baja] la prioridad se convierte en 0, [!UICONTROL Mediana] la prioridad se convierte en 5 y [!UICONTROL Alta] la prioridad se convierte en 10. Si lo necesita, puede ajustar estos valores.<P>**Nota:** para deshabilitar esta opción después de usar las prioridades específicas, hay que volver a fijar todas las prioridades en 0, 5 y 10. |
   | [!UICONTROL Duración] | Defina las fechas de inicio y finalización de la actividad. Puede seleccionar [!UICONTROL Cuando está activado] o puede especificar una fecha y una hora específicas. |
   | [!UICONTROL Objetivo de optimización] | Especifique el objetivo de optimización, que consta de dos parámetros:<ul><li>Qué quiere medir con la actividad</li><li>La acción realizada por el participante de una actividad que muestra que se ha logrado el objetivo.</li></ul>Puede elegir asignar un nombre al objetivo de optimización seleccionando los tres puntos a la derecha de [!UICONTROL Mi objetivo principal]. [!UICONTROL Automated Personalization] las actividades pueden medir [!UICONTROL Conversión] o [!UICONTROL Ingresos]. La conversión se puede realizar viendo una página o un mbox. También se realiza un seguimiento de los clics.<P>El objetivo principal también se convierte en la métrica de modelado que utiliza el sistema de modelado para calcular el éxito de la experiencia.<P>Los visitantes pueden continuar en la actividad con fines de seguimiento después de alcanzar el objetivo de modelado. Por ejemplo, a menudo una [!UICONTROL Automated Personalization] La actividad de se utiliza para mejorar las tasas de clics, y eso se establece como objetivo de modelado. Sin embargo, es importante ver cómo las tasas de clics incrementadas llevan a conversión final, por lo que resulta esencial el seguimiento a través de la conversión final.<P>Dispone de dependencia respecto a varias métricas y tiene la posibilidad de elegir si una métrica debe alcanzarse o no para que su contador aumente.<P>Debe definir ambas (o varias) métricas de éxito antes de poder hacer una dependiente de la otra.<P>La opción [!UICONTROL Añadir dependencia] permite que la métrica de éxito aumente si se alcanza otra métrica de éxito (o todo lo contrario, si no se alcanza).<P>Para agregar una dependencia:<ol><li>Después de agregar métricas adicionales, haga clic en **[!UICONTROL Configuración avanzada]**[!UICONTROL  en el menú de tres puntos que hay a la derecha de Objetivo adicional].</li><li>Haga clic en la opción **[!UICONTROL Agregar dependencia]** en la parte inferior de la sección [!UICONTROL Configuración de informes].</li><li>Arrastre y suelte las métricas deseadas del panel izquierdo al panel derecho y, a continuación, haga clic en [!UICONTROL Alcanzado] para alternar el valor entre [!UICONTROL Alcanzado] y [!UICONTROL No alcanzado] </li></ol>Puede editar o eliminar dependencias después de añadirlas. |
   | [!UICONTROL Métrica de conversión] | De forma predeterminada, la métrica de conversión es la misma que la métrica de objetivo de optimización. Sin embargo, puede definir una métrica de conversión independiente desmarcando la opción [!UICONTROL Igual que el objetivo de optimización]. |
   | [!UICONTROL Métricas adicionales] | Añada las métricas adicionales de creación de informes que desee utilizar. Puede agregar métricas de conversión, participación o ingresos.<P>**Nota**: La [!UICONTROL Participación] Esta métrica no se admite como métrica adicional. El [!DNL Target] La interfaz de usuario puede permitirle seleccionar [!UICONTROL Participación] , pero los datos no se muestran con precisión en los informes. |
   | [!UICONTROL Audiencias para los informes] | Añada audiencias para habilitar el filtrado por audiencias en los informes. De manera predeterminada, el informe muestra los resultados para todos los visitantes que cumplen los criterios. Añada audiencias para filtrar los resultados para subconjuntos de visitantes más específicos.<P>**Nota**: a diferencia de otros tipos de actividades, [!UICONTROL Automated Personalization] no se puede usar [!UICONTROL Adobe Analytics] como fuente de informes (A4T). |
   | [!UICONTROL Notas] | Escriba cualquier información sobre la actividad que sea útil para usted o para otros integrantes del equipo. El [!UICONTROL Notas] El panel se puede cambiar de tamaño. |

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

Después de hacer clic en **[!UICONTROL Guardar y cerrar]**, la actividad es [!UICONTROL Información general] página muestra. Clic **Previsualizar experiencias** para obtener una vista previa del aspecto que tendrán las experiencias cuando se entreguen. Aparece una ventana emergente que puede usar para ver y compartir vínculos a sus experiencias AP en su sitio para obtener una &quot;auténtica vista previa&quot; de las experiencias fuera de [!UICONTROL Target] [!UICONTROL Compositor de experiencias visuales] (VEC). Debe compartir los vínculos del mensaje para compartir la vista previa. No funciona hacer clic en un vínculo y copiar la dirección URL directamente desde el explorador. Si se copia el vínculo, la dirección URL contiene un parámetro que muestra la página correctamente solo cuando se accede a la página desde el vínculo del mensaje.

Para obtener información sobre los informes, consulte [Informes de Personalización automatizada](/help/main/c-reports/personalization-reports/reports-ap.md).
