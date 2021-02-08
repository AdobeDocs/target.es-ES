---
keywords: crear experiencia;crear;experiencia;prioridad;audiencia;experiencia;compositor de experiencias visuales
description: Descubra cómo usar el Compositor de experiencias visuales (VEC) de Adobe Target para crear y editar experiencias en la página en una actividad de segmentación de experiencias (XT).
title: ¿Cómo se crean experiencias en una Actividad de segmentación de experiencias?
feature: Experience Targeting
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '986'
ht-degree: 87%

---


# Crear experiencia en actividades de segmentación de experiencias (XT)

El [!UICONTROL Compositor de experiencias visuales] (VEC) de [!DNL Adobe Target] proporciona una interfaz visual para editar las experiencias en la página en una actividad [!UICONTROL Segmentación de experiencias] (XT).

1. Seleccione los elementos que quiera cambiar y realice los cambios necesarios.

   Al [crear una actividad de XT](/help/c-activities/t-experience-target/t-xt-create/xt-create.md), el paso uno del flujo de trabajo guiado de tres partes ([!UICONTROL Experiencias]) muestra la [!UICONTROL Experiencia A] predeterminada con una audiencia de [!UICONTROL Todos los visitantes].

   ![Audiencia de todos los visitantes](/help/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   Los cambios que realice ahora se aplican a la Experiencia A. En un paso inferior, haga clic en **[!UICONTROL Añadir segmentación de experiencias]** para crear experiencias adicionales.

   Al desplazar el cursor sobre los elementos de la página, estos se resaltarán. Los elementos resaltados se pueden modificar con el VEC. Para obtener una lista de las acciones que se pueden realizar en un elemento para cambiar la experiencia, consulte [Opciones del Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

   Si creó una solicitud [!DNL Target] en la página mediante [!DNL Target Classic], esa solicitud [!DNL Target] aparece como un elemento que muestra el nombre de la solicitud y se puede modificar como cualquier otro elemento.

   >[!NOTE]
   >
   >De manera predeterminada, el VEC no permite realizar cambios en elementos que contengan JavaScript, como banners giratorios. Es posible deshabilitar JavaScript para alterar esos elementos mediante el VEC.

1. Para crear experiencias adicionales, haga clic en **[!UICONTROL Añadir Segmentación de experiencias]**.

   ![Añadir vínculo de Segmentación de experiencias](/help/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   Se abre el cuadro de diálogo [!UICONTROL Seleccionar audiencia]. Si va a segmentar una experiencia a una audiencia, debe seleccionar la audiencia antes de añadir la experiencia.

   La biblioteca de audiencias contiene las audiencias que se han definido anteriormente, entre las que se incluyen algunas audiencias comunes predefinidas como parte de [!DNL Target]. Puede seleccionar una audiencia de la biblioteca o [crear una audiencia nueva](/help/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271).

   >[!NOTE]
   >
   >Además de seleccionar una audiencia existente, puede combinar varias audiencias para crear audiencias combinadas específicas en lugar de crear una nueva. Para obtener más información, consulte [Combinar varias audiencias](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

   Al crear una audiencia, puede seleccionar una ubicación y especificar los parámetros de dicha ubicación. En [!UICONTROL Personalizado] (Crear Audiencia > Añadir regla > Personalizado), seleccione la ubicación y luego especifique los parámetros deseados.

   >[!NOTE]
   >
   >Las audiencias se importan automáticamente en segundo plano cuando abre la lista de audiencias y las audiencias importadas tienen más de diez minutos de antigüedad.

1. Seleccione una o varias audiencias para segmentar con la experiencia y, a continuación, haga clic en **[!UICONTROL Listo]**.

   ![Experiencia B](/help/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   Verá que la Experiencia B ahora aparece en la ilustración anterior y esta experiencia está dirigida a la audiencia de Visitantes de EE. UU.

1. Seleccione los elementos que desee cambiar para esta experiencia y realice los cambios necesarios, como se explica en el paso 1.

1. Repita los pasos anteriores para crear más experiencias segmentadas, según sea necesario.

1. Haga clic en **[!UICONTROL Siguiente]** cuando termine de diseñar las experiencias.

   Se muestra el diagrama de actividad:

   ![Diagrama de segmentación de XT](/help/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

   >[!NOTE]
   >
   >Si entrega una imagen desde un origen distinto a la página principal (por ejemplo, una imagen alojada en `akamai.net` y entregada en `adobe.com`), dicha imagen no se mostrará en la miniatura de la página mostrada en el diagrama de flujo.

1. (Condicional) Arrastre y suelte una pareja de audiencia/experiencia mientras cuando cree o edite actividades XT para colocar las parejas en el orden deseado.

   Las experiencias de los visitantes se evalúan en orden, de arriba abajo.

   ![Mover experiencias](/help/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   [!UICONTROL La segmentación de experiencias supone que ese orden importa. ] Si un visitante encaja en el primer par de audiencia/experiencia, se le sirve la primera experiencia.

   Por ejemplo, suponga que no es consciente de que el orden importa al crear una actividad XT. Más adelante repara, durante las pruebas, que los visitantes que creía que encajarían en las experiencias B o C acaban en la experiencia A. Podría deberse a que las audiencias no son mutuamente excluyentes y no están situadas en el orden apropiado (por ejemplo, experiencia A = Estados Unidos, experiencia B = San Francisco, experiencia C = California). En este escenario, todos los usuarios de Estados Unidos entrarán en la experiencia A, aunque se encuentren en San Francisco o alguna otra parte de California. Puede reordenar los pares de audiencia/experiencia de más restrictivo a menos restrictivo (San Francisco > California > Estados Unidos) sin necesidad de reconstruir toda la actividad.

   Si tiene una audiencia de [!UICONTROL Todos los visitantes], compruebe que no sea la primera audiencia en el diagrama. Se puede utilizar una experiencia segmentada a “Todos los visitantes” como la última experiencia de la actividad de segmentación de experiencias para “captar” a los visitantes que no han participado de otras experiencias.

## Cambiar el nombre o editar una experiencia

Puede hacer clic en el icono [!UICONTROL Editar] (tres puntos verticales) de una experiencia en una actividad de segmentación de experiencias (XT) y elegir de las siguientes opciones, según sea necesario:

* Cambiar nombre
* Editar

![Opciones de Cambiar nombre y editar](/help/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## Eliminar una experiencia

En la página **[!UICONTROL Experiencias]** (el primer paso del flujo de trabajo guiado de tres pasos), haga clic en las tres elipses verticales > **[!UICONTROL Eliminar]**.

![Eliminar experiencia](/help/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## Duplicar experiencias

Puede copiar una experiencia en una actividad de XT y así realizar cambios menores sin tener que volver a crear la experiencia desde cero.

En la página **[!UICONTROL Experiencias]** (el primer paso del flujo de trabajo guiado de tres pasos), haga clic en las tres elipses verticales > **[!UICONTROL Duplicar]**.

![Duplicar experiencia](/help/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

## Vídeos de formación:

Los siguientes vídeos contienen más información sobre los conceptos mencionados en este artículo.

### De pruebas A/B a segmentación de experiencias

Este vídeo describe cómo se llevan las pruebas A/B al siguiente nivel con Segmentación de experiencias (XT).

* Describe el flujo de trabajo guiado de tres pasos para la configuración de una actividad XT
* Describe cómo se entrega contenido dependiente de la ubicación a audiencias situadas en distintas zonas geográficas
* Describe cómo se reordenan las experiencias para asegurar que cada contenido se envíe a la audiencia correcta

>[!VIDEO](https://video.tv.adobe.com/v/22418/)

### Tipos de actividad (9:03)

En este vídeo se describen los tipos de actividades disponibles en Target Standard/Premium. La segmentación de experiencias se describe a partir del minuto 5:15.

* Describe los tipos de actividades incluidas en [!DNL Adobe Target]
* Seleccionar el tipo de actividad adecuado para lograr los objetivos
* Describir el flujo de trabajo guiado de tres pasos que sirve para todos los tipos de actividad

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### Uso del Compositor de experiencias visuales

El siguiente vídeo proporciona información sobre cómo usar las opciones del Compositor de experiencias visuales.

* Cambiar el contenido de una página
* Cambiar el diseño de una página

>[!VIDEO](https://video.tv.adobe.com/v/17399)