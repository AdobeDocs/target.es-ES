---
keywords: dirección IP;direcciones IP;lista de permitidos;cortafuegos;recomendaciones;fuente;servidores;adobe experience cloud;recommendations
description: Vea una lista de direcciones IP que se usan en [!DNL Target] servidores de procesamiento de fuentes de Recommendations para configurar el firewall de modo que permita las direcciones IP procedentes de los servidores de Adobe.
title: ¿Qué direcciones IP utilizan los servidores de procesamiento de fuentes de Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
TQID: 'https://experienceleague.adobe.com/-EhfjK6jTuHX33utQig-XYhf-nzkWlxb58VRmK9fLWo'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 19%
---
# Direcciones IP que usaron [!DNL Recommendations] servidores de procesamiento de fuentes

Lista de direcciones IP que se usaron en [!DNL Adobe Target] [!DNL Recommendations] servidores de procesamiento de fuentes para configurar el firewall de modo que admita las direcciones IP procedentes de [!DNL Adobe] servidores.

>[!IMPORTANT]
>
>El equipo [!DNL Target] está actualizando actualmente las direcciones de puerta de enlace NAT para descargar fuentes de [!DNL Recommendations]. Si implementa la inclusión en la lista de permitidos de IP, asegúrese de realizar la lista de permitidos de los siguientes hosts nuevos de AWS. Los hosts existentes están programados para su retirada el 30 de junio de 2024. Para garantizar una transición sin problemas, realice la lista de permitidos de las nueve direcciones. No es urgente eliminar las direcciones existentes.

Las actividades de [!DNL Target] [!UICONTROL Recommendations] utilizan los siguientes hosts de AWS al acceder a los servidores FTP de los clientes:

**Nuevos hosts**:

| Ubicación | Host |
| --- | --- |
| Oregón | `52.40.124.129` |
| Oregón | `54.148.219.69` |
| Oregón | `54.189.208.212` |
| Oregón | `44.230.236.35` |
| Oregón | `54.190.78.243` |
| Oregón | `52.41.73.133` |

**Hosts existentes**:

| Ubicación | Host |
| --- | --- |
| Oregón | `44.241.237.28` |
| Oregón | `44.232.167.82` |
| Oregón | `52.41.252.205` |

[!DNL Target] [!UICONTROL Las API de Recommendations] también usan los mismos hosts de AWS.
