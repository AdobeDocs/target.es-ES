---
keywords: compositor de experiencias visuales;vec;url predeterminada;compositor de experiencias mejorado;eec;contenido mixto;instantáneas de experiencias;ventanilla móvil;css;selectores css
description: Obtenga información sobre cómo configurar el Compositor de experiencias visuales (VEC) de Adobe [!DNL Target] especificando su configuración general, la configuración de las ventanillas móviles y los selectores CSS.
title: ¿Cómo configuro el Compositor de experiencias visuales (VEC)?
feature: Administration & Configuration
role: Admin
exl-id: cf6c9ece-6745-477e-81ac-a3e9a9fddb09
TQID: https://experienceleague.adobe.com/E1ck4-aG4txqaFLs3t3-8bN-BQIoY8stRASTRJfhZMY
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
subfeature_v2:
  - id: b1d5cd6a-4ed3-43f6-9a52-2721acea1129
    internal-label: Troubleshooting
  - id: c011fe9c-b94b-4a88-93d8-f2acece55112
    internal-label: Administration
  - id: fc9c2184-9102-403f-bd6c-0055021e4bea
    internal-label: Overview
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 553aa8fb523a62f72f0e2be7d7fd1b4eb663da6b
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 32%
---
# Configurar el Compositor de experiencias visuales (VEC)

Use la ficha **[!UICONTROL Compositor de experiencias visuales]** en **[!UICONTROL Administración]** para establecer los valores predeterminados de toda la cuenta para [!DNL Adobe Target] [!UICONTROL Compositor de experiencias visuales] (VEC). Esta configuración se aplica cada vez que los autores crean o previsualizan experiencias en el VEC.

**Resumen de configuración**

1. [Configuración general](#general-settings): URL predeterminada, Compositor de experiencias mejorado, contenido mixto e instantáneas de experiencias.
1. [Configuración de ventanilla móvil](#mobile-viewport-configuration): Previsualizar dispositivos para experiencias adaptables ([solo Target Premium](/help/main/c-intro/intro.md#premium)).
1. [Selectores CSS](#css): Cómo Target genera selectores para la entrega de contenido.

Para abrir la página de configuración, haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Compositor de experiencias visuales]**.

>[!NOTE]
>
>La configuración de esta página se aplica a toda la cuenta de [!DNL Target].

## Configuración general {#general-settings}

En la sección **[!UICONTROL Configuración general]**, configure los valores predeterminados utilizados al abrir el VEC.

![Sección de configuración general](/help/main/administrating-target/assets/general-settings.png)

Las configuraciones disponibles son las siguientes:

* **URL predeterminada**

  La dirección URL predeterminada que utiliza el [!UICONTROL Compositor de experiencias visuales]. Esta es la página predeterminada, como la página principal, que se utiliza siempre que quiere configurar una experiencia para cada nueva actividad. Si no establece una URL predeterminada, tiene que escribir una URL para cada actividad en el momento de la creación.

* **Habilitar Compositor de experiencias mejorado**

  Permite editar en sitios con eliminación de iFrames y sitios con contenido mixto. Es posible que algunos sitios no sean compatibles con la versión mejorada. Anule la selección de esta opción para volver al [!UICONTROL Compositor de experiencias visuales] original. La publicación de actividades en los sitios no se verá afectada por esta opción.

  Tenga en cuenta que [!UICONTROL Enhanced Experience Composer] no es compatible con [!DNL Safari].

  Para obtener más información, consulte [Solución de problemas del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

  También puede habilitar [!UICONTROL Enhanced Experience Composer] en el nivel de actividad. Consulte [Obtenga información sobre cómo habilitar el Compositor de experiencias mejorado en el nivel de actividad](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md).

* **Cargar contenido mixto**

  Habilite el contenido combinado al abrir un sitio web mediante [!UICONTROL Enhanced Experience Composer] (EEC). Al habilitar esta opción, se evitará una carga excesiva de recursos estáticos a través de [!DNL Target] servidores proxy.

  Esta opción resulta útil si, por ejemplo:

  * Los encabezados de la Política de seguridad de contenido (CSP) permiten cargar contenido mixto sin el uso de servidores proxy con el EEC habilitado.
  * El sitio web HTTP se enfrenta a un mayor tiempo de carga en el EEC, donde JavaScript, imágenes, etc. tardan más en cargarse mediante proxy.

* **Generar instantáneas de experiencia en el diagrama de flujo de la actividad**

  Cuando se habilitan las instantáneas de experiencia, se generan miniaturas de las experiencias en el diagrama de flujo de trabajo de la actividad. Si deshabilita las instantáneas, podría obtener un rendimiento más rápido para algunos usuarios.

## Configuración de las ventanillas móviles {#mobile-viewport-configuration}

>[!NOTE]
>
>La configuración de la **[!UICONTROL ventanilla móvil]** es una característica de [Target Premium](/help/main/c-intro/intro.md#premium).

Agregue dispositivos para utilizarlos al obtener una vista previa de las experiencias. Cada dispositivo tiene una audiencia asociada.

![Sección de configuración de ventanilla móvil](/help/main/administrating-target/assets/mobile-viewport-configuration.png)

Siga estos pasos para agregar una ventanilla móvil:

1. Haga clic en **[!UICONTROL Agregar]**.
1. Especifique un nombre descriptivo para la ventanilla móvil, especifique la anchura y la altura y seleccione el sistema operativo que desee.
1. Haga clic en **[!UICONTROL Guardar]**.

Para obtener detalles de vista previa y audiencia, consulte [Aprenda a utilizar las ventanillas móviles para las experiencias adaptables](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md).

## Selectores CSS {#css}

Explica cómo [!DNL Target] genera los selectores CSS.

![Sección de selectores CSS](/help/main/administrating-target/assets/css-selectors.png)

Estas opciones ayudan a [!DNL Target] a comprender la estructura de su sitio para generar mejores selectores CSS para la entrega de contenido. De forma predeterminada, [!DNL Target] genera selectores en función de los ID de elementos de la página. Si el sitio usa pocos ID, o ID duplicados en la misma página, usar estas clases puede ser una mejor opción.

Puede elegir una o ambas de las siguientes opciones:

* **Usar ID de elemento**

  Desmarque esta opción si se usa el mismo identificador para varios elementos o si el identificador de elemento puede cambiar en la carga de página.

* **Usar clases de elementos**

  De manera predeterminada, [!DNL Target] solo usa ID de elementos. Sin embargo, si la página está diseñada para usar clases para identificar elementos, como una página creada con [!DNL Adobe Experience Manager], también debería seleccionar **[!UICONTROL Usar clases de elementos]**. La precisión del selector suele ser mayor cuando se utilizan ID, menor cuando se utilizan clases y menor cuando no se selecciona ninguna opción. Pruebe la página en el VEC para confirmar que los selectores son correctos.

  Puede anular esta configuración por actividad si hace clic en el icono de engranaje **[!UICONTROL Settings]** y selecciona **[!UICONTROL Selectores CSS]**, lo cual resulta útil cuando los sitios de la misma cuenta se configuran de forma diferente. Las invalidaciones por actividad no están disponibles en las actividades **[!UICONTROL Automated Personalization]** o **[!UICONTROL Multivariate Testing]**. Para ver el comportamiento del selector y la solución de problemas, consulte [Selectores de elementos utilizados en el Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md).

## Vídeo de formación: Preferencias de cuenta (7:33) ![Distintivo de información general](/help/main/assets/overview.png)

>[!BEGINSHADEBOX]

La interfaz de usuario del menú [!DNL Target] **[!UICONTROL Administración]** (anteriormente **[!UICONTROL Configuración]**) se ha rediseñado para proporcionar un rendimiento mejorado, reducir el tiempo de mantenimiento necesario al lanzar nuevas características y mejorar la experiencia del usuario en todo el producto. La información que aparece en el siguiente vídeo es, en general, correcta; sin embargo, las opciones pueden estar en ubicaciones ligeramente diferentes. Los vídeos actualizados se publicarán próximamente.

>[!ENDSHADEBOX]

Este vídeo incluye información sobre las preferencias de cuenta.

* Describir la configuración de la cuenta disponible en [!DNL Target Standard]

>[!VIDEO](https://video.tv.adobe.com/v/17379)
