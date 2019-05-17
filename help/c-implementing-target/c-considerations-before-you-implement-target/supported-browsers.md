---
description: La aplicación y la entrega de contenido de Adobe Target se han probado en un amplio abanico de navegadores y dispositivos.
keywords: requisitos previos;requisitos;exploradores;internet explorer;chrome;firefox;safari;android;surface
seo-description: La aplicación y la entrega de contenido de Adobe Target se han probado en un amplio abanico de navegadores y dispositivos.
seo-title: Navegadores admitidos
solution: Target
subtopic: Primeros pasos
title: Navegadores admitidos
topic: Standard
uuid: 614088da-412c-45e3-9f2d-6985391973be
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Navegadores admitidos{#supported-browsers}

La aplicación y la entrega de contenido de [!DNL Adobe Target] se han probado en una amplia gama de navegadores y dispositivos.

Para obtener información importante sobre TLS, consulte [Cambios en el cifrado de TLS (Seguridad de la capa de transporte)](../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

## [!DNL Target]Interfaz de Standard/Premium {#section_1B73CA4B7BBC460BB7009DF00A2AFC4D}

La interfaz [!DNL [!DNL Target]] Standard/Premium] es compatible con los siguientes exploradores y dispositivos:

| Tipo de dispositivo | Versión del navegador |
|--- |--- |
| Windows | <ul><li>Microsoft Internet Explorer 11.<br>**Nota**: [!DNL Target] y Adobe Experience Cloud dejarán de ofrecer asistencia para Microsoft Internet Explorer 11 a partir de marzo de 2019. Este cambio solo afecta a la creación de [!DNL Target]; este cambio no afecta al envío de la experiencia. Cambie a Microsoft Edge u otro explorador compatible.</li><li>Microsoft Edge</li><li>Google Chrome (versión más reciente, la anterior a la más reciente)</li><li>Mozilla Firefox (versiones última y penúltima)</li></ul> |
| Mac | <ul><li>Firefox (versiones última y penúltima)</li><li>Chrome (versión más reciente, la anterior a la más reciente)</li></ul> |

## Entrega de contenido {#section_1045A946056441268D40025529918D3D}

La entrega de contenido se ha probado en los siguientes navegadores y dispositivos:

| Tipo de dispositivo | Versión del navegador |
|--- |--- |
| Windows | <ul><li>Internet Explorer 9 y 10. Probado en modo de emulación.<br>**Nota**: at.js 1.3.0 (y versiones posteriores) ya no es compatible con la entrega de contenido en Microsoft Internet Explorer 9.</li><li>Internet Explorer 11</li><li>Microsoft Edge</li><li>Chrome (versión más reciente, la anterior a la más reciente)</li><li>Firefox (versiones última y penúltima)</li></ul> |
| Mac | <ul><li>Apple Safari (versión más reciente)<br>**Nota**: Para obtener más información sobre cómo gestiona Safari las cookies de origen y de terceros, consulte [Cookie de Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/cookie-behavior.md).</li><li>Firefox (versiones última y penúltima)</li><li>Chrome (versión más reciente, la anterior a la más reciente)</li></ul> |
| Móvil o tableta | <ul><li>Apple iOS (versión más reciente)</li><li>Dispositivos y tabletas Android (Android 4 y versiones posteriores)</li><li>Microsoft Surface (Windows 8.1)</li></ul> |

Para implementaciones de [!DNL at.js], [!DNL Target] muestra el contenido predeterminado en versiones anteriores de Internet Explorer y, posiblemente, en versiones anteriores de los exploradores enumerados anteriormente. Para implementaciones de [!DNL mbox.js], [!DNL Target] intenta reproducir contenido, aunque podría no tener éxito.

[!DNL Target] muestra el contenido predeterminado en navegadores que no aparecen enumerados anteriormente y en navegadores que utilicen [quirks mode](https://en.wikipedia.org/wiki/Quirks_mode). at.js requiere un tipo de documento que se muestre en modo estándar, por ejemplo: `<!DOCTYPE html>`.

>[!NOTE]
>
>La infraestructura de Adobe Delivery está siendo protegida para NO admitir dispositivos y exploradores TLS 1.0 a partir del 12 de septiembre de 2018. Consulte [Cambios en el cifrado de TLS (Seguridad de capa de transporte)](../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451) para entender el impacto general de este cambio.
