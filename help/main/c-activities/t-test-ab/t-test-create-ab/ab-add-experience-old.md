---
keywords: Segmentación;experiencia;añadir experiencia;adición de experiencia
description: Aprenda a usar el [!UICONTROL Compositor de experiencias visuales] (VEC) en [!DNL Adobe Target].
title: ¿Cómo agrego experiencias en una actividad  [!DNL Target] A/B?
feature: A/B Tests
exl-id: c0f1b5a7-07b0-46c2-97f3-95dcc0fcbe3d
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 41%

---

# Añadir experiencia

El [!DNL Adobe Target] [!UICONTROL Compositor de experiencias visuales] (VEC) proporciona una interfaz visual para agregar y editar las experiencias en su página.

Para obtener más información sobre las experiencias, consulte [Experiencias](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D).

1. En la página **[!UICONTROL Experiencias]** del VEC, haga clic en **[!UICONTROL Agregar experiencia]**.

   ![Opción Añadir experiencia](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/add-experience.png)

   >[!NOTE]
   >
   >Si va a segmentar una experiencia a un público, debe seleccionar el público antes de añadir la experiencia. Aparecerá un mensaje para recordarle que elija un público.

1. Seleccione los elementos que desee cambiar y realice los cambios necesarios.

   Al pasar el ratón por encima de los elementos de la página, estos se resaltan. Los elementos resaltados se pueden modificar con el VEC.

   Si creó una solicitud [!DNL Target] en la página con [!DNL Target Classic] (anteriormente [!DNL Test&Target]), esa solicitud [!DNL Target] aparece como un elemento que muestra el nombre de la solicitud y se puede modificar como cualquier otro elemento.

   Para obtener una lista de las acciones que se pueden realizar en un elemento de la página mostrada para cambiar la experiencia, consulte [Opciones del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   >[!NOTE]
   >
   >Si entrega una imagen desde un origen distinto a la página principal (por ejemplo, una imagen alojada en `akamai.net` y entregada en `example.com`), dicha imagen no se mostrará en la miniatura de la página mostrada en el diagrama de flujo.

1. Haga clic en **[!UICONTROL Guardar]** cuando termine de diseñar la experiencia.

## Cambiar el nombre de la experiencia

1. Haga clic en el icono **[!UICONTROL Cambiar el nombre de la experiencia]** en una experiencia de [!UICONTROL prueba A/B] o de [!UICONTROL Segmentación de experiencias] (XT) para cambiar el nombre de la experiencia.

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

1. Haga clic en el icono **[!UICONTROL Más]** (los puntos suspensivos verticales) de una experiencia en una actividad de [!UICONTROL Prueba A/B] o [!UICONTROL Segmentación de experiencias] (XT) y, a continuación, haga clic en **[!UICONTROL Redireccionar a URL]**.

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

1. (Condicional) Marque la casilla de verificación **[!UICONTROL Incluir parámetros de consulta actuales]**.

## Duplicar experiencias

Puede copiar una experiencia en una [!UICONTROL prueba A/B] para poder realizar cambios menores sin tener que volver a crear la experiencia desde cero.

1. En la página **[!UICONTROL Experiencias]** (el primer paso del flujo de trabajo guiado de tres pasos), haga clic en el icono de puntos suspensivos verticales > **[!UICONTROL Duplicar]**.

   ![Opción Duplicar experiencia](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/duplicate-experience.png)

## Eliminar una experiencia

1. En la página **[!UICONTROL Experiencias]** (el primer paso del flujo de trabajo guiado de tres pasos), haga clic en el icono de puntos suspensivos verticales > **[!UICONTROL Duplicar]**.

   ![Opción Eliminar experiencia](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/delete-experience.png)

## Vídeo de formación: Uso del [!UICONTROL Compositor de experiencias visuales]

El siguiente vídeo proporciona información sobre cómo usar las opciones de [!UICONTROL Compositor de experiencias visuales]. (7:17)

* Cambiar el contenido de una página
* Cambiar el diseño de una página

>[!VIDEO](https://video.tv.adobe.com/v/17399)
