---
keywords: Segmentación;compositor de experiencias visuales;lista de direcciones permitidas;lista de direcciones permitidas;lista de permitidos;lista de permitidos;compositor de experiencias visuales mejorado;vec;solución de problemas del compositor de experiencias visuales;solución de problemas;eec;compositor de experiencias mejorado;tls;tls 1.2
description: Aprenda a solucionar problemas que a veces ocurren en  [!DNL Target] [!UICONTROL Compositor de experiencias visuales] (VEC) y [!UICONTROL Compositor de experiencias mejorado] (EEC) en ciertas condiciones.
title: ¿Cómo puedo solucionar problemas relacionados con [!UICONTROL Compositor de experiencias visuales] y [!UICONTROL Compositor de experiencias mejorado]?
feature: Visual Experience Composer (VEC)
exl-id: d829cd63-950f-4bb4-aa58-0247f85de383
TQID: https://experienceleague.adobe.com/4v7Qe-Yzjke-GceUSRDO2SMZGkxvrkdsSXQt8TR-bic
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1271
ht-degree: 31%

---

# Resolución de problemas relacionados con [!DNL Adobe Target] [!UICONTROL Compositor de experiencias visuales] y [!UICONTROL Compositor de experiencias mejorado]

Los problemas de visualización y otros problemas a veces ocurren en [!DNL Target] [!UICONTROL Compositor de experiencias visuales] (VEC) y [!UICONTROL Compositor de experiencias mejorado] (EEC) en ciertas condiciones.

## ¿Cómo afectan las políticas de aplicación de cookies de Google Chrome SameSite a los VEC y EEC? {#samesite}

+++Detalles
Tenga en cuenta los cambios que afectan al VEC y EEC al utilizar las siguientes [!DNL Chrome] versiones:

>[!NOTE]
>
>El siguiente cambio afecta a las tres actualizaciones descritas a continuación:
>
> * *no* podrá usar el VEC sin la extensión [VEC Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) instalada y habilitada para páginas de sus sitios protegidas con contraseña. Las cookies de inicio de sesión del sitio se consideran cookies de terceros y no se envían con solicitudes de inicio de sesión dentro del editor VEC en modo [!UICONTROL Browse]. La única excepción es cuando las cookies de inicio de sesión del sitio ya tienen establecidos los atributos `SameSite=None` y `Secure`.

**Chrome 94 (21 de septiembre de 2021)**: Con los cambios inminentes planificados para la versión de Chrome 94 (21 de septiembre de 2021), el siguiente cambio afecta a todos los usuarios con versiones de explorador Chrome 94 y posteriores:

* Se quitará la marca de la línea de comandos `--disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure`.

**Chrome 91 (25 de mayo de 2021)**: Con los cambios implementados para la versión de Chrome 91 (25 de mayo de 2021), el siguiente cambio afecta a todos los usuarios con versiones de explorador de Chrome 91+:

* Se han quitado los marcadores `#same-site-by-default-cookies` y `#cookies-without-same-site-must-be-secure` de `chrome://flags`. Este comportamiento ahora está habilitado de forma predeterminada.

**Chrome 80 (agosto de 2020)**: con los cambios implementados en agosto de 2020, todos los usuarios con versiones de explorador Chrome 80+:

* ¿No podrá *not* descargar [!DNL Target] bibliotecas mientras edita una actividad (cuando no estén ya en el sitio)? Esto se debe a que la llamada de descarga se realiza desde el dominio del cliente hacia un dominio [!DNL Adobe] protegido y se rechaza por no autenticarse.

* El EEC *no* funcionará para todos los usuarios porque no puede establecer el atributo SameSite para las cookies en `adobemc.com domain`. Sin este atributo, el explorador rechaza estas cookies, lo que provoca que el EEC falle.

+++

### Determinar qué cookies están bloqueadas

+++Detalles
Para determinar qué cookies están bloqueadas debido a las directivas de aplicación de cookies de SameSite, use [!DNL Developer Tools] en [!DNL Chrome].

1. Para obtener acceso a [!DNL Developer Tools] mientras ve el VEC en [!DNL Chrome], haga clic en el icono de **[!UICONTROL puntos suspensivos]** en la esquina superior derecha de Chrome > **[!UICONTROL Más herramientas]** > **[!UICONTROL Herramientas para desarrolladores]**.
1. Haz clic en la pestaña **[!UICONTROL Red]** > y busca las cookies bloqueadas.

   >[!NOTE]
   >
   >Use la casilla de verificación **[!UICONTROL Ha bloqueado las cookies]** para facilitar la búsqueda de cookies bloqueadas.

+++

## ¿Admite [!DNL Target] iframes de varios niveles?

+++Detalles
[!DNL Target] no admite iframes de varios niveles. Si el sitio web carga un iframe que tiene un iframe secundario, at.js interactúa únicamente con el iframe principal. Las bibliotecas de [!DNL Target] no interactúan con el iframe secundario.

Como solución alternativa, puede agregar una página en la experiencia con la URL del iframe secundario.

+++

## Cuando intento editar una página, lo único que veo es un control de número en lugar de mi página. (VEC y EEC) {#section_313001039F79446DB28C70D932AF5F58}

+++Detalles
Esta situación puede suceder si la dirección URL contiene el carácter #. Para solucionar el problema, cambie al modo [!UICONTROL Examinar] en el VEC o EEC y luego vuelva al modo [!UICONTROL Componer]. El control de número debería desaparecer y la página debería cargarse.

+++

## Los encabezados de Política de seguridad de contenido (CSP) bloquean las bibliotecas de [!DNL Target] de mi sitio web. (VEC y EEC) {#section_89A30C7A213D43BFA0822E66B482B803}


+++Detalles
Si los encabezados CSP de su sitio web bloquean las bibliotecas de [!DNL Target] y luego el sitio web se carga pero no es posible editar, asegúrese de que las bibliotecas de [!DNL Target] no estén bloqueadas.

>[!NOTE]
>
>Además de la siguiente información, puede usar la [extensión del explorador Adobe Target VEC Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) para [!DNL Google Chrome].

![imagen cps_headers](assets/cps_headers.png)

Como solución alternativa, puede configurar una regla [!DNL Requestly] para eliminar los encabezados CSP, como se muestra a continuación:

![imagen cps_headers_2](assets/cps_headers_2.png)

Puede configurar una regla [!DNL Requestly] similar para cualquier encabezado que haga que un recurso no se cargue dentro del VEC.

Para [!DNL Requestly], siempre que sea necesario quitar encabezados, debe realizar una de las siguientes acciones:

* Agregar reglas de URL para la URL que desea abrir en el VEC para que los encabezados se eliminen solo para esas URL.
* Habilitar la regla cuando esté editando en el VEC y deshabilitarla cuando no esté usando el VEC.

+++

## El VEC o EEC parece roto o no se inicializa cuando se vuelve a editar una actividad guardada. (VEC y EEC) {#section_5AC3BA8F8FBB451EA814F298D0645E54}

+++Detalles
Si el sitio web ha cambiado fuera del VEC después de definir la experiencia, no se pueden encontrar los selectores en los que se realizaron acciones anteriormente cuando la actividad se abre para reeditarla. La página parece no funcionar, pero no se muestra ninguna advertencia.

+++

## El VEC o EEC no muestra los banners rotativos y otro contenido que contiene JavaScript. (VEC y EEC) {#section_8B5BE6EB050B42D6A14A054724C41330}

+++Detalles
De forma predeterminada, el VEC bloquea los elementos de JavaScript. Puede trabajar con estos elementos si desactiva JavaScript. Según la configuración del sitio, es posible que algunos elementos se sigan mostrando de forma incorrecta o que no estén disponibles.

+++

## Al cambiar un elemento de la página, se cambian varios elementos. (VEC y EEC) {#section_309188ACF34942989BE473F63C5710AF}

+++Detalles
Si se usa el mismo ID de elemento DOM en varios elementos de la página, al cambiar uno de estos elementos se cambiarán todos los elementos con dicho ID. Para evitar este error, los ID solo han de usarse una vez por página. Esta práctica es una práctica recomendada estándar de HTML. Para obtener más información, consulte [Escenarios de modificación de página](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

+++

## No puedo modificar experiencias desde un sitio con eliminación de iFrames. (VEC y EEC) {#section_9FE266B964314F2EB75604B4D7047200}

+++Detalles
Este problema se puede solucionar habilitando [!UICONTROL Enhanced Experience Composer] (EEC). Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Compositor de experiencias visuales]** y, a continuación, active la casilla que habilita el [!UICONTROL Compositor de experiencias mejorado]. El EEC usa un proxy administrado por [!DNL Adobe] para cargar la página y editarla. Este proxy permite realizar modificaciones en sitios con eliminación de iFrames y en sitios y páginas donde aún no ha agregado código [!DNL Adobe Target]. Las actividades no se muestran en el sitio hasta que el código se haya añadido. Es posible que algunos sitios no se carguen a través del EEC. En este caso, puede desactivar esta opción para cargar el EEC a través de un iFrame.

>[!NOTE]
>
>El servidor proxy [!DNL Adobe] no puede acceder a sus páginas hospedadas localmente ni a las páginas a las que no se puede acceder desde fuera de su red. EEC tampoco podrá abrir estas páginas. Estas páginas pueden incluir direcciones URL por fases, direcciones URL de prueba de aceptación del usuario o páginas hospedadas localmente.

+++

## Deseo configurar pruebas en páginas que aún no tengan la implementación de mbox/[!DNL Target] completada. (VEC y EEC) {#section_DE63BCCB5B124E10A71FA579B582A80A}

+++Detalles
Consulte “No puedo modificar experiencias desde un sitio con eliminación de iFrames” (arriba).

+++

## Los estilos de texto en negrita y cursiva con [!UICONTROL Editar texto]/[!UICONTROL Editar HTML] o [!UICONTROL Cambiar texto]/[!DNL Change HTML] no se muestran en mi página. A veces el texto desaparece después de aplicar estos cambios de estilo. (VEC y EEC) {#section_7A71D6DF41084C58B34C18701E8774E5}

+++Detalles
Si usa **[!UICONTROL Editar texto]/[!UICONTROL Editar HTML]** en el VEC para actividades de [!UICONTROL Prueba A/B] o [!UICONTROL Segmentación de experiencias] o **[!UICONTROL Cambiar texto]/[!UICONTROL Cambiar HTML]** para actividades de [!UICONTROL Automated Personalization] o [!UICONTROL Prueba multivariable] para hacer que el texto esté en negrita o en cursiva, es posible que esos estilos no se apliquen en la página o que el texto desaparezca de la página en el VEC. Esto sucede debido a la forma en que el editor de texto enriquecido aplica estos estilos, lo que podría interferir con el marcado del sitio web.

Si ve este problema, haga lo siguiente:

1. Haga clic en el botón **[!UICONTROL HTML]** del editor de texto enriquecido para introducir el modo de edición de la fuente.
1. Busque los elementos de estilo del texto.

   * Si quiere texto en negrita, cambie los elementos `<strong>` por `<b>`.

   * Si quiere texto en cursiva, cambie los elementos `<em>` por `<i>`.

+++

## Para las actividades de Personalización automatizada, el intercambio de imágenes aparece dañado en el VEC o EEC. (VEC y EEC) {#section_88AABFDFE6A3420299B0D508B12A3994}

+++Detalles
Si agrega una oferta de imagen a una ubicación, en el VEC o EEC se ocupa la dimensión completa del espacio de la imagen original. Cuando se muestra, la imagen no se expande y se muestra tal cual, así que no produce ningún impacto en la publicación.

+++
