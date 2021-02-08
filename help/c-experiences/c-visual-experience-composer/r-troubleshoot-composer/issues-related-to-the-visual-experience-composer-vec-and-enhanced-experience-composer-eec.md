---
keywords: Segmentación;compositor de experiencias visuales;lista blanca;lista de permitidos;lista de permitidos;compositor de experiencias visuales mejorado;vec;resolución de problemas del compositor de experiencias visuales;resolución de problemas;eec;compositor de experiencias mejorado;tls;tls 1.2
description: Descubra cómo solucionar problemas que a veces se producen en el Compositor de experiencias visuales (VEC) de Adobe Target y en el Compositor de experiencias mejorado (EEC) en determinadas condiciones.
title: ¿Cómo puedo solucionar problemas relacionados con el Compositor de experiencias visuales y el Compositor de experiencias mejorado?
feature: Visual Experience Composer (VEC)
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '1403'
ht-degree: 65%

---


# Resolución de problemas relacionados con el Compositor de experiencias visuales y el Compositor de experiencias mejorado

Los problemas de visualización y otros problemas a veces ocurren en el [!DNL Adobe Target] Compositor de experiencias visuales (VEC) y el Compositor de experiencias mejorado (EEC) bajo ciertas condiciones.

## ¿Cómo afectan las políticas de aplicación de cookies Google Chrome SameSite al VEC y EEC? {#samesite}

Con los cambios más recientes (agosto de 2020), todos los usuarios con versiones de navegador Chrome 80+:

* *no* podrá utilizar el VEC (con o sin la extensión del asistente de VEC instalada y habilitada) en páginas de sus sitios protegidas por contraseña. Esto se debe a que las cookies de inicio de sesión del sitio se considerarán cookies de terceros y no se enviarán con la solicitud de inicio de sesión. La única excepción es cuando la cookie de inicio de sesión del sitio del cliente ya tiene el parámetro SameSite establecido en &quot;none&quot;.
* *no* podrá descargar [!DNL Target] bibliotecas mientras edita una actividad (cuando no se encuentren ya en el sitio). Esto se debe a que la llamada de descarga se realiza desde el dominio del cliente hacia un dominio de Adobe seguro y se rechaza como no autenticada.
* El EEC *no* funcionará para todos los usuarios porque no puede establecer el atributo SameSite para las cookies en `adobemc.com domain`. Sin este atributo, el explorador rechazará estas cookies, lo que ocasionará que el EEC falle.

Adobe ha enviado una extensión del asistente VEC actualizada a la tienda Google Chrome. Esta extensión sobrescribe los atributos de cookie para establecer el atributo `SameSite="none"` cuando sea necesario. La extensión [actualizada se puede encontrar aquí](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak?hl=en). Para obtener más información sobre la instalación y el uso de la extensión del asistente de VEC, consulte [Extensión del asistente del Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md).

Para las cookies de su propio sitio, debe especificar las cookies por nombre. Cambie el control deslizante [!UICONTROL Cookie] a la posición on y, a continuación, especifique la cookie por nombre y el dominio de la cookie. El nombre de la cookie es &quot;mbox&quot; y el dominio de la cookie es el segundo nivel y el nivel superior de los dominios desde los que se proporciona el mbox. Dado que se proporciona desde el dominio de la compañía, se trata de una cookie de origen. Ejemplo: `mycompany.com`. Para obtener más información, consulte [Cookies de Adobe Target](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-target.html) en la *Guía del usuario de la interfaz de Experience Cloud*.

![Alternar las cookies en la extensión del asistente de VEC](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

### Alternativas y soluciones alternativas

Utilice una de las siguientes opciones para asegurarse de que el VEC y EEC siguen funcionando según lo esperado:

* Descargue y utilice la [extensión auxiliar de VEC](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak?hl=en) actualizada.
* Utilice el navegador Mozilla Firefox. Firefox aún no está aplicando esta directiva.
* Continúe utilizando Chrome, pero establezca el indicador `chrome://flags/#same-site-by-default-cookies` en &quot;Deshabilitado&quot;.

   >[!NOTE]
   >
   >Esto *no será suficiente si las cookies ya tienen el atributo SameSite establecido en &quot;Lax&quot; o &quot;Strict&quot; desde el servidor.*

## ¿Admite Target los iframes de varios niveles?

Target no admite iframes de varios niveles. Si el sitio web carga un iframe que tiene un iframe secundario, las bibliotecas de Target (at.js y mbox.js) interactúan únicamente con el iframe principal. Las bibliotecas de Target no interactúan con el iframe secundario.

Como solución alternativa, puede agregar una página en la experiencia con la URL del iframe secundario.

## Cuando intento editar una página, lo único que veo es un control de número en lugar de mi página. (VEC y EEC) {#section_313001039F79446DB28C70D932AF5F58}

Esto puede ocurrir si la dirección URL contiene un carácter #. Para corregir el problema, cambie en modo Examinar en el Compositor de experiencias visuales y después vuelva a cambiar al modo Componer. El control de número debería desaparecer y la página debería cargarse.

## Los encabezados Content Security Policy (CSP) bloquean las bibliotecas de Target en mi sitio web. (VEC y EEC) {#section_89A30C7A213D43BFA0822E66B482B803}

Si los encabezados CSP de su sitio web bloquean las bibliotecas de Target y luego el sitio web se carga pero no es posible editar, asegúrese de que las bibliotecas de Target no estén bloqueadas.

>[!NOTE]
>
>Además de la siguiente información, puede utilizar la [extensión del explorador Adobe Target VEC Helper](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) para Google Chrome.

![](assets/cps_headers.png)

Como solución alternativa, puede configurar una regla de Requestly para eliminar los encabezados CSP, como se muestra abajo:

![](assets/cps_headers_2.png)

Puede configurar una regla de Requestly similar para cualquier encabezado que provoque que un recurso no se cargue dentro del VEC.

Para Requestly, siempre que sea necesario eliminar encabezados, debe hacer lo siguiente:

* Agregar reglas de URL para la URL que desea abrir en el VEC para que los encabezados se eliminen solo para esas URL.
* Habilitar la regla cuando esté editando en el VEC y deshabilitarla cuando no esté usando el VEC.

## El VEC o EEC parece roto o no se inicializa cuando se vuelve a editar una actividad guardada. (VEC y EEC) {#section_5AC3BA8F8FBB451EA814F298D0645E54}

Si el sitio web ha cambiado fuera del Compositor de experiencias visuales después de haber definido la experiencia, cuando se abre la actividad para modificarla de nuevo, no se pueden encontrar los selectores en los que antes se realizaron las acciones. La página parece no funcionar, pero no se muestra ninguna advertencia.

## El VEC o EEC no muestra los banners rotativos y otro contenido que contiene JavaScript. (VEC y EEC) {#section_8B5BE6EB050B42D6A14A054724C41330}

De manera predeterminada, el Compositor de experiencias visuales bloquea elementos de JavaScript. Para trabajar con estos elementos deberá deshabilitar JavaScript en la configuración del Compositor de experiencias visuales. Según la configuración del sitio, es posible que algunos elementos se sigan mostrando de forma incorrecta o que no estén disponibles.

## Mi archivo target.js alojado no se carga en las siguientes cargas de una página. (VEC y EEC) {#section_87F6418C2CD142A7B4D1E7037935F81F}

Este problema ocurre cuando los clientes tienen una versión de mbox.js anterior a la 57 (es decir, la versión 56 o anterior).

Recomendamos que todos los usuarios de VEC actualicen a la [versión más reciente de mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A) o que, al menos, actualicen a la versión 57. También debe considerar [realizar la transición a at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17).

## Al cambiar un elemento de la página, se cambian varios elementos. (VEC y EEC) {#section_309188ACF34942989BE473F63C5710AF}

Si se usa el mismo ID de elemento DOM en varios elementos de la página, al cambiar uno de estos elementos se cambiarán todos los elementos con dicho ID. Para evitar este error, los ID solo han de usarse una vez por página. Esta es una práctica recomendada estándar para HTML. Para obtener más información, consulte  [Escenarios de modificación de página](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## No puedo modificar experiencias desde un sitio con eliminación de iFrames. (VEC y EEC) {#section_9FE266B964314F2EB75604B4D7047200}

Este problema se puede solucionar habilitando el Compositor de experiencias mejorado. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Compositor de experiencias visuales]** y, a continuación, seleccione la casilla de verificación que habilita el Compositor de experiencias mejorado. El Compositor de experiencias mejorado utiliza un proxy administrado por Adobe para cargar la página para editarla. Esto permite realizar modificaciones en sitios con eliminación de iFrames y en sitios y páginas donde aún no ha añadido código de Adobe Target. Las actividades no se muestran en el sitio hasta que el código se haya añadido. Es posible que algunos sitios no se carguen a través del Compositor de experiencias visuales. En este caso, puede desactivar esta opción para cargar el Compositor de experiencias visuales a través de un iFrame.   []

>[!NOTE]
>
>El servidor proxy de Adobe no puede acceder a sus páginas hospedadas localmente ni a las páginas a las que no se puede acceder desde fuera de su red. EEC tampoco podrá abrir estas páginas. Estas páginas pueden incluir direcciones URL por fases, direcciones URL de prueba de aceptación del usuario o páginas hospedadas localmente.

## Quiero configurar pruebas en páginas que aún no tienen implementado mbox/Target. (VEC y EEC) {#section_DE63BCCB5B124E10A71FA579B582A80A}

Consulte “No puedo modificar experiencias desde un sitio con eliminación de iFrames” (arriba).

## Los estilos de texto negrita y cursiva con Editar texto/HTML o Cambiar texto/HTML no se muestran en la página. A veces el texto desaparece después de aplicar estos cambios de estilo. (VEC y EEC) {#section_7A71D6DF41084C58B34C18701E8774E5}

Si usa **[!UICONTROL Editar texto / HTML]** en el Compositor de experiencias visuales para actividades A/B o de Segmentación de experiencias o si usa **[!UICONTROL Cambiar texto / HTML]** para actividades de prueba multivariable o de Personalización automatizada para definir que el texto esté en negrita o en cursiva, puede que esos estilos no se apliquen en la página o que el texto desaparezca de la página en el Compositor de experiencias visuales. Se debe a que la forma en la que el editor de texto enriquecido aplica estos estilos puede interferir con el marcado del sitio web.

Si ve este problema, haga lo siguiente:

1. Haga clic en el botón **[!UICONTROL HTML]** del editor de texto enriquecido para introducir el modo de edición de la fuente.
1. Busque los elementos de estilo del texto.

   * Si quiere texto en negrita, cambie los elementos `<strong>` por `<b>`.

   * Si quiere texto en cursiva, cambie los elementos `<em>` por `<i>`.

## Para las actividades de Personalización automatizada, el intercambio de imágenes aparece dañado en el VEC o EEC. (VEC y EEC) {#section_88AABFDFE6A3420299B0D508B12A3994}

Si agrega una oferta de imagen a una ubicación, en el VEC o EEC se ocupa la dimensión completa del espacio de la imagen original. Cuando se muestra, la imagen no se expande y se muestra tal cual, así que no produce ningún impacto en la publicación.
