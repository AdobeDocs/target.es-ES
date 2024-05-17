---
keywords: Segmentación;eec;compositor de experiencias visuales;resolución de problemas del compositor de experiencias mejorado;resolución de problemas
description: Aprenda a solucionar problemas que a veces se producen en el Adobe [!DNL Target] Compositor de experiencias mejorado (EEC) bajo ciertas condiciones.
title: ¿Cómo puedo solucionar problemas relacionados con el Compositor de experiencias mejorado?
feature: Visual Experience Composer (VEC)
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
source-git-commit: 7562a1da201b570ee529db9763ef5f4b463f65a8
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 23%

---

# Resolución de problemas relacionados con [!UICONTROL Enhanced Experience Composer]

Los problemas de visualización a veces ocurren en [!DNL Adobe Target] [!UICONTROL Enhanced Experience Composer] (CEE) en determinadas condiciones.

## El EEC no carga una URL de control de calidad interna que no es accesible desde una IP pública. {#section_D29E96911D5C401889B5EACE267F13CF}

Esto se puede resolver mediante la inclusión en la lista de permitidos de las siguientes direcciones IP. Estas direcciones IP son para el servidor de Adobe utilizado para el proxy EEC. Solo se requieren para edición de actividades. Los visitantes del sitio no necesitan estas direcciones IP incluidas en la lista de permitidos.

Solicite a su equipo de TI que realice la lista de permitidos de las siguientes direcciones IP:

* 34 254 77 200
* 54.73.207.147
* 54 229 152 123
* 3 224 194 242
* 54 90 51 39
* 34 228 136 112
* 54 150 116 11
* 18.178.142.8
* 54 199 107 77
* 99 80 139 221
* 54.78.56.224
* 54 247 179 246
* 54.80.219.243
* 34 201 235 54
* 54 196 224 236
* 35.75.212.45
* 52 199 184 130
* 18 180 161 176

Puede ver el siguiente mensaje de error en [!DNL Target]:

`Error: Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer]. You can allowlist the [!UICONTROL Enhanced Experience Composer]'s IP addresses or turn off [!UICONTROL Enhanced Experience Composer] in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![Imagen EEC_error](assets/EEC_error.png)

Lo que sigue son motivos por los que podría ver este mensaje de error y remedios para la situación:

* **Problema:** El dominio del sitio web (ISP) está bloqueando el [!UICONTROL Enhanced Experience Composer].

  **Solución:** Lista de permitidos las direcciones IP enumeradas anteriormente.

* **Problema:** Las direcciones IP están incluidas en la lista de permitidos, pero el sitio web no admite TLS versión 1.2. [!DNL Target] actualmente utiliza la configuración predeterminada de 1.2. Antes de la [!DNL Target] 18.4.1 (25 de abril de 2018), la configuración predeterminada admite TLS 1.0. Para obtener más información, consulte [Cambios en el cifrado de TLS (Seguridad de capa de transporte)](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank}.

  **Solución:** Consulte la siguiente pregunta (La [!UICONTROL Enhanced Visual Experience Composer] no se carga en páginas seguras de mi sitio que utilizan TLS 1.2).

## El EEC no se carga en páginas seguras de mi sitio que utilizan TLS 1.0. (Solo EEC)   {#section_C5B31E3D32A844F68E5A8153BD17551F}

Podría ver el mensaje de error descrito anteriormente en &quot;La [!UICONTROL Enhanced Visual Experience Composer] no se carga en páginas seguras de mi sitio&quot;. si las direcciones IP anteriores están incluidas en la lista de permitidos, pero el sitio web no admite TLS versión 1.2. [!DNL Target] actualmente utiliza la configuración predeterminada de 1.2. Antes de la [!DNL Target] 18.4.1 (25 de abril de 2018), la configuración predeterminada admite TLS 1.0. Para obtener más información, consulte [Cambios en el cifrado de TLS (Seguridad de capa de transporte)](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank}.

Para consultar la versión TLS en su sitio web utilizando Firefox (otros navegadores tienen pasos similares):

1. Abra el sitio web afectado en Firefox.
1. Haga clic en **[!UICONTROL Show Site Information]** en la barra de direcciones del navegador.

   ![imagen firefox_more_info](assets/firefox_more_info.png)

1. Clic **[!UICONTROL Show Connection Details]** > **[!UICONTROL More Information]**.

   ![imagen firefox_more_info_2](assets/firefox_more_info_2.png)

1. Examine la información de versión TLS en Detalles técnicos:

   ![imagen firefox_more_info_3](assets/firefox_more_info_3.png)

1. Si encuentra que el sitio web está mostrando TLS 1.0, consulte [Cambios en el cifrado de TLS (Seguridad de capa de transporte)](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank} para obtener información acerca de la directiva de compatibilidad con TLS de Target. Para remediar la situación por ahora (válido hasta el 12 de septiembre de 2018){target=_blank}, póngase en contacto con [Atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para la configuración con su versión TLS y el dominio.

## Veo errores de tiempo de espera o “acceso denegado” al cargar sitios con el proxy habilitado. (Solo EEC)   {#section_60CBB9022DC449F593606C0E6252302D}

Asegúrese de que las IP del proxy no estén bloqueadas en el entorno.
