---
keywords: Segmentación;eec;compositor de experiencias visuales;resolución de problemas del compositor de experiencias mejorado;resolución de problemas
description: Los problemas de visualización a veces ocurren en el Compositor de experiencias mejorado (EEC) bajo ciertas condiciones.
title: Resolución de problemas relacionados con el Compositor de experiencias mejorado
uuid: 2ea9a91f-08ca-4a06-ad5d-35ced140db14
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Resolución de problemas relacionados con el Compositor de experiencias mejorado{#troubleshooting-issues-related-to-the-enhanced-experience-composer}

Los problemas de visualización a veces ocurren en el Compositor de experiencias mejorado (EEC) bajo ciertas condiciones.

## El EEC no carga una URL de control de calidad interna que no es accesible desde una IP pública. (Solo EEC) {#section_D29E96911D5C401889B5EACE267F13CF}

Esto se puede resolver al hacer una lista blanca con las siguientes direcciones IP. Estas direcciones IP son para el servidor de Adobe y se usan para el proxy del Compositor de experiencias mejoradas. Solo se requieren para edición de actividades. Los visitantes del sitio no necesitan tener una lista blanca con estas direcciones IP

Pida al equipo de TI que incluya las siguientes direcciones IP en una lista blanca:

| Región | Direcciones IP | Nombres de host |
|--- |--- |--- |
| Estados Unidos | 52.55.99.45 | `us1-proxy.adobemc.com` |
| Europa, Oriente Medio y África (EMEA) | 52.51.238.221 | `emea1-proxy.adobemc.com` |
| Asia-Pacífico (APAC) | 52.193.67.35 | `apac1-proxy.adobemc.com` |

Puede ver el siguiente mensaje de error en Target:

`Error: Your website domain (ISP) is blocking the Enhanced Experience Composer. You can whitelist the Enhanced Experience Composer's IP addresses or turn off Enhanced Experience Composer in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![](assets/EEC_error.png)

Lo que sigue son motivos por los que podría ver este mensaje de error y remedios para la situación:

* **Problema**: el dominio del sitio web (ISP) está bloqueando el Compositor de experiencias mejorado.

   **Remedio:** incluya en la lista de direcciones permitidas las direcciones IP indicadas arriba.

* **Problema:** las direcciones IP están en una lista blanca, pero el sitio web no admite TLS versión 1.2. Target actualmente usa la configuración predeterminada de 1.2. Antes de Target 18.4.1 (25 de abril de 2018), la configuración predeterminada admitía TLS 1.0. Para obtener más información, consulte   [Cambios en el cifrado de TLS (Seguridad de capa de transporte)](../../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

   **Solución:** vea la siguiente pregunta (El Compositor de experiencias visuales mejorado no se carga en las páginas seguras en mi sitio que usan TLS 1.2).

## El EEC no se carga en páginas seguras de mi sitio que utilizan TLS 1.0. (Solo EEC) {#section_C5B31E3D32A844F68E5A8153BD17551F}

Podría ver el mensaje de error descrito en “El Compositor de experiencias visuales mejorado no se carga en las páginas seguras en mi sitio”. si las direcciones IP están en una lista blanca, pero el sitio web no admite TLS versión 1.2. Target actualmente usa la configuración predeterminada de 1.2. Antes de Target 18.4.1 (25 de abril de 2018), la configuración predeterminada admitía TLS 1.0. Para obtener más información, consulte   [Cambios en el cifrado de TLS (Seguridad de capa de transporte)](../../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

Para consultar la versión TLS en su sitio web utilizando Firefox (otros navegadores tienen pasos similares):

1. Abra el sitio web afectado en Firefox.
1. Haga clic en el icono **[!UICONTROL Mostrar información del sitio]en la barra de direcciones del navegador.**

   ![](assets/firefox_more_info.png)

1. Haga clic en **[!UICONTROL Mostrar detalles de conexión]** &gt; **[!UICONTROL Más información]**.

   ![](assets/firefox_more_info_2.png)

1. Examine la información de versión TLS en Detalles técnicos:

   ![](assets/firefox_more_info_3.png)

1. Si encuentra que el sitio web está mostrando TLS 1.0, consulte   [Cambios en el cifrado de TLS (Seguridad de capa de transporte)](../../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451) para obtener información sobre la política de compatibilidad con TLS de Target. Para solucionar la situación por el momento (válido hasta el 12 de septiembre de 2018), póngase en contacto con el [Servicio de atención al cliente](../../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para configurar su versión TLS y el dominio.

## Veo errores de tiempo de espera o “acceso denegado” al cargar sitios con el proxy habilitado. (Solo EEC) {#section_60CBB9022DC449F593606C0E6252302D}

Asegúrese de que las IP del proxy no estén bloqueadas en el entorno.
