---
keywords: preguntas frecuentes;faq;analytics para target;a4T;visita;infladas;visitante;visita parcial;huérfano;huérfana
description: Encuentre respuestas a preguntas sobre los recuentos inflados de visitas y visitantes al usar Analytics para [!DNL Target] (A4T). Aprenda a minimizar los "datos parciales".
title: ¿Dónde puedo encontrar preguntas más frecuentes sobre los recuentos inflados de visitas y visitantes con A4T?
feature: Analytics for Target (A4T)
exl-id: e936b1f6-dc72-4ab2-9bb5-169d1710edbe
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 62%

---

# Recuentos inflados de visitas y visitantes: preguntas más frecuentes sobre A4T

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre los recuentos inflados de visitas y visitantes al usar Analytics como fuente de informes para Target (A4T).

## ¿Por qué mis datos de Analytics muestran visitas sin vistas de página u otros valores de variables? {#section_4D8C2C2D766842E6B12F3ECC774A64D5}

When [!DNL Adobe Analytics] se utiliza para medir [!DNL Target] actividades (denominadas A4T), [!DNL Analytics] recopila datos que no están disponibles cuando no hay [!DNL Target] actividad en la página. Esto se debe a que la actividad de [!DNL Target] activa una llamada al principio de la página, pero [!DNL Analytics] suele activar sus llamadas de recopilación de datos al final de la página. En las implementaciones de A4T realizadas hasta la fecha, el Adobe incluye estos datos adicionales siempre que se [!DNL Target] la actividad estaba activa.

Para obtener más información, consulte [Minimización de recuentos inflados de visitas y visitantes en A4T](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## ¿Qué es una visita de datos parciales? {#section_59A203E289564576BF6821F96B0B9E11}

Las visitas de datos parciales se obtienen cuando se activa una etiqueta de [!DNL Target] al principio de la página, pero no se activa ninguna etiqueta de [!DNL Analytics] al final de la página. Hay varias razones por las que esta situación ocurre. En el [!DNL A4T] implementación hasta la fecha, Adobe incluye datos parciales sobre estas visitas siempre que [!DNL Target] la actividad estaba activa. De ahora en adelante, los Adobes incluirán estos datos adicionales solo cuando [!DNL Target] y [!DNL Analytics] se han activado las etiquetas .

Para obtener más información, consulte [Minimización de recuentos inflados de visitas y visitantes en A4T](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## He observado un pico en las visitas. ¿Cómo puedo saber si estas visitas están provocadas por visitas de datos parciales? {#section_28506672C6224ED18AC74F6A02F6F811}

Puede ponerse en contacto con el [Servicio de atención al cliente de Adobe](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para recuperar un informe de datos parciales. Esta información no se puede obtener directamente desde la interfaz de usuario de [!DNL Analytics].

## ¿Qué puede provocar las visitas de datos parciales? {#section_C4BB9925CE6444BE8CB9FBEFE5085546}

Las visitas de datos parciales suelen deberse a un fallo en la implementación, como una desalineación de ID de grupos de informes. También puede ser por causas legítimas, como páginas lentas, errores de página, ofertas de redireccionamiento en una actividad o versiones de bibliotecas antiguas.

Para obtener más información, consulte “¿Qué provoca la aparición de datos parciales?” en   [Minimización de los recuentos inflados de visitas y visitantes en A4T](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Tengo visitas de datos parciales. ¿Cómo puedo limpiar los datos?   {#section_CBE778A9D07A469E8FF98F68BACC7124}

Puede crear un grupo de informes virtuales para excluir los datos parciales históricos de sus informes.

Para obtener más información, consulte “¿Cómo puedo ver las tendencias históricas sin datos parciales?” en [Minimización de los recuentos inflados de visitas y visitantes en A4T](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## ¿Puedo hacer algo para evitar que mis páginas generen visitas de datos parciales? {#section_4B00E7E618444BE98A0798DE98F08B21}

A partir del 14 de noviembre de 2016, los Adobes incluirán datos solamente cuando [!DNL Target] y [!DNL Analytics] se han activado las etiquetas . Este cambio no es retroactivo. Si los informes históricos muestran recuentos inflados, puede excluirlos de los informes creando un grupo de informes virtuales. Consulte &quot;¿Cómo puedo ver las tendencias históricas sin datos parciales?&quot; en [Minimización de los recuentos inflados de visitas y visitantes en A4T](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

También puede seguir algunos pasos para minimizar las visitas de datos parciales. Para obtener más información, consulte “¿Qué es lo mejor para reducir la cantidad de datos parciales?” en [Minimización de los recuentos inflados de visitas y visitantes en A4T](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Si se eliminan las visitas de datos parciales de los informes, ¿no se está perdiendo valor? [!DNL Target] o datos de Analytics? {#section_EBC39E8A0F6A40E58F51E776936F7D9E}

Inclusión de datos parciales en [!DNL Analytics] los informes proporcionan información adicional, pero también crean incoherencia con los datos históricos de periodos en los que no hubo [!DNL Target] actividades en ejecución. La inclusión de datos de visitas parciales puede causar problemas en [!DNL Analytics] usuarios que analizan tendencias a lo largo del tiempo.

Puede seguir algunos pasos para minimizar las visitas de datos parciales. Para obtener más información, consulte “¿Qué es lo mejor para reducir la cantidad de datos parciales?” en [Minimización de los recuentos inflados de visitas y visitantes en A4T](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## ¿Hay algún tipo particular de [!DNL Target] ¿actividades que tienen más probabilidades de generar visitas de datos parciales? {#section_69837442A9B84366BEFDA4588B31E574}

Las ofertas de redireccionamiento envían inmediatamente a un usuario a una página distinta, por lo que la llamada de [!DNL Analytics] no se activa en la primera página.
