---
keywords: dirección IP;direcciones IP;lista de direcciones permitidas;lista de permitidos;servidor de seguridad;registros;fuente;servidores;adobe marketing cloud;recomendaciones
description: Vista de una lista de direcciones IP utilizadas en los servidores de procesamiento de fuentes de Recommendations de Destinatario para ayudarle a configurar el servidor de seguridad de modo que permita las direcciones IP que se originan en los servidores de Adobe.
title: ¿Qué direcciones IP utilizan los servidores de procesamiento de fuentes de Recommendations?
feature: Recommendations
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 61%

---


# ![PREMIUM](/help/assets/premium.png) Servidores de procesamiento de fuentes de Recommendations que usan direcciones IP{#ip-addresses-used-by-recommendations-feed-processing-servers}

Esta es la lista de direcciones IP que se usan en los servidores de procesamiento de fuentes de Recommendations en el centro de datos de Oregon para configurar el firewall de modo que bloquee las direcciones IP procedentes de los servidores de Adobe.

Las actividades de[!DNL Target] [!UICONTROL Recommendations] de utilizan las siguientes direcciones IP, ubicadas en el centro de datos de Oregon, al acceder a los servidores FTP de los clientes (asegúrese de comprobar el vínculo que aparece abajo para consultar la información más actual):

| Anotación CIDR | IP inicial | IP final |
|---|---|---|
| 192.243.242.0/24 | 192.243.242.0 | 192.243.242.255 |

Las API de[!DNL Target] [!UICONTROL Recommendations ]se utilizan las siguientes direcciones IP, ubicadas en el centro de datos de Oregon (asegúrese de comprobar el vínculo que aparece abajo para consultar la información más actual):

| Anotación CIDR | IP inicial | IP final |
|---|---|---|
| 192.243.224.0/20 | 192.243.224.0 | 192.243.239.255 |

>[!NOTE]
>
>Para obtener la lista completa y más actualizada, consulte [Direcciones IP utilizadas en el Adobe Experience Cloud](https://helpx.adobe.com/analytics/kb/adobe-ip-addresses.html).

