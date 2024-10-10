---
keywords: Segmentación;experiencia;añadir experiencia;adición de experiencia
description: Domine el [!UICONTROL Visual Experience Composer] (VEC) para agregar experiencias a las actividades.
title: ¿Cómo añado experiencias en una actividad A/B?
feature: A/B Tests
hide: true
hidefromtoc: true
source-git-commit: 6e9d18b8347d8ae68be699640c4cde91bdec762c
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 28%

---

# Añadir experiencia

El [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) proporciona una interfaz visual para agregar y editar las experiencias en su página.

Para obtener más información sobre las experiencias, consulte [Experiencias](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D).

1. En la página **[!UICONTROL Experiences]** del VEC, haga clic en el icono [!UICONTROL Add] ( ![Agregar icono](/help/main/assets/icons/Add.svg) ) en la parte superior del panel [!UICONTROL Experiences].

   El VEC muestra dos pestañas en el lado izquierdo después de crear una nueva actividad: la Experiencia A y la Experiencia B. La Experiencia A es la experiencia de control. Puede agregar varias experiencias a la prueba.

1. Seleccione los elementos que desee cambiar y realice los cambios necesarios.

   Al pasar el ratón por encima de los elementos de la página, estos se resaltan. Cualquier elemento resaltado se puede modificar con el VEC.

   Si creó una solicitud [!DNL Target] en la página con [!DNL Target Classic] (anteriormente [!DNL Test&Target]), esa solicitud [!DNL Target] aparece como un elemento que muestra el nombre de la solicitud y se puede modificar como cualquier otro elemento.

   Para obtener una lista de las acciones que se pueden realizar en un elemento de la página mostrada para cambiar la experiencia, consulte [Opciones del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   >[!NOTE]
   >
   >Si entrega una imagen desde un origen distinto a la página principal (por ejemplo, una imagen alojada en `akamai.net` y entregada en `example.com`), dicha imagen no se mostrará en la miniatura de la página mostrada en el diagrama de flujo.

1. Haga clic en **[!UICONTROL Next]** cuando termine de diseñar la experiencia.

## Cambiar el nombre de la experiencia

1. Haga clic en el icono **[!UICONTROL Rename Experience]** ( ![Cambiar nombre](/help/main/assets/icons/Rename.svg) ) junto a una experiencia para darle un nombre nuevo a la experiencia.

2. Especifique un nombre nuevo y luego haga clic en **[!UICONTROL Save]**.

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

1. En el panel **[!UICONTROL Experiences]**, haga clic en el icono **[!UICONTROL More]** ( ![icono Más](/help/main/assets/icons/MoreSmall.svg) ) junto a una experiencia y, a continuación, haga clic en **[!UICONTROL Redirect to URL]**.

   Para obtener más información, consulte [Redireccionamiento a URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md).

1. Especifique la URL a la que desea redirigir la experiencia.

1. (Condicional) Marque la casilla **[!UICONTROL Include Current Query Parameters]**.

1. Haga clic en **[!UICONTROL Save]**.

## Duplicar experiencias

Puede copiar una experiencia en un [!UICONTROL A/B Test] para poder realizar cambios menores sin tener que volver a crear la experiencia.

1. En el panel **[!UICONTROL Experiences]**, haga clic en el icono **[!UICONTROL More]** ( ![icono Más](/help/main/assets/icons/MoreSmall.svg) ) junto a una experiencia y, a continuación, haga clic en **[!UICONTROL Duplicate]**.

## Eliminar una experiencia

1. En el panel **[!UICONTROL Experiences]**, haga clic en el icono **[!UICONTROL More]** ( ![icono Más](/help/main/assets/icons/MoreSmall.svg) ) junto a una experiencia, haga clic en **[!UICONTROL Delete]** y, a continuación, haga clic en **[!UICONTROL Delete]** para confirmar la acción.