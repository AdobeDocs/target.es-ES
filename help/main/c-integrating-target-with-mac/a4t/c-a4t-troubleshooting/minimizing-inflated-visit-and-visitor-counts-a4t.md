---
keywords: datos parciales;A4T;discrepancias;analytics for target;huérfano;grupo de informes virtual;fantasma;resolución de problemas;no vinculado;inflado;no especificado
description: Aprenda a minimizar los efectos de los recuentos inflados de visitas y visitantes al utilizar Analytics for  [!DNL Target]  (A4T). Conozca qué son los “datos parciales” y cómo reducirlos.
title: ¿Cómo minimizo los recuentos inflados de visitas y visitantes en A4T?
feature: Analytics for Target (A4T)
exl-id: 308711f7-e630-4f6b-8a6d-a1f36ed7902d
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '1320'
ht-degree: 99%

---

# Minimización de los recuentos inflados de visitas y visitantes en A4T

Información que le ayudará a minimizar los efectos de los recuentos inflados de visitas y visitantes al utilizar [!DNL Adobe Analytics] como fuente de informes de [!DNL Adobe Target] (A4T).

>[!IMPORTANT]
>El 14 de noviembre de 2016, Adobe Analytics cambió el modo de procesar determinados datos para clientes mediante los informes de Analytics for Target (A4T). Estos cambios permiten que los datos de Adobe Target estén más alineados con el modelo de datos de Adobe Analytics. Estos cambios se publicaron para todos los clientes con A4T. Estos cambios resolverán un problema específico de algunos clientes, que han observado un recuento de visitantes inflado mientras se ejecutan las actividades de Target.
>
>Este cambio no es retroactivo. Si sus informes históricos muestran recuentos inflados y quiere excluirlos de sus informes, puede crear un grupo de informes virtuales, tal y como se explica a continuación.
>
>Además, se han actualizado varias bibliotecas de JavaScript para minimizar los recuentos inflados. Adobe recomienda que actualice su biblioteca a una de las siguientes versiones (o una versión posterior):
>
>* Servicio ID de visitante de Experience Cloud: visitorAPI.js versión 2.3.0 o posterior.
>* Adobe Analytics: appMeasurement.js versión 2.1.
>* Adobe Target: versión 0.9.6 de at.js o posterior (excepto la versión 1.1.0 si se utilizan ofertas de redireccionamiento con A4T).

## Cambios  {#section_9CCF45F5D66D48EBA88F3A178B27D986}

Cuando se utiliza [!DNL Adobe Analytics] para medir las actividades de [!DNL Target] (lo que se conoce como A4T), [!DNL Analytics] recopila datos adicionales que no están disponibles si no hay actividad de [!DNL Target] en la página. La actividad de [!DNL Target] activa una llamada al principio de la página, pero [!DNL Analytics] suele activar sus llamadas de recopilación de datos al final de la página. En las implementaciones de A4T realizadas hasta la fecha, Adobe incluye estos datos adicionales siempre que había una actividad de [!DNL Target] activa. En adelante, Adobe incluirá estos datos adicionales solo si se han activado tanto la etiqueta de [!DNL Target] como la de [!DNL Analytics].

## ¿Por qué ha hecho Adobe este cambio?  {#section_92380A4BD69E4B8886692DD27540C92A}

Adobe se enorgullece de la calidad y la precisión de sus datos. Cuando la etiqueta [!DNL Target] se activa, pero la etiqueta [!DNL Analytics] no, Analytics registra “datos parciales” (también conocidos como “visitas no vinculadas”). Estas visitas no vinculadas no serían capturadas por [!DNL Analytics] si no hay actividad de [!DNL Target]. Aunque, al incluir estos datos parciales en los informes de [!DNL Analytics] se proporciona información adicional, también se crea incoherencia con los datos históricos de periodos en los que no se ejecutó ninguna actividad de [!DNL Target]. Esto puede causar problemas a los usuarios de [!DNL Analytics] que analizan las tendencias a lo largo del tiempo. Con el fin de garantizar la coherencia de los datos en [!DNL Analytics], Adobe excluye todos los datos parciales.

## Contribuciones a los datos parciales  {#section_C9C906BEAA7D44DAB9D3C03932A2FEB8}

Adobe ha encontrado algunos clientes con altas tasas de datos parciales en [!DNL Analytics]. Las altas tasas de datos parciales pueden resultar de una implementación incorrecta, pero también hay causas legítimas.

Estas son algunas de las causas que se han identificado para los datos parciales:

* **Desalineación de ID de grupos de informes (implementación):** el grupo de informes especificado durante la configuración de la actividad no coincide con el grupo de informes de la página en la que se realiza la prueba. Los datos no se pueden conciliar en [!DNL Analytics] por lo que parecen datos parciales.
* **Páginas lentas:** las llamadas de [!DNL Target] se encuentran en la parte superior de la página y las llamadas de [!DNL Analytics] suelen aparecer en la parte inferior de la página. Si la página se carga lentamente, aumenta la probabilidad de que un visitante salga de la página después de que se active la llamada a [!DNL Target], pero antes de la llamada a [!DNL Analytics]. Las páginas lentas pueden resultar especialmente problemáticas en los sitios web móviles, cuya conexión suele ser más lenta.
* **Errores de página:** si hay algún error de JavaScript o cualquier otra situación en la que no se activen los puntos de contacto (servicio Experience Cloud ID, Target y Analytics), se obtendrán datos parciales.
* **Redirección de ofertas en actividad [!DNL Target]:** para redireccionar ofertas en actividades que utilizan A4T, su implementación debe satisfacer ciertos requisitos mínimos. Además, hay información importante que debe conocer. Para obtener más información, consulte las [preguntas más frecuentes de A4T sobre las ofertas de redireccionamiento](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#section_FA9384C2AA9D41EDBCE263FFFD1D9B58).
* **Versiones antiguas de bibliotecas:** a lo largo del último año Adobe ha realizado algunas mejoras en las bibliotecas JavaScript ([!DNL appMeasurement.js], `at.js` y `visitorAPI.js`) para garantizar que los datos se envían de la manera más eficiente posible. Para obtener más información sobre los requisitos de implementación, consulte [Antes de realizar la implementación](/help/main/c-integrating-target-with-mac/a4t/before-implement.md#concept_046BC89C03044417A30B63CE34C22543).

## Prácticas recomendadas para reducir la cantidad de datos parciales  {#section_065C38501527451C8058278054A1818D}

Revise los siguientes pasos con el fin de reducir la recopilación de datos parciales:

| Paso | Tarea |
| --- | --- |
| ![Paso 1](assets/step1_icon.png) | Asegúrese de que el grupo de informes seleccionado en [!DNL Target] es igual que en las páginas donde se presenta la actividad. |
| ![Paso 2](assets/step2_icon.png) | Asegúrese de que las bibliotecas visitorAPI.js, appMeasurement.js y at.js estén en versiones compatibles con A4T. Para obtener más información sobre los requisitos de implementación, consulte [Antes de realizar la implementación](/help/main/c-integrating-target-with-mac/a4t/before-implement.md). |
| ![Paso 3](assets/step3_icon.png) | Compruebe que se define el SDID en todas las llamadas de [!DNL Target] y [!DNL Analytics] que salen de la página y que coinciden.<br/>Use un analizador de redes o una herramienta de depuración con el fin de garantizar que el parámetro `mboxMCSDID` de las llamadas de [!DNL Target] coincide con el parámetro SDID de la llamada de [!DNL Analytics]. |
| ![Paso 4](assets/step4_icon.png) | Confirme que las bibliotecas de implementación se cargan en el orden correcto en sus sitios. Para obtener más información, consulte [Implementación de Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). |

## Ver la cantidad de datos parciales guardada  {#section_89B663E2824A4805AB934153508A0F4B}

Aunque esta información no está disponible directamente en [!DNL Analytics], puede ponerse en contacto con el servicio de atención al cliente de Adobe para recibir un informe de datos parciales. El objetivo de este informe es facilitar la depuración.

## Visualización de las tendencias históricas sin datos parciales  {#section_4C9DED560FAD4428B362DDA2064897C3}

Este cambio de procesamiento solo afecta a los datos después de la fecha de la versión (14 de noviembre de 2016). Si desea ajustar las métricas históricas para que coincidan, Adobe recomienda crear un segmento para excluir los datos parciales.

La siguiente información, relacionada con este cambio, incluye instrucciones que le ayudarán a definir el segmento y aplicarlo a un grupo de informes virtuales, de modo que el segmento siempre se aplique en sus visualizaciones de [!DNL Analytics].

En la mayoría de los casos, una visita de [!DNL Target] se vincula con una visita de [!DNL Analytics] en cada página web. La vinculación se realiza si aparece un SDID consistente en ambas llamadas de [!DNL Target] y [!DNL Analytics] y si hay un [!DNL Experience Cloud ID] (MCID) en la llamada de [!DNL Analytics] en la misma página. Normalmente, [!DNL Target] también tiene el MCID, pero si la llamada a [!DNL Target] se realiza antes de que regrese el ID del visitante, la visita se vinculará debido al SDID. Además, el usuario debe permanecer en la página el tiempo suficiente para que se active una llamada de [!DNL Analytics] después de que se active una llamada de [!DNL Target]. Este escenario es ideal.

**Visitas de datos parciales:** a veces los usuarios no permanecen en una página el tiempo suficiente para que se envíe una llamada de [!DNL Analytics], pero [!DNL Target] tiene el MCID adecuado. Esto provoca la aparición de visitas de datos parciales (visitas sin visualizaciones de página de [!DNL Analytics]). Si estos usuarios vuelven al sitio y ven una página que contenga código de [!DNL Analytics], se contarán debidamente como visitantes que repiten. Estas son visitas que se habrían perdido si solo existiera código de [!DNL Analytics] en la página. Algunos clientes no quieren datos para estas visitas porque inflan algunas métricas (visitas) y desinflan otras (visualizaciones de la página por visita, tiempo por visita, etc.). También verá visitas que no tengan ninguna visualización de página. Sin embargo, existen varios motivos para conservar estos datos.

Para minimizar las visitas de datos parciales, puede hacer que su página se cargue más rápido, actualizar las bibliotecas a la versión más reciente o crear un [grupo de informes virtuales](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html?lang=es) que excluya esas visitas. Puede consultar las instrucciones paso a paso en [Creación de grupos de informes virtuales](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html?lang=es), en la *Guía de componentes de Analytics*.

En la siguiente ilustración se muestra la definición de un segmento para el grupo de informes virtuales:

![imagen ts_a4t](assets/ts_a4t.png)

Cuando cree un grupo de informes virtuales, especifique la siguiente configuración para la definición del segmento (tal y como se muestra en la ilustración anterior):

* **Mostrar visitas:**
* Analytics for Target: existe
* Y
* Visualizaciones de página: no existe
* Y
* Instancias de vínculos personalizados: no existe
* Y
* Instancias de vínculos de descarga: no existe
* Y
* Instancias de vínculos de salida: no existe

**Visitas huérfanas:** con menor frecuencia, los usuarios no permanecen en la página el tiempo suficiente para que se realice la llamada de Analytics y, además, Target no tiene un MCID apropiado. Estas visitas son lo que Adobe define como visitas “huérfanas”. Estas visitas representan a los clientes que raramente regresan e inflan indebidamente los recuentos de visitas y visitantes.

Para minimizar estas visitas &quot;huérfanas&quot;, puede crear un [grupo de informes virtuales](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html?lang=es) que las excluya, tal y como hemos explicado.

## Consecuencias para los informes de [!DNL Target]  {#section_AAD354C722BE46D4875507F0FCBA5E36}

Una vez que se realice este cambio, es probable que observe que disminuyen los nuevos visitantes y las visitas en las pruebas en directo, porque [!DNL Adobe] no procesa la entrada de datos parciales. Las conversiones y visitas a otras métricas [!DNL Analytics] no se verán afectadas.
