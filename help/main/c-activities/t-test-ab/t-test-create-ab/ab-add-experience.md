---
keywords: Segmentación;experiencia;añadir experiencia;adición de experiencia
description: Use [!UICONTROL Compositor de experiencias visuales] (VEC) para agregar experiencias a las actividades.
title: ¿Cómo añado experiencias en una actividad A/B?
feature: A/B Tests
exl-id: c0f1b5a7-07b0-46c2-97f3-95dcc0fcbe3d
TQID: https://experienceleague.adobe.com/7qEiUXkfMbPmtB2eMio0LztOYM3naHxG-WRQZOyMmlU
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 420
ht-degree: 30%

---

# Añadir experiencia

El [!DNL Adobe Target] [!UICONTROL Compositor de experiencias visuales] (VEC) proporciona una interfaz visual para agregar y editar las experiencias en su página.

Para obtener más información sobre las experiencias, consulte [Experiencias](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D).

1. En la página **[!UICONTROL Experiencias]** del VEC, haga clic en el icono [!UICONTROL Agregar] ( ![Agregar icono](/help/main/assets/icons/Add.svg) ) en la parte superior del panel [!UICONTROL Experiencias].

   El VEC muestra dos pestañas en el lado izquierdo después de crear una nueva actividad: la Experiencia A y la Experiencia B. La Experiencia A es la experiencia de control. Se pueden añadir varias experiencias a la prueba.

1. Seleccione los elementos que desee cambiar y realice los cambios necesarios.

   Al pasar el ratón por encima de los elementos de la página, estos se resaltan. Los elementos resaltados se pueden modificar con el VEC.

   Si creó una solicitud [!DNL Target] en la página con [!DNL Target Classic] (anteriormente [!DNL Test&Target]), esa solicitud [!DNL Target] aparece como un elemento que muestra el nombre de la solicitud y se puede modificar como cualquier otro elemento.

   Para obtener una lista de las acciones que se pueden realizar en un elemento de la página mostrada para cambiar la experiencia, consulte [Opciones del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   >[!NOTE]
   >
   >Si entrega una imagen desde un origen distinto a la página principal (por ejemplo, una imagen alojada en `akamai.net` y entregada en `example.com`), dicha imagen no se mostrará en la miniatura de la página mostrada en el diagrama de flujo.

1. Haga clic en **[!UICONTROL Siguiente]** cuando termine de diseñar la experiencia.

## Cambiar el nombre de la experiencia

1. Haga clic en el icono **[!UICONTROL Cambiar el nombre de la experiencia]** ( ![Cambiar el nombre del icono](/help/main/assets/icons/Rename.svg) ) junto a una experiencia para asignar a la experiencia un nombre nuevo.

2. Especifique un nombre nuevo y luego haga clic en **[!UICONTROL Guardar]**.

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

1. En el panel **[!UICONTROL Experiencias]**, haga clic en el icono **[!UICONTROL Más]** ( ![Icono de más](/help/main/assets/icons/MoreSmall.svg) ) junto a una experiencia y, a continuación, haga clic en **[!UICONTROL Redireccionar a dirección URL]**.

   Para obtener más información, consulte [Redireccionamiento a URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md).

1. Especifique la URL a la que desea redirigir la experiencia.

1. (Condicional) Marque la casilla de verificación **[!UICONTROL Incluir parámetros de consulta actuales]**.

1. Haga clic en **[!UICONTROL Guardar]**.

## Duplicar experiencias

Puede copiar una experiencia en una [!UICONTROL prueba A/B] para poder realizar cambios menores sin tener que volver a crear la experiencia.

1. En el panel **[!UICONTROL Experiencias]**, haga clic en el icono **[!UICONTROL Más]** ( ![Icono de más](/help/main/assets/icons/MoreSmall.svg) ) junto a una experiencia y, a continuación, haga clic en **[!UICONTROL Duplicar]**.

## Eliminar una experiencia

1. En el panel **[!UICONTROL Experiencias]**, haga clic en el icono **[!UICONTROL Más]** ( ![Icono de más](/help/main/assets/icons/MoreSmall.svg) ) junto a una experiencia, haga clic en **[!UICONTROL Eliminar]** y, a continuación, haga clic en **[!UICONTROL Eliminar]** para confirmar la acción.
