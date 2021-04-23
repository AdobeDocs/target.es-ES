---
keywords: implementar;implementación;lista de direcciones permitidas;lista de direcciones permitidas;lista de permitidos;lista de permitidos;borde;bordes
description: Vea una lista de hosts para ayudarle a almacenar en lista de permitidos los Adobes [!DNL Target] bordes (nodos de servicio distribuidos geográficamente que aseguran tiempos de respuesta óptimos para los usuarios finales).
title: ¿Cómo Lista de permitidos los nodos [!DNL Target] Edge?
feature: Privacidad y seguridad
role: Developer
exl-id: 2d8399b9-eec8-40b0-8b35-2812f83ff4dc
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 6%

---

# Nodos perimetrales [!DNL Target] de lista de permitidos

Información y una lista actualizada de hosts para ayudarle a realizar la lista de permitidos de [!DNL Adobe Target] bordes.

Una arista es una arquitectura de servidores distribuidos geográficamente que garantiza tiempos de respuesta óptimos para los usuarios finales que solicitan contenido, independientemente de su ubicación. Cada nodo perimetral tiene toda la información necesaria para responder a la solicitud de contenido del usuario y para rastrear los datos de análisis de esa solicitud. Las solicitudes de usuario se dirigen al nodo perimetral más cercano. Para obtener más información, consulte [The edge network](/help/c-intro/how-target-works.md#concept_0AE2ED8E9DE64288A8B30FCBF1040934) en *Cómo funciona el Adobe [!DNL Target]*.

Si lo desea, puede realizar la lista de permitidos de [!DNL Target] nodos perimetrales.

## Direcciones de red Traducción de direcciones (NAT) Direcciones IP de [!DNL Target] bordes

Lista de direcciones IP de salida de [!DNL Target] bordes. Lista de permitidos estas IP si planea que Target se ponga en contacto con sus servicios.

| Ubicación de borde | Direcciones IP de salida |
| --- | --- |
| Edge31 (Bombay) | 13.126.131.246<br>13.234.229.8 |
| Edge32 (Tokio) | 3.115.154.28<br>3.115.227.146 |
| Edge34 (costa este de EE. UU.) | 34.232.149.249<br>52.21.139.93 |
| Edge35 (Costa Oeste de EE. UU.) | 52.10.11.139<br>44.231.171.161 |
| Edge36 (Sydney) | 13 237 227 20<br>13 210 93 142 |
| Edge37 (Irlanda) | 54.72.21.68<br>52.208.139.19 |
| Edge38 (Singapur) | 18.141.132.96<br>54.179.187.167 |

## Direcciones IP perimetrales de Target

Lista de direcciones IP de los bordes [!DNL Target]. Lista de permitidos estas direcciones IP si desea realizar llamadas de API a los perímetros de Target.

| Ubicación de borde | Dominio | Direcciones IP |
| --- | --- | --- |
|  | `CLIENTCODE.tt.omtrdc.net`<br>(donde CLIENTCODE es su ID de  [!DNL Target] cliente) |  |
| Edge31 (Bombay) | `mboxedge31.tt.omtrdc.net` | 15.207.157.131<br>15.206.8.201 |
| Edge32 (Tokio) | `mboxedge32.tt.omtrdc.net` | 54.199.66.101<br>54.64.93.37 |
| Edge34 (costa este de EE. UU.) | `mboxedge34.tt.omtrdc.net` | 3.225.56.36<br>3.230.207.249<br>34.198.55.51<br>52.3.14.12<br>52.21.222.9 3<br>52.55.235.132<br>52.70.52.52<br>54.165.204.89 |
| Edge35 (Costa Oeste de EE. UU.) | `mboxedge35.tt.omtrdc.net` | 52.10.244.20<br>52.36.232.38<br>52.88.209.29<br>54.214.180.56<br>35.162 74.35<br>34.214.12.211<br>52.42.35.202<br>54.148.71.13 |
| Edge36 (Sydney) | `mboxedge36.tt.omtrdc.net` | 13.238.34.185<br>3.24.250.17<br>3.104.234.91<br>13.211.248.241 |
| Edge37 (Irlanda) | `mboxedge37.tt.omtrdc.net` | 52.212.193.208<br>52.19.133.54<br>52.51.251.137<br>34.252.156.174<br>5 2.213.168.74<br>34.252.166.160<br>52.18.150.20<br>18.203.205.32 |
| Edge38 (Singapur) | `mboxedge38.tt.omtrdc.net` | 52.221.145.65<br>52.220.44.99<br>13.250.75.226<br>54.151.139.123 |
