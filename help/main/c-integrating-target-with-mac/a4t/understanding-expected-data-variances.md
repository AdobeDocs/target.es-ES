---
keywords: variaciones de datos;analytics;variación;a4t;analytics para target;analytics como fuente de informes;diferencias;discrepancias;discrepancia
description: Obtenga información sobre las variaciones de datos previstas entre Adobes [!DNL Target] y Analytics al no usar Analytics para [!DNL Target] (A4T), que elimina totalmente la variación de datos.
title: ¿Cuál es la variación de datos esperada entre Analytics y A4T?
feature: Analytics for Target (A4T)
exl-id: 9e63f309-8ec1-4ed5-a1f9-6c3098a7b8f6
source-git-commit: 4abd24f63dd65e65a1d8b07647630eeb640e7a1d
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 46%

---

# Variaciones de datos previstas entre Adobes [!DNL Target] y Adobe Analytics al usar y no usar A4T

Información sobre variaciones de datos previstas entre [!DNL Target] y Adobe [!DNL Analytics] al *usar* y *no* usar Analytics como Fuente de informes (A4T). A4T reduce considerablemente la variación de datos.

## Variaciones de datos previstas al no usar A4T {#expected-using-a4t}

Con A4T, la creación de informes con Analytics y con Target usa datos de Analytics exclusivamente, por lo que no hay variación entre las soluciones en los informes de actividad de Target. En algunas circunstancias, sin embargo, los clientes comparan los datos de Target con los datos de Analytics fuera del ámbito de la integración con A4T y, de este modo, experimentan los problemas de variación que se describen a continuación.

Estos son algunos escenarios en los que puede experimentar variaciones de datos esperadas:

* A4T permite que se produzca una visita de Target (parte superior de la página), pero no se produce ninguna visita de Analytics (final de página). Por ejemplo, supongamos que un visitante carga la página, pero cierra el explorador antes de activar la llamada de Analytics. En estos casos, A4T excluye la visita de Target de los datos. Si se permite que las visitas de Target (nuevamente, parte superior de la página) cuenten como visitas de Analytics en ausencia de una llamada real de Analytics, se crearán incoherencias con el conjunto de datos en Analytics (inflación de visitantes, etc.).

   Si se configura una prueba de redirección en Target para dividir el tráfico 50/50 (o 25/25/25/25, etc.), es posible que el comportamiento del usuario no se divida uniformemente. Si ve una división desigual, simplemente significa que un grupo de usuarios falló en la ejecución de una llamada de Analytics en la página de aterrizaje más que los demás grupos. Este error al ejecutar la llamada de Analytics para un grupo provocó que se excluyera la visita de Target para ese usuario, lo que crea uniformidad.

   Adobe espera abordar este problema en el futuro, a medida que los equipos de Adobe trabajen para A4T en Adobe Experience Platform. Los equipos de Adobe están determinando cómo gestionar estos diferentes eventos en diferentes momentos en la página.

## Variaciones de datos previstas al *no usar* A4T {#expected-not-using-a4t}

Es normal encontrar unas variaciones de entre el 15 y el 20%, incluso en conjuntos de datos similares. Los sistemas que realizan recuentos de manera distinta pueden arrojar unas variaciones de datos mucho mayores, de incluso entre el 35 y el 50%. A veces, las variaciones pueden ser aún más altas.

Aunque los datos reales pueden variar de forma muy considerable, las tendencias suelen ser coherentes. Siempre y cuando las diferencias y tendencias sean coherentes, los datos seguirán conservando su valor y utilidad. Si no lo son, puede ser indicativo de que hay algo mal configurado, en cuyo caso deberá ponerse en contacto con el representante de cuentas para obtener ayuda.

[!DNL Analytics] emplea un sistema basado en visitas y transacciones, mientras que usa métricas basadas en visitantes. [!DNL Target] Cada vez que un visitante abre una página, se cuenta como una visita en [!DNL Analytics], pero [!DNL Target] no cuenta la visita hasta que se cumplen las condiciones establecidas en la actividad.

Informes en [!DNL Target] mostrar rendimiento basado en el mbox de conversión seleccionado al definir la actividad. Sin embargo, estos datos de mbox de conversión no se envían a [!DNL Analytics], que tiene sus propias variables de conversión definidas por la variable [!DNL Analytics] implementación de etiquetado. Si se esperan datos idénticos (por ejemplo, si el pedido de un minorista confirma que la página contiene tanto un mbox de conversión como un archivo [!DNL Analytics] purchase (evento de compra), los datos pueden variar debido a la colocación de estas etiquetas. En general, las tendencias en los informes de los dos productos son similares.

Las variaciones de datos previstas pueden estar originadas por variaciones de índole tanto técnica como empresarial.

### Ejemplos de variaciones técnicas  {#section_C3B50ED2E2F9416FAC91437CF1A87369}

A continuación se indican las situaciones que pueden desembocar en variaciones de datos debido a diferencias técnicas:

* [!DNL Target]Los visitantes de deben permitir las cookies y JavaScript
* Las cookies de origen y de terceros se procesan de modo distinto, con lo cual los datos procedentes de ambos tipos de cookies no coinciden
* Ubicación relativa de las etiquetas en las páginas y la “fuga” provocada por los visitantes que abandonan la página antes de que se cargue completamente
* Consideraciones de zona horaria
* Diferencias en las que se pueden contar dispositivos

### Ejemplos de variaciones empresariales.  {#section_2E1EB5E15BB64A1A80E4CDB1A5062AEE}

A continuación se indican las situaciones que pueden desembocar en variaciones de datos debido a diferencias empresariales:

* Diferencias entre las métricas de visitante y visita
* Centrarse en las actividades excluye a algunos visitantes.
* Un solo mbox en varias páginas, contando los visitantes en cada una de esas páginas
* Las prioridades de actividad pueden incluir algunos visitantes y excluir otros en una página
* Los visitantes que se hayan convertido una vez podrán volver a contarse cuando vuelvan a entrar en la actividad
* [!DNL Analytics] cuenta todas las conversiones de todas las visitas y visitantes, mientras que [!DNL Target] cuenta las conversiones de las visitas y visitantes que se incluyen en la actividad.
