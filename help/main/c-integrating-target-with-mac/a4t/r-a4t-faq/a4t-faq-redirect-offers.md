---
keywords: faq;preguntas más frecuentes;analytics para target;a4T;redireccionamiento;oferta de redireccionamiento;adobe-mc-sdid;adobe_mc_ref
description: Encuentre respuestas a preguntas acerca del uso de ofertas de redireccionamiento al usar Analytics for [!DNL Target] (A4T). A4T le permite utilizar los informes de Analytics para  [!DNL Target] actividades.
title: ¿Dónde puedo encontrar preguntas frecuentes acerca de ofertas de redireccionamiento con A4T?
feature: Analytics for Target (A4T)
exl-id: 4706057f-bd8b-4562-94e0-be22b2e19297
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '1430'
ht-degree: 50%

---

# Ofertas de redireccionamiento: preguntas más frecuentes sobre A4T

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre el uso de ofertas de redireccionamiento al usar [!DNL Adobe Analytics] como fuente de informes para [!DNL Adobe Target] (A4T).

## ¿Admite Analytics for Adobe Target (A4T) ofertas de redireccionamiento? {#section_46B8B03ED4D542C6AD875F5F61176298}

+++Respuesta
Sí, si su implementación utiliza [!DNL at.js]. Sin embargo, la implementación debe cumplir los requisitos mínimos enumerados a continuación para utilizar [ofertas de redireccionamiento](/help/main/c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94) en actividades que usen Analytics como fuente de informes.

+++

## ¿Cuáles son los requisitos mínimos para utilizar ofertas de redireccionamiento con A4T? {#section_FA9384C2AA9D41EDBCE263FFFD1D9B58}

+++Respuesta
Su implementación debe cumplir los siguientes requisitos mínimos:

* Servicio ID de visitante de Experience Cloud: [!DNL visitorAPI.js] versión 2.3.0 o posterior.
* Adobe Analytics: [!DNL appMeasurement.js] versión 2.1.
* Adobe Target: [!DNL at.js] versión 1.6.2 o posterior.

Las tres bibliotecas deben incluirse en la página con la oferta de redireccionamiento y en aquella a la que se redireccione al visitante.

+++

## ¿Por qué algunas veces hay discrepancias en los datos entre A4T y Analytics?

+++Respuesta
Se esperan algunas discrepancias en los datos. Para obtener más información, consulte [Variaciones de datos previstas entre Target y Analytics al utilizar y no utilizar A4T](/help/main/c-integrating-target-with-mac/a4t/understanding-expected-data-variances.md).

+++

## ¿Cómo puedo minimizar las discrepancias en la distribución del tráfico al utilizar ofertas de redireccionamiento en actividades de A4T? {#discrepancies}

+++Respuesta
Un número limitado de clientes ha informado de grados de variación más altos en la distribución del tráfico al utilizar ofertas de redireccionamiento en actividades configuradas con [!UICONTROL Analytics for Target] (A4T).

Tenga en cuenta lo siguiente:

* El orden incorrecto de las llamadas a [!DNL Target] y [!DNL Analytics] puede ser responsable de grados de variación más altos.

  La llamada de [!DNL Target] debe preceder a la llamada de [!DNL Analytics] en la página de origen (donde se produce el redireccionamiento) y en la página de destino (donde termina el redireccionamiento).

* Asegúrese de utilizar ofertas de redireccionamiento en las actividades de redireccionamiento de A4T.
* Si hay varias [!DNL Target] solicitudes de ubicación en la página de origen (donde se produce la redirección), [!DNL Adobe] recomienda que ejecute la actividad de redirección en la primera [!DNL Target] solicitud de ubicación.

  La ejecución de la actividad de redireccionamiento en la primera solicitud de ubicación de [!DNL Target] reduce las posibilidades de que se cuenten en el informe las cualificaciones de actividad que se produzcan en otras [!DNL Target] solicitudes de ubicación. Los visitantes que son redirigidos no tienen por qué contarse en los informes de otras actividades, ya que no verán las experiencias.

+++

## ¿Por qué las vistas de página a veces se cuentan en la página original y a veces en la página de redirección?  {#section_B8F6CC2190B84CF08D945E797C5AF07B}

+++Respuesta
Al utilizar la versión 1.6.3 o posterior de at.js, el recuento de vistas de página en ambas páginas no supone un problema. Esta condición de carrera solo afecta a los clientes que utilizan versiones más antiguas. El equipo de Target mantiene dos versiones de at.js: la actual y la penúltima. Actualice at.js cuando sea posible para garantizar que dispone de una [versión compatible](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank}.

Si utiliza una versión anterior y no compatible de at.js, existe la posibilidad de que se produzca una condición de carrera que pueda provocar que la llamada de Analytics se active antes de que se ejecute la redirección en la primera página. Esta situación puede provocar que se cuenten las vistas de página en la página original y en la página de redirección. Como consecuencia, se cuenta una vista de página adicional en la primera página, cuando en realidad el visitante nunca “vio” esa primera página.

Se recomienda utilizar el compositor basado en formularios para crear una actividad de redireccionamiento a fin de aumentar la velocidad del redireccionamiento de páginas, ya que el código se ejecuta en la página. También se recomienda crear una oferta de redireccionamiento para cada experiencia, incluso para la experiencia predeterminada, en la que la redirección devuelva la página original. La creación de una oferta de redireccionamiento para cada experiencia garantiza que, si se produce un recuento incorrecto, se produzca en todas las experiencias. Los informes y análisis siguen siendo válidos para la prueba.

Una ventaja de utilizar ofertas de redireccionamiento para todas las experiencias de la actividad, incluida la experiencia predeterminada (control), es que puede reunir las mismas condiciones en todas las experiencias. Por ejemplo, si la experiencia predeterminada no tiene una oferta de redireccionamiento y las demás experiencias sí, la velocidad de la experiencia sin la oferta de redireccionamiento tiene una ventaja inherente. Solo se recomiendan las ofertas de redireccionamiento para situaciones temporales, como las pruebas. No se recomiendan ofertas de redireccionamiento para situaciones permanentes, como la personalización. Después de determinar el &quot;ganador&quot;, debe eliminar la redirección para mejorar el rendimiento de carga de página.

+++

## ¿Son compatibles el Compositor de experiencias visuales (VEC) y el Compositor de experiencias basado en formularios? {#section_FDA26FE7909B48539DA770559E687677}

+++Respuesta
Sí, ambos son compatibles mientras se utilicen las ofertas de redireccionamiento integradas.

Si utiliza su propio código personalizado para el redireccionamiento, debe asegurarse de rellenar los dos nuevos parámetros asociados con direcciones URL de redireccionamiento (`adobe_mc_sdid` y `adobe_mc_ref`, explicados más adelante).

+++

## ¿Cuáles son los nuevos parámetros de cadena de consulta agregados a las direcciones URL de redireccionamiento? {#section_BA73E8B3CFCC4CBEB5BE3F76B2BC8682}

+++Respuesta
Los siguientes parámetros de cadena de consulta se asocian con las ofertas de redireccionamiento:

| Parámetro | Descripción |
|--- |--- |
| `adobe_mc_sdid` | El parámetro `adobe_mc_sdid` pasa los valores Supplemental Data Id (SDID) y Experience Cloud Org Id de la página predeterminada a la nueva página. Estos ID permiten a A4T &quot;unir&quot; la solicitud de Target en la página predeterminada con la solicitud de Analytics en la nueva página.<br>El formato esperado para pasar sdid en la dirección URL (para aplicaciones híbridas o de una aplicación al sitio web o un sitio web a otro) es `ex. adobe_mc_sdid=SDID=123|MCORGID=123456789@AdobeOrg|TS=1498569322` |
| `adobe_mc_ref` | El parámetro `adobe_mc_ref` pasa la dirección URL de referencia de la página predeterminada a la nueva página. Cuando se utiliza con AppMeasurement.js versión 2.1 (o posterior), Analytics utiliza este valor de parámetro como dirección URL de referencia en la nueva página. |

Estos parámetros se agregan automáticamente a las direcciones URL de redireccionamiento al utilizar las ofertas de redireccionamiento integradas en el Compositor de experiencias visuales y el Compositor de experiencias basado en formularios cuando se implementa en la página el servicio Visitor Id. Si está utilizando código personalizado de redireccionamiento en VEC o el Compositor de experiencias basado en formularios, debe asegurarse de pasar estos parámetros junto al código personalizado.

+++

## Mis servidores web eliminan estos parámetros de mis direcciones URL, ¿qué debo hacer?  {#section_0C2DDB72939F4875B6D0428B8DCB38E5}

+++Respuesta
Trabaje con su equipo de TI para que estos parámetros ( `adobe_mc_sdid` y `adobe_mc_ref`) se vean incluidos en la lista de permitidos.

+++

## ¿Qué sucede si yo no utilizo A4T en mi actividad de redireccionamiento y no quiero que se agreguen estos parámetros adicionales a mis direcciones URL? {#section_9E608D75FF9349FE96C65FEDD7539F45}

+++Respuesta
Utilice una redirección con código personalizado si:

* No utiliza A4T en su actividad de redireccionamiento
* Ha implementado el servicio de ID de visitante
* No desea que estos parámetros se agreguen automáticamente a las direcciones URL

En cualquier caso, se recomienda mantener el parámetro `adobe_mc_ref` en la dirección URL para transmitir correctamente a [!DNL Analytics] la información del referente.

+++

## ¿Por qué los parámetros adobe_mc_ref y adobe_mc_sdid se codifican dos veces en la dirección URL en mi implementación? {#section_5EFE5F012B944C40865731EA18E7E79E}

+++Respuesta
Si utiliza A4T y ofertas de redireccionamiento, Target añade los parámetros `adobe_mc_ref` y `adobe_mc_sdid` a la dirección URL. Estos valores ya están codificados en la dirección URL. La mayoría de las veces, todo funciona según lo esperado, pero algunos clientes podrían disponer de equilibradores de carga o servidores WEB que traten de codificar una vez más los parámetros de la cadena de consulta.

Debido a esta doble codificación, cuando la API de visitante intenta descodificar el valor `adobe_mc_sdid`, no consigue extraer el valor SDID y genera un SDID nuevo. Este proceso lleva a que se envíen valores SDID incorrectos a Target y Analytics, y que se vean divisiones de redireccionamiento desiguales en los informes de Analytics.

Adobe recomienda que hable con su equipo de TI para asegurarse de que `adobe_mc_ref` y `adobe_mc_sdid` estén incluidos en la lista de permitidos de modo que estos valores no se transformen en modo alguno.

+++

## ¿Por qué se debe pasar la dirección URL de referencia a la nueva página? {#section_91AB8B0891F6416CBF7E973DCAF54EB5}

+++Respuesta
Supongamos que un visitante hace clic en un vínculo de [!DNL `www.google.com`] a su página de inicio (`www.mysite.com/index.html`), y que una actividad de redireccionamiento en dicha página lo redirige a una nueva página (`www.mysite.com/index2.html`).

Anteriormente, la solicitud [!DNL Analytics] de la nueva página informaría de que la dirección URL de referencia es [!DNL `www.mysite.com/index.html`], no [!DNL `www.google.com`]. Este comportamiento provocaba informes imprecisos en [!DNL Analytics] en cuanto a las direcciones URL de referencia (por ejemplo, en los informes de canales de mercadotecnia). Los informes no reflejaban el hecho de que usted llegó al sitio desde [!DNL `www.google.com`].

Con [!DNL at.js] versión 0.9.6 (o posterior) y [!DNL AppMeasurement.js] 2.1 (o posterior), la solicitud [!DNL Analytics] de la nueva página informa de que la dirección URL de referencia es [!DNL `www.google.com`].

+++

## ¿Puedo utilizar ofertas de redireccionamiento personalizadas/HTML? {#section_E49F9A83A286488C8F1098A040203D7E}

+++Respuesta
No, debe utilizar una oferta de redireccionamiento integrada para las actividades que empleen [!DNL Analytics] como fuente de informes (A4T). Desde la perspectiva de [!DNL Target], las ofertas HTML son opacas: [!DNL Target] no tiene forma de saber si un fragmento particular de HTML contiene código JavaScript que crea una instancia de redireccionamiento.

+++

## ![Insignia de Adobe Experience Platform Web SDK](/help/main/assets/platform.png) ¿Admite [!DNL Adobe Experience Platform Web SDK] ofertas de redireccionamiento para A4T? {#platform}

Las siguientes preguntas frecuentes proporcionan más información sobre el uso de A4T y redirigen ofertas con [!DNL Platform Web SDK].

### ¿Admite Analytics for Target (A4T) ofertas de redireccionamiento?

+++Respuesta
Sí, A4T a través de Platform Web SDK admite [ofertas de redireccionamiento](/help/main/c-experiences/c-manage-content/offer-redirect.md).

+++

### ¿Son compatibles [!UICONTROL Visual Experience Composer] (VEC) y [!UICONTROL Form-Based Experience Composer]?

+++Respuesta
Sí, el [[!UICONTROL Visual Experience Composer]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) y el [[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md) son compatibles si usa ofertas de redireccionamiento integradas.

+++

### ¿Puedo usar ofertas de redireccionamiento personalizadas/HTML con [!DNL Platform Web SDK]?

+++Respuesta
No, debe utilizar una oferta de redireccionamiento integrada para las actividades que utilizan A4T. Desde la perspectiva de [!DNL Target], las ofertas de HTML son opacas. [!DNL Target] no puede saber que un fragmento particular de HTML contiene JavaScript que crea una instancia de redireccionamiento.

+++
