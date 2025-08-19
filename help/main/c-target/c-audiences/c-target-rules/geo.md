---
keywords: segmentación;a4t;segmentación geográfica;geografía;precisión de segmentación geográfica;país;estado;ciudad;código postal;dma;operador de telefonía móvil;códigos de ciudad;códigos regionales;códigos de país;códigos de metro;scripts de perfil;scripts de perfil de segmentación geográfica;segmentación geográfica móvil
description: Aprenda a crear audiencias en  [!DNL Adobe Target]  para segmentar usuarios según su ubicación geográfica.
title: ¿Puedo segmentar visitantes según la ubicación?
feature: Audiences
solution: Target,Analytics
exl-id: e4a71a4d-e8f3-4f94-a1a7-fd250f4d5095
source-git-commit: 195028613dec0294c816703b9145e720e3209d74
workflow-type: tm+mt
source-wordcount: '1014'
ht-degree: 42%

---

# Geografía

Use audiencias en [!DNL Adobe Target] para segmentar usuarios según su ubicación geográfica.

Los parámetros de ubicación geográfica permiten segmentar las actividades y experiencias en función de la ubicación geográfica de los visitantes. Puede incluir o excluir visitantes en función de su país, estado/provincia, ciudad, código postal, latitud, longitud, DMA y operador de telefonía móvil. Estos datos se envían con cada solicitud [!DNL Target] y se basan en la dirección IP del visitante. Seleccione estos parámetros igual que cualquier otro valor de segmentación.

## Creación de una audiencia con segmentación geográfica {#section_49CBFFAAC8694C4AAD3DE4B2DB7B05DE}

1. En la interfaz [!DNL Target], haga clic en **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Asigne un nombre a la audiencia y añada una descripción opcional.
1. Arrastre y suelte **[!UICONTROL Geo]** en el panel del generador de audiencias.

1. Haga clic en **[!UICONTROL Select]** y luego seleccione una de las siguientes opciones:

   * [!UICONTROL Country/Region]
   * [!UICONTROL State]
   * [!UICONTROL City]
   * [!UICONTROL Zip Code]
   * [!UICONTROL Longitude]
   * [!UICONTROL Latitude]
   * [!UICONTROL DMA]
   * [!UICONTROL Mobile Carrier]

   La información geográfica de un visitante se determina a partir de la dirección IP de origen de una solicitud de ubicación [!DNL Target] (solicitud mBox). La resolución de IP a ubicación geográfica está lista para la primera llamada de una nueva sesión. Esto significa que, si la dirección IP de un visitante cambia a mitad de la sesión de una visita, la información geográfica sigue basándose en la dirección IP de la primera llamada.

   Para [!UICONTROL Mobile Carrier], [!DNL Target] utiliza los datos de registro de la dirección IP (a quien pertenece el bloque de direcciones IP) para determinar el operador de telefonía móvil apropiado mediante [códigos de país móviles (MCC, Mobile Country Codes) y códigos de red móviles (MNC, Mobile Network Codes)](https://www.mcc-mnc.com).

1. Especifique un operador y el valor adecuado.
1. (Opcional) Configure reglas adicionales para la audiencia.
1. Haga clic en **[!UICONTROL Done]**.

La siguiente ilustración muestra una audiencia que segmenta usuarios que acceden a la actividad desde una latitud superior a 44° y una longitud inferior a 22°.

![imagen target_geo](assets/target_geo.png)

## Precisión {#section_D63D5FFCB49C42F9933AFD0BD7C79DF1}

La precisión de la segmentación geográfica depende de varios factores. Las conexiones WiFi son más precisas que las redes móviles. Cuando un visitante está usando una conexión de datos móviles, la precisión de la búsqueda geográfica puede verse afectada por la ubicación, la relación de datos del proveedor con [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester) y otros factores. Las conexiones de redes basadas en torres celulares pueden ser menos precisas que las conexiones cableadas o WiFi. Además, la dirección IP de un visitante puede asignarse a la ubicación del ISP del visitante, que puede no ser la misma que la ubicación real del visitante. Algunos problemas de localización geográfica móvil se pueden resolver con la [API de geolocalización](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API).

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

## Uso del targeting geográfico en scripts de perfil {#section_92C93138542C4A94997E3F4BE3F5DA28}

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

## Usar valores de targeting geográfico como tokens {#section_E7F7FDF62C3B4934A6565D04B24655F6}

Puede usar valores de `profile.geolocation` directamente como tokens en ofertas, complementos, etc.

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

## Preguntas frecuentes sobre la segmentación geográfica {#section_DD308A53AF0F48FA8C81423580561FE7}

Con frecuencia se plantean las siguientes preguntas sobre la segmentación geográfica:

### ¿Cómo se especifica la latitud y la longitud?

+++Ver detalles
* El valor de latitud y longitud debe ser un valor numérico en grados.
* El valor de latitud y longitud puede tener una precisión máxima de cinco decimales.
* El valor de latitud debe situarse entre -90 y 90.
* El valor de longitud debe situarse entre -180 y 180.

+++

### ¿Cómo funciona la segmentación geográfica en los dispositivos móviles?

+++Ver detalles
La mayoría de los usuarios de dispositivos móviles acceden al contenido a través de WiFi, lo que significa que la segmentación geográfica basada en IP de [!DNL Target] es tan precisa como en un equipo de escritorio. Las conexiones basadas en torres celulares pueden ser menos exactas porque la dirección IP del visitante se basa en la torre de donde se está recibiendo la señal. Algunos problemas de localización geográfica móvil se pueden resolver con la [API de geolocalización](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API).

+++

### ¿Cómo gestiona la función geográfica los visitantes de AOL?

+++Ver detalles
Debido a la forma en que AOL proporciona su tráfico, [!DNL Target] solo puede dirigirlos a nivel de país. Por ejemplo, una campaña dirigida a Francia se dirige correctamente a los usuarios de AOL en Francia. Sin embargo, una campaña dirigida a París no tiene como objetivo exitoso a los usuarios de AOL en París. Si desea realizar el enfoque específicamente para usuarios de AOL, puede establecer el campo de región en “aol”. De hecho, puede dirigirse a usuarios de AOL de EE. UU. si especifica dos condiciones de segmentación: un país que coincida exactamente con “united states” (Estados Unidos) y una región que coincida exactamente con “aol”.

+++

### ¿Qué granularidad de ubicación ofrece la segmentación geográfica?

+++Ver detalles
* País: global
* Estado/provincia/región: global
* Ciudad: global
* Código postal: EE. UU., Alemania, Canadá
* DMA/ITV (Reino Unido): EE. UU., Reino Unido
* Operador de telefonía móvil - global

+++

### ¿Cómo puedo probar las actividades si soy un usuario de una ubicación diferente?

+++Ver detalles
* **at.js 1.*x***: puede anular su dirección IP con una dirección IP de una ubicación diferente y usar el parámetro `mboxOverride.browserIp url`. Por ejemplo, si su empresa está en el Reino Unido, pero la campaña global está dirigida a visitantes de Auckland, Nueva Zelanda, use este estilo de dirección URL suponiendo que `60.234.0.39` es una dirección IP de Auckland:

  `https://www.mycompany.com?mboxOverride.browserIp=60.234.0.39`

  Borre las cookies antes de probar la actividad.

  >[!NOTE]
  >
  >`mboxOverride.browserIp` se admite en at.js 1.Solamente *x*. Esta funcionalidad no es compatible con at.js 2.*x*.

* **at.js 2.*x***: Para anular su dirección IP con at.js 2.*x*, instale una extensión/complemento del explorador (como X-Forwarded-For Header para Chrome o Firefox). Esta extensión le permite pasar el encabezado x-forwarded-for en las solicitudes de página.

+++

### ¿Cómo se asignan los territorios, como Puerto Rico y Hong Kong, a la estructura de targeting geográfico?

+++Ver detalles
Puerto Rico, Hong Kong y otros territorios se tratan como valores de “País” independientes.

+++

### ¿[!DNL Target] captura (y almacena) información como el código postal cuando la actividad está segmentada con capacidades de segmentación por ubicación geográfica?

+++Ver detalles
No, [!DNL Target] utiliza datos geográficos solo durante la sesión, por lo que los datos se descartan.

+++

## Vídeo de formación: Creación de audiencias ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo contiene información sobre el uso de las categorías de audiencias.

* Crear audiencias
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)
