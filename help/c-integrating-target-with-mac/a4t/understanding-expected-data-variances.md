---
keywords: data variances;analytics;differences;variance;a4t;analytics for target;analytics as the reporting source;discrepancies;discrepancy
description: Información sobre variaciones de datos previstas entre Target y Adobe Analytics al no usar Analytics como Fuente de informes (A4T), lo que elimina totalmente la variación de datos.
title: Variaciones de datos previstas al no usar A4T
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: cf47b7f3625bb1c3430b9fba00c573f489efc448
workflow-type: tm+mt
source-wordcount: '853'
ht-degree: 100%

---


# Variaciones de datos previstas entre Target y Analytics al utilizar y no utilizar A4T{#expected-data-variances-when-not-using-a-t}

Información sobre variaciones de datos previstas entre [!DNL Target] y Adobe [!DNL Analytics] al *usar* y *no* usar Analytics como Fuente de informes (A4T). A4T reduce considerablemente la variación de datos.

## Variaciones de datos previstas al no usar A4T {#expected-using-a4t}

Con A4T, la creación de informes con Analytics y con Target usa datos de Analytics exclusivamente, por lo que no hay variación entre las soluciones en los informes de actividad de Target. En algunas circunstancias, sin embargo, los clientes podrían comparar los datos de Target con los datos de Analytics fuera del alcance de la integración con A4T y, de esta manera, experimentar los problemas de variación que se describen más abajo.

Estos son algunos escenarios en los que podría experimentar variaciones de datos esperadas:

* A4T permite que se produzca una visita de Target (parte superior de la página), pero no se produce ninguna visita de Analytics (final de página). Un ejemplo de este comportamiento sería si el usuario carga la página, pero cierra el explorador antes de activar la llamada de Analytics. En estos casos, A4T excluye la visita de Target de nuestros datos. El motivo por el que ocurre es que permitir que las visitas de Target (nuevamente, parte superior de la página) cuenten como visitas de Analytics en ausencia de una llamada real de Analytics crearía incoherencias con el conjunto de datos en Analytics (inflación de visitantes, etc.).

   Si se configura una prueba de redireccionamiento en Target para dividir el tráfico 50/50 (o 25/25/25/25, etc.), es posible que el comportamiento del usuario no se divida uniformemente. Si ve una división desigual, simplemente significa que un grupo de usuarios falló en la ejecución de una llamada de Analytics en la página de aterrizaje más que los demás grupos. Este error al ejecutar la llamada de Analytics para un grupo provocó que se excluyera la visita de Target para ese usuario, lo que crea uniformidad.

   Este es un problema que esperamos abordar en el futuro a medida que trabajamos en la Adobe Experience Platform para A4T. Nuestros equipos están trabajando en la mejor manera de controlar los distintos eventos en diferentes momentos en la página.

   >[!NOTE]
   >
   >Hay un problema conocido que provoca que un número limitado de clientes que utilizan redireccionamientos con A4T vean un porcentaje más alto de tasas de visitas no vinculadas. Consulte [Problemas conocidos y problemas resueltos](/help/r-release-notes/known-issues-resolved-issues.md#redirect).

* Supongamos que crea una actividad de asignación automática abierta a todos los visitantes de una página en particular. Como las actividades de asignación automática no admiten A4T, [!DNL Target] recopila todos los datos de la actividad. Se podría esperar que los visitantes de la actividad en la creación de informes de [!DNL Target] coincidan con los visitantes de la página en la creación de informes de [!DNL Analytics] para el mismo intervalo de fechas. Este es un escenario en que se espera la variación descrita más abajo.

   Para ver una lista completa de tipos de actividad compatibles con A4T, consulte [Tipos de actividades compatibles](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA).

## Variaciones de datos previstas al *no usar* A4T   {#expected-not-using-a4t}

Es normal encontrar unas variaciones de entre el 15 y el 20%, incluso en conjuntos de datos similares. Los sistemas que realizan recuentos de manera distinta pueden arrojar unas variaciones de datos mucho mayores, de incluso entre el 35 y el 50%. En algunas ocasiones, estas variaciones pueden ser aún más acusadas.

Aunque los datos reales pueden variar de forma muy considerable, las tendencias suelen ser coherentes. Siempre y cuando las diferencias y tendencias sean coherentes, los datos seguirán conservando su valor y utilidad. Si no lo son, puede ser indicativo de que hay algo mal configurado, en cuyo caso deberá ponerse en contacto con el representante de cuentas para obtener ayuda.

[!DNL Analytics] emplea un sistema basado en visitas y transacciones, mientras que usa métricas basadas en visitantes. [!DNL Target] Esto quiere decir que, cada vez que un visitante abre una página, lo considera una visita en [!DNL Analytics], pero [!DNL Target] no lo considera como tal hasta que se reúnen las condiciones establecidas para la actividad en cuestión.

Los informes de [!DNL Target] muestran el rendimiento según el mbox de conversión que se seleccionó al definir la actividad; sin embargo, los datos de este mbox de conversión no se envían a [!DNL Analytics], que posee sus propias variables de conversión definidas según la [!DNL Analytics]implementación de etiquetas. En aquellas situaciones en las que se esperaría encontrar datos idénticos (por ejemplo, si la página de confirmación de pedidos de un minorista contiene un mbox de conversión y un evento de compra de [!DNL Analytics]), tales datos podrían variar según la colocación de estas etiquetas. Con todo, por lo general las tendencias en los informes de ambos productos deberían ser similares.

Las variaciones de datos previstas pueden estar originadas por variaciones de índole tanto técnica como empresarial.

### Ejemplos de variaciones técnicas   {#section_C3B50ED2E2F9416FAC91437CF1A87369}

A continuación se indican las situaciones que pueden desembocar en variaciones de datos debido a diferencias técnicas:

* [!DNL Target]Los visitantes de deben permitir las cookies y JavaScript
* Las cookies de origen y de terceros se procesan de modo distinto, con lo cual los datos procedentes de ambos tipos de cookies no coinciden
* Ubicación relativa de las etiquetas en las páginas y la “fuga” provocada por los visitantes que abandonan la página antes de que se cargue completamente
* Consideraciones de zona horaria
* Diferencias en las que se pueden contar dispositivos

### Ejemplos de variaciones empresariales.   {#section_2E1EB5E15BB64A1A80E4CDB1A5062AEE}

A continuación se indican las situaciones que pueden desembocar en variaciones de datos debido a diferencias empresariales:

* Diferencias entre las métricas de visitante y visita
* Centrarse en las actividades excluye a algunos visitantes.
* Un solo mbox puede estar en varias páginas, lo cual hace que se incluyan en el recuento los visitantes de cada una de esas páginas.
* Las prioridades de actividad pueden incluir a algunos visitantes y excluir a otros en una página.
* Los visitantes que se han convertido una vez pueden volver a incluirse en el recuento cuando entran de nuevo en la actividad.
* [!DNL Analytics] cuenta todas las conversiones de todas las visitas y visitantes, mientras que [!DNL Target] cuenta las conversiones de las visitas y visitantes que se incluyen en la actividad.