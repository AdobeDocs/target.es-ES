---
keywords: opciones del explorador;tipo;tipo de explorador;idioma del explorador;idioma;versión;versión del explorador
description: Aprenda a crear audiencias en  [!DNL Adobe Target]  para segmentar usuarios que usen un explorador específico u opciones específicas del explorador cuando visiten la página.
title: ¿Puedo segmentar visitantes según el tipo de explorador?
feature: Audiences
exl-id: 8420bbe3-b58a-4ddb-89bb-0265dab6b5fc
TQID: https://experienceleague.adobe.com/D7cLw1OVT61u8SgkjpzEvWylcX1uz14Ia4rf8jAJyXs
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1116
ht-degree: 35%

---

# [!UICONTROL Explorador]

Puede segmentar usuarios que usen un navegador específico y opciones del navegador concretas cuando visiten una página.

Se pueden segmentar los siguientes navegadores:

* [!UICONTROL Chrome]
* [!UICONTROL Firefox]
* [!UICONTROL Safari]
* [!UICONTROL Internet Explorer]
* [!UICONTROL Microsoft Edge]
* [!UICONTROL Ópera]
* [!DNL iPad]
* [!DNL iPhone]

>[!IMPORTANT]
>
>A partir de [!DNL Target] Standard/Premium 24.3.1 (del 4 al 6 de marzo de 2024), las audiencias integradas creadas con la interfaz de usuario de Target, como `Browser:iPad` y `Browser:iPhone`, se han actualizado para realizar el direccionamiento adecuado de [!DNL iPad] y [!DNL iPhone] con `profile.mobile.deviceVendor`, `profile.mobile.isMobilePhone` y `profile.mobile.isTablet`.
>
>Esta actualización no requiere ninguna acción por parte de los clientes. Las etiquetas de la interfaz de usuario de [!DNL Target] se cambiarán en el futuro y se anunciarán en [[!DNL Target] notas de la versión (actual)](/help/main/r-release-notes/release-notes.md) cuando se realicen estos cambios.
>
>Para obtener la configuración de la solución, consulta [Actualizaciones para [!DNL iPad] y [!DNL iPhone] en los atributos de audiencia de [!UICONTROL Browser] (30 de abril de 2024)](#updates) a continuación.

Hay dos formar de segmentar según el navegador:

* **Audiencia prediseñada:** utilice la audiencia prediseñada si quiere segmentar solo los visitantes que usan un navegador concreto para visitar el sitio. Por ejemplo, si ofrece una extensión [!DNL Chrome], solo se dirigiría a [!DNL Chrome] usuarios.

   1. Al configurar la actividad, seleccione el explorador en la lista desplegable.

      Esta opción dirige la actividad únicamente a los visitantes que usan el navegador especificado.

      ![Usuarios de Chrome de destino](/help/main/c-target/c-audiences/c-target-rules/assets/target-chrome.png)

* **Regla de audiencia de explorador personalizada:** Una audiencia personalizada le permite segmentar varios exploradores o configurar reglas o exclusiones para exploradores, versiones de exploradores o idiomas específicos. Esta funcionalidad proporciona una flexibilidad considerable a la hora de segmentar una actividad según los atributos del explorador.

   1. En la interfaz [!DNL Target], haga clic en **[!UICONTROL Audiencias]** > **[!UICONTROL Crear audiencia]**.
   1. Asigne un nombre a la audiencia y añada una descripción opcional.
   1. Arrastre y suelte **[!UICONTROL Browser]** en el Generador de audiencias.

      ![Reglas > Explorador](assets/target_browser.png)

   1. Haga clic en **[!UICONTROL Seleccionar]** y, a continuación, elija una de estas opciones:

      * **Tipo:** dirija la actividad a un navegador o exclúyalo. Consulte [Tipo](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_6ADC758F23F145B3A310151546D83D56).
      * **Idioma:** Dirija la actividad a ciertos navegadores que están configurados para usar idiomas específicos o exclúyalos. Consulte [Idioma](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_7520D1AA464A45A6843EABE2D2B431A1).
      * **Versión:** dirija la actividad a ciertas versiones del navegador o exclúyalas. Consulte [Versión](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_37CC8CE45DA04E8682AE6388321BA6EF).

   1. (Opcional) Configure reglas adicionales para la audiencia.
   1. Haga clic en **[!UICONTROL Finalizado]**.

  El siguiente ejemplo muestra una audiencia que incluye [!DNL Microsoft Edge] usuarios de las versiones 91 o 92:

  ![Target Edge 91 o 92](assets/target_edge.png)

## Opciones del navegador {#concept_221D8EEF53CC45AEACEB17CF336A3658}

Dirija la actividad a visitantes o exclúyalos en función del tipo, el idioma o la versión de navegador que tengan.

### Tipo {#section_6ADC758F23F145B3A310151546D83D56}

Dirija la actividad a un navegador o exclúyalo.

Seleccione **[!UICONTROL Tipo]** y, a continuación, elija igual a o no es igual a.

* [!UICONTROL Es igual a]: Oriente los exploradores seleccionados.
* [!UICONTROL No es igual a]: excluir los exploradores seleccionados.

Seleccione uno o varios. Si hay varias opciones, se conectan con un parámetro O.

### Idioma {#section_7520D1AA464A45A6843EABE2D2B431A1}

Dirija la actividad ciertos navegadores que estén configurados en idiomas específicos o exclúyalos.

Por ejemplo, si una oferta solo está disponible en español, puede segmentar exploradores en los que el idioma establecido sea el español. O, si su página no está habilitada para los idiomas de doble byte, puede excluir los navegadores en los que se haya establecido un idioma asiático oriental.

La inclusión o exclusión de idiomas de navegador puede proporcionar una segmentación del visitante más precisa que segmentarlos según la ubicación geográfica, al menos en aquellos casos en los que el idioma es más importante que la ubicación. Si, por ejemplo, ofrece un artículo escrito en español, puede dirigirlo a los países de habla hispana o a los navegadores en los que el idioma establecido es el español. Segmentar según el navegador facilita el artículo a los hablantes de español ubicados en países en los que el español no es el principal idioma.

Seleccione **[!UICONTROL Idioma]** y, a continuación, elija igual a o no es igual a.

* [!UICONTROL Es igual a]: Oriente los idiomas de explorador seleccionados.
* [!UICONTROL No es igual a]: excluir los idiomas de explorador seleccionados.

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

### Versión {#section_37CC8CE45DA04E8682AE6388321BA6EF}

Dirija la actividad a ciertas versiones del navegador o exclúyalas.

Por ejemplo, si la página no aparece correctamente en [!DNL Internet Explorer] versión 11 o anteriores, puede crear una audiencia que excluya esas versiones. En ese caso, debe configurar una regla en la que el tipo de explorador sea igual a [!DNL Internet Explorer] y agregar una segunda regla en la que la versión sea menor o igual que 11.

Seleccione **[!UICONTROL Versión]** y, a continuación, elija un operador:

* [!UICONTROL Es igual a]
* [!UICONTROL No es igual a]
* [!UICONTROL Es mayor que]
* Es mayor que o igual a
* [!UICONTROL &#x200B; es menor que &#x200B;]
* [!UICONTROL Es menor o igual que]

Escriba el nombre de la versión. En el campo de texto solo se pueden introducir versiones principales. Es decir, la versión especificada incluye las versiones secundarias de la principal. Por ejemplo, si especifica la versión 10, también se incluyen los visitantes de la versión 10.1.

Si hay varias opciones, se conectan con un parámetro O.

## Vídeo de formación: Creación de audiencias ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo contiene información sobre el uso de las categorías de audiencias.

* Crear públicos
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)

## Actualizaciones para [!DNL iPad] y [!DNL iPhone] en los atributos de audiencia de [!UICONTROL Browser] (30 de abril de 2024) {#updates}

[!DNL Adobe Target] le permite [segmentar cualquiera de los atributos de categoría](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), incluidos los usuarios que usan un explorador específico u opciones del explorador cuando visitan la página.

A partir de [!DNL Target] Standard/Premium 24.3.1 (del 4 al 6 de marzo de 2024), las audiencias integradas creadas con la interfaz de usuario de Target, como `Browser:iPad` y `Browser:iPhone`, se han actualizado para realizar el direccionamiento adecuado de [!DNL iPad] y [!DNL iPhone] con `profile.mobile.deviceVendor`, `profile.mobile.isMobilePhone` y `profile.mobile.isTablet`.

Las audiencias integradas creadas con la interfaz de usuario de [!DNL Target], como `Browser:iPad` y `Browser:iPhone`, se moverán automáticamente a la nueva definición de audiencia y no requiere ninguna acción por parte de los clientes. Sin embargo, en adelante, debería usar la configuración [que se describe a continuación](#ui).

Si usa `user.browserType` en cualquier script de perfil para comprobar si es un [!DNL iPhone] o [!DNL iPad] (por ejemplo, `user.browserType == 'iphone'` o `user.browserType != 'ipad'`), esos scripts de perfil deben cambiarse como se indica a continuación [6&rbrace; antes del 30 de abril de 2024 para garantizar que estas audiencias sigan funcionando según lo esperado.](#profile-scripts)

Las audiencias de JavaScript son audiencias heredadas que utilizan expresiones [!DNL Target] que quedaron obsoletas con la interfaz de usuario [!DNL Target Classic]. Estas audiencias se pueden modificar únicamente mediante API. Los clientes deben actualizar estas audiencias solo si siguen utilizando audiencias heredadas en las actividades de.

### Audiencias creadas con la interfaz de usuario de [!DNL Target] {#ui}

Se pueden utilizar los siguientes ajustes a partir de ahora:

* **Para coincidencias de explorador[!DNL Apple]**: [!UICONTROL Móvil] > [!UICONTROL Proveedor de dispositivo] [!UICONTROL coincide] [!DNL Apple]

  ![Apple](/help/main/r-release-notes/assets/apple.png)

* **Para que el explorador coincida con la tableta**: [!UICONTROL Móvil] > [!UICONTROL es una tableta] > [!UICONTROL true]

  ![móvil es tableta](/help/main/r-release-notes/assets/is-tablet.png)

* **Para las coincidencias de explorador con iPad**: [!UICONTROL Móvil] > [!UICONTROL Nombre de marketing de dispositivo] [!UICONTROL coincide] [!DNL iPad] con un contenedor Y con [!UICONTROL Móvil] > [!UICONTROL Es una tableta] es [!DNL true]

  ![iPad](/help/main/r-release-notes/assets/ipad.png)

* **Para las coincidencias de explorador con iPhone**: [!UICONTROL Móvil] > [!UICONTROL Nombre de marketing de dispositivo] [!UICONTROL coincide] [!DNL iPhone] con un contenedor Y con [!UICONTROL Móvil] > [!UICONTROL Es un teléfono móvil] es [!DNL true]

  ![iPhone](/help/main/r-release-notes/assets/iphone.png)

Existen muchas otras configuraciones posibles que se pueden utilizar, por ejemplo, cuando se niegan condiciones. Algunos ejemplos de condiciones negadas podrían tener el siguiente aspecto:

* **Para el explorador no coincide con iPhone**: [!UICONTROL Móvil] > [!UICONTROL Proveedor de dispositivo] [!UICONTROL no coincide] [!UICONTROL Apple] con un contenedor O con [!UICONTROL Móvil] > [!UICONTROL Es un teléfono móvil] [!UICONTROL falso]

  ![No es un teléfono móvil](/help/main/r-release-notes/assets/mobile-phone-false.png)

* **Para el explorador no coincide con iPad**: [!UICONTROL Móvil] > [!UICONTROL Proveedor de dispositivo] [!UICONTROL no coincide] [!UICONTROL Apple] con un contenedor O con [!UICONTROL Móvil] > [!UICONTROL Es una tableta] que es [!UICONTROL falsa].

  ![No es tablet](/help/main/r-release-notes/assets/tablet-false.png)

### Audiencias creadas con scripts de perfil {#profile-scripts}

Si usa `user.browserType` en audiencias heredadas de [!DNL Target Classic] o en scripts de perfil, los cambios deben incluir lo siguiente:

* **BrowserType es iPhone**:

  Reemplazar:

  `user.browserType=="iphone"`

  Con:

  `profile.mobile.deviceVendor == "Apple" && profile.mobile.isMobilePhone`

* **BrowserType no es iPhone**:

  Reemplazar:

  `user.browserType!="iphone"`

  Con:

  `profile.mobile.deviceVendor != "Apple" || !profile.mobile.isMobilePhone`

* **BrowserType es iPad**:

  Reemplazar:

  `user.browserType=="ipad"`

  Con:

  `profile.mobile.deviceVendor == "Apple" && profile.mobile.isTablet`

* **BrowserType no es iPad**:

  Reemplazar:

  `user.browserType!="ipad"`

  Con:

  `profile.mobile.deviceVendor != "Apple" || !profile.mobile.isTablet`