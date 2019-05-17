---
description: El Compositor de experiencias proporciona una interfaz gráfica para editar las experiencias de la página.
keywords: crear experiencia;crear;experiencia;prioridad;audiencia;experiencia;compositor de experiencias visuales
seo-description: El Compositor de experiencias proporciona una interfaz gráfica para editar las experiencias de la página.
seo-title: Crear experiencia
solution: Target
title: Crear experiencia
topic: Advanced,Standard,Classic
uuid: ce559c3c-5a16-46b8-b2a7-df696626c7c0
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Crear experiencia{#create-experience}

El Compositor de experiencias proporciona una interfaz gráfica para editar las experiencias de la página.

Para obtener más información sobre las experiencias, consulte [Experiencias](../../../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D).

1. Haga clic en **[!UICONTROL Agregar experiencia]**.

   >[!NOTE]
   >
   >Si va a segmentar una experiencia a una audiencia, debe seleccionar la audiencia antes de añadir la experiencia. Aparecerá un mensaje para recordarle que elija una audiencia.

1. Cuando se le pida, introduzca la dirección URL de la actividad. Escriba la dirección URL completa (incluido `https://`) y haga clic en **[!UICONTROL Continuar]**.

   El Compositor de experiencias (consulte [Experiencias](../../../c-experiences/experiences.md#concept_1D011219034B492BB03C08B3BB80E3F0)) abre la página que se especifica en Preferencias de cuenta. Para mostrar una página distinta, haga clic en el icono del globo, escriba la dirección URL en el cuadro de selección de dirección URL del Compositor de experiencias y haga clic en **[!UICONTROL Continuar]**. Si escribe una dirección URL de un sitio que no incluye el código de JavaScript de Target Standard, no podrá seleccionar elementos de página.

   De manera predeterminada, el compositor de experiencias visuales no permite realizar cambios en elementos que contengan JavaScript, como banners giratorios. Puede deshabilitar JavaScript si quiere poder modificar estos elementos con el Compositor de experiencias visuales.

   >[!NOTE]
   >
   >Si cambia la dirección URL después de realizar cambios en una página para una o más experiencias, la experiencia se restablecerá con la nueva página y se perderán los cambios que haya realizado.

1. Seleccione los elementos que quiera cambiar y realice los cambios necesarios.

   Al desplazar el cursor sobre los elementos de la página, estos se resaltarán. Los elementos resaltados se pueden modificar con el Compositor de experiencias.

   Si creó un mbox en la página mediante Target Classic (antes denominado Test&amp;Target), ese mbox aparece como un elemento que muestra el nombre del mbox y se puede modificar como cualquier otro elemento.

   Para obtener una lista de las acciones que se pueden realizar en un elemento de la página mostrada para cambiar la experiencia, consulte [Opciones del Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

   >[!NOTE]
   >
   >Si entrega una imagen desde un origen distinto a la página principal (por ejemplo, una imagen alojada en akamai.net y entregada en dell.com), dicha imagen no se mostrará en la miniatura de la página mostrada en el diagrama de flujo.

1. Haga clic en el botón de la marca de verificación cuando haya terminado de diseñar la experiencia.

   Se muestra el diagrama de actividad:

   ![](assets/xt_diagram.png)

   Si una experiencia incluye contenido entre dominios, es posible que la miniatura no se muestre de forma precisa y que sea reemplazada por un icono.
1. Cree experiencias adicionales, como desee.

   >[!NOTE]
   >
   >Puede arrastrar y soltar pares de audiencia/experiencia al crear o editar actividades XT para reorganizar los pares en el orden deseado. Las experiencias de los visitantes se evalúan en orden, de arriba abajo.

   ![](assets/move_experiences.jpg)

   La segmentación de experiencias supone que ese orden importa. Si un visitante encaja en el primer par de audiencia/experiencia, se le sirve la primera experiencia.

   Por ejemplo, suponga que no es consciente de que el orden importa al crear una actividad XT. Más adelante repara, durante las pruebas, que los visitantes que creía que encajarían en las experiencias B o C acaban en la experiencia A. Podría deberse a que las audiencias no son mutuamente excluyentes y no están situadas en el orden apropiado (por ejemplo, experiencia A = Estados Unidos, experiencia B = San Francisco, experiencia C = California). En este escenario, todos los usuarios de Estados Unidos entrarán en la experiencia A, aunque se encuentren en San Francisco o alguna otra parte de California. Puede reordenar los pares de audiencia/experiencia de más restrictivo a menos restrictivo (San Francisco &gt; California &gt; Estados Unidos) sin necesidad de reconstruir toda la actividad.

## Cambiar nombre, editar o eliminar una experiencia

Puede hacer clic en el icono Editar (tres elipses verticales) de una experiencia en una prueba A/B o una actividad de segmentación de experiencias (XT) y elegir de las siguientes opciones, según sea necesario:

* Cambiar nombre
* Editar  
* Eliminar

![](assets/experience_edit.png)

Haga clic en **[!UICONTROL Continuar]cuando haya completado este paso.**

## Duplicar experiencias

Puede copiar una experiencia en una actividad de segmentación de experiencias (XT), por lo que puede realizar cambios menores sin tener que volver a crear la experiencia desde cero.

En la página **[!UICONTROL Experiencias]** (el primer paso del flujo de trabajo guiado de tres pasos), haga clic en las tres elipses verticales &gt; **[!UICONTROL Duplicar]**.

![](assets/duplicate_experience.png)

## Vídeo de formación: Uso del Compositor de experiencias visuales

El siguiente vídeo proporciona información sobre cómo usar las opciones del Compositor de experiencias visuales.

* Cambiar el contenido de una página
* Cambiar el diseño de una página

>[!VIDEO](https://video.tv.adobe.com/v/17399)