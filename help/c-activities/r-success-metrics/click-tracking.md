---
keywords: Rastreo de clics;rastrear clics;clics;AppMeasurement
description: Descubra cómo [!DNL Adobe Target] le permite rastrear clics en cualquier elemento como una métrica de éxito.
title: ¿Qué es el rastreo de clics?
feature: Success Metrics
exl-id: 9181424b-179e-49fc-b760-b764a0c3458a
source-git-commit: f4b490c489427130e78d84b573b2d290a8a60585
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 60%

---

# Rastreo de clics

[!DNL Adobe Target] permite rastrear clics en cualquier elemento como una métrica de éxito.

>[!NOTE]
>
>El rastreo de clics no es compatible con la solicitud global [!DNL Target] cuando se utiliza como ubicación en una actividad basada en formularios.

## Configuración del rastreo de clics {#section_5540C5A533114E57BAE022A600B02E72}

1. Al establecer los objetivos en la página [!UICONTROL Objetivos y configuración] para su actividad, seleccione la métrica de conversión **[!UICONTROL Conversión]**.
1. Para la acción, seleccione **[!UICONTROL Se hizo clic en un elemento]** y luego haga clic en **[!UICONTROL Seleccionar elementos]**.

   La página se abre en el [!UICONTROL Compositor de experiencias visuales] (VEC).

1. Seleccione los elementos que desee rastrear.

   Consulte la sección *Consideraciones*, a continuación, para ver sugerencias sobre la selección de elementos.

1. Haga clic en **[!UICONTROL Save]** en la parte superior de la pantalla para guardar las selecciones.

Cuando el participante de una actividad hace clic en un elemento seleccionado, ese clic se cuenta como una conversión.

## Panel Elementos seleccionados {#selected-elements}

En las actividades [!UICONTROL Prueba A/B], [!UICONTROL Segmentación de experiencias] (XT), [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Prueba multivariable] (MVT), un panel [!UICONTROL Elementos seleccionados] enumera los elementos seleccionados para rastreo de clics en el lado derecho.

![Panel Elementos seleccionados](/help/c-activities/r-success-metrics/assets/selected-elements.png)

Existen varias acciones que se pueden aplicar al pasar el ratón por encima de un elemento del panel [!UICONTROL Elementos seleccionados]. La siguiente tabla describe cada acción que se puede realizar en un elemento:

| Acción | Descripción |
| --- | --- |
| Información | Muestra el tipo de elemento y la ruta DOM completa al selector. |
| Editar | Permite editar el selector de CSS. |
| Eliminar | Elimina el elemento. |

### Agregar elemento

Si ya conoce la ruta DOM al selector, puede agregarla manualmente haciendo clic en el icono de signo más en la parte superior del panel.

![Icono Agregar elemento](/help/c-activities/r-success-metrics/assets/add-element.png)

### Elemento emergente Elementos seleccionados

Después de seleccionar varios elementos para el rastreo de clics, puede hacer clic en el vínculo [!UICONTROL Elementos seleccionados] en el paso [!UICONTROL Objetivos y configuración] de la actividad para ver la lista completa de elementos seleccionados para el rastreo de clics. La lista contiene la ruta DOM completa para el elemento, que le ayudará a validar que el elemento seleccionado se utilizará para el rastreo de clics.

![Vínculo Elementos seleccionados](/help/c-activities/r-success-metrics/assets/elements-selected-link.png)

## Consideraciones {#considerations}

Existen varias cuestiones que se deben tener en cuenta al seleccionar elementos:

* La función de ruta DOM está disponible al configurar el rastreo de clics. Al hacer clic en un elemento de la página, aparece el menú de opciones de VEC. Además, la ruta DOM correspondiente aparece en la parte inferior de la página. Puede utilizar la ruta DOM para ver rápidamente información sobre el elemento seleccionado (tipo, ID y clase) y subir o bajar por la ruta DOM para seleccionar el elemento deseado.

   ![Ilustración de la ruta DOM](/help/c-activities/r-success-metrics/assets/click-tracking-dom.png)

   Al igual que cuando se crean experiencias en el paso 1 del flujo de trabajo de creación de actividades, el selector de rutas DOM en la parte inferior de la página le permite elegir un elemento. Al seleccionar un elemento desde la ruta DOM, el elemento correspondiente del VEC se muestra como &quot;Seleccionado&quot;. Para anular la selección de un elemento seleccionado, puede volver a hacer clic en el elemento en el selector de rutas DOM o hacer clic en el cuadro &quot;Seleccionado&quot; dentro del VEC.

   Para obtener más información, consulte [Desplazamiento por elementos utilizando la ruta DOM](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) en *Opciones del Compositor de experiencias visuales*.

* Puede buscar una página diferente para rastrear clics en una página donde podría no estar modificando contenido. Esta página diferente debe incluirse en la actividad que usa la   [función multipágina ](/help/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48) y  [!DNL at.js] debe implementarse en ella.
* Si selecciona más de un elemento, si un participante hace clic en cualquiera de los elementos elegidos, se cuenta el clic. Para contar cada elemento por separado, configure métricas de éxito individuales para cualquier elemento. Para contar un elemento haciendo clic en varios elementos de una página, edite el selector de elementos CSS para que coincida con varios elementos.
* Asegúrese de seleccionar el nivel de elemento que desee rastrear. Por ejemplo, al especificar un botón, asegúrese de seleccionar el vínculo y no el texto del botón.
* Los eventos de clic se envían a [!DNL Target] en la misma página que el clic.
* Si la métrica de rastreo de clics es la métrica Objetivo de una actividad [!UICONTROL Analytics for Target] (A4T), el visitante debe hacer clic en este elemento en los 60 segundos posteriores a la carga de la página para que la métrica realice un seguimiento.
* El rastreo de clics no funciona en elementos que incluyen caracteres de escape en los selectores, incluyendo los siguientes:

   | Carácter | Descripción |
   |---|---|
   | # | Signo de número  o almohadilla |
   | : | Dos puntos |
   | . | Periodo |
   | $ | Símbolo del dólar |
   | `[ ]` | Corchetes |

* Si utiliza el rastreo de clics de [!DNL at.js][!DNL Analytics] y también AppMeasurement, el rastreo de clics de [!DNL at.js] cancela cualquier otro controlador de eventos de clic. Como resultado, el controlador de eventos de AppMeasurement nunca llega a ejecutarse.

   [!DNL at.js] tiene un controlador especial para el rastreo de clics cuando el elemento subyacente es una etiqueta `A` (vínculo) o `FORM`.

   [!DNL at.js] ejecuta los siguientes pasos cuando el evento de rastreo de clics se adjunta una etiqueta `A`A (vínculo) o `FORM`:

   1. Invocar..`event.preventDefault()`

   1. Active la solicitud [!DNL Target].

   1. En caso de que la solicitud [!DNL Target] se complete correctamente o produzca una llamada de retorno de error, ejecute el comportamiento predeterminado:

      * Etiqueta`A` (vínculo): el comportamiento predeterminado es ir a la URL definida por el atributo HREF.
      * Etiqueta `FORM`: el comportamiento predeterminado es enviar el formulario.

   Este comportamiento predeterminado podría interferir con el rastreo de clics de [!DNL Analytics]. Si utiliza [!DNL Analytics], debe confiar en [!DNL Analytics] para el rastreo de clics en lugar de en [!DNL Target].

* El rastreo de clics no se registra en páginas en las que la URL de la página y de la actividad pertenecen a propiedades diferentes. Los permisos de usuario de Enterprise son una función [!DNL Target Premium]. Para obtener más información, consulte [Permisos de usuario de Enterprise](/help/administrating-target/c-user-management/property-channel/property-channel.md).

* Las métricas de seguimiento de clics no están vinculadas a ninguna experiencia específica de una actividad.

* Utilice audiencias si es necesario restringir el alcance de las métricas de rastreo de clics.

* Varias actividades pueden definir una métrica de rastreo de clics para el mismo selector. Si es así, cuando un visitante cumple los requisitos para una de esas actividades y hace clic en ese selector, la métrica rastreo de clics aumenta para todas las actividades asociadas para las que el visitante cumple los requisitos.

## Vídeo de capacitación {#section_36607204DAE146E3B8E2C609D244EDB1}

Este vídeo contiene información sobre la creación de métricas de éxito del rastreo de clics.

* Qué son las métricas de “objetivo”
* Comprender y crear métricas de [!UICONTROL Conversión], [!UICONTROL Ingresos] y [!UICONTROL Participación]
* Compilar una métrica para el rastreo de clics

>[!VIDEO](https://video.tv.adobe.com/v/17380)
