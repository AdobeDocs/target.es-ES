---
keywords: Target;at.js;migrate to at.js;readiness;audit at.js;integrate at.js
description: La migración de mbox.js a at.js es un proceso directo.
title: Cómo migrar de mbox.js a at.js
feature: null
topic: Standard
uuid: 45f81fe8-7b04-4a36-931d-bbf03ed6cbb3
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 99%

---


# Cómo migrar de mbox.js a at.js{#how-to-migrate-to-at-js-from-mbox-js}

La migración de mbox.js a at.js en [!DNL Adobe Target] es un proceso directo.

Siga estos pasos para migrar de [!DNL mbox.js] a [!DNL at.js] y para comprobar la migración:

1. Determine los requisitos de [compatibilidad con exploradores](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100) de su organización.
1. Compruebe si hay funciones que [!DNL mbox.js] no admite en la implementación de [!DNL at.js] actual de su sitio web.

   Cuando audite su implementación, busque lo siguiente:

   **¿Qué tipos de mboxes usa actualmente?**

   | Tipo | Detalles |
   |--- |--- |
   | Mbox global creado automáticamente | El mbox global creado automáticamente se crea cuando la única línea del código de Target en su sitio es el archivo mbox.js. Ese archivo genera automáticamente una llamada de mbox. |
   | mboxCreate global y vacío | Se recomienda cambiar al mbox global creado automáticamente. |
   | Envolver mboxCreate | La migración debería ser sencilla, siempre y cuando su `mboxCreate()` esté precedida por `<div class="mboxDefault"></div>`. |
   | mboxUpdate | La migración debería ser sencilla cuando   `mboxUpdate()` se usa junto con `mboxDefine()` o `mboxCreate()`. `mboxUpdate()` no actualiza el mbox global creado automáticamente ni un mbox creado originalmente por `getOffer()`. En estas circunstancias, se debería usar una combinación de `getOffer()` y `applyOffer()` para reemplazar a `mboxUpdate()` al migrar a at.js. |
   | Mboxes personalizados de rastreo de clics, incluido mboxTrack | Le recomendamos que actualice el código para que use   `trackEvent()`. |

   >[!NOTE]
   >
   >Para obtener más información sobre las diversas funciones mencionadas en la tabla anterior, consulte [funciones de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md).

   **¿Tiene personalizaciones para el archivo [!DNL mbox.js]?**

   * mboxParameters()
   * mboxSupported()
   * mboxCookieDomain()
   * JavaScript extra
   * Otras ubicaciones

   La mayoría de los [objetos y métodos de mbox.js](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md#section_8C78059D15D9452F95636A5640188537) (como `mbox`, `mboxCurrent`, `mboxFactoryDefault`, `mboxFactories`, etc.) no son compatibles. Tal vez pueda usar otros métodos para lograr lo que está intentando hacer.

   **¿Tiene el archivo [!DNL mbox.js] en alguna de sus páginas web?**

   Los archivos [!DNL at.js] y [!DNL mbox.js] no se pueden usar a la vez en la misma página web. Sin embargo, puede usar las dos bibliotecas de JavaScript en dos páginas distintas del mismo sitio web.

   La cookie de mbox es el principal medio que tiene Adobe de llevar al visitante de un sitio a otro. En el proceso de control de calidad, debe confirmar que la cookie se conserva y se lee correctamente cuando el visitante va y vuelve entre las páginas que tienen [!DNL at.js] y las que tienen [!DNL mbox.js]. Asegúrese de que se pasan los mismos valores de `mboxPC` y `mboxSession` en las llamadas de mbox independientemente de la sección del sitio ([!DNL at.js] o [!DNL mbox.js]) que el visitante vea primero y de la sección que establece la cookie originalmente. Si usa cookies de terceros en la implementación, debe cerciorarse de que estos valores permanecen inmutables al navegar por el sitio.

   **¿Integra [!DNL Target] con otras soluciones de Adobe?**

   * Analytics (A4T)
   * Analytics (integración anterior)
   * AAM (servidor)
   * AAM (front-end anterior)
   * AEM
   * Data Workbench:

   Algunas de las integraciones heredadas no son compatibles con [!DNL at.js]. Para obtener más información, consulte la página [Integraciones](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39).

   **¿Integra [!DNL Target] con herramientas de terceros?**

   * Otras herramientas de Analytics
   * Otos DMP
   * Demandbase
   * Click-tale
   * Otro:

   Puede que haya que ajustar estas integraciones para que funcionen con [!DNL at.js]. Para obtener más información, consulte la página [Integraciones](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39).

   **¿Usa un administrador de etiquetas?**

   * Dynamic Tag Management
   * Ensighten
   * Tealium
   * Signal/BrightTag

   Para obtener más información, consulte [Integraciones de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39).

   >[!NOTE]
   >
   >Si actualmente no usa un administrador de etiquetas para implementar [!DNL Target], este puede ser un buen momento para planteárselo. [Dynamic Tag Management](https://dtm.adobe.com) de Adobe es una herramienta gratuita para los clientes de [!DNL Target] y es el método recomendado para implementar [!DNL Target]. Para obtener más información, consulte [Prácticas recomendadas para implementar Adobe Target mediante Dynamic Tag Management](https://experienceleague.adobe.com/docs/dtm/implementing/overview.html).

1. Compruebe que todas las actividades e integraciones actuales funcionan correctamente.

   Estas son algunas acciones que puede realizar mientras prueba para confirmar que [!DNL at.js] funciona tal como se espera:

   * Asegúrese de que todas las actividades actuales funcionen con la nueva biblioteca JavaScript.
   * Confirme que todas las   Las [integraciones](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39) y [complementos](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-plugins.md#concept_F5D4C0A4DACF41409CC42FDD93B13FAF) funcionan según lo esperado.
   * Asegúrese de estar cómodo con la [depuración](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md#concept_CAE591DA8C404C22917584ECD4F7494F) de los enfoques disponibles con [!DNL at.js].

**Posibles problemas al migrar a at.js** Algunos clientes han informado de los siguientes problemas después de realizar la migración a at.js:

* Es posible que se deban actualizar algunas actividades del VEC generadas en una página con [!DNL mbox.js] para que funcionen con [!DNL at.js].

   Este problema ocurre principalmente en los sitios web que no utilizan muchos atributos de ID o de clase en los elementos HTML. Para comprobar si tiene este problema, cargue la página y determine si la experiencia se ofrece según lo previsto cargando la página con `?mboxDebug=true` y revisando los registros de la consola.

   ![](assets/mboxdebug.png)
En estos casos, los selectores de elementos podrían iniciarse con algo parecido a

   ```
   HTML > BODY > DIV:nth-of-type(2)
   ```

   y se han generado con la idea de que [!DNL mbox.js] agregó un elemento adicional de `<div>` al inicio de la página. Dado que [!DNL at.js] no agrega ningún elemento de `<div>` al inicio de la página, este selector no funcionaría con [!DNL at.js].

   Este problema se puede resolver recreando la actividad en el VEC en la URL que utiliza [!DNL at.js] o actualizando el selector de forma manual mediante la opción **[!UICONTROL Código &lt;/>]** > **[!UICONTROL Modificaciones]** en el VEC.

   Para resolver este problema, debe restar 1 del número nth-of-type en el primer elemento DIV después de BODY. En el ejemplo anterior, el código editado sería:

   ```
   HTML > BODY > DIV:nth-of-type(1)
   ```

   Para obtener más información sobre cómo utilizar el editor de código para hacer esto, consulte   [Editor de código](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md#concept_B3A6E9EE3A60406DB640E205EA1745B5).

* Como todos los mboxes ahora son asincrónicos, no bloquearán el procesamiento de páginas ni devolverán el orden en que se activaron. Para obtener más información, consulte “Consideraciones asincrónicas” en   [Limitaciones de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-limitations.md#concept_FA99E4D6EC274552BF45E01AFB76CCAE).
