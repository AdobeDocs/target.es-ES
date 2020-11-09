---
keywords: automated personalization;Audiences;ensemble;random forest;residual variance;error variance;lifetime value
description: El flujo de trabajo de actividades de personalización automatizada es distinto al flujo de trabajo de los otros tipos de actividades.
title: Crear una actividad de personalización automatizada
feature: ap
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '2039'
ht-degree: 98%

---


# ![PREMIUM](/help/assets/premium.png) Creación de una actividad de Personalización automatizada{#create-an-automated-personalization-activity}

El flujo de trabajo de actividades de personalización automatizada es distinto al flujo de trabajo de los otros tipos de actividades.

1. En la lista de actividades de Target Standard, haga clic en **[!UICONTROL Crear actividad]** > **[!UICONTROL Personalización automatizada]**.

   ![Crear actividad: Automated Personalization](/help/c-activities/t-automated-personalization/assets/ap_create-new.png)

1. Para utilizar el Compositor de experiencias visuales (VEC), haga clic en **[!UICONTROL Visual (predeterminado)]**.

   ![Cuadro de diálogo Crear actividad de Automated Personalization](/help/c-activities/t-automated-personalization/assets/ap_url-new.png)

   Si prefiere usar el Compositor de experiencias basadas en formularios, seleccione [!UICONTROL Formulario]. Consulte [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md) para obtener más información.

   >[!NOTE]
   >
   >Además del VEC y del Compositor de experiencias basadas en formularios, Target ofrece el VEC de aplicación de una sola página y el VEC para aplicaciones móviles. Para obtener más información sobre los distintos compositores, consulte [Experiencias y ofertas](/help/c-experiences/experiences.md).
   >
   >Para obtener información acerca de la solución de problemas del VEC, en caso de problemas, consulte [Solución de problemas del Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >La opción [!UICONTROL Elegir lugar de trabajo] de la ilustración anterior es una [función de Target Premium](/help/c-intro/intro.md). Su organización tiene una licencia de Target Standard si no ve esta opción.

1. (Condicional) Si es cliente de Target Premium, [elija un espacio de trabajo](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Compruebe o escriba la dirección URL de la actividad y haga clic en **[!UICONTROL Siguiente]**.

   >[!NOTE]
   >
   >[!DNL Target] no diferencia entre los protocolos URL ([!DNL https] y [!DNL http]). Esto quiere decir que tanto [!DNL `http://www.adobe.com`] como [!DNL `https://wwww.adobe.com`] coinciden.

   Se abre la página con la dirección URL especificada en el Compositor de experiencias visuales.

1. Para asignar un nombre a la actividad, haga clic en el campo Nombre y escriba el nombre de la actividad.

   ![Campo Nombre](/help/c-activities/t-automated-personalization/assets/ab_newname-new.png)

   No se permite usar los caracteres siguientes en el nombre de una actividad:

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

1. Modifique los elementos de página tal como se explica en [las opciones del Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

   Puede seleccionar varias imágenes a la vez desde el administrador de recursos. De este modo, puede ver rápidamente la página con cada una de las imágenes configuradas en la actividad. También puede editar fácilmente los elementos de texto en sus ofertas. Cuando edite un elemento, aparecen barras en ese elemento para indicar que lo ha cambiado.

1. Haga clic en **[!UICONTROL Gestionar contenido]** para configurar las combinaciones disponibles.

   ![Opción Administrar contenido](/help/c-activities/t-automated-personalization/assets/manage-content.png)

   Aparece un cuadro de diálogo con tres opciones en la parte superior de la pantalla: Experiencias, Ofertas y Grupos de exclusión.

   ![Cuadro de diálogo Administrar contenido](/help/c-activities/t-automated-personalization/assets/ap_content-new.png)

   >[!NOTE]
   >
   >Aunque se pueden crear hasta 30 000 experiencias en una actividad AP, el rendimiento de la actividad es mejor cuando se utilizan menos de 5000.

   La lista [!UICONTROL Experiencias] muestra cada parte de contenido seleccionada para la actividad y la ubicación que se le asigna.

   Puede excluir experiencias específicas pasando el puntero sobre la experiencia deseada y luego haciendo clic en el icono de exclusión.

   ![Icono Excluir al pasar el ratón por encima](/help/c-activities/t-automated-personalization/assets/icon-exclude.png)

   Puede excluir/incluir experiencias por lotes seleccionando la casilla de las experiencias relevantes y luego haciendo clic en el icono Excluir en la esquina superior derecha del cuadro de diálogo.

   ![Opciones de exclusión por lotes](/help/c-activities/t-automated-personalization/assets/batch-exclude.png)

   Puede filtrar esta vista de lista para ver solo actividades excluidas o incluidas haciendo clic en la lista desplegable **Estado**.

1. (Condicional) Haga clic en **[!UICONTROL Ofertas]** para seleccionar elementos de contenido y asignarlos a grupos de informes o para permitir que solo determinados visitantes vean determinadas ofertas con segmentación.

   Para obtener más información, consulte [Grupos de informes de ofertas en Personalización automatizada](/help/c-reports/offer-reporting-groups-in-automated-personalization.md#concept_194128C0B56B4B26AAB57DB49892960C).

   Utilice la lista [!UICONTROL Ubicación] para filtrar ofertas por ubicación. Utilice la lista [!UICONTROL Grupo de informes] para filtrar ofertas por grupos de informes. Ahora también puede usar la lista [!UICONTROL Grupo de informes] para filtrar por [!UICONTROL Ofertas no asignadas], de modo que puede asignar un grupo de informes a una oferta que no está actualmente asignada a ningún grupo de informes.

   Puede añadir experiencias específicas a un grupo de informes pasando el puntero sobre la oferta deseada y haciendo clic en el icono de la carpeta.

   ![Icono de carpeta al pasar el ratón por encima](/help/c-activities/t-automated-personalization/assets/icon-folder.png)

   Puede incluir experiencias en lote en un grupo de informes seleccionando la casilla de las experiencias relevantes y haciendo clic en el icono de la carpeta Grupo de informes, en la esquina superior derecha del cuadro de diálogo.

   ![Opciones del grupo de informes](/help/c-activities/t-automated-personalization/assets/report-group-options.png)

   Es importante comprender que los grupos de informes afectan a la forma en la que Target crea sus modelos. Como resultado, le recomendamos que use grupos de informes solo si planea reemplazar o agregar nuevas ofertas mientras la actividad está activa. Si se introduce una nueva oferta en una actividad en vivo, al poner la nueva oferta en un grupo con ofertas similares existentes, la máquina puede usar los datos ya recopilados en relación con las otras ofertas de su grupo para conocer la nueva oferta. Nunca debe colocar todas las ofertas en un solo grupo de informes.

   Para obtener información sobre la segmentación de una oferta para audiencias específicas, consulte [Ofertas PA de Target](/help/c-activities/t-automated-personalization/ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E).

1. (Condicional) Haga clic en **[!UICONTROL Grupos de exclusión]** para elegir cualquier combinación de elementos que desee excluir de la actividad.

   ![Pestaña Grupos de exclusión del cuadro de diálogo Administrar contenido](/help/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   Aunque puede crear hasta 30 000 experiencias en una prueba AP, el algoritmo funciona mejor cuando se usan menos de 10 000 experiencias distintas.

   Si actualmente no tiene grupos de exclusión incluidos en su actividad, haga clic en **Crear grupo de exclusión**. Puede filtrar para crear una lista que muestre solo las combinaciones que desea excluir. Asigne un nombre a su grupo de exclusión y haga clic en **Guardar**.

   Para editar un grupo de exclusión existente, desplace el cursor sobre el grupo que desea editar y luego haga clic en el icono del lápiz.

1. Haga clic en **[!UICONTROL Listo]** cuando haya terminado de configurar el contenido de su actividad.

1. El paso de **segmentación** le resultará familiar si ha utilizado otros tipos de actividad de Target. Aquí puede seleccionar una audiencia y especificar el porcentaje de visitantes que verán la experiencia de control haciendo clic en la lista desplegable **[!UICONTROL Asignación personalizada]**; a continuación, haga clic en **Siguiente**.

   La lista desplegable [!UICONTROL Asignación personalizada] le permite elegir entre las siguientes opciones:

   ![Lista desplegable Objetivo de asignación de tráfico](/help/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap.png)

   * **Evaluar el algoritmo de personalización (50/50):** si su objetivo es probar el algoritmo, utilice una división del 50/50 por ciento de los visitantes entre el control y el algoritmo seleccionado. Esta división proporciona la estimación más precisa del alza. Se sugiere utilizar con “experiencias aleatorias” como control.
   * **Maximización del tráfico de personalización (90/10):** si su objetivo es crear una actividad “siempre activada”, ponga el 10 % de los visitantes en el control a fin de asegurarse de que haya suficientes datos para que los algoritmos continúen aprendiendo a lo largo del tiempo. Tenga en cuenta que la compensación aquí es que, a cambio de personalizar una mayor proporción de su tráfico, tendrá menos precisión en la estimación del alza. Independientemente del objetivo, esta es la división de tráfico recomendada al usar una experiencia específica como control.
   * **Asignación personalizada:** divida manualmente el porcentaje como lo desee.

1. (Condicional) En la lista desplegable [!UICONTROL Control][, seleccione una experiencia específica para utilizarla como control](/help/c-activities/t-automated-personalization/experience-as-control.md) o seleccione [!UICONTROL Experiencia aleatoria.]

   La experiencia de control ofrece una comparación para determinar cuánta alza se proporciona con la prueba automatizada.

   Personalización automatizada siempre mide el rendimiento con respecto al grupo de control. Lo mejor es colocar al menos el 10 % de los participantes en el grupo de control. Si su objetivo es probar si el algoritmo de personalización en los datos que se ofrece tiene mejor rendimiento que la no personalización (es decir, el control servido aleatoriamente), entonces una división de tráfico del 50/50 por ciento entre el control y el algoritmo de personalización sería el más rápido y la forma más precisa para lograr este objetivo. Si desea maximizar la cantidad de tráfico que se personaliza y le preocupa menos comprender el alza exacta que está generando su actividad, entonces una división de tráfico del 10/90 por ciento entre el control y el algoritmo de personalización sería la manera más rápida y precisa para alcanzar esta meta.

   >[!NOTE]
   >
   >En las actividades de Personalización automatizada, los criterios de entrada (segmentación por URL, reglas de plantilla y objetivo de audiencia) se evalúan en cada solicitud. En las versiones anteriores, los criterios de entrada se evaluaban una vez por sesión.

1. Haga clic en **[!UICONTROL Siguiente]** para mostrar la página de **[!UICONTROL Objetivos y configuración]**.
1. Configure la actividad con las siguientes opciones y, a continuación, haga clic en **[!UICONTROL Guardar y cerrar]**.

   | Configuración | Descripción |
   |--- |--- |
   | Nombre | Asigne un nombre a la actividad. Asigne a la actividad un nombre que sea lo suficientemente descriptivo como para que los integrantes del equipo puedan reconocerlo en la lista Actividades.  Consulte la tabla anterior para ver los caracteres que no están permitidos en el nombre de la actividad. |
   | Objetivo | (Opcional) Escriba el objetivo de la prueba. El objetivo le ayuda a recordar la finalidad de la actividad. |
   | Prioridad | La interfaz de usuario y las opciones de Prioridad varían en función de la configuración. Puede usar la configuración heredada de bajo, medio o alto, o habilitar prioridades específicas de 0 a 999.<br>La prioridad se utiliza si se asignan varias actividades a la misma ubicación con la misma audiencia. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta.<br>Si esta opción no está activada en [!UICONTROL Administración] > [!UICONTROL Sistema de informes] (opción predeterminada), especifique una prioridad: Bajo, Medio o Alto.<br>Para habilitar las prioridades específicas, haga clic en [!UICONTROL Administración] > [!UICONTROL Sistema de informes]y, a continuación, coloque la opción [!UICONTROL Activar prioridades] específicas en la posición &quot;Activado&quot;.<br>Si esta opción está habilitada, indique un valor entre 0 y 999:<ul><li>0 = Bajo</li><li>999 = Alto</li></ul>En las actividades creadas en versiones anteriores de Target Standard/Premium, el nivel bajo de prioridad se convierte en 0; el medio, en 5; y el alto, en 10. Si lo necesita, puede ajustar estos valores.<br>**Nota:** para deshabilitar esta opción después de usar las prioridades específicas, hay que volver a fijar todas las prioridades en 0, 5 y 10. |
   | Duración | Defina las fechas de inicio y finalización de la actividad. |
   | Objetivo de optimización | Especifique el objetivo de optimización, que consta de dos parámetros:<ul><li>Qué quiere medir con la actividad</li><li>La acción realizada por el participante de una actividad que muestra que se ha logrado el objetivo.</li></ul>Puede elegir nombrar el objetivo de optimización seleccionando los tres puntos que hay a la derecha de Mi objetivo principal. Las actividades de Personalización automatizada pueden medir la conversión, los ingresos por visitante y el valor de pedido promedio. La conversión se puede conseguir visualizando una página o visualizando un mbox. También se realiza un seguimiento de los clics.<br>El objetivo principal también se convierte en la métrica de modelado, que el sistema de modelado utiliza para calcular el éxito de la experiencia.<br>Los visitantes pueden continuar en la actividad con fines de seguimiento después de alcanzar el objetivo de modelado. Por ejemplo, a menudo se usa una actividad de Personalización automatizada para mejorar las tasas de clics, y eso se establece en el objetivo de modelado. Sin embargo, es importante ver cómo las tasas de clics incrementadas llevan a conversión final, por lo que resulta esencial el seguimiento a través de la conversión final.<br>Dispone de dependencia respecto a varias métricas y tiene la posibilidad de elegir si una métrica debe alcanzarse o no para que su contador aumente.<br>Debe definir ambas (o varias) métricas de éxito antes de poder hacer una dependiente de la otra.<br>La opción Añadir dependencia permite que la métrica de éxito aumente si se alcanza otra métrica de éxito (o todo lo contrario, si no se alcanza).<br>Para agregar una dependencia:<ol><li>Después de agregar métricas adicionales, haga clic en [!UICONTROL Configuración avanzada] en el menú de tres puntos que hay a la derecha de Objetivo adicional.</li><li>Haga clic en la opción [!UICONTROL Agregar dependencia] en la parte inferior de la sección [!UICONTROL Configuración de informes].</li><li>Arrastre y suelte las métricas deseadas del panel izquierdo al panel derecho y, a continuación, haga clic en [!UICONTROL Alcanzado] para alternar el valor entre [!UICONTROL Alcanzado] y [!UICONTROL No alcanzado]</li></ol>Puede editar o eliminar dependencias después de añadirlas. |
   | Métrica de conversión | De forma predeterminada, la métrica de conversión es la misma que la métrica de objetivo de optimización. Sin embargo, puede definir una métrica de conversión independiente desmarcando la opción [!UICONTROL Igual que el objetivo de optimización]. |
   | Métricas adicionales | Añada cualquier métrica de informe adicional que quiera usar. Puede agregar métricas de conversión, participación o ingresos.<br>**Nota:** no se puede utilizar la métrica de compromiso como métrica adicional. Es posible que la interfaz de usuario le permita seleccionar la métrica de compromiso, pero los datos de los informes no serán precisos. |
   | Audiencias para los informes | Añada audiencias para habilitar el filtrado por audiencias en los informes. De manera predeterminada, el informe muestra los resultados para todos los visitantes que cumplen los criterios. Añada audiencias para filtrar los resultados para subconjuntos de visitantes más específicos.<br>**Nota:** a diferencia de otros tipos de actividades, la Personalización automatizada no puede usar Adobe Analytics como fuente de informes. |
   | Notas | Escriba la información sobre la actividad que sea útil tener disponible para el equipo. El panel Notas se puede redimensionar. |

   Tenga en cuenta que cuando nombra o renombra una métrica, no se permiten los siguientes caracteres:

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

Después de hacer clic en **[!UICONTROL Crear]** aparece el Resumen de actividad. Haga clic en **Vista previa de las experiencias** para previsualizar el aspecto de las experiencias cuando se entreguen. Aparece un elemento emergente que puede usar para ver y compartir vínculos a sus experiencias AP en su sitio para obtener una “auténtica vista previa” de las experiencias fuera del Compositor de experiencias visuales de Target. Debe compartir los vínculos del mensaje para compartir la vista previa. Hacer clic en un vínculo y luego copiar la dirección URL directamente desde la página no funcionará porque la dirección URL contiene un parámetro que solo muestra la página correctamente cuando tiene acceso a la página desde el vínculo en el mensaje.

Para obtener información sobre los informes, consulte [Informes de Personalización automatizada](/help/c-reports/reports-ap.md#concept_C02BAFC922114A44846998FD956E345A).
