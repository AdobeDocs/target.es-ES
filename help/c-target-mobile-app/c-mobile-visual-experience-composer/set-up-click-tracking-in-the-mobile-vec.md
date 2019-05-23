---
description: El Compositor de experiencias visuales móviles (VEC) permite configurar los objetivos de rastreo de clics para las actividades de Target.
keywords: VEC de aplicación móvil; compositor de experiencias visuales móviles; opciones del compositor de experiencias móviles; opciones de experiencia móvil; target view; clics; rastreo de clics; track
seo-description: El Compositor de experiencias visuales móviles (VEC) permite configurar los objetivos de rastreo de clics para las actividades de Adobe Target.
seo-title: Configuración del rastreo de clics en el VEC de aplicaciones móviles
solution: Target
title: Configuración del rastreo de clics en el VEC de aplicaciones móviles
topic: Standard
uuid: 7e4ce7c0-0027-417c-8dae-45b6f5045e65
translation-type: tm+mt
source-git-commit: aa729a8972547be065008c6504bb36dce9cd6e65

---


# Configuración del rastreo de clics en el VEC de aplicaciones móviles{#set-up-click-tracking-in-the-mobile-vec}

La aplicación móvil VEC permite configurar los objetivos de rastreo de clics para [!DNL Target] las actividades.

1. Al establecer los objetivos en la página Objetivos y configuración para su actividad, seleccione la métrica de conversión [!UICONTROL Conversión].

   ![](assets/mobile-vec-clicktrack1.png)

1. Para la acción, seleccione **[!UICONTROL Se hizo clic en un elemento]** y luego haga clic en **[!UICONTROL Seleccionar elementos]**.

   Su aplicación móvil se abre en el Compositor de experiencias visuales (VEC).

   ![](assets/mobile-vec-clicktrack2.png)

1. Seleccione los elementos que desee rastrear.

   Consulte la sección [!UICONTROL Consideraciones], a continuación, para ver sugerencias sobre la selección de elementos.

   ![](assets/mobile-vec-clicktrack3.png)

1. Haga clic en la marca de verificación que aparece en la parte superior de la pantalla para guardar los elementos seleccionados.

También puede editar y cambiar las selecciones de clic o eliminarlas si necesita comenzar de nuevo.

![](assets/mobile-vec-clicktrack4.png)

Cuando el participante de una actividad hace clic en un elemento seleccionado, ese clic se cuenta como una conversión.

## Consideraciones {#considerations}

Existen varias cuestiones que se deben tener en cuenta al seleccionar elementos:

* Cuando se selecciona más de un elemento y un visitante hace clic en alguno de estos elementos, se cuenta el clic. Para contar cada clic por separado, configure métricas de éxito individuales para cada elemento.
* Los eventos de clic se envían a Target tan pronto como el usuario hace clic en el elemento.
* En el VEC de la aplicación móvil, solo se permiten los elementos que tienen un controlador de clic adjunto.
* Puede navegar a cualquier sección de la aplicación, pero asegúrese de que las [vistas](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#target-views) estén definidas para la sección en la que está seleccionando elementos para el rastreo de clics.
* Al editar una actividad, si el dispositivo ya está seleccionado en el Paso 1, no es necesario que vuelva a seleccionarlo. Sin embargo, si aterriza directamente en la página de rastreo de clics, se mostrará la pantalla de selección del dispositivo para seleccionar un dispositivo autorizado.
