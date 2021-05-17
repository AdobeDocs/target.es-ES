---
keywords: Segmentación;eec;compositor de experiencias visuales;resolución de problemas del compositor de experiencias mejorado;resolución de problemas
description: Obtenga información sobre cómo solucionar problemas que a veces ocurren en el Compositor de experiencias mejorado (EEC) de Adobe [!DNL Target] en ciertas condiciones.
title: ¿Cómo puedo solucionar problemas relacionados con el Compositor de experiencias mejorado?
feature: 'Compositor de experiencias visuales (VEC) '
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
source-git-commit: b14c9bb4bc0363c77de084c7ae7110e73c5f2f13
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 53%

---

# Resolución de problemas relacionados con el [!UICONTROL Compositor de experiencias mejorado]

Los problemas de visualización a veces ocurren en el [!DNL Adobe Target] [!UICONTROL Compositor de experiencias mejorado] (EEC) bajo ciertas condiciones.

## El EEC no carga una URL de control de calidad interna que no es accesible desde una IP pública. {#section_D29E96911D5C401889B5EACE267F13CF}

Esto se puede resolver mediante la inclusión en la lista de permitidos de las siguientes direcciones IP. Estas direcciones IP son para el servidor de Adobe utilizado para el proxy EEC. Solo se requieren para edición de actividades. Los visitantes del sitio no necesitan estas direcciones IP incluidas en la lista de permitidos.

Pida a su equipo de TI que lista de permitidos las siguientes direcciones IP:

* 52.55.99.45
* 52.51.238.221
* 52.193.67.35

Puede ver el siguiente mensaje de error en [!DNL Target]:

`Error: Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer]. You can allowlist the [!UICONTROL Enhanced Experience Composer]'s IP addresses or turn off [!UICONTROL Enhanced Experience Composer] in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![](assets/EEC_error.png)

Lo que sigue son motivos por los que podría ver este mensaje de error y remedios para la situación:

* **Problema**[!UICONTROL : el dominio del sitio web (ISP) está bloqueando el Compositor de experiencias mejorado].

   **Remedio:** Lista de permitidos de las direcciones IP enumeradas anteriormente.

* **Problema:** las direcciones IP están incluidas en la lista de permitidos, pero el sitio web no admite TLS versión 1.2.  [!DNL Target] actualmente usa la configuración predeterminada de 1.2. Antes de la versión  [!DNL Target] 18.4.1 (25 de abril de 2018), la configuración predeterminada admitía TLS 1.0. Para obtener más información, consulte Cambios [ en el cifrado de ](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)TLS (Seguridad de capa de transporte).

   **Solución:**[!UICONTROL  vea la siguiente pregunta (El Compositor de experiencias visuales mejorado no se carga en las páginas seguras en mi sitio que usan TLS 1.2).]

## El EEC no se carga en páginas seguras de mi sitio que utilizan TLS 1.0. (Solo EEC)   {#section_C5B31E3D32A844F68E5A8153BD17551F}

Podría ver el mensaje de error descrito anteriormente en &quot;El [!UICONTROL Compositor de experiencias visuales mejorado] no se carga en las páginas seguras de mi sitio&quot;. si las direcciones IP anteriores están incluidas en la lista de permitidos pero su sitio web no es compatible con TLS versión 1.2. [!DNL Target] actualmente utiliza la configuración predeterminada de 1.2. Antes de [!DNL Target] 18.4.1 (25 de abril de 2018), la configuración predeterminada admitía TLS 1.0. Para obtener más información, consulte [Cambios de codificación de TLS (seguridad de capa de transporte)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

Para consultar la versión TLS en su sitio web utilizando Firefox (otros navegadores tienen pasos similares):

1. Abra el sitio web afectado en Firefox.
1. Haga clic en el icono **[!UICONTROL Mostrar información del sitio]** en la barra de direcciones del navegador.

   ![](assets/firefox_more_info.png)

1. Haga clic en **[!UICONTROL Mostrar detalles de conexión]** > **[!UICONTROL Más información]**.

   ![](assets/firefox_more_info_2.png)

1. Examine la información de versión TLS en Detalles técnicos:

   ![](assets/firefox_more_info_3.png)

1. Si encuentra que el sitio web está mostrando TLS 1.0, consulte   [Cambios en el cifrado de TLS (Seguridad de capa de transporte)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451) para obtener información sobre la política de compatibilidad con TLS de Target. Para solucionar la situación por el momento (válido hasta el 12 de septiembre de 2018), póngase en contacto con el [Servicio de atención al cliente](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para configurar su versión TLS y el dominio.

## Veo errores de tiempo de espera o “acceso denegado” al cargar sitios con el proxy habilitado. (Solo EEC)   {#section_60CBB9022DC449F593606C0E6252302D}

Asegúrese de que las IP del proxy no estén bloqueadas en el entorno.
