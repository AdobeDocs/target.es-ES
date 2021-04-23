---
keywords: Dirección IP;direcciones IP;lista de direcciones permitidas;lista de permitidos;cortafuegos;recomendaciones;fuente;servidores;adobe marketing cloud;recommendations
description: 'Vea una lista de direcciones IP que se usan en los servidores de procesamiento de fuentes de Recommendations para configurar el firewall de modo que permita las direcciones IP procedentes de los servidores de Adobe. [!DNL Target] '
title: ¿Qué direcciones IP utilizan los servidores de procesamiento de fuentes de Recommendations?
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 8%

---

# ![PREMIUM](/help/assets/premium.png) Servidores de procesamiento de fuentes de Recommendations que usan direcciones IP

Lista de direcciones IP utilizadas en los servidores de procesamiento de fuentes [!DNL Adobe Target] [!DNL Recommendations] para ayudarle a configurar el firewall de modo que permita las direcciones IP procedentes de los servidores de Adobe.

[!DNL Target]  Las actividades de Recommendations utilizan los siguientes hosts de AWS al acceder a los servidores FTP de los clientes:

| Ubicación | Host |
| --- | --- |
| Oregón | `44.241.237.28` |
| Oregón | `44.232.167.82` |
| Oregón | `52.41.252.205` |

[!DNL Target]  Las API de Recommendations también utilizan los mismos hosts de AWS.

>[!NOTE]
>
>Estas direcciones IP se actualizaron por última vez el 16 de marzo de 2021. Anteriormente, los servidores que accedían a los servidores FTP estaban en el bloque CIDR de la dirección IP 192.243.242.0/24 . Los servidores que alojaban las API de Recommendations estaban en el bloque CIDR de la dirección IP 192.243.224.0/20 .
