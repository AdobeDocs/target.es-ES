---
keywords: Segmentación;compositor de experiencias visuales;lista de direcciones permitidas;lista de direcciones permitidas;lista de permitidos;lista de permitidos;compositor de experiencias visuales mejorado;vec;solución de problemas del compositor de experiencias visuales;solución de problemas;eec;compositor de experiencias mejorado;tls;tls 1.2
description: Aprenda a solucionar problemas que a veces ocurren en el Adobe  [!DNL Target] Compositor de experiencias visuales (VEC) y el Compositor de experiencias mejorado (EEC) en ciertas condiciones.
title: ¿Cómo puedo solucionar problemas relacionados con el Compositor de experiencias visuales y el Compositor de experiencias mejorado?
feature: Visual Experience Composer (VEC)
exl-id: d829cd63-950f-4bb4-aa58-0247f85de383
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '1401'
ht-degree: 46%

---

# Solucionando problemas relacionados con [!UICONTROL Visual Experience Composer] y [!UICONTROL Enhanced Experience Composer]

Mostrar problemas y otros problemas que a veces ocurren en [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) y [!UICONTROL Enhanced Experience Composer] (EEC) bajo ciertas condiciones.

## ¿Cómo afectan las políticas de aplicación de cookies de Google Chrome SameSite a los VEC y EEC? {#samesite}

Tenga en cuenta los cambios que afectan al VEC y EEC al utilizar las siguientes versiones de Chrome:

>[!NOTE]
>
>El siguiente cambio afecta a las tres actualizaciones descritas a continuación:
>
> * *no* podrá usar el VEC sin la extensión VEC Helper instalada y habilitada para páginas de sus sitios protegidas con contraseña. Las cookies de inicio de sesión del sitio se consideran cookies de terceros y no se envían con solicitudes de inicio de sesión dentro del editor VEC en modo Examinar. La única excepción es cuando las cookies de inicio de sesión del sitio ya tienen establecidos los atributos `SameSite=None` y `Secure`.

**Chrome 94 (21 de septiembre de 2021)**: Con los cambios inminentes planificados para la versión de Chrome 94 (21 de septiembre de 2021), el siguiente cambio afecta a todos los usuarios con versiones de explorador Chrome 94 y posteriores:

* Se quitará la marca de la línea de comandos `--disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure`.

**Chrome 91 (25 de mayo de 2021)**: Con los cambios implementados para la versión de Chrome 91 (25 de mayo de 2021), el siguiente cambio afecta a todos los usuarios con versiones de explorador de Chrome 91+:

* Se han quitado los marcadores `#same-site-by-default-cookies` y `#cookies-without-same-site-must-be-secure` de `chrome://flags`. Este comportamiento ahora está habilitado de forma predeterminada.

**Chrome 80 (agosto de 2020)**: con los cambios implementados en agosto de 2020, todos los usuarios con versiones de explorador Chrome 80+:

* ¿No podrá *not* descargar [!DNL Target] bibliotecas mientras edita una actividad (cuando no estén ya en el sitio)? Esto se debe a que la llamada de descarga se realiza desde el dominio del cliente hacia un dominio [!DNL Adobe] protegido y se rechaza por no autenticarse.
* El EEC *no* funcionará para todos los usuarios porque no puede establecer el atributo SameSite para las cookies en `adobemc.com domain`. Sin este atributo, el explorador rechaza estas cookies, lo que provoca que el EEC falle.

### Determinar qué cookies están bloqueadas

Para determinar qué cookies están bloqueadas debido a las políticas de aplicación de cookies de SameSite, utilice las herramientas para desarrolladores de Chrome.

1. Para acceder a las herramientas para desarrolladores, mientras ve el VEC en Chrome, haga clic en el icono **[!UICONTROL ellipsis]** en la esquina superior derecha de Chrome > **[!UICONTROL More Tools]** > **[!UICONTROL Developer Tools]**.
1. Haga clic en la ficha **[!UICONTROL Network]** > y luego busque las cookies bloqueadas.

   >[!NOTE]
   >
   >Utilice la casilla de verificación **[!UICONTROL Has blocked cookies]** para facilitar la búsqueda de cookies bloqueadas.

   La siguiente ilustración muestra una cookie bloqueada:

   ![Herramientas para desarrolladores > pestaña Red que muestra una cookie bloqueada](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/chrome-developer-tools.png)

### [!DNL Adobe Target] extensión de VEC Helper

A partir de la versión 0.7.1, la extensión del explorador [!DNL Adobe Target] VEC Helper agrega los atributos `SameSite=None` y `Secure` a todas las cookies en las respuestas que se originan en páginas web editadas dentro del VEC cuando la opción &quot;Cookies&quot; está activada en la interfaz de usuario de la extensión:

![Extensión del ayudante del VEC de Adobe Target UIAxcepción del ayudante del VEC de Adobe Target UI](assets/cookies-vec-helper.png)

### Alternativas y soluciones

Utilice una de las siguientes opciones para asegurarse de que el VEC y el EEC siguen funcionando según lo esperado:

* Descargue y use la [extensión VEC Helper actualizada](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak?hl=en).
* Utilice el navegador Mozilla Firefox. Firefox aún no está aplicando esta directiva.
* Utilice los siguientes indicadores para ejecutar Google Chrome desde la línea de comandos hasta el 21 de septiembre de 2021. A partir del 21 de septiembre, las funciones que requieren cookies dejarán de funcionar en el VEC, como el inicio de sesión o las ventanas emergentes de consentimiento de cookies. Si actualiza a Chrome 94, debe generar manualmente las cookies de `SameSite=none` y `Secure` en sus sitios web.

  ```
  --disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure
  ```

## ¿Admite [!DNL Target] iframes de varios niveles?

[!DNL Target] no admite iframes de varios niveles. Si el sitio web carga un iframe que tiene un iframe secundario, at.js interactúa únicamente con el iframe principal. Las bibliotecas de [!DNL Target] no interactúan con el iframe secundario.

Como solución alternativa, puede agregar una página en la experiencia con la URL del iframe secundario.

## Cuando intento editar una página, lo único que veo es un control de número en lugar de mi página. (VEC y EEC)   {#section_313001039F79446DB28C70D932AF5F58}

Esta situación puede suceder si la dirección URL contiene el carácter #. Para corregir el problema, cambie en modo Examinar en el Compositor de experiencias visuales y después vuelva a cambiar al modo Componer. El control de número debería desaparecer y la página debería cargarse.

## Los encabezados de Política de seguridad de contenido (CSP) bloquean las bibliotecas de [!DNL Target] de mi sitio web. (VEC y EEC)   {#section_89A30C7A213D43BFA0822E66B482B803}

Si los encabezados CSP de su sitio web bloquean las bibliotecas de Target y luego el sitio web se carga pero no es posible editar, asegúrese de que las bibliotecas de Target no estén bloqueadas.

>[!NOTE]
>
>Además de la siguiente información, puede utilizar la [extensión del explorador Adobe Target VEC Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) para Google Chrome.

![imagen cps_headers](assets/cps_headers.png)

Como solución alternativa, puede configurar una regla de Requestly para eliminar los encabezados CSP, como se muestra abajo:

![imagen cps_headers_2](assets/cps_headers_2.png)

Puede configurar una regla de Requestly similar para cualquier encabezado que provoque que un recurso no se cargue dentro del VEC.

Para Requestly, siempre que sea necesario eliminar encabezados, debe hacer lo siguiente:

* Agregar reglas de URL para la URL que desea abrir en el VEC para que los encabezados se eliminen solo para esas URL.
* Habilitar la regla cuando esté editando en el VEC y deshabilitarla cuando no esté usando el VEC.

## El VEC o EEC parece roto o no se inicializa cuando se vuelve a editar una actividad guardada. (VEC y EEC)   {#section_5AC3BA8F8FBB451EA814F298D0645E54}

Si el sitio web ha cambiado fuera del Compositor de experiencias visuales después de haber definido la experiencia, cuando se abre la actividad para modificarla de nuevo, no se pueden encontrar los selectores en los que antes se realizaron las acciones. La página parece no funcionar, pero no se muestra ninguna advertencia.

## El VEC o EEC no muestra los banners rotativos y otro contenido que contiene JavaScript. (VEC y EEC)   {#section_8B5BE6EB050B42D6A14A054724C41330}

De manera predeterminada, el Compositor de experiencias visuales bloquea elementos de JavaScript. Para trabajar con estos elementos deberá deshabilitar JavaScript en la configuración del Compositor de experiencias visuales. Según la configuración del sitio, es posible que algunos elementos se sigan mostrando de forma incorrecta o que no estén disponibles.

## Al cambiar un elemento de la página, se cambian varios elementos. (VEC y EEC)   {#section_309188ACF34942989BE473F63C5710AF}

Si se usa el mismo ID de elemento DOM en varios elementos de la página, al cambiar uno de estos elementos se cambiarán todos los elementos con dicho ID. Para evitar este error, los ID solo han de usarse una vez por página. Esta práctica es una práctica recomendada para el HTML estándar. Para obtener más información, consulte [Escenarios de modificación de página](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## No puedo modificar experiencias desde un sitio con eliminación de iFrames. (VEC y EEC)   {#section_9FE266B964314F2EB75604B4D7047200}

Este problema se puede solucionar habilitando el Compositor de experiencias mejorado. Haga clic en **[!UICONTROL Administation]** > **[!UICONTROL Visual Experience Composer]** y, a continuación, active la casilla de verificación que habilita el Compositor de experiencias mejorado. El Compositor de experiencias mejorado utiliza un proxy administrado por Adobe para cargar la página para editarla. Este proxy permite realizar modificaciones en sitios con eliminación de iFrames y en sitios y páginas donde aún no ha añadido código Adobe Target. Las actividades no se muestran en el sitio hasta que el código se haya añadido. Es posible que algunos sitios no se carguen a través del Compositor de experiencias visuales. En este caso, puede desactivar esta opción para cargar el Compositor de experiencias visuales a través de un iFrame. 

>[!NOTE]
>
>El servidor proxy de Adobe no puede acceder a sus páginas hospedadas localmente ni a las páginas a las que no se puede acceder desde fuera de su red. EEC tampoco podrá abrir estas páginas. Estas páginas pueden incluir direcciones URL por fases, direcciones URL de prueba de aceptación del usuario o páginas hospedadas localmente.

## Quiero configurar pruebas en páginas que aún no tienen implementado mbox/Target. (VEC y EEC)   {#section_DE63BCCB5B124E10A71FA579B582A80A}

Consulte “No puedo modificar experiencias desde un sitio con eliminación de iFrames” (arriba).

## Los estilos de texto negrita y cursiva con Editar texto/HTML o Cambiar texto/HTML no se muestran en la página. A veces el texto desaparece después de aplicar estos cambios de estilo. (VEC y EEC)   {#section_7A71D6DF41084C58B34C18701E8774E5}

Si usa **[!UICONTROL Edit Text/HTML]** en el Compositor de experiencias visuales para actividades A/B o de Segmentación de experiencias o **[!UICONTROL Change Text/HTML]** para actividades de Automated Personalization o de Prueba multivariable para hacer que el texto esté en negrita o en cursiva, es posible que esos estilos no se apliquen en la página o que el texto desaparezca de la página en el Compositor de experiencias visuales. Esto sucede debido a la forma en que el editor de texto enriquecido aplica estos estilos, lo que podría interferir con el marcado del sitio web.

Si ve este problema, haga lo siguiente:

1. Haga clic en el botón **[!UICONTROL HTML]** del editor de texto enriquecido para especificar el modo de edición de código fuente.
1. Busque los elementos de estilo del texto.

   * Si quiere texto en negrita, cambie los elementos `<strong>` por `<b>`.

   * Si quiere texto en cursiva, cambie los elementos `<em>` por `<i>`.

## Para las actividades de Personalización automatizada, el intercambio de imágenes aparece dañado en el VEC o EEC. (VEC y EEC)   {#section_88AABFDFE6A3420299B0D508B12A3994}

Si agrega una oferta de imagen a una ubicación, en el VEC o EEC se ocupa la dimensión completa del espacio de la imagen original. Cuando se muestra, la imagen no se expande y se muestra tal cual, así que no produce ningún impacto en la publicación.
