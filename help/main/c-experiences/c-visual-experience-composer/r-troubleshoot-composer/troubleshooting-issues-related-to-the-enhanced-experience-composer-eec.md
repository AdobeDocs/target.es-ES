---
keywords: Segmentación;eec;compositor de experiencias visuales;resolución de problemas del compositor de experiencias mejorado;resolución de problemas
description: Aprenda a solucionar problemas que a veces ocurren en  [!DNL Adobe Target] [!UICONTROL Enhanced Experience Composer] (EEC) en ciertas condiciones.
title: ¿Cómo puedo solucionar problemas relacionados con [!UICONTROL Enhanced Experience Composer]?
feature: Visual Experience Composer (VEC)
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
source-git-commit: ef5df0ae37ca1d07c0e51c06ed78739b2d2983fc
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 22%

---

# Resolución de problemas relacionados con [!UICONTROL Enhanced Experience Composer]

Los problemas de visualización a veces ocurren en [!DNL Adobe Target] [!UICONTROL Enhanced Experience Composer] (EEC) bajo ciertas condiciones.

## El EEC no carga una URL de control de calidad interna que no es accesible desde una IP pública. {#section_D29E96911D5C401889B5EACE267F13CF}


+++Detalles
Este problema se puede resolver mediante la inclusión en la lista de permitidos de las siguientes direcciones IP. Estas direcciones IP son para el servidor [!DNL Adobe] utilizado para el proxy EEC. Estas direcciones IP solo son necesarias para la edición de actividades. Los visitantes del sitio no necesitan estas direcciones IP incluidas en la lista de permitidos.

Solicite a su equipo de TI que realice la lista de permitidos de las siguientes direcciones IP:

### EE. UU. (va7)

40.70.154.136/29
52.254.106.240/28
52.254.106.160/28
52.254.107.16/28
20.186.185.181
20.22.83.112
20.186.185.227
52.254.106.192/28
52.254.106.0/28
52.254.107.128/28
52.254.107.80/28
52.254.106.176/28
52.254.107.32/28
52.254.105.192/28
52.254.107.64/28
52.254.106.208/28
52.254.107.0/28
52.254.106.224/28
20.14.241.153
20.186.185.239
4.152.211.251
52.254.107.144/28
52.254.106.144/28

### EMEA (nld2)

51.138.17.16/28
51.138.17.48/28
51.138.16.128/28
51.138.17.32/28
51.138.16.240/28
51.138.17.112/28
51.138.16.160/28
51.138.16.208/28
51.138.17.80/28
51.138.17.0/28
51.138.17.96/28
51.138.16.144/28
20.31.145.248
20.126.189.248
51.138.16.224/28
51.138.16.192/28
51.138.12.94
51.138.12.11
51.138.16.176/28
51.138.12.100
51.138.17.64/28
51.138.12.160/28

### APAC (aus)

20.43.104.160/28
20.227.35.177
20.40.188.227
20.43.104.112/28
20.43.104.128/28
20.43.104.144/28
20.40.188.166
20.53.206.128
20.43.104.80/28
20.43.104.16/28
20.43.105.48/28
20.43.104.96/28
20.43.104.48/28
20.40.188.194
20.43.104.32/28
20.40.191.224/28
20.43.105.16/28
20.40.191.96/28
20.43.104.176/28
20.40.191.240/28
20.43.104.64/28
20.43.105.32/28
20.43.104.192/28
20.43.105.0/28
20.43.104.0/28

### Direcciones IP heredadas

Las siguientes direcciones IP heredadas deben seguir incluidas en la lista de permitidos hasta nuevo aviso.

34.254.77.200
54.73.207.147
54.229.152.123
3.224.194.242
54.90.51.39
34.228.136.112
54.150.116.11
18.178.142.8
54.199.107.77
99.80.139.221
54.78.56.224
54.247.179.246
54.80.219.243
34.201.235.54
54.196.224.236
35.75.212.45
52.199.184.130
18.180.161.176

Puede ver el siguiente mensaje de error en [!DNL Target]:

`Error: Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer]. You can allowlist the [!UICONTROL Enhanced Experience Composer]'s IP addresses or turn off [!UICONTROL Enhanced Experience Composer] in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![imagen EEC_error](assets/EEC_error.png)

Lo que sigue son motivos por los que podría ver este mensaje de error y remedios para la situación:

* **Problema:** El dominio del sitio web (ISP) está bloqueando [!UICONTROL Enhanced Experience Composer].

  **Remedy:** Lista de permitidos las direcciones IP enumeradas anteriormente.

* **Problema:** Las direcciones IP están incluidas en la lista de permitidos, pero el sitio web no admite TLS versión 1.2. [!DNL Target] actualmente usa la configuración predeterminada de 1.2. Antes de [!DNL Target] 18.4.1 (25 de abril de 2018), la configuración predeterminada admitía TLS 1.0. Para obtener más información, consulte [Cambios en el cifrado de TLS (Seguridad de capa de transporte)](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank}.

  **Solución:** Consulte la siguiente pregunta ([!UICONTROL Enhanced Visual Experience Composer] no se cargará en páginas seguras de mi sitio que usen TLS 1.2).

+++

## El EEC no se carga en páginas seguras de mi sitio que utilizan TLS 1.0. (Solo EEC)   {#section_C5B31E3D32A844F68E5A8153BD17551F}

+++Detalles
Podría ver el mensaje de error descrito en &quot;El [!UICONTROL Enhanced Visual Experience Composer] no se cargará en las páginas seguras de mi sitio&quot;. si las direcciones IP anteriores están incluidas en la lista de permitidos pero el sitio web no admite TLS versión 1.2. [!DNL Target] usa actualmente la configuración predeterminada de 1.2. Antes de [!DNL Target] 18.4.1 (25 de abril de 2018), la configuración predeterminada admitía TLS 1.0. Para obtener más información, consulte [Cambios en el cifrado de TLS (Seguridad de capa de transporte)](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank}.

Para consultar la versión TLS en su sitio web utilizando Firefox (otros navegadores tienen pasos similares):

1. Abra el sitio web afectado en Firefox.
1. Haga clic en el icono **[!UICONTROL Show Site Information]** en la barra de direcciones del explorador.

   ![imagen firefox_more_info](assets/firefox_more_info.png)

1. Haga clic en **[!UICONTROL Show Connection Details]** > **[!UICONTROL More Information]**.

   ![imagen de firefox_more_info_2](assets/firefox_more_info_2.png)

1. Examine la información de versión TLS en Detalles técnicos:

   ![imagen de firefox_more_info_3](assets/firefox_more_info_3.png)

1. Si descubre que su sitio web está mostrando TLS 1.0, consulte [Cambios en el cifrado de TLS (Seguridad de capa de transporte)](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank} para obtener información acerca de la directiva de compatibilidad con TLS de Target. Para solucionar la situación por el momento (válido hasta el 12 de septiembre de 2018){target=_blank}, póngase en contacto con el [Servicio de atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para configurar su versión TLS y el dominio.

+++

## Veo errores de tiempo de espera o “acceso denegado” al cargar sitios con el proxy habilitado. (Solo EEC)   {#section_60CBB9022DC449F593606C0E6252302D}

+++Detalles
Asegúrese de que las IP del proxy no estén bloqueadas en el entorno.

+++
