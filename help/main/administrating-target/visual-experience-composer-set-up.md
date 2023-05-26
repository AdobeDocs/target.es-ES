---
keywords: compositor de experiencias visuales;vec;url predeterminada;compositor de experiencias mejorado;eec;contenido mixto;instantáneas de experiencias;ventanilla móvil;css;selectores css
description: Obtenga información sobre cómo configurar el Adobe [!DNL Target] Compositor de experiencias visuales (VEC) especificando su configuración general, la configuración de las ventanillas móviles y los selectores CSS.
title: ¿Cómo configuro el Compositor de experiencias visuales (VEC)?
feature: Administration & Configuration
role: Admin
exl-id: cf6c9ece-6745-477e-81ac-a3e9a9fddb09
source-git-commit: fa11f93058b69e5e59e0ee20c65cffa4a1344ca0
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 57%

---

# Configuración del Compositor de experiencias visuales

Configure las variables [!DNL Adobe Target] [!UICONTROL Compositor de experiencias visuales] (VEC) especificando su configuración general, la configuración de la ventanilla móvil y los selectores CSS.

Para acceder a [!UICONTROL Compositor de experiencias visuales] , haga clic en **[!UICONTROL Administration]** > **[!UICONTROL Compositor de experiencias visuales].**

>[!NOTE]
>
>Tenga en cuenta que la configuración de esta página se aplica a todo el [!DNL Target] cuenta.

![Página de configuración del Compositor de experiencias visuales](/help/main/administrating-target/assets/vec.png)

## Ajustes generales

Puede especificar la configuración general del Compositor de experiencias visuales.

![Sección Configuración general](/help/main/administrating-target/assets/general-settings.png)

Las configuraciones disponibles son las siguientes:

### URL predeterminada

La dirección URL predeterminada que utiliza el [!UICONTROL Compositor de experiencias visuales]. Esta es la página predeterminada, como la página principal, que se utiliza siempre que quiere configurar una experiencia para cada nueva actividad. Si no establece una URL predeterminada, tiene que escribir una URL para cada actividad en el momento de la creación.

### Activar el compositor de experiencias mejorado {#eec}

Permite editar en sitios con eliminación de iFrames y sitios con contenido mixto. Es posible que algunos sitios no sean compatibles con la versión mejorada. Anule la selección de esta opción para volver al original [!UICONTROL Compositor de experiencias visuales]. La publicación de actividades en los sitios no se verá afectada por esta opción.

Para obtener más información, consulte [Solución de problemas del Compositor de experiencias visuales.](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)

También puede activar la variable [!UICONTROL Compositor de experiencias mejorado] en el nivel de actividad.

### Cargar contenido combinado

Habilite el contenido combinado al abrir un sitio web mediante [!UICONTROL Compositor de experiencias mejorado] (CEE). Al habilitar esta opción, se evitará una carga excesiva de recursos estáticos mediante [!DNL Target] servidores proxy.

Esta opción resulta útil si, por ejemplo:

* Los encabezados de la Política de seguridad de contenido (CSP) permiten cargar contenido mixto sin el uso de servidores proxy con el EEC habilitado.
* El sitio web HTTP tiene una mayor cantidad de tiempo de carga en el EEC, donde JavaScript, imágenes, etc. tardan más de lo esperado en cargarse mediante proxy.

### Cree instantáneas de experiencias en el diagrama de flujo de las actividades

Cuando se habilitan las instantáneas de experiencia, se generan miniaturas de las experiencias en el diagrama de flujo de trabajo de la actividad. Si deshabilita las instantáneas, podría obtener un rendimiento más rápido para algunos usuarios.

##  [!BADGE premium]{type=Positive url="/help/main/c-intro/intro.md#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."}

Puede añadir dispositivos para usarlos al obtener una vista previa de las experiencias. Cada dispositivo tiene una audiencia asociada.

![Sección Configuración de ventanillas móviles](/help/main/administrating-target/assets/mobile-viewport-configuration.png)

Clic **[!UICONTROL Añadir]**, especifique un nombre descriptivo para la ventanilla móvil, especifique la anchura y la altura, seleccione el sistema operativo que desee y haga clic en [!UICONTROL Guardar].

Si desea información sobre cómo añadir una ventanilla móvil, consulte [Configuración de la ventanilla móvil](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md).

## Selectores CSS {#css}

Explica cómo [!DNL Target] genera los selectores CSS.

![Sección Selectores CSS](/help/main/administrating-target/assets/css-selectors.png)

Estas opciones ayudan a [!DNL Target] a comprender la estructura de su sitio para generar mejores selectores CSS para la entrega de contenido. De forma predeterminada, [!DNL Target] genera selectores en función de los ID de elementos de la página. Si el sitio usa pocos ID, o ID duplicados en la misma página, usar estas clases puede ser una mejor opción.

Puede elegir una o ambas de las siguientes opciones:

### Usar identificadores de elementos

Desmarque esta opción si se usa el mismo identificador para varios elementos o si el identificador de elemento puede cambiar en la carga de página.

### Usar clases de elementos

De manera predeterminada, [!DNL Target] solo usa ID de elementos. Sin embargo, si la página está diseñada para usar clases para identificar elementos, como una página creada con [!DNL Adobe Experience Manager], también debería seleccionar [!UICONTROL Usar clases de elementos].

>[!NOTE]
>
>Aunque se ha hecho todo lo posible para garantizar la precisión, tenga en cuenta que el uso de clases puede provocar errores. Si no selecciona ninguna opción, también se ve afectada la precisión. El orden de la precisión es ID > clases > ninguna opción. También asegúrese de probar la página para asegurarse de que los selectores sean correctos.

Puede anular esta configuración por actividad (haga clic en el icono de engranaje [!UICONTROL Configuración], luego seleccione [!UICONTROL Selectores CSS]). Esto resulta especialmente útil si tiene varios sitios que están configurados de forma diferente.

>[!NOTE]
>
>No se puede anular la configuración por actividad en [!UICONTROL Automated Personalization] y [!UICONTROL Multivariate Testing] actividades.  Consulte [Selectores de elementos utilizados en el Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md) para obtener información adicional sobre selectores.

## Vídeo de formación: Preferencias de cuenta (7:33) ![Distintivo Información general](/help/main/assets/overview.png)

Este vídeo incluye información sobre las preferencias de cuenta.

* Describir la configuración de la cuenta disponible en [!DNL Target Standard]

>[!NOTE]
>
>La interfaz del menú [!UICONTROL Administración] de [!DNL Target] (anteriormente [!UICONTROL Configuración]) se ha rediseñado para proporcionar un rendimiento mejorado, reducir el tiempo de mantenimiento necesario al lanzar nuevas funciones y mejorar la experiencia del usuario en todo el producto. La información que aparece en el siguiente vídeo es, en general, correcta; sin embargo, las opciones pueden estar en ubicaciones ligeramente diferentes. Los vídeos actualizados se publicarán próximamente.

>[!VIDEO](https://video.tv.adobe.com/v/17379)
