---
description: Target permite rastrear clics en cualquier elemento como una métrica de éxito.
keywords: Rastreo de clics;rastrear clics;clics;AppMeasurement
seo-description: Target permite rastrear clics en cualquier elemento como una métrica de éxito.
seo-title: Rastreo de clics
solution: Target
subtopic: Primeros pasos
title: Rastreo de clics
topic: Standard
uuid: 4a8fbb23-93d8-49f3-aca3-dbbdd6da0178
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Rastreo de clics{#click-tracking}

Target permite rastrear clics en cualquier elemento como una métrica de éxito.

>[!NOTE]
>
>El rastreo de clics no se admite en el mbox global de Target cuando se utiliza como ubicación en una actividad basada en formularios.

## Configuración del rastreo de clics {#section_5540C5A533114E57BAE022A600B02E72}

1. Al establecer los objetivos en la página [!UICONTROL Objetivos y configuración] para su actividad, seleccione la métrica de conversión **[!UICONTROL Conversión].**
1. Para la acción, seleccione **[!UICONTROL Se hizo clic en un elemento]** y luego haga clic en **[!UICONTROL Seleccionar elementos]**.

   La página se abre en el [!UICONTROL Compositor de experiencias visuales] (VEC).

1. Seleccione los elementos que desee rastrear.

   Consulte la sección Consideraciones, a continuación, para ver sugerencias sobre la selección de elementos.

1. Haga clic en la marca de verificación que aparece en la parte superior de la pantalla para guardar los elementos seleccionados.

Cuando el participante de una actividad hace clic en un elemento seleccionado, ese clic se cuenta como una conversión.

## Consideraciones {#considerations}

Existen varias cuestiones que se deben tener en cuenta al seleccionar elementos:

* La función de ruta DOM está disponible al configurar el rastreo de clics. Al hacer clic en un elemento de la página, aparece el menú de opciones de VEC. Además, la ruta DOM correspondiente aparece en la parte inferior de la página. Puede utilizar la ruta DOM para ver rápidamente información sobre el elemento seleccionado (tipo, ID y clase) y subir o bajar por la ruta DOM para seleccionar el elemento deseado.

   ![Ilustración de la ruta DOM](/help/c-activities/r-success-metrics/assets/click-tracking-dom.png)

   Del mismo modo que cuando se crean experiencias en el paso 1 del flujo de trabajo de creación de actividad, el selector de ruta DOM en la parte inferior de la página le permite elegir un elemento. Al seleccionar un elemento desde la ruta DOM, el elemento correspondiente del VEC se muestra como &quot;Seleccionado&quot;. Para anular la selección de un elemento seleccionado, vuelva a hacer clic en dicho elemento en el selector de rutas DOM o haga clic en el cuadro &quot;Seleccionado&quot; dentro del VEC.

   Para obtener más información, consulte [Desplazamiento por elementos utilizando la ruta DOM](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) en *Opciones del Compositor de experiencias visuales*.

* Puede buscar una página diferente para rastrear clics en una página donde podría no estar modificando contenido. Esta página diferente debe incluirse en la actividad que usa la  [función multipágina](../../c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48), y debe tener implementada [!DNL at.js] o [!DNL mbox.js].
* Si selecciona más de un elemento, si un participante hace clic en cualquiera de los elementos elegidos, se cuenta el clic. Para contar cada elemento por separado, configure métricas de éxito individuales para cualquier elemento.
* Asegúrese de seleccionar el nivel de elemento que desee rastrear. Por ejemplo, al especificar un botón, asegúrese de seleccionar el vínculo y no el texto del botón.
* Los eventos de clic se envían a [!DNL Target] en la misma página que el clic.
* Si la métrica de rastreo de clics es la métrica objetivo de una actividad A4T, el visitante debe hacer clic en este elemento en un plazo de 60 segundos desde la carga de la página para que la métrica sea rastreada.
* El rastreo de clics no funciona en elementos que incluyen caracteres de escape en los selectores, incluyendo los siguientes:

   | Carácter | Descripción |
   |---|---|
   | # | Signo de número  o almohadilla |
   | : | Dos puntos |
   | . | Periodo |
   | $ | Símbolo del dólar |
   | [ ] | Corchetes |

* Si utiliza el rastreo de clics de [!DNL at.js] y también Analytics AppMeasurement, el rastreo de clics de [!DNL at.js] cancela cualquier otro controlador de eventos de clic. Como resultado, el controlador de eventos de AppMeasurement nunca llega a ejecutarse.

   [!DNL at.js] tiene un controlador especial para el rastreo de clics cuando el elemento subyacente es una etiqueta `A` (vínculo) o `FORM`.

   [!DNL at.js] ejecuta los siguientes pasos cuando el evento de rastreo de clics se adjunta una etiqueta `A`A (vínculo) o `FORM`:

   1. Invocar. `event.preventDefault()`

   1. Activar la solicitud de Target.

   1. En caso de que la solicitud de Target se complete correctamente o produzca una llamada de retorno de error, ejecutar el comportamiento predeterminado:

      * Etiqueta`A` (vínculo): el comportamiento predeterminado es ir a la URL definida por el atributo HREF.
      * Etiqueta `FORM`: el comportamiento predeterminado es enviar el formulario.
   Este comportamiento predeterminado podría interferir en el rastreo de clics de Analytics. Si utiliza Analytics, se recomienda confiar en Analytics para el rastreo de clics en vez de en Target.

* El rastreo de clics no se registra en páginas en las que la URL de la página y de la actividad pertenecen a propiedades diferentes. Los permisos de usuario de Enterprise son una función de Target Premium. Para obtener más información, consulte [Permisos de usuario de Enterprise](/help/administrating-target/c-user-management/property-channel/property-channel.md).

## Vídeo de capacitación {#section_36607204DAE146E3B8E2C609D244EDB1}

Este vídeo contiene información sobre la creación de métricas de éxito del rastreo de clics.

* Qué son las métricas de “objetivo”
* Qué son y cómo compilar las métricas de conversión, ingresos y participación
* Compilar una métrica para el rastreo de clics

>[!VIDEO](https://video.tv.adobe.com/v/17380)