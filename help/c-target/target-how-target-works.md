---
keywords: segmentación;cookie de origen
description: Adobe Target se integra con sus páginas web mediante la biblioteca de JavaScript at.js o mbox.js.
title: Funcionamiento de la segmentación
uuid: 8b5a36c0-555d-42c5-8b24-c08d07440a53
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Cómo funciona la segmentación{#how-targeting-works}

Adobe Target se integra con sus páginas web mediante la biblioteca de JavaScript at.js o mbox.js.

[!DNL Target Classic] utilizaba mboxes alrededor de cada área en la página donde quería mostrar contenido segmentado o recopilar datos. Estos mboxes no son necesarios en [!DNL Target Standard]. Lo único que necesitará para ejecutar las actividades de optimización es una referencia a una biblioteca de JavaScript en cada página.

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
