---
keywords: requisitos previos;requisitos;exploradores;internet explorer;chrome;firefox;safari;android;surface
description: Descubra qué Adobe de exploradores de Internet [!DNL Target] admite para su interfaz y para la entrega de contenido.
title: Qué hacen los navegadores [!DNL Target] ¿Asistencia?
feature: Implementation
role: Developer
exl-id: 8a366c79-d944-4d44-be5a-7c4f65385beb
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 39%

---

# Navegadores admitidos

La aplicación y la entrega de contenido de [!DNL Adobe Target] se han probado en una amplia gama de navegadores y dispositivos.

Para obtener información más importante sobre TLS, consulte [Cambios en el cifrado de TLS (Seguridad de capa de transporte)](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/){target=_blank}.

## [!DNL Target]Interfaz de Standard/Premium  {#section_1B73CA4B7BBC460BB7009DF00A2AFC4D}

La variable [!DNL Target] es compatible con los siguientes exploradores y dispositivos:

| Tipo de dispositivo | Versión del navegador |
|--- |--- |
| Windows | <ul><li>Microsoft Edge</li><li>Google Chrome (última versión, última versión menos 1)</li><li>Mozilla Firefox (última versión, última versión menos 1)</li></ul> |
| Mac | <ul><li>Firefox (último, último menos 1)</li><li>Chrome (última versión, última versión menos 1)</li></ul> |

## Entrega de contenido {#section_1045A946056441268D40025529918D3D}

La entrega de contenido se ha probado en los siguientes navegadores y dispositivos:

| Tipo de dispositivo | Versión del navegador |
|--- |--- |
| Windows | <ul><li>Microsoft Internet Explorer 9 y 10. Probado en modo de emulación.<br>**Nota**: La entrega de contenido en IE 9 ya no es compatible con at.js 1.3.0 (y versiones posteriores). La entrega de contenido en IE 10, 11 y todas las versiones anteriores ya no es compatible con at.js 2.5.0 (y versiones posteriores).</li><li>Internet Explorer 11 <br>**Nota**: La entrega de contenido en IE 10, 11 y todas las versiones anteriores ya no es compatible con at.js 2.5.0 (y versiones posteriores).</li><li>Microsoft Edge</li><li>Chrome (última versión, última versión menos 1)</li><li>Firefox (último, último menos 1)</li></ul> |
| Mac | <ul><li>Apple Safari (versión más reciente)<br>**Nota**: Para obtener más información sobre cómo gestiona Safari las cookies de origen y de terceros, consulte [Cookie de Target](https://developer.adobe.com/target/before-implement/privacy/cookie-behavior/){target=_blank}.</li><li>Firefox (último, último menos 1)</li><li>Chrome (última versión, última versión menos 1)</li></ul> |
| Móvil o tableta | <ul><li>Apple iOS (última versión)</li><li>Dispositivos y tabletas Android (Android 4 y versiones posteriores)</li><li>Microsoft Surface (Windows 8.1)</li></ul> |

Tenga en cuenta lo siguiente:

* Para implementaciones de [!DNL at.js], [!DNL Target] muestra el contenido predeterminado en versiones anteriores de Internet Explorer y, posiblemente, en versiones anteriores de los exploradores enumerados anteriormente.
* Internet Explorer trata todos los elementos desconocidos (como los elementos personalizados) como el mismo tipo de elemento. Como resultado, la entrega no funciona con elementos personalizados.
* [!DNL Target] muestra el contenido predeterminado en navegadores que no aparecen enumerados anteriormente y en navegadores que utilicen [quirks mode](https://en.wikipedia.org/wiki/Quirks_mode). at.js requiere un tipo de documento que se muestre en modo estándar, por ejemplo: `<!DOCTYPE html>`.
* La infraestructura de Adobe Delivery está siendo protegida para NO admitir dispositivos y exploradores TLS 1.0 a partir del 12 de septiembre de 2018. Consulte [Cambios en el cifrado de TLS (Seguridad de capa de transporte)](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/){target=_blank} para comprender el impacto general de este cambio.
