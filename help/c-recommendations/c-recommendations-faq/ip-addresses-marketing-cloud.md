---
keywords: Dirección IP;direcciones IP;lista de direcciones permitidas;lista de permitidos;cortafuegos;recomendaciones;fuente;servidores;adobe marketing cloud;recommendations
description: Vea una lista de direcciones IP que se usan en los servidores de procesamiento de fuentes de Target Recommendations para configurar el firewall de modo que permita las direcciones IP procedentes de los servidores de Adobe.
title: ¿Qué direcciones IP utilizan los servidores de procesamiento de fuentes de Recommendations?
feature: Recommendations
translation-type: tm+mt
source-git-commit: 55b246f5f0d660e6c4f71352c5b638347d55ac28
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 13%

---


# ![PREMIUM](/help/assets/premium.png) Servidores de procesamiento de fuentes de Recommendations que usan direcciones IP

Lista de direcciones IP utilizadas en los servidores de procesamiento de fuentes [!DNL Adobe Target] [!DNL Recommendations] para ayudarle a configurar el firewall de modo que permita las direcciones IP procedentes de los servidores de Adobe.

[!DNL Target]  Las actividades de Recommendations utilizan las siguientes direcciones IP al acceder a los servidores FTP de los clientes:

| Anotación CIDR |
|---|
| 44.241.237.28/32 |
| 44.232.167.82/32 |
| 52.41.252.205/32 |

[!DNL Target]  Las API de Recommendations utilizan las siguientes direcciones IP:

| Anotación CIDR |
|---|
| 44.241.237.28/32 |
| 44.232.167.82/32 |
| 52.41.252.205/32 |

>[!NOTE]
>
>Estas direcciones IP se actualizaron por última vez el 16 de marzo de 2021. Anteriormente, los servidores que accedían a los servidores FTP estaban en el bloque CIDR de la dirección IP 192.243.242.0/24 . Los servidores que alojaban las API de Recommendations estaban en el bloque CIDR de la dirección IP 192.243.224.0/20 .

