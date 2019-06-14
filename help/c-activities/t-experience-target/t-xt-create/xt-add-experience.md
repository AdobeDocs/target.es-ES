---
description: El Compositor de experiencias visuales (VEC) proporciona una interfaz visual para editar las experiencias en su página.
keywords: crear experiencia;crear;experiencia;prioridad;audiencia;experiencia;compositor de experiencias visuales
seo-description: El Compositor de experiencias visuales de Adobe Target (VEC) proporciona una interfaz visual para editar las experiencias en su página.
seo-title: Crear experiencia
solution: Target
title: Crear experiencia
topic: Advanced,Standard,Classic
uuid: ce559c3c-5a16-46b8-b2a7-df696626c7c0
translation-type: tm+mt
source-git-commit: 5eb79fcd0407e0da841048bcd0a1b64393490fcf

---


# Crear experiencia{#create-experience}

El Compositor de experiencias visuales (VEC) proporciona una interfaz visual para editar las experiencias en su página en una actividad de segmentación de experiencias (XT).

1. Seleccione los elementos que quiera cambiar y realice los cambios necesarios.

   Al [crear una actividad](/help/c-activities/t-experience-target/t-xt-create/xt-create.md)XT, el paso uno del flujo de trabajo guiado de tres partes (Experiencias) muestra la experiencia predeterminada [!UICONTROL A] con una audiencia [!UICONTROL de todos los visitantes] .

   ![Audiencia de todos los visitantes](/help/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   Los cambios que realice ahora se aplican a la Experiencia A. En un paso inferior, haga clic [!UICONTROL en Agregar segmentación de experiencias] para crear experiencias adicionales.

   Al desplazar el cursor sobre los elementos de la página, estos se resaltarán. Cualquier elemento resaltado puede modificarse con el VEC. Para obtener una lista de acciones que se pueden realizar en un elemento para cambiar la experiencia, consulte [Opciones del Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

   Si creó un mbox en la página mediante Target Classic (antes denominado Test&amp;Target), ese mbox aparece como un elemento que muestra el nombre del mbox y se puede modificar como cualquier otro elemento.

1. Para crear experiencias adicionales, haga clic **[!Aen dd Experience Targeting]**.

   ![Agregar vínculo de segmentación de experiencias](/help/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   Se abre el cuadro [!UICONTROL de] diálogo Elegir audiencia. Para dirigir una experiencia a una audiencia, debe seleccionar la audiencia antes de agregar una experiencia.

   La biblioteca de audiencias contiene las audiencias que se han definido anteriormente, entre las que se incluyen algunas audiencias comunes predefinidas como parte de Target. Seleccione una audiencia de la biblioteca o  [cree una audiencia nueva](../../../c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271). Para mostrar la misma experiencia a todos los participantes, seleccione Todos los visitantes.

   >[!NOTE]
   >
   >Además de seleccionar una audiencia existente, puede combinar varias audiencias para crear audiencias combinadas específicas en lugar de crear una nueva. Para obtener más información, consulte [Combinar varias audiencias](../../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

   Al crear una audiencia puede seleccionar una ubicación (mbox) y especificar parámetros para dicha ubicación. En Parámetros personalizados, seleccione el mbox y especifique los parámetros que desee.

   >[!NOTE]
   >
   >Las audiencias se importan automáticamente en segundo plano cuando abre la lista de audiencias y las audiencias importadas tienen más de diez minutos de antigüedad.

1. Seleccione una o varias audiencias para segmentar con la experiencia y, a continuación, haga clic **[!UICONTROL en Finalizado]**.

   ![Experiencia B](/help/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   Observará que la Experiencia B ahora aparece en la ilustración anterior y esta experiencia está dirigida a la audiencia de Visitantes de EE. UU.

1. Seleccione los elementos que desee cambiar para esta experiencia y realice los cambios deseados, como se explica en el paso 1 de arriba.

1. Repita los pasos anteriores para crear experiencias segmentadas adicionales, según sea necesario.

1. Haga clic **[!UICONTROL en Siguiente]** cuando termine de diseñar las experiencias.

   Se muestra el diagrama de actividad:

   ![Diagrama de segmentación XT](/help/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

1. (Condicional) Arrastre y suelte pares de audiencia/experiencia al crear o editar actividades XT para organizar los pares en el orden deseado.

   Los visitantes se evalúan para experiencias en orden, de arriba a abajo.

   ![Mover experiencias](/help/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   La segmentación de experiencias supone que ese orden importa. Si un visitante encaja en el primer par de audiencia/experiencia, se le sirve la primera experiencia.

   Por ejemplo, suponga que no es consciente de que el orden importa al crear una actividad XT. Más adelante repara, durante las pruebas, que los visitantes que creía que encajarían en las experiencias B o C acaban en la experiencia A. Podría deberse a que las audiencias no son mutuamente excluyentes y no están situadas en el orden apropiado (por ejemplo, experiencia A = Estados Unidos, experiencia B = San Francisco, experiencia C = California). En este escenario, todos los usuarios de Estados Unidos entrarán en la experiencia A, aunque se encuentren en San Francisco o alguna otra parte de California. Puede reordenar los pares de audiencia/experiencia de más restrictivo a menos restrictivo (San Francisco &gt; California &gt; Estados Unidos) sin necesidad de reconstruir toda la actividad.

## Cambiar el nombre o editar una experiencia

Puede hacer clic en [!UICONTROL el icono Editar] (tres elipses verticales) en una experiencia de una actividad XT y elegir entre las siguientes opciones, según sea necesario:

* Cambiar nombre
* Editar

![Opciones de Cambiar nombre y editar](/help/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## Eliminar una experiencia

En la página **[!UICONTROL Experiencias]** (el primer paso del flujo de trabajo guiado de tres pasos), haga clic en las tres elipses verticales &gt; **[!UICONTROL Eliminar]**.

![Eliminar experiencia](/help/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## Duplicar experiencias

Puede copiar una experiencia en una actividad de segmentación de experiencias (XT), por lo que puede realizar cambios menores sin tener que volver a crear la experiencia desde cero.

En la página **[!UICONTROL Experiencias]** (el primer paso del flujo de trabajo guiado de tres pasos), haga clic en las tres elipses verticales &gt; **[!UICONTROL Duplicar]**.

![Duplicar experiencia](/help/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

## Vídeo de formación: Uso del Compositor de experiencias visuales

El siguiente vídeo proporciona información sobre cómo usar las opciones del Compositor de experiencias visuales.

* Cambiar el contenido de una página
* Cambiar el diseño de una página

>[!VIDEO](https://video.tv.adobe.com/v/17399?captions=spa)