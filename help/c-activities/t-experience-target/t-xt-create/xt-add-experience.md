---
description: El Compositor de experiencias visuales (VEC) proporciona una interfaz visual para editar las experiencias en su página en una actividad de segmentación de experiencias (XT).
keywords: crear experiencia;crear;experiencia;prioridad;audiencia;experiencia;compositor de experiencias visuales
seo-description: El Compositor de experiencias visuales de Adobe Target (VEC) proporciona una interfaz visual para editar las experiencias en su página en una actividad de segmentación de experiencias (XT).
seo-title: Crear experiencia
solution: Target
title: Crear experiencia
topic: Advanced,Standard,Classic
uuid: ce559c3c-5a16-46b8-b2a7-df696626c7c0
translation-type: tm+mt
source-git-commit: ca9639ccca286dac182728f7bbd43fac78217209

---


# Crear experiencia{#create-experience}

El Compositor de experiencias visuales (VEC) proporciona una interfaz visual para editar las experiencias en su página en una actividad de segmentación de experiencias (XT).

1. Seleccione los elementos que quiera cambiar y realice los cambios necesarios.

   Al [crear una actividad](/help/c-activities/t-experience-target/t-xt-create/xt-create.md)XT, el paso uno del flujo de trabajo guiado de tres partes (Experiencias) muestra la experiencia predeterminada [!UICONTROL A] con una audiencia [!UICONTROL de todos los visitantes] .

   ![Audiencia de todos los visitantes](/help/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   Los cambios que realice ahora se aplican a la Experiencia A. En un paso inferior, haga clic **[!UICONTROL en Agregar segmentación de experiencias]** para crear experiencias adicionales.

   Al desplazar el cursor sobre los elementos de la página, estos se resaltarán. Cualquier elemento resaltado puede modificarse con el VEC. Para obtener una lista de acciones que se pueden realizar en un elemento para cambiar la experiencia, consulte [Opciones del Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

   Si creó un mbox en la página mediante Target Classic (antes denominado Test&amp;Target), ese mbox aparece como un elemento que muestra el nombre del mbox y se puede modificar como cualquier otro elemento.

   >[!NOTE]
   >
   >De manera predeterminada, el compositor de experiencias visuales no permite realizar cambios en elementos que contengan JavaScript, como banners giratorios. Puede seleccionar deshabilitar JavaScript si desea poder modificar esos elementos mediante el VEC.

1. Para crear experiencias adicionales, haga clic **[!Aen dd Experience Targeting]**.

   ![Agregar vínculo de segmentación de experiencias](/help/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   Se abre el cuadro [!UICONTROL de] diálogo Elegir audiencia. Para dirigir una experiencia a una audiencia, debe seleccionar la audiencia antes de agregar una experiencia.

   La biblioteca de audiencias contiene las audiencias que se han definido anteriormente, entre las que se incluyen algunas audiencias comunes predefinidas como parte de Target. Seleccione una audiencia de la biblioteca o  [cree una audiencia nueva](../../../c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271). 

   >[!NOTE]
   >
   >Además de seleccionar una audiencia existente, puede combinar varias audiencias para crear audiencias combinadas específicas en lugar de crear una nueva. Para obtener más información, consulte [Combinar varias audiencias](../../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

   Al crear una audiencia puede seleccionar una ubicación (mbox) y especificar parámetros para dicha ubicación. En [!UICONTROL Personalizado] (Crear audiencia &gt; Agregar regla &gt; Personalizar), seleccione el mbox y, a continuación, especifique los parámetros que desee.

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

   >[!NOTE]
   >
   >Si entrega una imagen desde una fuente distinta a la página principal (como una imagen alojada en akamai. net y entregada en adobe.com), dicha imagen no se muestra en la miniatura de la página mostrada en el diagrama de flujo.

1. (Condicional) Arrastre y suelte pares de audiencia/experiencia al crear o editar actividades XT para organizar los pares en el orden deseado.

   Los visitantes se evalúan para experiencias en orden, de arriba a abajo.

   ![Mover experiencias](/help/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   La segmentación de experiencias supone que ese orden importa. Si un visitante encaja en el primer par de audiencia/experiencia, se le sirve la primera experiencia.

   Por ejemplo, suponga que no es consciente de que el orden importa al crear una actividad XT. Más adelante repara, durante las pruebas, que los visitantes que creía que encajarían en las experiencias B o C acaban en la experiencia A. Podría deberse a que las audiencias no son mutuamente excluyentes y no están situadas en el orden apropiado (por ejemplo, experiencia A = Estados Unidos, experiencia B = San Francisco, experiencia C = California). En este escenario, todos los usuarios de Estados Unidos entrarán en la experiencia A, aunque se encuentren en San Francisco o alguna otra parte de California. Puede reordenar los pares de audiencia/experiencia de más restrictivo a menos restrictivo (San Francisco &gt; California &gt; Estados Unidos) sin necesidad de reconstruir toda la actividad.

   Si tiene una audiencia [!UICONTROL de Todos los visitantes] , asegúrese de que no sea la primera audiencia en el diagrama. Se puede utilizar una experiencia segmentada a “Todos los visitantes” como la última experiencia de la actividad de segmentación de experiencias para “captar” a los visitantes que no han participado de otras experiencias.

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

## Vídeos de formación:

Los siguientes vídeos contienen más información sobre los conceptos mencionados en este artículo.

### De pruebas A/B a segmentación de experiencias

Este vídeo describe cómo se llevan las pruebas A/B al siguiente nivel con Segmentación de experiencias (XT).

* Describe el flujo de trabajo guiado de tres pasos para la configuración de una actividad XT
* Describe cómo se entrega contenido dependiente de la ubicación a audiencias situadas en distintas zonas geográficas
* Describe cómo se reordenan las experiencias para asegurar que cada contenido se envíe a la audiencia correcta

>[!VIDEO](https://video.tv.adobe.com/v/22418/?captions=spa)

### Tipos de actividad (9:03)

En este vídeo se describen los tipos de actividades disponibles en Target Standard/Premium. La segmentación de experiencias se describe a partir del minuto 5:15.

* Describe los tipos de actividades incluidas en [!DNL Adobe Target]
* Seleccionar el tipo de actividad adecuado para lograr los objetivos
* Describir el flujo de trabajo guiado de tres pasos que sirve para todos los tipos de actividad

>[!VIDEO](https://video.tv.adobe.com/v/17386?captions=spa)

### Uso del Compositor de experiencias visuales

El siguiente vídeo proporciona información sobre cómo usar las opciones del Compositor de experiencias visuales.

* Cambiar el contenido de una página
* Cambiar el diseño de una página

>[!VIDEO](https://video.tv.adobe.com/v/17399?captions=spa)