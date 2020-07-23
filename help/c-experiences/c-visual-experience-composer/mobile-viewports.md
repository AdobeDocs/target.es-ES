---
keywords: responsive;mobile viewports;viewport;devices;mobile example;iphone
description: Las ventanillas móviles ayudan a obtener una vista previa de cómo aparecen las actividades en pantallas de diversos tamaños.
title: Ventanillas móviles para las experiencias adaptables
uuid: 86a74584-4a4d-428b-9d29-f7ebdf0cef2a
translation-type: tm+mt
source-git-commit: 3edb13b196240bb1918fc66edcc653936e32d3ef
workflow-type: tm+mt
source-wordcount: '1343'
ht-degree: 93%

---


# Ventanillas móviles para las experiencias adaptables{#mobile-viewports-for-responsive-experiences}

Las ventanillas móviles ayudan a obtener una vista previa de cómo aparecen las actividades en pantallas de diversos tamaños.

La característica de vista previa de ventanilla móvil está diseñada para sitios que responden. Use ventanillas móviles si su sitio se adapta y si en la página móvil se usan los mismos elementos que en su página de escritorio, con otra configuración. Si tiene un sitio móvil independiente con otra estructura como, por ejemplo, [!DNL m.mysite.com], utilice una [actividad multipágina](../../c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48).

>[!NOTE]
>
>Las ventanillas móviles no están disponibles si quedan superpuestas por una superposición de oferta de redireccionamiento.

Una ventanilla móvil está definida por el tamaño del rectángulo que se rellena con una página web en la pantalla. Es el tamaño de la ventana del navegador menos las barras de desplazamiento y las de herramientas. Los navegadores usan “píxeles de CSS”. Para muchos dispositivos, como los que tienen pantallas de retina, la ventanilla móvil es menor que la resolución anunciada para el dispositivo.

A continuación tiene las ventanillas móviles y las resoluciones de algunos dispositivos populares. No se olvide de usar el tamaño de la ventanilla móvil en Target.

| Dispositivo | Tamaño de la ventanilla móvil | Resolución del dispositivo |
|---|---|---|
| iPhone SE | 375 ancho x 667 alto | 750 ancho x 1.334 alto |
| iPhone 11 Pro Max | 414 ancho x 896 alto | 1242 ancho x 2688 alto |
| iPhone 11 Xs máx. | 414 ancho x 896 alto | 1242 ancho x 2688 alto |
| iPhone 11 | 414 ancho x 896 alto | 828 ancho x 1792 alto |
| iPhone 11 Xr | 414 ancho x 896 alto | 828 ancho x 1792 alto |
| iPhone 11 Pro | 375 ancho x 812 alto | 1125 ancho x 2436 alto |
| iPhone 11 X | 375 ancho x 812 alto | 1125 ancho x 2436 alto |
| iPhone 11 Xs | 375 ancho x 812 alto | 1125 ancho x 2436 alto |
| iPhone X | 375 ancho x 812 alto | 1125 ancho x 2436 alto |
| iPhone 8 Plus | 414 ancho x 736 alto | 1080 ancho x 1920 alto |
| iPhone 8 | 375 ancho x 667 alto | 750 ancho x 1.334 alto |
| iPhone 7 Plus | 414 ancho x 736 alto | 1080 ancho x 1920 alto |
| iPhone 7 | 375 ancho x 667 alto | 750 ancho x 1.334 alto |
| iPhone 6s Más | 414 ancho x 736 alto | 1080 ancho x 1920 alto |
| iPhone 6s | 375 ancho x 667 alto | 750 ancho x 1.334 alto |
| iPhone 6 Plus | 414 ancho x 736 alto | 1080 ancho x 1920 alto |
| iPhone 6 | 375 ancho x 667 alto | 750 ancho x 1.334 alto |
| iPad Pro | 1024 ancho x 1366 alto | 2048 ancho x 2732 alto |
| iPad de tercera y cuarta generación | 768 ancho x 1024 alto | 1.536 ancho x 2.048 alto |
| iPad Air 1 y 2 | 768 ancho x 1024 alto | 1.536 ancho x 2.048 alto |
| iPad Mini | 768 ancho x 1024 alto | 768 ancho x 1024 alto |
| iPad Mini 2 y 3 | 768 ancho x 1024 alto | 1.536 ancho x 2.048 alto |
| Nexus 6P | 411 ancho x 731 alto | 1440 ancho x 2560 alto |
| Nexus 5X | 411 ancho x 731 alto | 1080 ancho x 1920 alto |
| Google Pixel | 411 ancho x 731 alto | 1080 ancho x 1920 alto |
| Google Pixel XL | 411 ancho x 731 alto | 1440 ancho x 2560 alto |
| Google Pixel 2 | 411 ancho x 731 alto | 1080 ancho x 1920 alto |
| Google Pixel 2 XL | 411 ancho x 823 alto | 1440 ancho x 2880 alto |
| Samsung Galaxy Note 5 | 480 ancho x 853 alto | 1440 ancho x 2560 alto |
| LG G5 | 480 ancho x 853 alto | 1440 ancho x 2560 alto |
| One Plus 3 | 480 ancho x 853 alto | 1080 ancho x 1920 alto |
| Samsung Galaxy S9 | 360 ancho x 740 alto | 1440 ancho x 2960 alto |
| Samsung Galaxy S9+ | 360 ancho x 740 alto | 1440 ancho x 2960 alto |
| Samsung Galaxy S8 | 360 ancho x 740 alto | 1440 ancho x 2960 alto |
| Samsung Galaxy S8+ | 360 ancho x 740 alto | 1440 ancho x 2960 alto |
| Samsung Galaxy S7 | 360 ancho x 640 alto | 1440 ancho x 2560 alto |
| Samsung Galaxy S7 Edge | 360 ancho x 640 alto | 1440 ancho x 2560 alto |
| Nexus 7 (2013) | 600 ancho x 960 alto | 1200 ancho x 1920 alto |
| Nexus 9 | 768 ancho x 1024 alto | 1.536 ancho x 2.048 alto |
| Samsung Galaxy Tab 10 | 800 ancho x 1280 alto | 800 ancho x 1280 alto |
| Chromebook Pixel | 1280 ancho x 850 alto | 2560 ancho x 1700 alto |

Diversos sitios web enumeran los tamaños de las ventanillas para dispositivos populares. Por ejemplo, consulte [https://viewportsizer.com/devices/](https://viewportsizer.com/devices/) o el sitio web del fabricante del dispositivo.

Si quiere ofrecer una actividad en un dispositivo concreto, elija la audiencia adecuada para ese dispositivo en el diagrama de la actividad. Use el Compositor web móvil para editar la página en la actividad de dicho dispositivo. Si quiere llevar a cabo una actividad en toda la experiencia digital y asegurarse de que el aspecto sea satisfactorio en todos los dispositivos, no aplique segmentación y use ventanillas móviles para previsualizar la actividad en cada tamaño de pantalla.

Si tiene un sitio adaptable, se suele diseñar para que se abra en una vista diferente cuando accede un dispositivo con un tamaño de pantalla concreto. Los tamaños de pantalla que activan las vistas nuevas se conocen como *puntos de interrupción CSS*. Guarde los puntos de interrupción CSS en Target para poder previsualizar las experiencias de cada vista que defina. Cada una de estas experiencias se muestra en una ventanilla móvil en la interfaz de Target. En la parte superior de la pantalla, haga clic en la ventanilla móvil correspondiente para abrir la vista de cada tamaño de pantalla.

Aunque su sitio no sea adaptable, puede usar el Compositor web móvil para ver un sitio si la actividad está dirigida a un dispositivo concreto.

>[!NOTE]
>
>Aunque puede editar una experiencia desde las ventanillas móviles, esos cambios se aplican a todas las ventanillas y todos los dispositivos, no solo a la ventanilla móvil que modifique. De modo similar, si edita una experiencia en la vista de escritorio normal, se cambia la página en todos los tamaños de pantalla, no solo en la vista de escritorio. En estos momentos, no se admiten los cambios en páginas específicas de cada ventanilla móvil.

## Configuración de las ventanillas móviles {#task_B4B161499DC0470584ED922A4D20FCAB}

Configure todas las ventanillas móviles que quiera que estén disponibles cuando cree sus experiencias.

1. Haga clic en **[!UICONTROL Administración]** > Compositor **[!UICONTROL de experiencias]** visuales.
1. In the Mobile Viewports Configuration section of the Account Preferences page, click **[!UICONTROL Add]** to add a mobile viewport.

   Para cambiar la configuración de una ventanilla móvil existente, selecciónela y, a continuación, haga clic en el icono de editar (el lápiz).

   ![Añadir ventanilla](/help/c-experiences/c-visual-experience-composer/assets/viewpoert_add.png)

1. Escriba un nombre para la ventanilla móvil.

   Póngale un nombre descriptivo para que sea fácil reconocerla. El nombre puede tener hasta 36 caracteres.
1. Introduzca el tamaño de pantalla del dispositivo móvil, tanto la anchura como la altura.

   La anchura puede estar entre 150 y 968 píxeles. La altura puede estar entre 150 y 1.280 píxeles.

   >[!NOTE]

1. (Opcional) Seleccione el sistema operativo del dispositivo.

   Opciones:

   * Android
   * iOS
   * Windows
   * Symbian
   * BlackBerry

   Si usa el [Compositor de experiencias mejorado](../../c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D) y elige un sistema operativo, Target imita ese dispositivo cuando visualiza la página. Si, por ejemplo, existe un aspecto diferente para Android y para iOS en su sitio adaptable, Target imita ese comportamiento.
1. Haga clic en **[!UICONTROL Guardar]**.

## Crear experiencias adaptables {#task_D6332438B5EE48CCA8AF199270F1CAEF}

Agregue ventanillas móviles a las actividades de Target para crear experiencias adaptables para las pantallas móviles.

1. Cree una actividad.
1. En el Compositor de experiencias visuales, haga clic en el icono de engranaje de **[!UICONTROL Configuración]** y, a continuación, seleccione **[!UICONTROL Agregar ventanillas móviles]**.
1. Haga clic en el icono de **[!UICONTROL Dispositivos]** y, a continuación, active todos los dispositivos que deban tener una ventanilla móvil.

   ![](assets/MobileViewPorts.jpg)

   Las ventanillas móviles se muestran de la más grande a la más pequeña en anchura.
1. Edite las ventanillas móviles según quiera.

   Todos los cambios que realice en la experiencia (por ejemplo, si cambia el texto de un título) se aplicarán a la experiencia en todos los dispositivos.

   Pase el cursor por encima del nombre de una ventanilla móvil para ver su tamaño.
1. Si quiere, haga clic en el icono de orientación para cambiar entre los modos horizontal y vertical.

   * Vertical: ![Vertical](/help/c-experiences/c-visual-experience-composer/assets/viewport_portrait.png)
   * Horizontal: ![Horizontal](/help/c-experiences/c-visual-experience-composer/assets/viewport_landscape.png)

## Caso de uso: Dirigirse a dos versiones de iPhone {#task_CC3144BF5BA54034996E1D3DB0BC1A35}

Este caso de uso muestra cómo configurar experiencias para dos versiones de iPhone, la iPhone 6 y la iPhone 6 Plus, mediante la función Ventanillas móviles de Target Standard.

1. En Destinatario, haga clic en **[!UICONTROL Administración]**.
1. En la sección Configuración de ventanilla móvil, cree ventanillas móviles para iPhone 6 y iPhone 6 Plus.

   Aplique los ajustes siguientes para cada ventanilla:

   | Nombre | Anchura | Altura | Sistema operativo |
   |---|---|---|---|
   | iPhone 6 | 375 | 667 | iOS |
   | iPhone 6 Plus | 414 | 736 | iOS |

   ![](assets/iphoneviewportconfig.png)

1. Cree una actividad con la experiencia que quiere mostrar.
1. Seleccione la experiencia que quiere dirigir a los visitantes que accedan al sitio desde un iPhone 6 o un iPhone 6 Plus.
1. Al seleccionar el objetivo, haga clic en **[!UICONTROL Crear audiencia]** y configure una audiencia tal como se muestra en la imagen siguiente:

   ![](assets/iphoneaudiences.png)

   Como el teléfono podría girarse para colocarse en horizontal, el requisito de definir una altura y anchura simultáneas de más de 320 crea una condición que solo los dispositivos 6 y 6 Plus pueden satisfacer al combinarse con el modelo de dispositivo iPhone.
1. Haga clic en **[!UICONTROL Guardar]**.
1. Continúe configurando la actividad con normalidad.

## Vídeos de formación

Los siguientes vídeos contienen más información sobre los conceptos mencionados en este artículo.

### Compositor de experiencias visuales (2 de 2) (7:29) ![Distintivo de información general](/help/assets/overview.png)

El siguiente vídeo de demostración incluye información sobre cómo usar el Compositor de experiencias visuales para trabajar con ventanillas móviles:

* Cambiar el nombre de una experiencia y duplicarla
* Crear una experiencia de redirección
* Segmentar una actividad en una sola dirección URL o un grupo de direcciones URL
* Crear una actividad de varias páginas
* Obtener una vista previa y generar experiencia para sitios web adaptables
* Usar superposiciones para destacar tipos de elementos

>[!VIDEO](https://video.tv.adobe.com/v/17401)

### Indicador Preferencias de cuenta en ![Información general de Adobe Target](/help/assets/overview.png)

En este vídeo se explica cómo configurar las ventanillas móviles en las preferencias de cuenta a partir del minuto 4:40.

>[!VIDEO](https://video.tv.adobe.com/v/17379)