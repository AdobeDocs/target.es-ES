---
keywords: Segmentación;eec;compositor de experiencias visuales;resolución de problemas del compositor de experiencias mejorado;resolución de problemas
description: Obtenga información sobre cómo solucionar problemas que a veces ocurren en el Adobe [!DNL Target] Compositor de experiencias mejorado (EEC) en determinadas condiciones.
title: ¿Cómo puedo solucionar problemas relacionados con el Compositor de experiencias mejorado?
feature: Visual Experience Composer (VEC)
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 42%

---

# Resolución de problemas relacionados con el [!UICONTROL Compositor de experiencias mejorado]

Los problemas de visualización a veces ocurren en la variable [!DNL Adobe Target] [!UICONTROL Compositor de experiencias mejorado] (CEE) en determinadas condiciones.

## El EEC no carga una URL de control de calidad interna que no es accesible desde una IP pública. {#section_D29E96911D5C401889B5EACE267F13CF}

Esto se puede resolver mediante la inclusión en la lista de permitidos de las siguientes direcciones IP. Estas direcciones IP son para el servidor de Adobe utilizado para el proxy EEC. Solo se requieren para edición de actividades. Los visitantes del sitio no necesitan estas direcciones IP incluidas en la lista de permitidos.

Pida a su equipo de TI que lista de permitidos las siguientes direcciones IP:

* 34.253.100.20
* 34.248.100.23
* 52.49.228.246
* 54.205.42.123
* 107.22.177.39
* 52.201.5.105
* 52.193.211.177
* 18.180.24.249
* 52.194.154.154

Puede ver el siguiente mensaje de error en [!DNL Target]:

`Error: Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer]. You can allowlist the [!UICONTROL Enhanced Experience Composer]'s IP addresses or turn off [!UICONTROL Enhanced Experience Composer] in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![Imagen EEC_error](assets/EEC_error.png)

Lo que sigue son motivos por los que podría ver este mensaje de error y remedios para la situación:

* **Problema**[!UICONTROL : el dominio del sitio web (ISP) está bloqueando el Compositor de experiencias mejorado].

   **Remedio:** Lista de permitidos de las direcciones IP enumeradas anteriormente.

* **Problema:** Las direcciones IP están incluidas en la lista de permitidos, pero el sitio web no admite TLS versión 1.2. [!DNL Target] actualmente utiliza la configuración predeterminada de 1.2. Antes de [!DNL Target] 18.4.1 (25 de abril de 2018), la configuración predeterminada admite TLS 1.0. Para obtener más información, consulte [Cambios en el cifrado de TLS (Seguridad de capa de transporte)](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank}.

   **Solución:**[!UICONTROL  vea la siguiente pregunta (El Compositor de experiencias visuales mejorado no se carga en las páginas seguras en mi sitio que usan TLS 1.2).]

## El EEC no se carga en páginas seguras de mi sitio que utilizan TLS 1.0. (Solo EEC)   {#section_C5B31E3D32A844F68E5A8153BD17551F}

Puede ver el mensaje de error descrito anteriormente en &quot;La variable [!UICONTROL Compositor de experiencias visuales mejorado] no se carga en páginas seguras en mi sitio&quot;. si las direcciones IP anteriores están incluidas en la lista de permitidos, pero su sitio web no admite TLS versión 1.2. [!DNL Target] actualmente utiliza la configuración predeterminada de 1.2. Antes de [!DNL Target] 18.4.1 (25 de abril de 2018), la configuración predeterminada admite TLS 1.0. Para obtener más información, consulte [Cambios en el cifrado de TLS (Seguridad de capa de transporte)](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank}.

Para consultar la versión TLS en su sitio web utilizando Firefox (otros navegadores tienen pasos similares):

1. Abra el sitio web afectado en Firefox.
1. Haga clic en el icono **[!UICONTROL Mostrar información del sitio]** en la barra de direcciones del navegador.

   ![imagen firefox_more_info](assets/firefox_more_info.png)

1. Haga clic en **[!UICONTROL Mostrar detalles de conexión]** > **[!UICONTROL Más información]**.

   ![imagen firefox_more_info_2](assets/firefox_more_info_2.png)

1. Examine la información de versión TLS en Detalles técnicos:

   ![imagen firefox_more_info_3](assets/firefox_more_info_3.png)

1. Si encuentra que el sitio web está mostrando TLS 1.0, consulte [Cambios en el cifrado de TLS (Seguridad de capa de transporte)](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank} for information about Target's TLS support policy. To remedy the situation for now (valid until September 12, 2018){target=_blank}, póngase en contacto con [Servicio de atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para configurar con su versión TLS y el dominio .

## Veo errores de tiempo de espera o “acceso denegado” al cargar sitios con el proxy habilitado. (Solo EEC)   {#section_60CBB9022DC449F593606C0E6252302D}

Asegúrese de que las IP del proxy no estén bloqueadas en el entorno.
