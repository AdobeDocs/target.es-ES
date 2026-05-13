---
keywords: compositor de experiencias visuales;vec;url predeterminada;compositor de experiencias mejorado;eec;contenido mixto;instantáneas de experiencias;ventanilla móvil;css;selectores css
description: Aprenda a configurar el  [!DNL Target] Compositor de experiencias visuales (VEC) de Adobe especificando su configuración general, la configuración de la ventanilla móvil y los selectores CSS.
title: ¿Cómo configuro el Compositor de experiencias visuales (VEC)?
feature: Administration & Configuration
role: Admin
exl-id: cf6c9ece-6745-477e-81ac-a3e9a9fddb09
TQID: https://experienceleague.adobe.com/E1ck4-aG4txqaFLs3t3-8bN-BQIoY8stRASTRJfhZMY
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
subfeature_v2: id: b1d5cd6a-4ed3-43f6-9a52-2721acea1129id: c011fe9c-b94b-4a88-93d8-f2acece55112id: fc9c2184-9102-403f-bd6c-0055021e4bea
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11id: d095671a-1355-40aa-8b5f-06c33c68080bid: e0eb8757-182f-49f3-94a4-1587d16f5094id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 676
ht-degree: 49%

---

# Configurar [!UICONTROL Visual Experience Composer]

Configure [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) especificando su configuración general, la configuración de las ventanillas móviles y los selectores CSS.

Para obtener acceso a la página de configuración de [!UICONTROL Visual Experience Composer], haga clic en **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer].**

{{permissions-update}}

>[!NOTE]
>
>Tenga en cuenta que la configuración de esta página se aplica a toda la cuenta de [!DNL Target].

## Ajustes generales

Puede especificar la configuración general de [!UICONTROL Visual Experience Composer].

![Sección de configuración general](/help/main/administrating-target/assets/general-settings.png)

Las configuraciones disponibles son las siguientes:

### URL predeterminada

Establecer la dirección URL predeterminada utilizada por [!UICONTROL Visual Experience Composer]. Esta es la página predeterminada, como la página principal, que se utiliza siempre que quiere configurar una experiencia para cada nueva actividad. Si no establece una URL predeterminada, tiene que escribir una URL para cada actividad en el momento de la creación.

### Activar el compositor de experiencias mejorado {#eec}

Permite editar en sitios con eliminación de iFrames y sitios con contenido mixto. Es posible que algunos sitios no sean compatibles con la versión mejorada. Anule la selección de esta opción para revertir al(a) [!UICONTROL Visual Experience Composer] original. La publicación de actividades en los sitios no se verá afectada por esta opción.

Para obtener más información, consulte [Solución de problemas del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

También puede habilitar [!UICONTROL Enhanced Experience Composer] en el nivel de actividad.

### Cargar contenido combinado

Habilite el contenido combinado al abrir un sitio web mediante [!UICONTROL Enhanced Experience Composer] (EEC). Al habilitar esta opción, se evitará una carga excesiva de recursos estáticos a través de [!DNL Target] servidores proxy.

Esta opción resulta útil si, por ejemplo:

* Los encabezados de la Política de seguridad de contenido (CSP) permiten cargar contenido mixto sin el uso de servidores proxy con el EEC habilitado.
* El sitio web HTTP se enfrenta a un mayor tiempo de carga en el EEC, donde JavaScript, imágenes, etc. tardan más en cargarse mediante proxy.

### Cree instantáneas de experiencias en el diagrama de flujo de las actividades

Cuando se habilitan las instantáneas de experiencia, se generan miniaturas de las experiencias en el diagrama de flujo de trabajo de la actividad. Si deshabilita las instantáneas, podría obtener un rendimiento más rápido para algunos usuarios.

## Configuración de las ventanillas móviles

>[!NOTE]
>
>La configuración de [!UICONTROL Mobile Viewport Configuration] es una característica de [Target Premium](/help/main/c-intro/intro.md#premium).


Puede añadir dispositivos para usarlos al obtener una vista previa de las experiencias. Cada dispositivo tiene una audiencia asociada.

![Sección de configuración de ventanilla móvil](/help/main/administrating-target/assets/mobile-viewport-configuration.png)

Haga clic en **[!UICONTROL Add]**, especifique un nombre descriptivo para la ventanilla móvil, especifique la anchura y la altura, seleccione el sistema operativo deseado y, a continuación, haga clic en [!UICONTROL Save].

Si desea información sobre cómo añadir una ventanilla móvil, consulte [Configuración de la ventanilla móvil](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md).

## Selectores CSS {#css}

Explica cómo [!DNL Target] genera los selectores CSS.

![Sección de selectores CSS](/help/main/administrating-target/assets/css-selectors.png)

Estas opciones ayudan a [!DNL Target] a comprender la estructura de su sitio para generar mejores selectores CSS para la entrega de contenido. De forma predeterminada, [!DNL Target] genera selectores en función de los ID de elementos de la página. Si el sitio usa pocos ID, o ID duplicados en la misma página, usar estas clases puede ser una mejor opción.

Puede elegir una o ambas de las siguientes opciones:

### Usar identificadores de elementos

Desmarque esta opción si se usa el mismo identificador para varios elementos o si el identificador de elemento puede cambiar en la carga de página.

### Usar clases de elementos

De manera predeterminada, [!DNL Target] solo usa ID de elementos. Sin embargo, si la página está diseñada para usar clases para identificar elementos, como una página creada con [!DNL Adobe Experience Manager], también debería seleccionar [!UICONTROL Use element classes].

>[!NOTE]
>
>Aunque se ha hecho todo lo posible para garantizar la precisión, tenga en cuenta que el uso de clases puede provocar errores. Si no selecciona ninguna opción, también se ve afectada la precisión. El orden de la precisión es ID > clases > ninguna opción. También asegúrese de probar la página para asegurarse de que los selectores sean correctos.

Puede anular esta configuración por actividad (haga clic en el icono de engranaje [!UICONTROL Settings] y, a continuación, seleccione [!UICONTROL CSS Selectors]). Esto resulta especialmente útil si tiene varios sitios que están configurados de forma diferente.

>[!NOTE]
>
>No está disponible anular la configuración por actividad en las actividades [!UICONTROL Automated Personalization] y [!UICONTROL Multivariate Testing].  Consulte [Selectores de elementos utilizados en el Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md) para obtener información adicional sobre selectores.

## Vídeo de formación: Preferencias de cuenta (7:33) ![Distintivo de información general](/help/main/assets/overview.png)

Este vídeo incluye información sobre las preferencias de cuenta.

* Describir la configuración de la cuenta disponible en [!DNL Target Standard]

>[!NOTE]
>
>La interfaz de usuario del menú [!DNL Target] [!UICONTROL Administration] (anteriormente [!UICONTROL Setup]) se ha rediseñado para proporcionar un rendimiento mejorado, reducir el tiempo de mantenimiento necesario al lanzar nuevas características y mejorar la experiencia del usuario en todo el producto. La información que aparece en el siguiente vídeo es, en general, correcta; sin embargo, las opciones pueden estar en ubicaciones ligeramente diferentes. Los vídeos actualizados se publicarán próximamente.

>[!VIDEO](https://video.tv.adobe.com/v/17379)
