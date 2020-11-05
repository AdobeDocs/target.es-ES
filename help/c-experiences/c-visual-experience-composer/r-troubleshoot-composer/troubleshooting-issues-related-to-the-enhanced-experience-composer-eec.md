---
keywords: Targeting;eec;visual experience composer;troubleshoot enhanced experience composer;troubleshooting
description: Los problemas de visualización a veces ocurren en el Compositor de experiencias mejorado (EEC) bajo ciertas condiciones.
title: Resolución de problemas relacionados con el Compositor de experiencias mejorado
feature: vec
uuid: 2ea9a91f-08ca-4a06-ad5d-35ced140db14
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 71%

---


# Resolución de problemas relacionados con el Compositor de experiencias mejorado{#troubleshooting-issues-related-to-the-enhanced-experience-composer}

Los problemas de visualización a veces ocurren en el Compositor de experiencias mejorado (EEC) bajo ciertas condiciones.

## El EEC no carga una URL de control de calidad interna que no es accesible desde una IP pública. (Solo EEC) {#section_D29E96911D5C401889B5EACE267F13CF}

Esto se puede resolver mediante la inclusión en la lista de permitidos de las siguientes direcciones IP. Estas direcciones IP son para el servidor de Adobe y se usan para el proxy del Compositor de experiencias mejoradas. Solo se requieren para edición de actividades. Los visitantes del sitio no necesitan estas direcciones IP incluidas en la lista de permitidos

Pida a su equipo de TI que lista de permitidos las siguientes direcciones IP:

| Región | Direcciones IP | Nombres de host |
|--- |--- |--- |
| Estados Unidos | 52.55.99.45 | `us1-proxy.adobemc.com` |
| Europa, Oriente Medio y África (EMEA) | 52.51.238.221 | `emea1-proxy.adobemc.com` |
| Asia-Pacífico (APAC) | 52.193.67.35 | `apac1-proxy.adobemc.com` |

Puede ver el siguiente mensaje de error en Target:

`Error: Your website domain (ISP) is blocking the Enhanced Experience Composer. You can allowlist the Enhanced Experience Composer's IP addresses or turn off Enhanced Experience Composer in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![](assets/EEC_error.png)

Lo que sigue son motivos por los que podría ver este mensaje de error y remedios para la situación:

* **Problema**: el dominio del sitio web (ISP) está bloqueando el Compositor de experiencias mejorado.

   **Remedio:** Lista de permitidos las direcciones IP enumeradas anteriormente.

* **Problema:** Las direcciones IP están incluidas en la lista de permitidos pero su sitio web no admite TLS versión 1.2. Destinatario utiliza actualmente la configuración predeterminada de 1.2. Antes del Destinatario 18.4.1 (25 de abril de 2018), la configuración predeterminada admitía TLS 1.0. Para obtener más información, consulte Cambios [](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)en el cifrado de TLS (Transport Layer Security).

   **Solución:** vea la siguiente pregunta (El Compositor de experiencias visuales mejorado no se carga en las páginas seguras en mi sitio que usan TLS 1.2).

## El EEC no se carga en páginas seguras de mi sitio que utilizan TLS 1.0. (Solo EEC) {#section_C5B31E3D32A844F68E5A8153BD17551F}

Podría ver el mensaje de error descrito en “El Compositor de experiencias visuales mejorado no se carga en las páginas seguras en mi sitio”. if the above IP addresses are allowlisted but your website does not support TLS version 1.2. Target currently uses the default configuration of 1.2. Prior to the Target 18.4.1 (April 25, 2018), the default configuration supported TLS 1.0. For more information, see [TLS (Transport Layer Security) Encryption Changes](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

Para consultar la versión TLS en su sitio web utilizando Firefox (otros navegadores tienen pasos similares):

1. Abra el sitio web afectado en Firefox.
1. Haga clic en el icono **[!UICONTROL Mostrar información del sitio]** en la barra de direcciones del navegador.

   ![](assets/firefox_more_info.png)

1. Haga clic en **[!UICONTROL Mostrar detalles de conexión]** > **[!UICONTROL Más información]**.

   ![](assets/firefox_more_info_2.png)

1. Examine la información de versión TLS en Detalles técnicos:

   ![](assets/firefox_more_info_3.png)

1. Si encuentra que el sitio web está mostrando TLS 1.0, consulte   [Cambios en el cifrado de TLS (Seguridad de capa de transporte)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451) para obtener información sobre la política de compatibilidad con TLS de Target. Para solucionar la situación por el momento (válido hasta el 12 de septiembre de 2018), póngase en contacto con el [Servicio de atención al cliente](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para configurar su versión TLS y el dominio.

## Veo errores de tiempo de espera o “acceso denegado” al cargar sitios con el proxy habilitado. (Solo EEC) {#section_60CBB9022DC449F593606C0E6252302D}

Asegúrese de que las IP del proxy no estén bloqueadas en el entorno.
