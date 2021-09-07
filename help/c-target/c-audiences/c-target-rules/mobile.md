---
keywords: segmentación;móvil;segmentar por móvil;deviceatlas;iPhone;modelos de iPhone;device atlas;anchuradepantalla;anchura de pantalla;altura de pantalla;tipo de dispositivo;alturadepantalla;teléfono;tablet;modelo de dispositivo
description: Aprenda a crear audiencias en [!DNL Adobe Target] para dirigirse a dispositivos móviles.
title: ¿Puedo segmentar visitantes en función de las opciones móviles?
feature: Audiences
exl-id: 73d5c80c-bfa2-4806-8c04-652781b70bf2
source-git-commit: 1ad86925fb18df469fd1b80205f29f79a20ce4b6
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 40%

---

# Móvil

Cree audiencias en [!DNL Adobe Target] para segmentar dispositivos móviles en función de parámetros como dispositivo móvil, tipo de dispositivo, proveedor de dispositivo, dimensiones de pantalla, etc.

Por ejemplo, es posible que desee mostrar contenido distinto a los usuarios que visitan la página con un teléfono del que mostraría si visitan con un equipo. En ese caso, puede seleccionar la audiencia [!UICONTROL Mobile] y luego seleccionar la opción **[!UICONTROL Is Mobile Phone]**. A continuación, puede agregar cualquier detalle específico que sea importante para usted, como el tipo de teléfono, el tamaño de la pantalla (en píxeles), etc.

El destino para móviles se ofrece a través de [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester), un servicio de DotMobi. DeviceAtlas es una completa base de datos de dispositivos móviles creada a partir de datos compilados de numerosas fuentes, entre las que se incluyen fabricantes y operadores de red. Estos datos se verifican y se validan para crear una gran base de datos exacta de dispositivos móviles.

La detección de dispositivos se efectúa analizando las cadenas User-Agent. Algunos fabricantes de dispositivos, como Apple, proporcionan poca información en las UA para deshabilitar esta funcionalidad.

Por ejemplo, los dispositivos Apple no comparten en las UA tokens específicos sobre el modelo de dispositivo. El resultado es que no es posible detectar modelos de iPhone (como iPhone 12 Pro, iPhone 12, iPhone 11 Pro Max, etc.) utilizando un simple método basado en palabras clave.

Para resolver este problema, [!DNL Target] recopila datos adicionales para detectar con precisión los iPhone y otros dispositivos Apple mediante los siguientes parámetros:

| Parámetro | Tipo | Descripción |
|--- |--- |--- |
| devicePixelRatio | Cadena | Proporción entre píxeles físicos y píxeles independientes del dispositivo (dips) en el navegador. Por ejemplo, &quot;1,5&quot; o &quot;2&quot; |
| screenOrientation | Cadena | El dispositivo y el motor JavaScript del navegador admiten la orientación del dispositivo. Puede ser horizontal o vertical. |
| webGLRenderer | Cadena | Procesador del controlador de gráficos del navegador. |

>[!NOTE]
>
>Los clientes que utilicen el SDK móvil no necesitan hacer nada para aplicar esta funcionalidad. Los clientes que utilizan at.js deben [actualizar a la versión 1.5.0 de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A) (o posterior).

Puede elegirse más de una propiedad de dispositivo móvil. Las selecciones múltiples se unen con un operador OR.

Los clientes que utilicen una integración personalizada (sin usar at.js o el SDK móvil) pueden recopilar estos parámetros ellos mismos y pasarlos como parámetros de mbox.

1. En la interfaz de [!DNL Target], haga clic en **[!UICONTROL Audiencias]** > **[!UICONTROL Crear audiencia]**.
1. Asigne un nombre a la audiencia y añada una descripción opcional.
1. Arrastre y suelte **[!UICONTROL Mobile]** en el panel del generador de audiencias.
1. Haga clic en **[!UICONTROL Seleccionar]** y, a continuación, elija una de estas opciones:

   * Nombre de marketing del dispositivo
   * Modelo de dispositivo
   * Proveedor de dispositivo
   * Es dispositivo móvil
   * Es un teléfono móvil
   * Es una tableta
   * Sistema operativo
   * Altura de la pantalla (px)
   * Anchura de la pantalla (px)

   >[!NOTE]
   >
   >Puede segmentar por operador de dispositivo móvil mediante la [configuración Geográfica](/help/c-target/c-audiences/c-target-rules/geo.md#concept_5B4D99DE685348FB877929EE0F942670).

1. (Opcional) Configure reglas adicionales para la audiencia.
1. Haga clic en **[!UICONTROL Finalizado]**.

La siguiente ilustración muestra una audiencia dirigida a visitantes que utilizan dispositivos fabricados por Google que son dispositivos móviles.

![Segmentar dispositivos móviles](assets/target_mobile.png)

## Consideraciones

Tenga en cuenta la siguiente información al segmentar dispositivos móviles:

### Dispositivos de destino que ejecutan iOS 12.2 o posterior

Debido a los nuevos cambios introducidos en iOS 12.2, la creación de una audiencia con reglas definidas por [!UICONTROL Nombre de marketing del dispositivo] y [!UICONTROL Modelo de dispositivo] que especifique modelos de iPhone se ve afectada. [!DNL Target] ya no puede segmentar usuarios que tengan iPhone con iOS 12.2 (o posterior) instalado en ellos. Sin embargo, si esos usuarios no tienen iOS 12.2 (o posterior), la segmentación del modelo iPhone seguirá funcionando correctamente.

La actualización de iOS 12.2 (o posterior) no afecta a la identificación de los siguientes modelos, ya que estos no admiten la actualización a iOS 12.2: iPhone, iPhone 3G, iPhone 3GS, iPhone 4, iPhone 4s, iPhone 5, iPhone 5c, iPad, iPad 2, iPad / pantalla Retina, iPad Retina (4ª generación), iPod Touch 4 y iPod Touch 5.

### Dispositivos de destino que ejecutan Safari 14.0.2 (o posterior)

Cuando se utilizan reglas móviles para dirigirse a dispositivos que ejecutan Safari versión 14.0.2 (o posterior) en macOS, debido a un problema conocido que implica a agentes de usuario de Apple y DeviceAtlas, [!DNL Target] identifica incorrectamente Safari en dispositivos Mac como versión de iPad. Esta cuestión se abordará en el futuro.

## Vídeo de formación: Creación de audiencias

Este vídeo contiene información sobre el uso de las categorías de audiencias.

* Crear audiencias
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)
