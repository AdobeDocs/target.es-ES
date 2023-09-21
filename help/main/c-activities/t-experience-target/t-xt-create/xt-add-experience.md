---
keywords: crear experiencia;crear;experiencia;prioridad;audiencia;experiencia;compositor de experiencias visuales
description: Aprenda a utilizar el [!DNL Adobe Target] [!UICONTROL Compositor de experiencias visuales] (VEC) para crear y editar experiencias en su página en un [!UICONTROL Segmentación de experiencias] Actividad (XT).
title: ¿Cómo puedo crear experiencias en un [!UICONTROL Segmentación de experiencias] ¿Actividad?
feature: Experience Targeting
exl-id: ec3fcd93-5557-4f69-8f9c-4d00569188ad
source-git-commit: 0dfdd995c00961ed2aed91ec03406e8493292af7
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 39%

---

# Crear experiencia en [!UICONTROL Segmentación de experiencias] Actividades (XT)

El [!UICONTROL Compositor de experiencias visuales] (VEC) en [!DNL Adobe Target] proporciona una interfaz visual para editar las experiencias en la página en un [!UICONTROL Segmentación de experiencias] Actividad (XT).

1. Seleccione los elementos que desee cambiar y realice los cambios necesarios.

   While [creación de un [!UICONTROL Segmentación de experiencias] actividad](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md), paso uno del flujo de trabajo guiado de tres partes ([!UICONTROL Experiencias]) muestra el valor predeterminado [!UICONTROL Experiencia A] con un [!UICONTROL Todos los visitantes] audiencia.

   ![Audiencia de todos los visitantes](/help/main/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   Los cambios que realice ahora se aplican a [!UICONTROL Experiencia A]. En un paso inferior, haga clic en **[!UICONTROL Añadir segmentación de experiencias]** para crear experiencias adicionales.

   Al pasar el ratón por encima de los elementos de la página, estos se resaltan. Los elementos resaltados se pueden modificar con el VEC. Para obtener una lista de las acciones que se pueden realizar en un elemento para cambiar la experiencia, consulte [Opciones del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   >[!NOTE]
   >
   >De manera predeterminada, el VEC no permite realizar cambios en elementos que contengan JavaScript, como banners giratorios. Puede deshabilitar JavaScript para alterar esos elementos mediante el VEC.

1. Para crear experiencias adicionales, haga clic en **[!UICONTROL Añadir Segmentación de experiencias]**.

   ![Añadir vínculo de Segmentación de experiencias](/help/main/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   El [!UICONTROL Añadir audiencia] aparece el cuadro de diálogo. Para segmentar una experiencia a una audiencia, seleccione la audiencia antes de añadir la experiencia.

   La biblioteca de audiencias contiene las audiencias que se han definido anteriormente, entre las que se incluyen algunas audiencias comunes predefinidas como parte de [!DNL Target]. Puede seleccionar una audiencia de la biblioteca o [crear una audiencia nueva](/help/main/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271).

   Además de seleccionar una audiencia existente, puede combinar varias audiencias para crear audiencias combinadas específicas en lugar de crear una nueva. Para obtener más información, consulte [Combinar varias audiencias](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

   Al crear una audiencia, puede seleccionar una ubicación y especificar parámetros para esa ubicación. En [!UICONTROL Personalizado] ([!UICONTROL Crear audiencia] > [!UICONTROL Personalizado]), seleccione la ubicación y, a continuación, especifique los parámetros deseados.

   >[!NOTE]
   >
   >Las audiencias se importan automáticamente en segundo plano cuando abre la lista de audiencias y las audiencias importadas tienen más de diez minutos de antigüedad.

1. Seleccione una o varias audiencias para segmentar con la experiencia y, a continuación, haga clic en **[!UICONTROL Listo]**.

   ![Experiencia B](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   La experiencia B ahora aparece en la ilustración anterior y está dirigida a la audiencia de visitantes de EE. UU.

1. Seleccione los elementos que desee cambiar para esta experiencia y realice los cambios necesarios, tal como se explica en el paso 1 anterior.

1. Repita los pasos anteriores para crear más experiencias segmentadas, según sea necesario.

1. Haga clic en **[!UICONTROL Siguiente]** cuando termine de diseñar las experiencias.

   Se muestra el diagrama de actividad:

   ![Diagrama de segmentación de XT](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

   >[!NOTE]
   >
   >Puede enviar una imagen desde un origen distinto a la página principal (por ejemplo, una imagen alojada en `akamai.net` y se entregó el `adobe.com`). Las imágenes alojadas en otra parte no se muestran en la miniatura de la página mostrada en el diagrama de flujo.

1. (Condicional) Arrastre y suelte pares de audiencia y experiencia al crear o editar [!UICONTROL Segmentación de experiencias] actividades para organizar las parejas en el orden deseado.

   Las experiencias de los visitantes se evalúan en orden, de arriba abajo.

   ![Mover experiencias](/help/main/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   [!UICONTROL La segmentación de experiencias supone que ese orden importa. ] Si un visitante entra en el primer par de audiencia y experiencia, se ofrece la primera experiencia.

   Por ejemplo, supongamos que no sabía que el orden importaba al crear un [!UICONTROL Segmentación de experiencias] actividad. Más adelante repara, durante las pruebas, que los visitantes que creía que encajarían en las experiencias B o C acaban en la experiencia A. Podría deberse a que las audiencias no son mutuamente excluyentes y no están situadas en el orden apropiado (por ejemplo, experiencia A = Estados Unidos, experiencia B = San Francisco, experiencia C = California). En este escenario, todos los usuarios de Estados Unidos cumplen los requisitos para la experiencia A, incluso si están en San Francisco o en otro lugar de California. Puede reordenar los pares de audiencia y experiencia de más restrictivo a menos restrictivo (San Francisco > California > Estados Unidos) sin volver a crear toda la actividad.

   Si tiene una audiencia de [!UICONTROL Todos los visitantes], compruebe que no sea la primera audiencia en el diagrama. Una experiencia segmentada a &quot;[!UICONTROL Todos los visitantes]&quot; se puede usar como la última experiencia en el [!UICONTROL Segmentación de experiencias] actividad para &quot;captar&quot; a los visitantes que no han participado de otras experiencias.

## Cambiar el nombre o editar una experiencia

Puede hacer clic en [!UICONTROL Editar] (los puntos suspensivos verticales) de una experiencia en un [!UICONTROL Segmentación de experiencias] y elija entre las siguientes opciones, según sea necesario:

* [!UICONTROL Cambiar el nombre]
* [!UICONTROL Editar  ]

![Opciones de Cambiar nombre y editar](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## Eliminar una experiencia

En el **[!UICONTROL Experiencias]** (el primer paso del flujo de trabajo guiado de tres pasos), haga clic en los puntos suspensivos verticales > **[!UICONTROL Eliminar]**.

![Eliminar experiencia](/help/main/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## Duplicar experiencias

Puede copiar una experiencia en un [!UICONTROL Segmentación de experiencias] actividad para que pueda realizar cambios menores sin tener que volver a crear toda la experiencia.

En el **[!UICONTROL Experiencias]** (el primer paso del flujo de trabajo guiado de tres pasos), haga clic en los puntos suspensivos verticales > **[!UICONTROL Duplicar]**.

![Duplicar experiencia](/help/main/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

## Vídeos de formación:

Los siguientes vídeos contienen más información sobre los conceptos mencionados en este artículo.

### De prueba A/B a [!UICONTROL Segmentación de experiencias]

En este vídeo se describe cómo llevar las pruebas A/B al siguiente nivel con [!UICONTROL Segmentación de experiencias] (XT).

* Describa el flujo de trabajo guiado de tres pasos para configurar una [!UICONTROL Segmentación de experiencias] actividad
* Describa cómo distribuir contenido específico de una ubicación a audiencias de diferentes áreas geográficas
* Describe cómo se reordenan las experiencias para asegurar que cada contenido se envíe a la audiencia correcta

>[!VIDEO](https://video.tv.adobe.com/v/22418/)

### Tipos de actividad (9:03)

En este vídeo se describen los tipos de actividades disponibles en [!DNL Target]. [!UICONTROL La segmentación de experiencias se describe a partir del minuto 5:15.]

* Describe los tipos de actividades incluidas en [!DNL Adobe Target]
* Seleccionar el tipo de actividad adecuado para lograr los objetivos
* Describir el flujo de trabajo guiado de tres pasos que sirve para todos los tipos de actividad

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### Uso del [!UICONTROL Compositor de experiencias visuales]

Este vídeo proporciona información sobre el uso de [!UICONTROL Segmentación de experiencias] Opciones de (VEC).

* Cambiar el contenido de una página
* Cambiar el diseño de una página

>[!VIDEO](https://video.tv.adobe.com/v/17399)
