---
keywords: configuración avanzada de mbox.js;cliente;dominio del servidor;dominio x;nivel de compresión;compatibilidad con id de sesión de cliente;secureOnly;compatibilidad con id de pc de cliente;pasar página;url de referencia;nivel de tráfico;duración del tráfico;cuerpo de función mboxParameters();cuerpo de función mboxSupported();cuerpo de función mboxCookieDomain();JavaScript adicional;complemento de SiteCatalyst;Obtener mbox.js como JavaScript autoextraíble;parpadeo;ocultamiento de cuerpo;ocultar cuerpo
description: Obtenga información sobre la implementación de mbox.js heredada de Adobe Target. Migrar al SDK web de Adobe Experience Platform (SDK web de AEP) o a la versión más reciente de at.js.
title: ¿Cómo configuro la biblioteca mbox.js de Target?
feature: at.js
role: Developer
exl-id: 17821e60-2692-49af-a225-764bd1b6aec1
translation-type: tm+mt
source-git-commit: 0a685427a047bfc0a2f5e81525b32df70af6d69f
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 71%

---

# Configurar mbox.js

Información para definir varias configuraciones en la página Configuración de mbox.js.

>[!IMPORTANT]
>
>**Fin de vida útil de mbox.js**: Desde el 31 de marzo de 2021,  [!DNL Adobe Target] no es compatible con la biblioteca mbox.js . Después del 31 de marzo de 2021, todas las llamadas realizadas desde mbox.js producirán errores y afectarán a las páginas que tengan actividades [!DNL Target] ejecutándose al servir contenido predeterminado.
>
>Recomendamos que todos los clientes migren a la versión más reciente de la nueva [!DNL Adobe Experience Platform Web SDK] o la biblioteca JavaScript at.js antes de esta fecha para evitar cualquier problema potencial con sus sitios. Para obtener más información, consulte [Información general: implementar Target para la web del lado del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

La configuración predeterminada de la biblioteca de funciones [!DNL mbox.js] cubre las necesidades de prácticamente todos los clientes de [!DNL Target].

Si lo necesita, póngase en contacto con el representante de la cuenta para cambiar la configuración de [!DNL mbox.js].

Las configuraciones disponibles son las siguientes:

## Cliente

El código de cliente de la cuenta.

Al ver [!UICONTROL Administración > Implementación], el Cliente en la parte superior es el código de cliente para la cuenta.

## Tiempo de espera

El tiempo de espera de solicitud de Target.

Al ver [!UICONTROL Administración > Implementación], el tiempo de espera (en segundos) es el tiempo de espera de la solicitud de Target. De forma predeterminada, este valor es de 15 segundos, pero se recomienda establecerlo entre 2 y 5 segundos.

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
