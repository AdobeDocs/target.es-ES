---
keywords: limitaciones del compositor de experiencias visuales;compatibilidad con exploradores;integraciones;complementos;consideraciones asíncronas
description: Obtenga información sobre la implementación de mbox.js heredada de Adobe Target. Migrar al SDK web de Adobe Experience Platform (SDK web de AEP) o a la versión más reciente de at.js.
title: ¿Cuáles son las diferencias entre at.js y mbox.js?
feature: at.js
role: Developer
exl-id: 2fd0db66-0b47-41c0-86b6-44e711d70027
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 91%

---

# Limitaciones de at.js

Existen algunas diferencias entre at.js y mbox.js. En esta sección se señalan algunas de las diferencias y limitaciones para ayudarle a usar correctamente at.js.

## Limitaciones conocidas del Compositor de experiencias visuales {#section_4B63C97169DE4C93B22944E880FD3DF1}

* Las opciones Insertar elemento y Reorganizar en el Compositor de experiencias visuales deberían evitarse en aplicaciones de una sola página.

   Como el DOM no se borra en los eventos de carga de página en aplicaciones de una sola página como sí se hace con sitios web tradicionales, las manipulaciones de Insertar elemento y Reorganizar podrían volver a aplicarse varias veces en función de cómo el visitante navega por el SPA.

## Integraciones y complementos   {#section_D92E31170176406AAC7B5005F03D3425}

Algunas funciones dentro de [!DNL mbox.js] no están disponibles en [!DNL at.js]. Los [objetos y métodos de mbox.js](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md#section_8C78059D15D9452F95636A5640188537) (como `mbox`, `mboxCurrent`, `mboxFactoryDefault`, `mboxFactories` y otros) ya no son compatibles con [!DNL at.js] (por ejemplo: `mboxFactoryDefault`). Esto es intencional con el fin de desalentar que “hackee” [!DNL at.js] para desarrollar funcionalidad incompatible que a largo plazo pudiera dañar irreversiblemente una implementación e imposibilitar toda actualización. Los únicos métodos expuestos se cubren en las páginas de API de esta documentación. Debido a ello:

* Las [integraciones](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39) heredadas y basadas en páginas con otras soluciones Adobe podrían no funcionar y se deben actualizar con integraciones más nuevas del lado del servidor.

   Asegúrese de incluir todos los complementos como parte de la prueba.

## Consideraciones asincrónicas {#section_B586360A3DD34E2995AE25A18E3FB953}

Como todos los mboxes ahora son asincrónicos, no bloquearán el procesamiento de páginas ni devolverán el orden en que se activaron.

* Si está utilizando un mbox global en el [Compositor de experiencias basadas en formularios](/help/c-experiences/experiences.md#section_3643394BD424463C8768F2907DEBCC22), tenga en cuenta que las ofertas HTML deben contener únicamente etiquetas `<script>`, `<style>` y `<link>`.

   Durante la entrega, [!DNL at.js] elimina las demás etiquetas HTML al aplicar ofertas del mbox global. Las ofertas del mbox global se aplican a HTML HEAD, que no permite DIV, SPAN, etc. Por ejemplo, `<div>test</div>` no se puede aplicar porque la etiqueta `<div>` solo se puede utilizar dentro de HTML BODY.

* La integración anterior y basada en páginas de [!DNL Target] con [!DNL Analytics] no funcionará.

   Esta integración requiere que la llamada de [!DNL Target] se realice antes de la llamada de [!DNL Analytics].

* Tenga cuidado con las dependencias de JavaScript entre su oferta y la página.

   No se debería asumir que el JavaScript en la oferta se va a ejecutar antes del JavaScript codificado debajo del mbox.

* Tenga cuidado con las dependencias de JavaScript entre varias ofertas en la página.

   Ya no se puede asumir que la oferta entregada por el primer mbox se va a ejecutar antes de la oferta entregada por el segundo mbox.

* Las ofertas de Manipulación de DOM y de Redireccionamiento deberían entregarse mediante el mbox global creado automáticamente en [!DNL at.js] y entregarse en el `<head>`.

   Una función `mboxCreate()` en la parte superior del `<body>` posiblemente dará como resultado un parpadeo en el contenido predeterminado.
