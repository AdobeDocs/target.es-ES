---
keywords: dirección IP;direcciones IP;lista de permitidos;cortafuegos;recomendaciones;fuente;servidores;adobe experience cloud;recommendations
description: Consulte la lista de direcciones IP que se usan en los servidores de procesamiento de fuentes de recomendaciones de  [!DNL Target]  para configurar el firewall de modo que admita las direcciones IP procedentes de los servidores de Adobe.
title: ¿Qué direcciones IP utilizan los servidores de procesamiento de fuentes de Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
source-git-commit: be5b3158c758fa08802c1dc0541c9e989a2c7740
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 35%

---

# Direcciones IP que usaron [!DNL Recommendations] servidores de procesamiento de fuentes

Lista de direcciones IP que se usaron en [!DNL Adobe Target] [!DNL Recommendations] servidores de procesamiento de fuentes para configurar el firewall de modo que admita las direcciones IP procedentes de [!DNL Adobe] servidores.

>[!IMPORTANT]
>
>El equipo [!DNL Target] está actualizando actualmente las direcciones de puerta de enlace NAT para descargar fuentes de [!DNL Recommendations]. Si implementa la inclusión en la lista de permitidos de IP, asegúrese de realizar la lista de permitidos de los siguientes hosts nuevos de AWS. Los hosts existentes están programados para su retirada el 30 de junio de 2024. Para garantizar una transición sin problemas, realice la lista de permitidos de las nueve direcciones. No es urgente eliminar las direcciones existentes.

[!DNL Target] actividades [!UICONTROL Recommendations] utilizan los siguientes hosts de AWS al acceder a los servidores FTP de los clientes:

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

[!DNL Target] [!UICONTROL Recommendations] API también usan los mismos hosts de AWS.
