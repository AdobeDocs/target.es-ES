---
keywords: targeting;cookie;first-party cookie;1st-party cookie
description: Adobe Target se integra con sus páginas web mediante la biblioteca de JavaScript at.js o mbox.js.
title: Funcionamiento de la segmentación
uuid: 8b5a36c0-555d-42c5-8b24-c08d07440a53
translation-type: tm+mt
source-git-commit: ba4c776d93f911c122f36113a99ce4349b3c5524

---


# Cómo funciona la segmentación{#how-targeting-works}

Adobe Target se integra con sus páginas web mediante la biblioteca de JavaScript at.js o mbox.js. Una biblioteca de JavaScript a la que se hace referencia en cada página es todo lo que necesita para ejecutar sus actividades de optimización.

Cada vez que un visitante solicita una página con habilitado, [!DNL Target]Target usa el siguiente proceso para mostrar ofertas:

1. Un cliente solicita una página al servidor y esta se muestra en el navegador.
1. Se establece una cookie de origen en el navegador del cliente para definir un ID de visitante único.

   [!DNL Experience Cloud visitor ID] también se establece si utiliza el perfil de marketing principal.

1. La página realiza una llamada a [!DNL Target] a través del archivo [!DNL target.js] o de un mbox de la página.
1. [!DNL Target] hace referencia al perfil asociado al visitante.
1. [!DNL Target] ejecuta cualquier script de perfil asociado a ese perfil.
1. [!DNL Target] calcula su respuesta.
1. El contenido se muestra en función de las reglas de la actividad o la campaña.

La oferta que se muestra en una prueba A/B básica se elige de forma aleatoria. Esta división aleatoria del tráfico puede provocar que se consuma una gran cantidad de tráfico inicial antes de que se nivelen los porcentajes. Por ejemplo, si tiene una actividad con dos experiencias, la experiencia inicial se elige de forma aleatoria. Si hay poco tráfico, es posible que el porcentaje de visitantes se desvíe hacia una experiencia. A medida que aumente el tráfico, los porcentajes deberían de igualarse.
