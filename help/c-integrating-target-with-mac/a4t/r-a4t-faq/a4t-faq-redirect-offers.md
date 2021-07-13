---
keywords: faq;preguntas más frecuentes;analytics para target;a4T;redireccionamiento;oferta de redireccionamiento;adobe-mc-sdid;adobe_mc_ref
description: Encuentre respuestas a preguntas sobre el uso de ofertas de redireccionamiento al usar Analytics para actividades [!DNL Target] (A4T). A4T lets you use Analytics reporting for [!DNL Target] .
title: ¿Dónde puedo encontrar preguntas más frecuentes sobre las ofertas de redireccionamiento con A4T?
feature: 'Analytics for Target (A4T) '
exl-id: 4706057f-bd8b-4562-94e0-be22b2e19297
source-git-commit: 3c79b2ce70e456275ddf6774a35ae5c36f0ae99d
workflow-type: tm+mt
source-wordcount: '1298'
ht-degree: 62%

---

# Ofertas de redireccionamiento: preguntas más frecuentes sobre A4T

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre el uso de ofertas de redireccionamiento al usar [!DNL Adobe Analytics] como fuente de informes para [!DNL Adobe Target] (A4T).

## ¿Admite Analytics for Adobe Target (A4T) ofertas de redireccionamiento? {#section_46B8B03ED4D542C6AD875F5F61176298}

Sí, si la implementación utiliza [!DNL at.js]. Sin embargo, la implementación debe cumplir los requisitos mínimos enumerados a continuación para utilizar [ofertas de redireccionamiento](/help/c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94) en actividades que usen Analytics como fuente de informes.

>[!NOTE]
>
>Hay un problema conocido que provoca que un número limitado de clientes que utilizan redireccionamientos con A4T vean un porcentaje más alto de tasas de visitas no vinculadas. Consulte [Problemas conocidos y problemas resueltos](/help/r-release-notes/known-issues-resolved-issues.md#redirect).

## ¿Cuáles son los requisitos mínimos para utilizar ofertas de redireccionamiento con A4T? {#section_FA9384C2AA9D41EDBCE263FFFD1D9B58}

Su implementación debe cumplir los siguientes requisitos mínimos:

* Servicio ID de visitante de Experience Cloud: [!DNL visitorAPI.js] versión 2.3.0 o posterior.
* Adobe Analytics: [!DNL appMeasurement.js] versión 2.1.
* Adobe Target: [!DNL at.js] versión 1.6.2 o posterior.

Las tres bibliotecas deben incluirse en la página con la oferta de redireccionamiento y en aquella a la que se redireccione al visitante.

## ¿Por qué algunas veces hay discrepancias en los datos entre A4T y Analytics?

Se esperan algunas discrepancias en los datos. Para obtener más información, consulte [Variaciones de datos previstas entre Target y Analytics al utilizar y no utilizar A4T](/help/c-integrating-target-with-mac/a4t/understanding-expected-data-variances.md).

## ¿Por qué las vistas de página a veces se cuentan en la página original y a veces en la página de redirección?  {#section_B8F6CC2190B84CF08D945E797C5AF07B}

Si se utiliza la versión 1.6.3 o posterior de at.js , el recuento de las vistas de página en ambas páginas no supone ningún problema. Esta condición de carrera solo afecta a los clientes que utilizan versiones más antiguas. El equipo de Target mantiene dos versiones de at.js: la actual y la penúltima. Actualice at.js cuando sea posible para garantizar que dispone de una [versión compatible](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

Si utiliza una versión anterior y no compatible de at.js, existe la posibilidad de que se produzca una condición de carrera que pueda provocar que la llamada de Analytics se active antes de que se ejecute la redirección en la primera página. Esta situación puede provocar que se cuenten todas las vistas de página de la página original y de la página de redirección. Como consecuencia, se cuenta una vista de página adicional en la primera página, cuando en realidad el visitante nunca “vio” esa primera página.

Se recomienda utilizar el compositor basado en formularios para crear una actividad de redireccionamiento para aumentar la velocidad del redireccionamiento de página debido al lugar en el que se ejecuta el código en la página. También se recomienda crear una oferta de redireccionamiento para cada experiencia, incluso para la experiencia predeterminada, en la que la redirección devuelva la página original. La creación de una oferta de redireccionamiento para cada experiencia garantiza que, si se produce un recuento erróneo, se produzca en todas las experiencias. Los informes y análisis siguen siendo válidos para la prueba.

Una ventaja de utilizar ofertas de redireccionamiento para todas las experiencias de la actividad, incluida la experiencia predeterminada (control), es que puede reunir las mismas condiciones en todas las experiencias. Por ejemplo, si la experiencia predeterminada no tiene una oferta de redireccionamiento y las demás experiencias sí, la velocidad de la experiencia sin la oferta de redireccionamiento tiene una ventaja inherente. Solo se recomiendan las ofertas de redireccionamiento para situaciones temporales, como las pruebas. No se recomiendan ofertas de redireccionamiento para situaciones permanentes, como la personalización. Después de determinar el “ganador”, debe quitar la redirección para mejorar el rendimiento de carga de página.

Para obtener más información sobre este problema, consulte la información “Ofertas de redireccionamiento” en [Problemas conocidos](/help/r-release-notes/known-issues-resolved-issues.md#redirect).

## ¿Son compatibles el Compositor de experiencias visuales (VEC) y el Compositor de experiencias basado en formularios? {#section_FDA26FE7909B48539DA770559E687677}

Sí, ambos son compatibles mientras se utilicen las ofertas de redireccionamiento integradas.

Si utiliza su propio código personalizado para el redireccionamiento, debe asegurarse de rellenar los dos nuevos parámetros asociados con direcciones URL de redireccionamiento (`adobe_mc_sdid` y `adobe_mc_ref`, explicados más adelante).

## ¿Cuáles son los nuevos parámetros de cadena de consulta agregados a las direcciones URL de redireccionamiento? {#section_BA73E8B3CFCC4CBEB5BE3F76B2BC8682}

Los siguientes parámetros de cadena de consulta se asocian con las ofertas de redireccionamiento:

| Parámetro | Descripción |
|--- |--- |
| `adobe_mc_sdid` | El parámetro `adobe_mc_sdid` pasa los valores Supplemental Data Id (SDID) y Experience Cloud Org Id de la página predeterminada a la nueva página. Estos ID permiten a A4T &quot;unir&quot; la solicitud de Target en la página predeterminada con la solicitud de Analytics en la nueva página. |
| `adobe_mc_ref` | El parámetro `adobe_mc_ref` pasa la dirección URL de referencia de la página predeterminada a la nueva página. Cuando se utiliza con la versión 2.1 (o posterior) de AppMeasurement.js , Analytics utiliza este valor de parámetro como dirección URL de referencia en la nueva página. |

Estos parámetros se agregan automáticamente a las direcciones URL de redireccionamiento al utilizar las ofertas de redireccionamiento integradas en el Compositor de experiencias visuales y el Compositor de experiencias basado en formularios cuando se implementa en la página el servicio Visitor Id. Si está utilizando código personalizado de redireccionamiento en VEC o el Compositor de experiencias basado en formularios, debe asegurarse de pasar estos parámetros junto al código personalizado.

## Mis servidores web eliminan estos parámetros de mis direcciones URL, ¿qué debo hacer?  {#section_0C2DDB72939F4875B6D0428B8DCB38E5}

Trabaje con su equipo de TI para que estos parámetros ( `adobe_mc_sdid` y `adobe_mc_ref`) estén incluidos en la lista de permitidos.

## ¿Qué sucede si yo no utilizo A4T en mi actividad de redireccionamiento y no quiero que se agreguen estos parámetros adicionales a mis direcciones URL? {#section_9E608D75FF9349FE96C65FEDD7539F45}

Utilice un redireccionamiento con código personalizado si:

* No utiliza A4T en su actividad de redireccionamiento
* Tiene implementado el servicio de ID de visitante
* No desea que estos parámetros se agreguen automáticamente a sus direcciones URL

En cualquier caso, se recomienda mantener el parámetro `adobe_mc_ref` en la dirección URL para transmitir correctamente a [!DNL Analytics] la información del referente.

## ¿Por qué los parámetros adobe_mc_ref y adobe_mc_sdid se codifican dos veces en la dirección URL en mi implementación? {#section_5EFE5F012B944C40865731EA18E7E79E}

Si utiliza A4T y ofertas de redireccionamiento, Target añade los parámetros `adobe_mc_ref` y `adobe_mc_sdid` a la dirección URL. Estos valores ya están codificados en la dirección URL. La mayoría de las veces, todo funciona según lo esperado, pero algunos clientes podrían disponer de equilibradores de carga o servidores WEB que traten de codificar una vez más los parámetros de la cadena de consulta.

Debido a esta doble codificación, cuando la API de visitante intenta descodificar el valor `adobe_mc_sdid`, no consigue extraer el valor SDID y genera un SDID nuevo. Este proceso provoca que se envíen valores SDID incorrectos a Target y Analytics, y que se vean divisiones desiguales para las redirecciones en los informes de Analytics.

Adobe recomienda hablar con su equipo de TI para asegurarse de que `adobe_mc_ref` y `adobe_mc_sdid` estén incluidos en la lista de permitidos, de modo que estos valores no se transformen de modo alguno.

## ¿Por qué se debe pasar la dirección URL de referencia a la nueva página? {#section_91AB8B0891F6416CBF7E973DCAF54EB5}

Supongamos que un visitante hace clic en [!DNL `www.google.com`] un vínculo a su página de inicio (`www.mysite.com/index.html`) en el que una actividad de redireccionamiento está activa y luego se redirige a una nueva página (`www.mysite.com/index2.html`).

Anteriormente, la solicitud de [!DNL Analytics] para la nueva página informaría de que la dirección URL de referencia es [!DNL `www.mysite.com/index.html`], no [!DNL `www.google.com`]. Este comportamiento provocaba informes imprecisos en [!DNL Analytics] en cuanto a las direcciones URL de referencia (por ejemplo, en los informes de canales de mercadotecnia). No se reflejaba el hecho de que se había llegado al sitio desde [!DNL `www.google.com`].

Con las versiones [!DNL at.js] 0.9.6 (o posterior) y [!DNL AppMeasurement.js] 2.1 (o posterior), la solicitud [!DNL Analytics] de la nueva página informa de que la dirección URL de referencia es [!DNL `www.google.com`].

## ¿Puedo utilizar ofertas de redireccionamiento personalizadas/HTML? {#section_E49F9A83A286488C8F1098A040203D7E}

No, debe utilizar una oferta de redireccionamiento integrada para las actividades que empleen [!DNL Analytics] como fuente de informes (A4T). Desde la perspectiva de [!DNL Target], las ofertas HTML son opacas: [!DNL Target] no tiene forma de saber si un fragmento particular de HTML contiene código JavaScript que crea una instancia de redireccionamiento.

## ![Distintivo del SDK web de Adobe Experience Platform ](/help/assets/platform.png) ¿Admite las ofertas de redireccionamiento de  [!DNL Adobe Experience Platform Web SDK] A4T? {#platform}

Las siguientes preguntas frecuentes proporcionan más información sobre el uso de A4T y ofertas de redireccionamiento con [!DNL Platform Web SDK].

### ¿Admite Analytics for Target (A4T) ofertas de redireccionamiento?

Sí, A4T a través del SDK web de Platform admite [ofertas de redireccionamiento](/help/c-experiences/c-manage-content/offer-redirect.md).

### ¿Son compatibles el [!UICONTROL Compositor de experiencias visuales] (VEC) y el [!UICONTROL Compositor de experiencias basadas en formularios]?

Sí, el [[!UICONTROL Compositor de experiencias visuales]](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) y el [[!UICONTROL Compositor de experiencias basadas en formularios]](/help/c-experiences/form-experience-composer.md) son compatibles si utiliza ofertas de redireccionamiento integradas.

### ¿Puedo utilizar ofertas de redireccionamiento personalizadas/HTML con [!DNL Platform Web SDK]?

No, debe utilizar una oferta de redireccionamiento integrada para las actividades que utilicen A4T. Desde la perspectiva [!DNL Target], las ofertas HTML son opacas. [!DNL Target] no puede saber si un fragmento particular de HTML contiene JavaScript que crea una instancia de redireccionamiento.
