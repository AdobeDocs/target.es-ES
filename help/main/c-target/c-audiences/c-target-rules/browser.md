---
keywords: opciones del explorador;tipo;tipo de explorador;idioma del explorador;idioma;versión;versión del explorador
description: Aprenda a crear audiencias en  [!DNL Adobe Target]  para segmentar usuarios que usen un explorador específico u opciones específicas del explorador cuando visiten la página.
title: ¿Puedo segmentar visitantes según el tipo de explorador?
feature: Audiences
exl-id: 8420bbe3-b58a-4ddb-89bb-0265dab6b5fc
source-git-commit: 784f41a73941877135a5902f2331972ba9d0e880
workflow-type: tm+mt
source-wordcount: '1015'
ht-degree: 33%

---

# [!UICONTROL Browser]

Puede segmentar usuarios que usen un navegador específico y opciones del navegador concretas cuando visiten una página.

Se pueden segmentar los siguientes navegadores:

* [!UICONTROL Chrome]
* [!UICONTROL Firefox]
* [!UICONTROL Safari]
* [!UICONTROL Internet Explorer]
* [!UICONTROL Microsoft Edge]
* [!UICONTROL Opera]
* [!DNL iPad]
* [!DNL iPhone]

>[!IMPORTANT]
>
>A partir de [!DNL Target] Standard/Premium 24.3.1 (del 4 al 6 de marzo de 2024), las audiencias integradas creadas con la interfaz de usuario de Target, como `Browser:iPad` y `Browser:iPhone`, se han actualizado para realizar el direccionamiento adecuado de [!DNL iPad] y [!DNL iPhone] con `profile.mobile.deviceVendor`, `profile.mobile.isMobilePhone` y `profile.mobile.isTablet`.
>
>Esta actualización no requiere ninguna acción por parte de los clientes. Las etiquetas de la interfaz de usuario de [!DNL Target] se cambiarán en el futuro y se anunciarán en [[!DNL Target] notas de la versión (actual)](/help/main/r-release-notes/release-notes.md) cuando se realicen estos cambios.
>
>Para ver la configuración de la solución, consulta [Actualizaciones para [!DNL iPad] y [!DNL iPhone] en [!UICONTROL Browser] atributos de audiencia (30 de abril de 2024)](#updates) a continuación.

Hay dos formar de segmentar según el navegador:

* **Audiencia prediseñada:** utilice la audiencia prediseñada si quiere segmentar solo los visitantes que usan un navegador concreto para visitar el sitio. Por ejemplo, si ofrece una extensión [!DNL Chrome], solo se dirigiría a [!DNL Chrome] usuarios.

   1. Al configurar la actividad, seleccione el explorador en la lista desplegable.

      Esta opción dirige la actividad únicamente a los visitantes que usan el navegador especificado.

      ![Usuarios de Chrome de destino](/help/main/c-target/c-audiences/c-target-rules/assets/target-chrome.png)

* **Regla de audiencia de explorador personalizada:** Una audiencia personalizada le permite segmentar varios exploradores o configurar reglas o exclusiones para exploradores, versiones de exploradores o idiomas específicos. Esta funcionalidad proporciona una flexibilidad considerable a la hora de segmentar una actividad según los atributos del explorador.

   1. En la interfaz [!DNL Target], haga clic en **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
   1. Asigne un nombre a la audiencia y añada una descripción opcional.
   1. Arrastre y suelte **[!UICONTROL Browser]** en el Generador de audiencias.

      ![Reglas > Explorador](assets/target_browser.png)

   1. Haga clic en **[!UICONTROL Select]** y luego seleccione una de las siguientes opciones:

      * **Tipo:** dirija la actividad a un navegador o exclúyalo. Consulte [Tipo](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_6ADC758F23F145B3A310151546D83D56).
      * **Idioma:** Dirija la actividad a ciertos navegadores que están configurados para usar idiomas específicos o exclúyalos. Consulte [Idioma](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_7520D1AA464A45A6843EABE2D2B431A1).
      * **Versión:** dirija la actividad a ciertas versiones del navegador o exclúyalas. Consulte [Versión](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_37CC8CE45DA04E8682AE6388321BA6EF).

   1. (Opcional) Configure reglas adicionales para la audiencia.
   1. Haga clic en **[!UICONTROL Done]**.

  El siguiente ejemplo muestra una audiencia que incluye [!DNL Microsoft Edge] usuarios de las versiones 91 o 92:

  ![Target Edge 91 o 92](assets/target_edge.png)

## Opciones del navegador {#concept_221D8EEF53CC45AEACEB17CF336A3658}

Dirija la actividad a visitantes o exclúyalos en función del tipo, el idioma o la versión de navegador que tengan.

### Tipo  {#section_6ADC758F23F145B3A310151546D83D56}

Dirija la actividad a un navegador o exclúyalo.

Seleccione **[!UICONTROL Type]** y, a continuación, elija igual a o no es igual a.

* [!UICONTROL Equals]: seleccione como destino los exploradores seleccionados.
* [!UICONTROL Does not equal]: excluir los exploradores seleccionados.

Seleccione uno o varios. Si hay varias opciones, se conectan con un parámetro O.

### Idioma  {#section_7520D1AA464A45A6843EABE2D2B431A1}

Dirija la actividad ciertos navegadores que estén configurados en idiomas específicos o exclúyalos.

Por ejemplo, si una oferta solo está disponible en español, puede segmentar exploradores en los que el idioma establecido sea el español. O, si su página no está habilitada para los idiomas de doble byte, puede excluir los navegadores en los que se haya establecido un idioma asiático oriental.

La inclusión o exclusión de idiomas de navegador puede proporcionar una segmentación del visitante más precisa que segmentarlos según la ubicación geográfica, al menos en aquellos casos en los que el idioma es más importante que la ubicación. Si, por ejemplo, ofrece un artículo escrito en español, puede dirigirlo a los países de habla hispana o a los navegadores en los que el idioma establecido es el español. Segmentar según el navegador facilita el artículo a los hablantes de español ubicados en países en los que el español no es el principal idioma.

Seleccione **[!UICONTROL Language]** y, a continuación, elija igual a o no es igual a.

* [!UICONTROL Equals]: establezca como destino los idiomas de explorador seleccionados.
* [!UICONTROL Does not equal]: excluir los idiomas de explorador seleccionados.

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

Por ejemplo, si la página no aparece correctamente en [!DNL Internet Explorer] versión 11 o anteriores, puede crear una audiencia que excluya esas versiones. En ese caso, debe configurar una regla en la que el tipo de explorador sea igual a [!DNL Internet Explorer] y agregar una segunda regla en la que la versión sea menor o igual que 11.

Seleccione **[!UICONTROL Version]** y luego elija un operador:

* [!UICONTROL Equals]
* [!UICONTROL Does not equal]
* [!UICONTROL Is greater than]
* Es mayor que o igual a
* [!UICONTROL Is less than]
* [!UICONTROL Is less than or equal to]

Escriba el número de versión. En el campo de texto solo se pueden introducir versiones principales. Es decir, la versión especificada incluye las versiones secundarias de la principal. Por ejemplo, si especifica la versión 10, también se incluyen los visitantes de la versión 10.1.

Si hay varias opciones, se conectan con un parámetro O.

## Vídeo de formación: Creación de audiencias ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo contiene información sobre el uso de las categorías de audiencias.

* Crear audiencias
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)

## Actualizaciones para [!DNL iPad] y [!DNL iPhone] en [!UICONTROL Browser] atributos de audiencia (30 de abril de 2024) {#updates}

[!DNL Adobe Target] le permite [segmentar cualquiera de los atributos de categoría](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), incluidos los usuarios que usan un explorador específico u opciones del explorador cuando visitan la página.

A partir de [!DNL Target] Standard/Premium 24.3.1 (del 4 al 6 de marzo de 2024), las audiencias integradas creadas con la interfaz de usuario de Target, como `Browser:iPad` y `Browser:iPhone`, se han actualizado para realizar el direccionamiento adecuado de [!DNL iPad] y [!DNL iPhone] con `profile.mobile.deviceVendor`, `profile.mobile.isMobilePhone` y `profile.mobile.isTablet`.

Las audiencias integradas creadas con la interfaz de usuario de [!DNL Target], como `Browser:iPad` y `Browser:iPhone`, se moverán automáticamente a la nueva definición de audiencia y no requiere ninguna acción por parte de los clientes. Sin embargo, en adelante, debería usar la configuración [que se describe a continuación](#ui).

Si usa `user.browserType` en cualquier script de perfil para comprobar si es un [!DNL iPhone] o [!DNL iPad] (por ejemplo, `user.browserType == 'iphone'` o `user.browserType != 'ipad'`), esos scripts de perfil deben cambiarse como se indica a continuación [6} antes del 30 de abril de 2024 para garantizar que estas audiencias sigan funcionando según lo esperado.](#profile-scripts)

Las audiencias de JavaScript son audiencias heredadas que utilizan expresiones [!DNL Target] que quedaron obsoletas con la interfaz de usuario [!DNL Target Classic]. Estas audiencias se pueden modificar únicamente mediante API. Los clientes deben actualizar estas audiencias solo si siguen utilizando audiencias heredadas en las actividades de.

### Audiencias creadas con la interfaz de usuario de [!DNL Target] {#ui}

Se pueden utilizar los siguientes ajustes a partir de ahora:

* **Para coincidencias de explorador[!DNL Apple]**: [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL matches] [!DNL Apple]

  ![Apple](/help/main/r-release-notes/assets/apple.png)

* **Para que el explorador coincida con la tableta**: [!UICONTROL Mobile] > [!UICONTROL is Tablet] > [!UICONTROL true]

  ![móvil es tableta](/help/main/r-release-notes/assets/is-tablet.png)

* **Para que el explorador coincida con iPad**: [!UICONTROL Mobile] > [!UICONTROL Device Marketing Name] [!UICONTROL matches] [!DNL iPad] con un contenedor Y con [!UICONTROL Mobile] > [!UICONTROL Is Tablet] es [!DNL true]

  ![iPad](/help/main/r-release-notes/assets/ipad.png)

* **Para que el explorador coincida con iPhone**: [!UICONTROL Mobile] > [!UICONTROL Device Marketing Name] [!UICONTROL matches] [!DNL iPhone] con un contenedor Y con [!UICONTROL Mobile] > [!UICONTROL Is Mobile Phone] es [!DNL true]

  ![iPhone](/help/main/r-release-notes/assets/iphone.png)

Existen muchas otras configuraciones posibles que se pueden utilizar, por ejemplo, cuando se niegan condiciones. Algunos ejemplos de condiciones negadas podrían tener el siguiente aspecto:

* **Para el explorador no coincide con iPhone**: [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL does not match] [!UICONTROL Apple] con un contenedor O con [!UICONTROL Mobile] > [!UICONTROL Is Mobile Phone] es [!UICONTROL false]

  ![No es un teléfono móvil](/help/main/r-release-notes/assets/mobile-phone-false.png)

* **Para el explorador no coincide con iPad**: [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL does not match] [!UICONTROL Apple] con un contenedor O con [!UICONTROL Mobile] > [!UICONTROL Is Tablet] es [!UICONTROL false].

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