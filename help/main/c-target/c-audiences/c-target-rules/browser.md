---
keywords: opciones del explorador;tipo;tipo de explorador;idioma del explorador;idioma;versión;versión del explorador
description: Obtenga información sobre cómo crear audiencias en [!DNL Adobe Target] para dirigirse a los usuarios que utilizan un explorador específico u opciones específicas del explorador cuando visitan la página.
title: ¿Puedo segmentar visitantes según el tipo de explorador?
feature: Audiences
exl-id: 8420bbe3-b58a-4ddb-89bb-0265dab6b5fc
source-git-commit: 1e1641a52478e21bba4a1991f62809c7046dd33e
workflow-type: tm+mt
source-wordcount: '970'
ht-degree: 51%

---

# Explorador

Puede segmentar usuarios que usen un navegador específico y opciones del navegador concretas cuando visiten una página.

Se pueden segmentar los siguientes navegadores:

* Chrome
* Firefox
* Safari
* Internet Explorer
* Microsoft Edge
* Opera
* iPad
* iPhone

>[!IMPORTANT]
>
>A partir del 30 de abril de 2024, iPad y iPhone se eliminarán de las versiones de disponibles [!UICONTROL Explorador] escriba lista desplegable al crear categorías para audiencias. Para ver la configuración de la solución, consulte [Obsolescencia de iPad y iPhone a partir del atributo de audiencia del explorador (30 de abril de 2024)](#deprecation) más abajo.

Hay dos formar de segmentar según el navegador:

* **Audiencia prediseñada:** utilice la audiencia prediseñada si quiere segmentar solo los visitantes que usan un navegador concreto para visitar el sitio. Si, por ejemplo, ofrece una extensión de Chrome, se dirigiría solo a los usuarios de este navegador.

   1. Al configurar la actividad, seleccione el explorador en la lista desplegable.

      Esta opción dirige la actividad únicamente a los visitantes que usan el navegador especificado.

      ![Usuarios de Target Chrome](/help/main/c-target/c-audiences/c-target-rules/assets/target-chrome.png)

* **Regla de audiencia del explorador personalizada:** Una audiencia personalizada le permite dirigirse a varios exploradores o configurar reglas o exclusiones para exploradores, versiones de exploradores o idiomas específicos. Esta funcionalidad proporciona una flexibilidad considerable a la hora de segmentar una actividad según los atributos del explorador.

   1. En el [!DNL Target] interfaz, haga clic en **[!UICONTROL Audiencias]** > **[!UICONTROL Crear audiencia]**.
   1. Asigne un nombre a la audiencia y añada una descripción opcional.
   1. Arrastrar y soltar **[!UICONTROL Explorador]** en el Generador de audiencias.

      ![Reglas > Explorador](assets/target_browser.png)

   1. Haga clic en **[!UICONTROL Seleccionar]** y, a continuación, elija una de estas opciones:

      * **Tipo:** dirija la actividad a un navegador o exclúyalo. Consulte [Tipo](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_6ADC758F23F145B3A310151546D83D56).
      * **Idioma:** Dirija la actividad ciertos navegadores configurados en idiomas específicos o exclúyalos. Consulte [Idioma](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_7520D1AA464A45A6843EABE2D2B431A1).
      * **Versión:** dirija la actividad a ciertas versiones del navegador o exclúyalas. Consulte [Versión](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_37CC8CE45DA04E8682AE6388321BA6EF).

   1. (Opcional) Configure reglas adicionales para la audiencia.
   1. Haga clic en **[!UICONTROL Finalizado]**.

  El siguiente ejemplo muestra una audiencia que incluye a los usuarios de Microsoft Edge en las versiones 91 o 92:

  ![Target Edge 91 o 92](assets/target_edge.png)

## Opciones del navegador {#concept_221D8EEF53CC45AEACEB17CF336A3658}

Dirija la actividad a visitantes o exclúyalos en función del tipo, el idioma o la versión de navegador que tengan.

### Tipo  {#section_6ADC758F23F145B3A310151546D83D56}

Dirija la actividad a un navegador o exclúyalo.

Seleccione **[!UICONTROL Tipo]** y, a continuación, elija igual a o no es igual a.

* Igual a: dirija la actividad a los navegadores seleccionados.
* No es igual a: excluya los navegadores seleccionados.

Seleccione uno o varios. Si hay varias opciones, se conectan con un parámetro O.

### Idioma  {#section_7520D1AA464A45A6843EABE2D2B431A1}

Dirija la actividad ciertos navegadores que estén configurados en idiomas específicos o exclúyalos.

Por ejemplo, si una oferta solo está disponible en español, puede segmentar exploradores en los que el idioma establecido sea el español. O, si su página no está habilitada para los idiomas de doble byte, puede excluir los navegadores en los que se haya establecido un idioma asiático oriental.

La inclusión o exclusión de idiomas de navegador puede proporcionar una segmentación del visitante más precisa que segmentarlos según la ubicación geográfica, al menos en aquellos casos en los que el idioma es más importante que la ubicación. Si, por ejemplo, ofrece un artículo escrito en español, puede dirigirlo a los países de habla hispana o a los navegadores en los que el idioma establecido es el español. Segmentar según el navegador facilita el artículo a los hablantes de español ubicados en países en los que el español no es el principal idioma.

Seleccione **[!UICONTROL Idioma]** y, a continuación, elija igual a o no es igual a.

* Igual: dirija el artículo a los idiomas de navegador seleccionados.
* No es igual a: excluya los idiomas de navegador seleccionados.

Seleccione uno o varios. Si hay varias opciones, se conectan con un parámetro O.

Los siguientes idiomas de navegador se pueden incluir o excluir de la segmentación:

* Inglés
* Francés
* Alemán
* Japonés
* Coreano
* Portugués
* Ruso
* Español
* Chino tradicional

### Versión  {#section_37CC8CE45DA04E8682AE6388321BA6EF}

Dirija la actividad a ciertas versiones del navegador o exclúyalas.

Si, por ejemplo, su página no se muestra correctamente en la versión 11 o anteriores de Internet Explorer, puede crear una audiencia que las excluya. En ese caso, debe configurar una regla en la que el tipo de navegador sea igual a Internet Explorer y agregar una segunda regla en la que la versión sea menor o igual a 11.

Seleccione **[!UICONTROL Versión]** y, a continuación, elija un operador:

* Es igual a
* No es igual a
* Es mayor que
* Es mayor que o igual a
* Es menor que
* Es menor que o igual a

Escriba el número de versión. En el campo de texto solo se pueden introducir versiones principales. Es decir, la versión especificada incluye las versiones secundarias de la principal. Por ejemplo, si especifica la versión 10, también se incluyen los visitantes de la versión 10.1.

Si hay varias opciones, se conectan con un parámetro O.

## Vídeo de formación: Creación de audiencias ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo contiene información sobre el uso de las categorías de audiencias.

* Crear audiencias
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)

## Obsolescencia de iPad y iPhone a partir del atributo de audiencia del explorador (30 de abril de 2024) {#deprecation}

[!DNL Adobe Target] le permite [segmentar en cualquiera de los atributos de categoría](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), incluidos los usuarios que usan un explorador específico u opciones del explorador cuando visitan la página.

A partir del 30 de abril de 2024, iPad y iPhone se eliminarán de las versiones de disponibles [!UICONTROL Explorador] escriba lista desplegable al crear categorías para audiencias.

Si tiene audiencias dirigidas a iPads o iPhone que utilizan [!UICONTROL Explorador] debe cambiar esta configuración antes del 30 de abril de 2024 para garantizar que estas audiencias sigan funcionando según lo esperado.

Se pueden utilizar los siguientes ajustes a partir de ahora:

* **Para coincidencias de explorador[!DNL Apple]**: [!UICONTROL Móvil] > [!UICONTROL Proveedor de dispositivo] [!UICONTROL matches] [!DNL Apple]

  ![Apple](/help/main/r-release-notes/assets/apple.png)

* **Para las coincidencias de navegador y tableta**: [!UICONTROL Móvil] > [!UICONTROL es tableta] > [!UICONTROL true]

  ![mobile es tablet](/help/main/r-release-notes/assets/is-tablet.png)

* **Para coincidencias de explorador con iPad**: [!UICONTROL Móvil] > [!UICONTROL Nombre de marketing del dispositivo] [!UICONTROL matches] [!DNL iPad] con un contenedor Y con [!UICONTROL Móvil] > [!UICONTROL Es tableta] es [!DNL true]

  ![iPad](/help/main/r-release-notes/assets/ipad.png)

* **Para coincidencias de explorador con iPhone**: [!UICONTROL Móvil] > [!UICONTROL Nombre de marketing del dispositivo] [!UICONTROL matches] [!DNL iPhone] con un contenedor Y con [!UICONTROL Móvil] > [!UICONTROL Es un teléfono móvil] es [!DNL true]

  ![iPhone](/help/main/r-release-notes/assets/iphone.png)

Existen muchas otras configuraciones posibles que se pueden utilizar, por ejemplo, cuando se niegan condiciones. Algunos ejemplos de condiciones negadas podrían tener el siguiente aspecto:

* **Para el navegador no coincide con iPhone**: [!UICONTROL Móvil] > [!UICONTROL Proveedor de dispositivo] [!UICONTROL no coincide con] [!UICONTROL Apple] con un contenedor O con [!UICONTROL Móvil] > [!UICONTROL Es un teléfono móvil] es [!UICONTROL false]

  ![No es un teléfono móvil](/help/main/r-release-notes/assets/mobile-phone-false.png)

* **Para el navegador no coincide con iPad**: [!UICONTROL Móvil] > [!UICONTROL Proveedor de dispositivo] [!UICONTROL no coincide con] [!UICONTROL Apple] con un contenedor O con [!UICONTROL Móvil] > [!UICONTROL Es tableta] es [!UICONTROL false].

  ![No es tableta](/help/main/r-release-notes/assets/tablet-false.png)

Si utiliza `user.browserType` en segmentos de JavaScript, los cambios podrían incluir lo siguiente:

* **BrowserType es iPhone**:

  Reemplazar:

  `user.browserType=="iphone"`

  Con:

  `user.mobile.deviceVendor == "Apple" && user.mobile.deviceModel && user.mobile.deviceModel.toLowerCase().includes("iphone")`

* **BrowserType no es iPhone**:

  Reemplazar:

  `user.browserType!="iphone"`

  Con:

  `user.mobile.deviceVendor != "Apple" || user.mobile.deviceModel == null !! !user.mobile.deviceModel.toLowerCase().includes("iphone")`

* **BrowserType es iPad**:

  Reemplazar:

  `user.browserType=="ipad"`

  Con:

  `user.mobile.deviceVendor == "Apple" && user.mobile.deviceModel && user.mobile.deviceModel.toLowerCase().includes("ipad")`

* **BrowserType no es iPad**:

  Reemplazar:

  `user.browserType!="ipad"`

  Con:

  `user.mobile.deviceVendor != "Apple" || user.mobile.deviceModel == null !! !user.mobile.deviceModel.toLowerCase().includes("ipad")`