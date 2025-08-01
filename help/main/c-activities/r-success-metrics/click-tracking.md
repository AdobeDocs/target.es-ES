---
keywords: Rastreo de clics;rastrear clics;clics;AppMeasurement
description: Descubra cómo  [!DNL Adobe Target]  le permite rastrear clics en cualquier elemento como una métrica de éxito.
title: ¿Qué es el rastreo de clics?
feature: Success Metrics
exl-id: 9181424b-179e-49fc-b760-b764a0c3458a
source-git-commit: 43d2484e57b1e2d292cf65c041fb9f5f49b2084c
workflow-type: tm+mt
source-wordcount: '858'
ht-degree: 75%

---

# Rastreo de clics

[!DNL Adobe Target] le permite rastrear clics en cualquier elemento como una métrica de éxito. El rastreo de clics hace referencia al proceso de monitorización y registro de interacciones del usuario, específicamente los clics, en elementos dentro de una página web o experiencia. Esto es una parte clave de la medición de la participación y el rendimiento en pruebas A/B, pruebas multivariable y actividades de personalización.

>[!NOTE]
>
>El rastreo de clics no se admite en la solicitud global de [!DNL Target] cuando se utiliza como ubicación en una actividad basada en formularios.

## Configuración del rastreo de clics {#section_5540C5A533114E57BAE022A600B02E72}

1. Al establecer sus metas en la página [!UICONTROL Goals & Settings] de su actividad, seleccione la métrica de éxito **[!UICONTROL Conversion]**.
1. Para la acción, seleccione **[!UICONTROL Clicked an element]** y luego haga clic en **[!UICONTROL Select elements]**.

   Su página se abre en [!UICONTROL Visual Experience Composer] (VEC).

1. Seleccione los elementos que desee rastrear.

   Consulte la sección *Consideraciones*, a continuación, para ver sugerencias sobre la selección de elementos.

1. Haga clic en **[!UICONTROL Done]** en la parte superior de la pantalla para guardar las selecciones.

Cuando el participante de una actividad hace clic en un elemento seleccionado, ese clic se cuenta como una conversión.

## Panel Elementos seleccionados {#selected-elements}

Para las actividades [!UICONTROL A/B Test], [!UICONTROL Experience Targeting] (XT), [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Multivariate Test] (MVT), un panel [!UICONTROL Selected Elements] enumera los elementos seleccionados para el rastreo de clics en el lado izquierdo.

![Panel Elementos seleccionados](/help/main/c-activities/r-success-metrics/assets/selected-elements.png)

Existen varias acciones que se pueden aplicar al hacer clic en un elemento del panel [!UICONTROL Tracked Components]. La siguiente tabla describe cada acción que se puede realizar en un elemento:

| Acción | Descripción |
| --- | --- |
| [!UICONTROL Tracked actions] | Muestra la acción del elemento. |
| [!UICONTROL CSS selector] | Permite editar el selector de CSS. |
| [!DNL Delete] | Elimina el elemento. |

### Agregar elemento

Si ya conoce la ruta DOM al selector, puede agregarla manualmente si hace clic en el icono [!UICONTROL Add Component] en la parte superior del panel.

## Consideraciones {#considerations}

Existen varias cuestiones que se deben tener en cuenta al seleccionar elementos:

* La función de ruta DOM está disponible al configurar el rastreo de clics. Al hacer clic en un elemento de la página, aparece el menú de opciones de VEC. Además, la ruta DOM correspondiente aparece en la parte inferior de la página. Puede utilizar la ruta DOM para ver rápidamente información sobre el elemento seleccionado (tipo, ID y clase) y subir o bajar por la ruta DOM para seleccionar el elemento deseado.

  Del mismo modo que cuando se crean experiencias en el paso 1 del flujo de trabajo de creación de actividades, el selector de ruta DOM en la parte inferior de la página le permite elegir un elemento. Al seleccionar un elemento desde la ruta DOM, el elemento correspondiente del VEC se muestra como &quot;Seleccionado&quot;. Para anular la selección de un elemento, vuelva a hacer clic en dicho elemento en el selector de rutas DOM o haga clic en el cuadro “Seleccionado” dentro del VEC.

  Para obtener más información, consulte [Desplazamiento por elementos utilizando la ruta DOM](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) en *Opciones del Compositor de experiencias visuales*.

* Puede buscar una página diferente para rastrear clics en una página donde podría no estar modificando contenido. Se debe incluir esta página diferente en la actividad que usa la [característica multipágina](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48) y se debe implementar [!DNL at.js] en ella.
* Si selecciona más de un elemento, si un participante hace clic en cualquiera de los elementos elegidos, se cuenta el clic. Para contar cada elemento por separado, configure métricas de éxito individuales para cualquier elemento. Para contar un elemento haciendo clic en varios elementos de una página, edite el selector de elementos CSS para que coincida con varios elementos.
* Asegúrese de seleccionar el nivel de elemento que desee rastrear. Por ejemplo, al especificar un botón, asegúrese de seleccionar el vínculo y no el texto del botón.
* Los eventos de clic se envían a [!DNL Target] en la misma página que el clic.
* Si la métrica de rastreo de clics es la métrica objetivo de una actividad [!UICONTROL Analytics for Target] (A4T), el visitante debe hacer clic en este elemento en un plazo de 60 segundos desde la carga de la página para que la métrica se rastree.
* El rastreo de clics no funciona en elementos que incluyen caracteres de escape en los selectores, incluyendo los siguientes:

  | Carácter | Descripción |
  |---|---|
  | # | Signo de número o hash |
  | : | Dos puntos |
  | . | Periodo |
  | $ | Símbolo del dólar |
  | `[ ]` | Corchetes |

* Si utiliza el rastreo de clics de [!DNL at.js] y también [!DNL Analytics] AppMeasurement, el rastreo de clics de [!DNL at.js] cancela cualquier otro controlador de eventos de clic. Como resultado, el controlador de eventos de AppMeasurement nunca llega a ejecutarse.

  [!DNL at.js] tiene un controlador especial para el rastreo de clics cuando el elemento subyacente es una etiqueta `A` (vínculo) o `FORM`.

  [!DNL at.js] ejecuta los siguientes pasos cuando el evento de rastreo de clics se adjunta una etiqueta `A`A (vínculo) o `FORM`:

   1. Invocar..`event.preventDefault()`

   1. Active la solicitud de [!DNL Target].

   1. En caso de que la solicitud de [!DNL Target] se complete correctamente o produzca una llamada de retorno de error, ejecute el comportamiento predeterminado:

      * Etiqueta`A` (vínculo): el comportamiento predeterminado es ir a la URL definida por el atributo HREF.
      * Etiqueta `FORM`: el comportamiento predeterminado es enviar el formulario.

  Este comportamiento predeterminado podría interferir en el rastreo de clics de [!DNL Analytics]. Si utiliza [!DNL Analytics], se recomienda confiar en [!DNL Analytics] para el rastreo de clics en vez de en [!DNL Target].

* El rastreo de clics no se registra en páginas en las que la URL de la página y de la actividad pertenecen a propiedades diferentes. Los permisos de usuario de Enterprise son una función de [!DNL Target Premium]. Para obtener más información, consulte [Permisos de usuario de Enterprise](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

* Las métricas de seguimiento de clics no están vinculadas a ninguna experiencia específica de una actividad.

* Utilice audiencias si es necesario restringir el ámbito de las métricas de rastreo de clics.

* Varias actividades pueden definir una métrica de rastreo de clics para el mismo selector. Si es así, cuando un visitante cumple los requisitos para una de esas actividades y hace clic en ese selector, la métrica de rastreo de clics aumenta para todas las actividades asociadas para las que el visitante cumple los requisitos.

## Vídeo de capacitación {#section_36607204DAE146E3B8E2C609D244EDB1}

Este vídeo contiene información sobre la creación de métricas de éxito del rastreo de clics.

* Qué son las métricas de “objetivo”
* Comprender y generar las métricas [!UICONTROL Conversion], [!UICONTROL Revenue] y [!UICONTROL Engagement]
* Compilar una métrica para el rastreo de clics

>[!VIDEO](https://video.tv.adobe.com/v/17380)
