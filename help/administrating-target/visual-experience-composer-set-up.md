---
keywords: visual experience composer;vec;default url;enhanced experience composer;eec;mixed content;experience snapshots;mobile viewport;css;css selectors
description: Configure el Compositor de experiencias visuales (VEC) de Adobe Target especificando su configuración general, la configuración de ventanilla móvil y los selectores CSS.
title: Configuración del Compositor de experiencias visuales de Adobe Target
feature: administration general
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 51%

---


# Configuración del Compositor de experiencias visuales

Configure el Compositor [!DNL Adobe Target] de experiencias  visuales (VEC) especificando su configuración general, la configuración de ventanilla móvil y los selectores CSS.

Para acceder a la página de configuración del Compositor [!UICONTROL de experiencias] visuales, haga clic en **[!UICONTROL Administración]** > Compositor **[!UICONTROL de experiencias]visuales.**

>[!NOTE]
>
>Tenga en cuenta que la configuración de esta página se aplica a toda la [!DNL Target] cuenta.

![Página de configuración del Compositor de experiencias visuales](/help/administrating-target/assets/vec.png)

## Ajustes generales

Puede especificar la configuración general del Compositor de experiencias visuales.

![Sección Configuración general](/help/administrating-target/assets/general-settings.png)

Las configuraciones disponibles son las siguientes:

### Dirección URL predeterminada

La dirección URL predeterminada que utiliza el [!UICONTROL Compositor de experiencias visuales]. Esta es la página predeterminada, como la página principal, que se utiliza siempre que quiere configurar una experiencia para cada nueva actividad. Si no establece una URL predeterminada, tiene que escribir una URL para cada actividad en el momento de la creación.

### Activar el compositor de experiencias mejorado

Permite editar en sitios con eliminación de iFrames y sitios con contenido mixto. Es posible que algunos sitios no sean compatibles con la versión mejorada. Deselect this option to revert to the original [!UICONTROL Visual Experience Composer]. La publicación de actividades en los sitios no se verá afectada por esta opción.

Para obtener más información, consulte [Solución de problemas del Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

You can also enable the [!UICONTROL Enhanced Experience Composer] at the activity level.

### Cargar contenido combinado

Enable mixed content while opening a website using the [!UICONTROL Enhanced Experience Composer] (EEC). Enabling this option avoids the extra overhead of loading static resources via [!DNL Target] proxy servers.

Esta opción resulta útil si, por ejemplo:

* Los encabezados de la directiva de seguridad de contenido (CSP) permiten cargar contenido mixto sin el uso de servidores proxy con la EEC habilitada.
* El sitio web HTTP se enfrenta a un aumento del tiempo de carga en EEC, donde JavaScript, imágenes, etc. tardan más en cargarse mediante proxy.

### Generar instantáneas de experiencia en el diagrama de flujo de actividad

Cuando se habilitan las instantáneas de experiencia, se generan miniaturas de las experiencias en el diagrama de flujo de trabajo de la actividad. Si deshabilita las instantáneas, podría obtener un rendimiento más rápido para algunos usuarios.

## ![Configuración de la ventanilla](/help/assets/premium.png) Premium para móviles

Puede añadir dispositivos para usarlos al obtener una vista previa de las experiencias. Cada dispositivo tiene una audiencia asociada.

![Sección Configuración de ventanillas móviles](/help/administrating-target/assets/mobile-viewport-configuration.png)

Click **[!UICONTROL Add]**, specify a descriptive name for the mobile viewport, specify the width and height, select the desired operating system, then click [!UICONTROL Save].

Si desea información sobre cómo añadir una ventanilla móvil, consulte [Configuración de la ventanilla móvil](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md).

## Selectores CSS {#css}

Explica cómo [!DNL Target] genera los selectores CSS.

![Sección Selectores CSS](/help/administrating-target/assets/css-selectors.png)

Estas opciones ayudan a [!DNL Target] a comprender la estructura de su sitio para generar mejores selectores CSS para la entrega de contenido. De forma predeterminada, [!DNL Target] genera selectores en función de los ID de elementos de la página. Si el sitio usa pocos ID, o ID duplicados en la misma página, usar estas clases puede ser una mejor opción.

Puede elegir una o ambas de las siguientes opciones:

### Usar identificadores de elementos

Desmarque esta opción si se usa el mismo identificador para varios elementos o si el identificador de elemento puede cambiar en la carga de página.

### Usar clases de elementos

De manera predeterminada, [!DNL Target] solo usa ID de elementos. Sin embargo, si la página está diseñada para usar clases para identificar elementos, como una página creada con [!DNL Adobe Experience Manager], también debería seleccionar [!UICONTROL Usar clases de elementos].

>[!NOTE]
>
>Aunque se ha hecho todo para garantizar la precisión, tenga en cuenta que el uso de clases puede dar como resultado errores. Si no selecciona ninguna opción, también se ve afectada la precisión. El orden de la precisión es ID > clases > ninguna opción. También asegúrese de probar la página para asegurarse de que los selectores sean correctos.

Puede anular esta configuración por actividad (haga clic en el icono de engranaje [!UICONTROL Configuración], luego seleccione [!UICONTROL Selectores CSS]). Esto resulta especialmente útil si tiene varios sitios que están configurados de forma diferente.

>[!NOTE]
>
>Overriding the setting per activity is not available in [!UICONTROL Automated Personalization] and [!UICONTROL Multivariate Testing] activities.  Consulte [Selectores de elementos utilizados en el Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/vec-selectors.md) para obtener información adicional sobre selectores.

## Vídeo de capacitación: Distintivo ![Información general de preferencias de cuenta (7:33)](/help/assets/overview.png)

Este vídeo incluye información sobre las preferencias de cuenta.

* Describir la configuración de la cuenta disponible en [!DNL Target Standard]

>[!NOTE]
>
>La interfaz de usuario del menú [!DNL Target] Administración [!UICONTROL (anteriormente] Ajustes ) se ha rediseñado para proporcionar un rendimiento mejorado, reducir el tiempo de mantenimiento necesario al lanzar nuevas funciones y mejorar la experiencia del usuario en todo el producto. La información del siguiente vídeo es, en general, correcta; sin embargo, las opciones pueden estar en ubicaciones ligeramente diferentes. Los vídeos actualizados se publicarán pronto.

>[!VIDEO](https://video.tv.adobe.com/v/17379)
