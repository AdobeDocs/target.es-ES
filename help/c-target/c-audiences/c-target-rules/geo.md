---
keywords: segmentación;a4t;segmentación geográfica;geografía;precisión de segmentación geográfica;país;estado;ciudad;código postal;dma;operador de telefonía móvil;códigos de ciudad;códigos regionales;códigos de país;códigos de metro;scripts de perfil;scripts de perfil de segmentación geográfica;segmentación geográfica móvil
description: Aprenda a crear audiencias en [!DNL Adobe Target] para dirigirse a los usuarios según su ubicación geográfica.
title: ¿Puedo segmentar visitantes en función de la ubicación?
feature: Audiencias
solution: Target,Analytics
exl-id: e4a71a4d-e8f3-4f94-a1a7-fd250f4d5095
source-git-commit: b46966a8dbb2ff6d2efbfb8f126783f750c2f08c
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 50%

---

# Geografía

Utilice audiencias en [!DNL Adobe Target] para segmentar usuarios según su ubicación geográfica.

Los parámetros de ubicación geográfica permiten segmentar actividades y experiencias en función de la ubicación geográfica de los visitantes. Puede incluir o excluir visitantes en función de su país, estado/provincia, ciudad, código postal, latitud, longitud, DMA y operador de telefonía móvil. Estos datos se envían con cada solicitud [!DNL Target] y se basan en la dirección IP del visitante. Seleccione estos parámetros igual que cualquier otro valor de segmentación.

## Crear una audiencia con segmentación geográfica {#section_49CBFFAAC8694C4AAD3DE4B2DB7B05DE}

1. En la interfaz de [!DNL Target], haga clic en **[!UICONTROL Audiencias]** > **[!UICONTROL Crear audiencia]**.
1. Asigne un nombre a la audiencia y añada una descripción opcional.
1. Arrastre y suelte **[!UICONTROL Geografía]** en el panel del generador de audiencias.

1. Haga clic en **[!UICONTROL Seleccionar]** y, a continuación, elija una de estas opciones:

   * [!UICONTROL País/región]
   * [!UICONTROL Estado]
   * [!UICONTROL Ciudad]
   * [!UICONTROL Código postal]
   * [!UICONTROL Longitud]
   * [!UICONTROL Latitud]
   * [!UICONTROL DMA]
   * [!UICONTROL Operador de telefonía móvil]

   La dirección IP de los visitantes se transmite con una solicitud de mbox, una vez por visita (sesión), para resolver los parámetros de segmentación geográfica para dichos visitantes.

   Para [!UICONTROL Operador de telefonía móvil], [!DNL Target] utiliza los datos de registro de la dirección IP (a quien pertenece el bloque de direcciones IP) para determinar el operador de telefonía móvil correspondiente mediante [Mobile Country Codes (MCC) y Mobile Network Codes (MNC)](https://www.mcc-mnc.com).

1. Especifique un operador y el valor adecuado.
1. (Opcional) Configure reglas adicionales para la audiencia.
1. Haga clic en **[!UICONTROL Finalizado]**.

La siguiente ilustración muestra una audiencia que segmenta usuarios que acceden a la actividad desde una latitud buena de 44° y una longitud inferior a 22°.

![](assets/target_geo.png)

## Precisión {#section_D63D5FFCB49C42F9933AFD0BD7C79DF1}

La precisión de la segmentación geográfica depende de varios factores. Las conexiones WiFi son más precisas que las redes móviles. Cuando el visitante está usando una conexión de datos móviles, la precisión de la búsqueda geográfica puede verse afectada por la ubicación, la relación de datos del proveedor con [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester) y otros factores. Las conexiones de redes basadas en torres celulares pueden ser menos precisas que las conexiones cableadas o WiFi. Además, la dirección IP de un visitante puede asignarse a la ubicación ISP del visitante, que puede no ser la misma que la ubicación real del visitante. Algunos problemas de geolocalización en dispositivos móviles se pueden resolver usando la [API de geolocalización](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API).

En la tabla siguiente se muestra la precisión de la información geográfica basada en IP desde [DigitalEnvoy](https://www.digitalelement.com/solutions/) para conexiones a Internet cableadas o WiFi. DigitalEnvoy proporciona los datos más precisos de la industria. La precisión global es de más del 99,9 por ciento en el ámbito de país y de hasta el 97 por ciento en el ámbito de ciudad. La información de precisión no se aplica a redes basadas en torres celulares.

| País | Estado | Ciudad | Región |
|--- |--- |--- |--- |
| US | 99,99 % | 96 % | 94 % |
| Canadá | 99,99 % | 96 % | 94 % |
| Europa | 99,99 % |  |  |
| RU | 99,99 % |  | 87 % |
| Alemania | 99,99 % | 95 % | 93 % |
| Escandinavia | 99 % | Entre el 90 % y el 95 % | Alrededor de 85 % |
| España | 99,99 % | Alrededor del 90 % | Entre el 95 % y el 100 % |
| Asia | 99 % | Alrededor de 95 % | Entre el 90 % y el 95 % |
| Japón | 99,99 % | Alrededor de 95 % | Entre el 90 % y el 95 % |
| Australia | 99,99 % | 94 % | 91 % |

## Uso de targeting geográfico en scripts de perfil {#section_92C93138542C4A94997E3F4BE3F5DA28}

Puede usar la información geográfica para scripts de perfil.

Por ejemplo, use:

* `profile.geolocation.country`
* `profile.geolocation.state`
* `profile.geolocation.city`
* `profile.geolocation.zip`
* `profile.geolocation.dma`
* `profile.geolocation.domainName`
* `profile.geolocation.ispName`
* `profile.geolocation.connectionSpeed`
* `profile.geolocation.mobileCarrier`

De este modo, puede escribir una expresión de segmento denominada “De Norteamérica” con el siguiente código:

`return profile.geolocation.country == 'united states' || profile.geolocation.country == 'canada' || profile.geolocation.country == 'mexico';`

## Utilizar valores de segmentación geográfica como tokens {#section_E7F7FDF62C3B4934A6565D04B24655F6}

Puede utilizar valores `profile.geolocation` directamente como tokens en ofertas, complementos, etc.

Por ejemplo, use:

* `${profile.geolocation.country}`
* `${profile.geolocation.state}`
* `${profile.geolocation.city}`
* `${profile.geolocation.zip}`
* `${profile.geolocation.dma}`
* `${profile.geolocation.domainName}`
* `${profile.geolocation.ispName}`
* `${profile.geolocation.connectionSpeed}`
* `${profile.geolocation.mobileCarrier}`
* `${profile.geolocation.latitude}`
* `${profile.geolocation.longitude}`

## Preguntas más frecuentes sobre segmentación geográfica {#section_DD308A53AF0F48FA8C81423580561FE7}

Las preguntas siguientes se plantean a menudo sobre la segmentación geográfica:

### ¿Cómo especifico la latitud y la longitud?

* El valor de latitud y longitud debe ser un valor numérico en grados.
* El valor de latitud y longitud puede tener una precisión máxima de cinco decimales.
* El valor de latitud debe situarse entre -90 y 90.
* El valor de longitud debe situarse entre -180 y 180.

### ¿Cómo funciona la segmentación geográfica en los dispositivos móviles?

La mayoría de los usuarios de dispositivos móviles accede al contenido a través de una red WiFi, lo que significa que la segmentación geográfica basada en IP de [!DNL Target] es tan precisa como en un equipo de escritorio. Las conexiones basadas en torres celulares pueden ser menos exactas porque la dirección IP del visitante se basa en la torre de donde se está recibiendo la señal. Algunos problemas de geolocalización en dispositivos móviles se pueden resolver usando la [API de geolocalización](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API).

### ¿Cómo gestiona la función geográfica los visitantes de AOL?

Debido al modo en que AOL dirige su tráfico, [!DNL Target] solo puede dirigirse a ellos a nivel de país. Por ejemplo, una campaña dirigida a Francia se dirige correctamente a los usuarios de AOL de Francia. Sin embargo, una campaña dirigida a París no se dirige correctamente a los usuarios de AOL de París. Si desea realizar el enfoque específicamente para usuarios de AOL, puede establecer el campo de región en “aol”. De hecho, puede dirigirse a usuarios de AOL de EE. UU. si especifica dos condiciones de segmentación: un país que coincida exactamente con “united states” (Estados Unidos) y una región que coincida exactamente con “aol”.

### ¿Qué granularidad de ubicación ofrece el targeting geográfico?

* País: global
* Estado/provincia/región: global
* Ciudad: global
* Código postal: EE. UU., Alemania, Canadá
* DMA/ITV (Reino Unido): EE. UU., Reino Unido
* Operador de telefonía móvil - global

### ¿Cómo puedo probar mis actividades si soy un usuario de una ubicación diferente?

* **at.js 1.*x***: Puede sustituir su dirección IP por una dirección IP de una ubicación diferente y usar el  `mboxOverride.browserIp url` parámetro . Por ejemplo, si su empresa está en el Reino Unido, pero la campaña global está dirigida a visitantes de Auckland, Nueva Zelanda, use este estilo de URL suponiendo que `60.234.0.39` sea una dirección IP de Auckland:

   `https://www.mycompany.com?mboxOverride.browserIp=60.234.0.39`

   Borre las cookies antes de probar la actividad.

   >[!NOTE]
   >
   >`mboxOverride.browserIp` es compatible con at.js 1.Solamente *x*. Esta funcionalidad no es compatible con at.js 2.*x*.

* **at.js 2.*x***: Para anular su dirección IP por at.js 2.*x*, instale una extensión/complemento del explorador (como el encabezado X-Forwarded-For para Chrome o Firefox). Esta extensión le permite pasar el encabezado x-forward-for en las solicitudes de página.

### ¿Cómo se asignan los territorios, como Puerto Rico y Hong Kong, a la estructura de segmentación geográfica?

Puerto Rico, Hong Kong y otros territorios se tratan como valores de “País” independientes.

### ¿[!DNL Target] captura (y almacena) información como código postal cuando la actividad está dirigida con funcionalidades de segmentación por ubicación geográfica?

No, [!DNL Target] utiliza solo datos geográficos durante la sesión y luego se descartan los datos.

## Vídeo de formación: Creación de audiencias ![Distintivo del tutorial](/help/assets/tutorial.png)

Este vídeo contiene información sobre el uso de las categorías de audiencias.

* Crear audiencias
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)
