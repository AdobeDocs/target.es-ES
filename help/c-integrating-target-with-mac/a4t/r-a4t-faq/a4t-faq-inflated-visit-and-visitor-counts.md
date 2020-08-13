---
keywords: faq;frequently asked questions;analytics for target;a4T;inflated;visit;visitor;partial hit;orphaned;orphan;partial-hit
description: En este tema encontrará respuestas a preguntas que se plantean a menudo sobre los recuentos inflados de visitas y visitantes al usar Analytics como fuente de informes para Target (A4T).
title: 'Recuentos inflados de visitas y visitantes: preguntas más frecuentes sobre A4T'
feature: a4t troubleshooting
topic: Standard
uuid: 5d1b77bb-9053-4533-bd01-d6f53f0751e9
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 100%

---


# Recuentos inflados de visitas y visitantes: preguntas más frecuentes sobre A4T{#inflated-visit-and-visitor-counts-a-t-faq}

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre los recuentos inflados de visitas y visitantes al usar Analytics como fuente de informes para Target (A4T).

## ¿Por qué mis datos de Analytics muestran visitas sin vistas de página u otros valores de variables?{#section_4D8C2C2D766842E6B12F3ECC774A64D5}

Cuando se utiliza [!DNL Adobe Analytics] para medir las actividades de [!DNL Target] (lo que se conoce como A4T), [!DNL Analytics] recopila datos adicionales que no están disponibles si no hay actividad de [!DNL Target] en la página. Esto se debe a que la actividad de [!DNL Target] activa una llamada al principio de la página, pero [!DNL Analytics] suele activar sus llamadas de recopilación de datos al final de la página. En las implementaciones de A4T realizadas hasta la fecha, hemos incluido estos datos adicionales siempre que había una actividad de [!DNL Target] activa.

Para obtener más información, consulte [Minimización de recuentos inflados de visitas y visitantes en A4T](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## ¿Qué es una visita de datos parciales?{#section_59A203E289564576BF6821F96B0B9E11}

Las visitas de datos parciales se obtienen cuando se activa una etiqueta de [!DNL Target] al principio de la página, pero no se activa ninguna etiqueta de [!DNL Analytics] al final de la página. Esto puede ocurrir por diversos motivos. En las implementaciones de [!DNL A4T] realizadas hasta la fecha, hemos incluido los datos parciales de estas visitas cuando había una actividad de [!DNL Target] activa. En adelante, incluiremos estos datos adicionales solo si se han activado tanto la etiqueta de [!DNL Target] como la de [!DNL Analytics].

Para obtener más información, consulte [Minimización de recuentos inflados de visitas y visitantes en A4T](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## He observado un pico en las visitas. ¿Cómo sé si esto es debido a las visitas de datos parciales?   {#section_28506672C6224ED18AC74F6A02F6F811}

Puede ponerse en contacto con el [Servicio de atención al cliente de Adobe](../../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para recuperar un informe de datos parciales. Esta información no se puede obtener directamente desde la interfaz de usuario de [!DNL Analytics].

## ¿Qué puede provocar las visitas de datos parciales?{#section_C4BB9925CE6444BE8CB9FBEFE5085546}

Las visitas de datos parciales suelen deberse a un fallo en la implementación, como una desalineación de ID de grupos de informes. También puede ser por causas legítimas, como páginas lentas, errores de página, ofertas de redireccionamiento en una actividad o versiones de bibliotecas antiguas.

Para obtener más información, consulte “¿Qué provoca la aparición de datos parciales?” en   [Minimización de los recuentos inflados de visitas y visitantes en A4T](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Tengo visitas de datos parciales. ¿Cómo puedo limpiar los datos?   {#section_CBE778A9D07A469E8FF98F68BACC7124}

Puede crear un grupo de informes virtuales para excluir los datos parciales históricos de sus informes.

Para obtener más información, consulte “¿Cómo puedo ver las tendencias históricas sin datos parciales?” en [Minimización de los recuentos inflados de visitas y visitantes en A4T](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## ¿Puedo hacer algo para evitar que mis páginas generen visitas de datos parciales?{#section_4B00E7E618444BE98A0798DE98F08B21}

A partir del 14 de noviembre de 2016, incluiremos estos datos solo si se han activado tanto la etiqueta de [!DNL Target] como la de [!DNL Analytics]. Este cambio no es retroactivo. Si los informes históricos muestran recuentos inflados y desea excluirlos, puede crear un grupo de informes virtuales, tal y como se explica en “¿Cómo puedo ver las tendencias históricas sin datos parciales?” en [Minimización de los recuentos inflados de visitas y visitantes en A4T](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

También puede seguir algunos pasos para minimizar las visitas de datos parciales. Para obtener más información, consulte “¿Qué es lo mejor para reducir la cantidad de datos parciales?” en [Minimización de los recuentos inflados de visitas y visitantes en A4T](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Si se eliminan las visitas de datos parciales de los informes, ¿no se perderán datos valiosos de Target o Analytics? {#section_EBC39E8A0F6A40E58F51E776936F7D9E}

Al incluir estos datos parciales en los informes de [!DNL Analytics] se obtiene información adicional, pero también se crea incoherencia con los datos históricos de periodos en los que no se ejecutó ninguna actividad de [!DNL Target]. Esto puede causar problemas a los usuarios de [!DNL Analytics] que analizan las tendencias a lo largo del tiempo.

Puede seguir algunos pasos para minimizar las visitas de datos parciales. Para obtener más información, consulte “¿Qué es lo mejor para reducir la cantidad de datos parciales?” en [Minimización de los recuentos inflados de visitas y visitantes en A4T](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## ¿Hay algún tipo de actividad de Target con mayor probabilidad de generar visitas de datos parciales?{#section_69837442A9B84366BEFDA4588B31E574}

Las ofertas de redireccionamiento envían inmediatamente a un usuario a una página distinta, por lo que la llamada de [!DNL Analytics] no se activa en la primera página.
