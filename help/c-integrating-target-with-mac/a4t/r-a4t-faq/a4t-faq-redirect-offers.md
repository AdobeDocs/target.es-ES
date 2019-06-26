---
description: En este tema encontrará respuestas a preguntas que se plantean a menudo sobre el uso de ofertas de redireccionamiento al usar Analytics como fuente de informes para Target (A4T).
keywords: faq;preguntas más frecuentes;analytics para target;a4T;redireccionamiento;oferta de redireccionamiento;adobe-mc-sdid;adobe_mc_ref
seo-description: En este tema encontrará respuestas a preguntas que se plantean a menudo sobre el uso de ofertas de redireccionamiento al usar Analytics como fuente de informes para Target (A4T).
seo-title: 'Ofertas de redireccionamiento: preguntas más frecuentes sobre A4T'
solution: Target
title: 'Ofertas de redireccionamiento: preguntas más frecuentes sobre A4T'
topic: Standard
uuid: a45cef89-3003-4177-bf84-3d5a486b950d
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Ofertas de redireccionamiento: preguntas más frecuentes sobre A4T{#redirect-offers-a-t-faq}

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre el uso de ofertas de redireccionamiento al usar Analytics como fuente de informes para Target (A4T).

## ¿Admite Analytics for Target (A4T) ofertas de redireccionamiento?{#section_46B8B03ED4D542C6AD875F5F61176298}

Sí, siempre que su implementación utilice [!DNL at.js]. Sin embargo, la implementación debe cumplir los requisitos mínimos enumerados a continuación para utilizar [ofertas de redireccionamiento](../../../c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94) en actividades que usen Analytics como fuente de informes.

## ¿Cuáles son los requisitos mínimos para utilizar ofertas de redireccionamiento con A4T?{#section_FA9384C2AA9D41EDBCE263FFFD1D9B58}

Su implementación debe cumplir los siguientes requisitos mínimos:

* Servicio ID de visitante de Experience Cloud: [!DNL visitorAPI.js] versión 2.3.0 o posterior.
* Adobe Analytics: [!DNL appMeasurement.js] versión 2.1.
* Adobe Target: [!DNL at.js] versión 1.6.2 o posterior.

   La biblioteca [!DNL mbox.js] no admite ofertas de redireccionamiento con A4T. La implementación debe utilizar [!DNL at.js].

Las tres bibliotecas deben incluirse en la página con la oferta de redireccionamiento y en aquella a la que se redireccione al visitante.

## ¿Por qué algunas veces hay discrepancias en los datos entre A4T y Analytics?

Se esperan algunas discrepancias en los datos. Para obtener más información, consulte [Variaciones de datos previstas entre Target y Analytics al utilizar y no utilizar A4T](/help/c-integrating-target-with-mac/a4t/understanding-expected-data-variances.md).

## ¿Por qué las vistas de página a veces se cuentan en la página original y a veces en la página de redirección?  {#section_B8F6CC2190B84CF08D945E797C5AF07B}

Existe la posibilidad de que se produzca una condición de carrera que provoque que Analytics haga una llamada de activación antes de que la redirección se ejecute en la primera página. Esto puede provocar que se cuenten tanto las vistas de página de la página original como las de la página de redirección. Como consecuencia, se cuenta una vista de página adicional en la primera página, cuando en realidad el visitante nunca “vio” esa primera página.

Para aumentar la velocidad de redirección de la página, se recomienda utilizar el compositor basado en formulario para crear una actividad de redirección. Esto depende del lugar de la página en que se ejecuta el código. También se recomienda crear una oferta de redireccionamiento para cada experiencia, incluso para la experiencia predeterminada, en la que la redirección devuelva la página original. Así se garantiza que si se produce un error de recuento, este se produzca en todas las experiencias, de modo que los informes y los análisis sigan siendo válidos para la prueba.

>[!NOTE]
>
>Esta condición de carrera solo afecta a los clientes que utilizan la versión 1.6.3 o anterior de at.js. Tenga en cuenta que el equipo de Target mantiene solo dos versiones de at.js: la actual y la penúltima. Actualice at.js cuando sea posible para garantizar que dispone de una [versión compatible](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

Para obtener más información sobre este problema, consulte la columna “Ofertas de redireccionamiento” en la tabla [Problemas conocidos](../../../r-release-notes/known-issues-resolved-issues.md#concept_625C3A16B7F24D4B82EFF130F0945541).

## ¿Puedo utilizar ofertas de redireccionamiento con A4T si empleo la biblioteca mbox.js de JavaScript?{#section_D2A8B182B7254D61A8BB2BCBA0C0F64A}

La biblioteca [!DNL mbox.js] no admite ofertas de redireccionamiento con A4T. La implementación debe utilizar [!DNL at.js].

## ¿Son compatibles el Compositor de experiencias visuales (VEC) y el Compositor de experiencias basado en formularios?{#section_FDA26FE7909B48539DA770559E687677}

Sí, ambos son compatibles mientras se utilicen las ofertas de redireccionamiento integradas.

Si utiliza su propio código personalizado para el redireccionamiento, debe asegurarse de rellenar los dos nuevos parámetros asociados con direcciones URL de redireccionamiento (`adobe_mc_sdid` y `adobe_mc_ref`, explicados más adelante).

## ¿Cuáles son los nuevos parámetros de cadena de consulta agregados a las direcciones URL de redireccionamiento?{#section_BA73E8B3CFCC4CBEB5BE3F76B2BC8682}

Los siguientes parámetros de cadena de consulta se asocian con las ofertas de redireccionamiento:

| Parámetro | Descripción |
|--- |--- |
| `adobe_mc_sdid` | El parámetro `adobe_mc_sdid` pasa los valores Supplemental Data Id (SDID) y Experience Cloud Org Id de la página predeterminada a la nueva página para que A4T “vincule” la solicitud de Target para la página predeterminada con la solicitud de Analytic de la nueva página. |
| `adobe_mc_ref` | El parámetro `adobe_mc_ref` pasa la dirección URL de referencia de la página predeterminada a la nueva página. Cuando se utiliza con la versión 2.1 (o posterior) de AppMeasurement.js, Analytics emplea el valor de este parámetro como dirección URL de referencia en la nueva página. |

Estos parámetros se agregan automáticamente a las direcciones URL de redireccionamiento al utilizar las ofertas de redireccionamiento integradas en el Compositor de experiencias visuales y el Compositor de experiencias basado en formularios cuando se implementa en la página el servicio Visitor Id. Si está utilizando código personalizado de redireccionamiento en VEC o el Compositor de experiencias basado en formularios, debe asegurarse de pasar estos parámetros junto al código personalizado.

## Mis servidores web eliminan estos parámetros de mis direcciones URL, ¿qué debo hacer?  {#section_0C2DDB72939F4875B6D0428B8DCB38E5}

Debe trabajar junto a su equipo de TI para que los parámetros (`adobe_mc_sdid` y `adobe_mc_ref`) resulten admitidos.

## ¿Qué sucede si yo no utilizo A4T en mi actividad de redireccionamiento y no quiero que se agreguen estos parámetros adicionales a mis direcciones URL?{#section_9E608D75FF9349FE96C65FEDD7539F45}

Si no utiliza A4T en su actividad de redireccionamiento, tiene implementado el servicio Visitor Id y no quiere que estos parámetros se agreguen automáticamente a sus direcciones URL, debe utilizar código personalizado para el redireccionamiento.

En cualquier caso, se recomienda mantener el parámetro `adobe_mc_ref` en la dirección URL para transmitir correctamente a [!DNL Analytics] la información del referente.

## ¿Por qué los parámetros adobe_mc_ref y adobe_mc_sdid se codifican dos veces en la dirección URL en mi implementación?{#section_5EFE5F012B944C40865731EA18E7E79E}

Si utiliza A4T y ofertas de redireccionamiento, Target añade los parámetros `adobe_mc_ref` y `adobe_mc_sdid` a la dirección URL. Estos valores ya están codificados en la dirección URL. La mayoría de las veces, todo funciona según lo esperado, pero algunos clientes podrían disponer de equilibradores de carga o servidores WEB que traten de codificar una vez más los parámetros de la cadena de consulta.

Debido a esta doble codificación, cuando la API de visitante intenta descodificar el valor `adobe_mc_sdid`, no consigue extraer el valor SDID y genera un SDID nuevo. Esto provoca que se envíen valores SDID incorrectos a Target y a Analytics, y que se vean divisiones de redireccionamiento desiguales en los informes de Analytics.

Se recomienda hablar con el equipo de TI para asegurar que `adobe_mc_ref` y `adobe_mc_sdid` estén en la lista de admitidos, de manera que estos valores no se transformen de modo alguno.

## ¿Por qué se debe pasar la dirección URL de referencia a la nueva página?{#section_91AB8B0891F6416CBF7E973DCAF54EB5}

Supongamos que un visitante hace clic en [!DNL `www.google.com`] en un vínculo a su página de inicio ([!DNL `www.mysite.com/index.html]`), y que una actividad de redireccionamiento en dicha página lo redirige a una nueva página ([!DNL `www.mysite.com/index2.html`]).

Anteriormente, la solicitud de [!DNL Analytics] para la nueva página informaría de que la dirección URL de referencia es [!DNL `www.mysite.com/index.html`], no [!DNL `www.google.com`]. Este comportamiento provocaba informes imprecisos en [!DNL Analytics] en cuanto a las direcciones URL de referencia (por ejemplo, en los informes de canales de mercadotecnia). No se reflejaba el hecho de que se había llegado al sitio desde [!DNL `www.google.com`].

Con las versiones 0.9.6 (o posterior) de [!DNL at.js] y 2.1 (o posterior) de [!DNL AppMeasurement.js], la solicitud de [!DNL Analytics] para la nueva página informa de que la dirección URL de referencia es [!DNL `www.google.com`].

## ¿Puedo utilizar ofertas de redireccionamiento personalizadas/HTML?{#section_E49F9A83A286488C8F1098A040203D7E}

No, debe utilizar una oferta de redireccionamiento integrada para las actividades que empleen [!DNL Analytics] como fuente de informes (A4T). Desde la perspectiva de [!DNL Target], las ofertas HTML son opacas: [!DNL Target] no tiene forma de saber si un fragmento particular de HTML contiene código JavaScript que crea una instancia de redireccionamiento.
