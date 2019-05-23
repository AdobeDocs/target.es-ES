---
description: Puede segmentar por dispositivo móvil en función de parámetros como dispositivo móvil, tipo de dispositivo, proveedor de dispositivo, dimensiones de pantalla (en píxeles) y muchos más.
keywords: segmentación;móvil;segmentar por móvil;deviceatlas;iPhone;modelos de iPhone;device atlas;anchuradepantalla;anchura de pantalla;altura de pantalla;tipo de dispositivo;alturadepantalla;teléfono;tablet;modelo de dispositivo
seo-description: Puede segmentar por dispositivo móvil en función de parámetros como dispositivo móvil, tipo de dispositivo, proveedor de dispositivo, dimensiones de pantalla (en píxeles) y muchos más.
seo-title: Móvil
solution: Target
title: Móvil
topic: Standard
uuid: a731e8c0-e9c1-4971-95b7-882cefcabfc7
translation-type: tm+mt
source-git-commit: f59e96cd5afcae9d27d730aecead9eb360f04026

---


# Móvil{#mobile}

Puede segmentar por dispositivo móvil en función de parámetros como dispositivo móvil, tipo de dispositivo, proveedor de dispositivo, dimensiones de pantalla (en píxeles) y muchos más.

Por ejemplo, es posible que quiera mostrar contenido distinto a los usuarios cuando acceden a su página desde un teléfono con respecto a cuando acceden desde un equipo. En ese caso, puede elegir la audiencia de dispositivos móviles y seleccionar la opción **[!UICONTROL Es un teléfono móvil]. Después, puede agregar cualquier detalle específico que sea importante para usted, como el tipo de teléfono, el tamaño de la pantalla (en píxeles), etc.**

El destino para móviles se ofrece a través de [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester), un servicio de DotMobi. DeviceAtlas es una completa base de datos de dispositivos móviles creada a partir de datos compilados de numerosas fuentes, entre las que se incluyen fabricantes y operadores de red. Estos datos se verifican y se validan para crear una gran base de datos exacta de dispositivos móviles.

La detección de dispositivos se efectúa analizando las cadenas User-Agent. Algunos fabricantes de dispositivos, como Apple, proporcionan poca información en las UA para deshabilitar esta funcionalidad.

Por ejemplo, los dispositivos Apple no comparten en las UA tokens específicos sobre el modelo de dispositivo. La consecuencia es que los modelos de iPhone (como iPhone 5S, iPhone SE, iPhone 6, etc.) no se pueden detectar con un simple método de palabras clave.

Para resolver esto, Target recopila datos adicionales para detectar con precisión los iPhone y otros dispositivos Apple mediante los siguientes parámetros:

| Parámetro | Tipo | Descripción |
|--- |--- |--- |
| devicePixelRatio | Cadena | Proporción entre píxeles físicos y píxeles independientes del dispositivo (dips) en el navegador.  por ejemplo, “1,5” o “2” |
| screenOrientation | Cadena | El dispositivo y el motor JavaScript del navegador admiten la orientación del dispositivo. Puede ser horizontal o vertical. |
| webGLRenderer | Cadena | Procesador del controlador de gráficos del navegador. |

>[!NOTE]
>
>Los clientes que utilicen el SDK móvil no tienen que hacer nada para aprovechar esta funcionalidad. Los clientes que utilizan at.js deben [actualizar a la versión 1.5.0 de at.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A) (o posterior).

Puede elegirse más de una propiedad de dispositivo móvil. Si realiza varias selecciones, debe unirlas mediante OR.

Los clientes que utilicen una integración personalizada (sin usar at.js o el SDK móvil) pueden recopilar estos parámetros ellos mismos y pasarlos como parámetros de mbox.

1. En la interfaz de [!DNL Target], haga clic en **[!UICONTROL Audiencias]** &gt; **[!UICONTROL Crear audiencia]**.
1. Ponga un nombre a la audiencia.
1. Haga clic en **[!UICONTROL Agregar regla]** &gt; **[!UICONTROL Móvil]**.

   ![](assets/target_mobile.png)

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
   >Puede segmentar por operador de dispositivo móvil mediante la [configuración Geográfica](../../../c-target/c-audiences/c-target-rules/geo.md#concept_5B4D99DE685348FB877929EE0F942670).

1. (Opcional) Haga clic en **[!UICONTROL Agregar regla]** y configure reglas adicionales para la audiencia.
1. Haga clic en **[!UICONTROL Guardar]**.

## Vídeo de formación: Creación de audiencias

Este vídeo contiene información sobre el uso de las categorías de audiencias.

* Crear audiencias
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)
