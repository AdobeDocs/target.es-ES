---
keywords: Segmentación;experiencia;añadir experiencia;adición de experiencia
description: Aprenda a utilizar el [!UICONTROL Visual Experience Composer] (VEC) en  [!DNL Adobe Target].
title: ¿Cómo agrego experiencias en una actividad  [!DNL Target] A/B?
feature: A/B Tests
exl-id: c0f1b5a7-07b0-46c2-97f3-95dcc0fcbe3d
source-git-commit: 6fa1b428e7955bae976649c42d3eb9b2ddc2c79f
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 43%

---

# Añadir experiencia

El [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) proporciona una interfaz visual para agregar y editar las experiencias en su página.

Para obtener más información sobre las experiencias, consulte [Experiencias](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D).

1. En la página **[!UICONTROL Experiences]** del VEC, haga clic en **[!UICONTROL Add Experience]**.

   ![Opción Añadir experiencia](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/add-experience.png)

   >[!NOTE]
   >
   >Si va a segmentar una experiencia a una audiencia, debe seleccionar la audiencia antes de añadir la experiencia. Aparecerá un mensaje para recordarle que elija una audiencia.

1. Seleccione los elementos que desee cambiar y realice los cambios necesarios.

   Al pasar el ratón por encima de los elementos de la página, estos se resaltan. Cualquier elemento resaltado se puede modificar con el VEC.

   Si creó una solicitud [!DNL Target] en la página con [!DNL Target Classic] (anteriormente [!DNL Test&Target]), esa solicitud [!DNL Target] aparece como un elemento que muestra el nombre de la solicitud y se puede modificar como cualquier otro elemento.

   Para obtener una lista de las acciones que se pueden realizar en un elemento de la página mostrada para cambiar la experiencia, consulte [Opciones del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   >[!NOTE]
   >
   >Si entrega una imagen desde un origen distinto a la página principal (por ejemplo, una imagen alojada en `akamai.net` y entregada en `example.com`), dicha imagen no se mostrará en la miniatura de la página mostrada en el diagrama de flujo.

1. Haga clic en **[!UICONTROL Save]** cuando termine de diseñar la experiencia.

## Cambiar el nombre de la experiencia

1. Haga clic en el icono **[!UICONTROL Rename Experience]** de una experiencia en una actividad [!UICONTROL A/B Test] o [!UICONTROL Experience Targeting] (XT) para modificar el nombre de la experiencia.

   ![Cambiar el nombre de la experiencia](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/rename-experience.png)

2. Especifique un nombre nuevo.

   Al asignar un nombre a una experiencia o cambiarla por otro, no se permiten los siguientes caracteres:

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

## Redirigir a URL

1. Haga clic en el icono **[!UICONTROL More]** (los puntos suspensivos verticales) de una experiencia en una actividad de [!UICONTROL A/B Test] o [!UICONTROL Experience Targeting] (XT) y, a continuación, haga clic en **[!UICONTROL Redirect to URL]**.

   Para obtener más información, consulte [Redireccionamiento a URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md).

   **NOTA**: Cuando nombra o cambia el nombre de una experiencia, no se permiten los siguientes caracteres:

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

1. Especifique la URL a la que desea redirigir la experiencia.

1. (Condicional) Marque la casilla **[!UICONTROL Include Current Query Parameters]**.

## Duplicar experiencias

Puede copiar una experiencia en un [!UICONTROL A/B Test] para poder realizar cambios menores sin tener que volver a crear la experiencia desde cero.

1. En la página **[!UICONTROL Experiences]** (el primer paso del flujo de trabajo guiado de tres pasos), haga clic en el icono de puntos suspensivos verticales > **[!UICONTROL Duplicate]**.

   ![Opción Duplicar experiencia](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/duplicate-experience.png)

## Eliminar una experiencia

1. En la página **[!UICONTROL Experiences]** (el primer paso del flujo de trabajo guiado de tres pasos), haga clic en el icono de puntos suspensivos verticales > **[!UICONTROL Duplicate]**.

   ![Opción Eliminar experiencia](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/delete-experience.png)

## Vídeo de formación: Uso de [!UICONTROL Visual Experience Composer]

El siguiente vídeo proporciona información sobre el uso de las opciones de [!UICONTROL Visual Experience Composer]. (7:17)

* Cambiar el contenido de una página
* Cambiar el diseño de una página

>[!VIDEO](https://video.tv.adobe.com/v/17399)
