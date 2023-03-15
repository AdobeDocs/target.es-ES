---
keywords: dirección IP;direcciones IP;lista de permitidos;cortafuegos;recomendaciones;fuente;servidores;adobe experience cloud;recommendations
description: Consulte la lista de direcciones IP que se usan en los servidores de procesamiento de fuentes de recomendaciones de  [!DNL Target]  para configurar el firewall de modo que admita las direcciones IP procedentes de los servidores de Adobe.
title: ¿Qué direcciones IP utilizan los servidores de procesamiento de fuentes de Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 100%

---

# Direcciones IP que usan los servidores de procesamiento de fuentes de Recommendations

Consulte la lista de direcciones IP que se usan en los servidores de procesamiento de fuentes de [!DNL Adobe Target] [!DNL Recommendations] para configurar el firewall de modo que admita las direcciones IP procedentes de los servidores de Adobe.

Las actividades de [!DNL Target] [!UICONTROL Recommendations] utilizan los siguientes hosts de AWS al acceder a los servidores FTP de los clientes:

| Ubicación | Host |
| --- | --- |
| Oregón | `44.241.237.28` |
| Oregón | `44.232.167.82` |
| Oregón | `52.41.252.205` |

Las API de [!DNL Target] [!UICONTROL Recommendations] también utilizan los mismos hosts de AWS.

>[!NOTE]
>
>Estas direcciones IP se actualizaron por última vez el 16 de marzo de 2021. Anteriormente, los servidores que accedían a los servidores FTP estaban en el bloque CIDR de la dirección IP 192.243.242.0/24. Los servidores que alojaban las API de Recommendations estaban en el bloque CIDR de la dirección IP 192.243.224.0/20.
