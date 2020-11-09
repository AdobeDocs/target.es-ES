---
keywords: advanced mbox.js settings;client;server domain;xdomain;compression level;client session id support;secureOnly;client pc id support;pass page;referring url;traffic level;traffic duration;mboxParameters() function body;mboxSupported() function body;mboxCookieDomain() function body;Extra JavaScript;SiteCatalyst plug-in;Get mbox.js as self-extracting JavaScript;flicker;body hiding;hide body
description: Información para definir varias configuraciones en la página Configuración de mbox.js.
title: Configurar mbox.js
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 91%

---


# Configurar mbox.js{#configure-mbox-js}

Información para definir varias configuraciones en la página Configuración de mbox.js.

La configuración predeterminada de la biblioteca de funciones [!DNL mbox.js] cubre las necesidades de prácticamente todos los clientes de [!DNL Target].

Si lo necesita, póngase en contacto con el representante de la cuenta para cambiar la configuración de [!DNL mbox.js].

Las configuraciones disponibles son las siguientes:

## Cliente

El código de cliente de la cuenta.

When viewing [!UICONTROL Administration > Implementation], the Client at the top is the client code for your account.

## Tiempo de espera

El tiempo de espera de solicitud de Target.

Al ver [!UICONTROL Administración > Implementación], el tiempo de espera (segundos) es el tiempo de espera de la solicitud de Destinatario. De forma predeterminada, este valor es de 15 segundos, pero se recomienda establecerlo entre 2 y 5 segundos.

## XDomain

Determina si el navegador define cookies en su propio dominio (cookies individuales), en el dominio de Target o en ambos.

Modificar esta opción afecta a mbox.js y at.js.

## Nivel de compresión

Determina el grado de compresión del archivo de biblioteca mbox.js. Si se aumenta el nivel de compresión, disminuye el tiempo de carga de la página.

## Cuerpo de función mboxParameters()

Devuelve parámetros adicionales para pasarlos a cada llamada de mbox.

Por ejemplo:

return &quot;test=123&quot;;

## Cuerpo de función mboxSupported()

Devuelve “falso” para excluir a usuarios concretos.

Por ejemplo:

return !navigator.userAgent.indexOf(&#39;Safari&#39;) != -1;

Los siguientes navegadores se pueden aceptar o excluir:

* IE 5.0 o superior (Windows)
* Netscape 5.0 o superior (Mac, Windows, Linux)
* Safari 1.2.4 o superior (Mac)
* Mozilla Firefox 1.0 o superior (Mac, Windows, Linux)

## Cuerpo de función mboxCookieDomain()

Devuelve una cadena que describe el dominio en el que se van a establecer cookies de origen.

Por ejemplo:

return “YOUR-DOMAIN”;

## JavaScript extra

Incluye todo el JavaScript adicional que se quiere ejecutar en cada página.

## Complemento de SiteCatalyst

Habilita el complemento Target de Analytics.

Si se habilita, el complemento de Analytics genera código de complemento en mbox.js. Esto envía información de etiquetas de Analytics a los servidores de Target como una petición de mbox en cada página etiquetada con Analytics.

Recuerde que sigue siendo necesario hacer referencia al complemento de Analytics en la página.

## secureOnly

Indica si mbox.js debería utilizar solo HTTPS o se le debería permitir alternar entre HTTP y HTTPS según el protocolo de la página. Se trata de un ajuste avanzado que se establece en False de manera predeterminada.