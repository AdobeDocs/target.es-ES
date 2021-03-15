---
keywords: solución de problemas;discrepancias en las métricas;preguntas más frecuentes;informes;nuevo visitante;nuevos visitantes;visitantes que regresan;visita de retorno;nueva visita
description: Explore una lista de las preguntas más frecuentes y las respuestas sobre los informes de Adobe Target.
title: ¿Dónde puedo encontrar respuestas a preguntas sobre los informes de Target?
feature: Informes
translation-type: tm+mt
source-git-commit: dd938125e2b75bb360d18f540d2638c6e6fd0d9f
workflow-type: tm+mt
source-wordcount: '1221'
ht-degree: 23%

---


# Preguntas más frecuentes sobre la creación de informes

Lista de las preguntas más frecuentes sobre los informes en [!DNL Adobe Target].

## ¿Cómo se cuentan las métricas Nuevos visitantes y Visitantes que regresan? {#methodology}

La primera visita de un nuevo visitante dura mientras el visitante esté activo en el sitio.
Si el usuario está inactivo durante 30 minutos o más, la sesión se restablece. Restablecer la sesión significa que el visitante vuelve a ser un visitante que regresa en la siguiente visita o vuelve a estar activo después de 30 minutos de inactividad.
Si el visitante se desplaza por el sitio cada 29 minutos durante un día completo, ese visitante se contabilizará como un visitante nuevo ese día entero. La sesión nunca se restableció porque el visitante nunca superó el umbral de 30 minutos.

La siguiente información explica con más detalle cómo se cuentan los nuevos visitantes y los visitantes que regresan. También se incluyen ejemplos que explican por qué la suma de estos dos segmentos no siempre suman el número de visitantes totales.

### Visitantes nuevos

Un visitante se incluye en el segmento Nuevos visitantes si se cumple una de las siguientes condiciones:

* Es la primera vez que el visitante visita el sitio.
* Es la primera vez que el visitante visita el sitio desde que se borraron las cookies.
* Es la primera vez que el visitante visita el sitio desde que caducó la duración del perfil del [visitante](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md).

### Visitantes que regresan

El visitante se incluye en el segmento Visitantes que regresan si el usuario ha visitado el sitio anteriormente, lo ha abandonado durante 30 minutos como mínimo y ha vuelto al sitio con las mismas cookies. Siempre y cuando un visitante regrese dentro de su duración de perfil, este visitante será un visitante reincidente.

Supongamos que la duración de su perfil se establece para 14 días (valor predeterminado). Un visitante se incluye en el segmento Visitantes que regresan si se cumplen las siguientes condiciones:

* Un visitante visita el sitio por primera vez y se registra como nuevo visitante.
* El visitante abandona el sitio, pero regresa seis días después.

Debido a que la duración del perfil se establece durante 14 días, este visitante se incluye en el segmento Visitantes que regresan . Si el visitante ha eliminado cookies dentro de ese período de seis días, ese visitante se incluye en el segmento Nuevos visitantes .

### Ejemplos que explican discrepancias entre recuentos de métricas

**Ejemplo 1**: Si estos dos segmentos se aplican a una actividad, el segmento Nuevos visitantes y el segmento Visitantes que regresan no siempre suman el número total de visitantes.

Consideremos el siguiente ejemplo, teniendo en cuenta las condiciones mencionadas anteriormente para los visitantes nuevos y los visitantes que regresan:

* Un visitante visita el sitio por primera vez y se cuenta como un visitante nuevo.
* El visitante regresa al sitio después de que se cumplan las condiciones para los visitantes que regresan y se cuente como un visitante que regresa.

Este visitante se cuenta como un solo visitante en el recuento de visitantes general de la actividad aunque se cuente tanto en los segmentos de Visitantes nuevos como de Visitantes que regresan .

**Ejemplo 2**: Las discrepancias entre los recuentos de Nuevos visitantes y Visitantes que regresan también dependen de cómo configure las métricas [ de ](/help/c-activities/r-success-metrics/success-metrics.md)éxito de la actividad.

Por ejemplo:

Varios visitantes nuevos visitan el sitio y cumplen los requisitos para una actividad. Estos nuevos visitantes se contabilizan en el segmento Nuevos visitantes . Todos estos visitantes también registraron una visita en esa actividad.

Algunos visitantes llegan a la métrica de conversión, que se configuró como &quot;Aumentar recuento y mantener al usuario en la actividad&quot;. Supongamos que algunos de estos usuarios llegan a la métrica de conversión varias veces, la métrica de conversión no aumenta. Sin embargo, dada esa configuración, algunos usuarios pueden acceder a la métrica de conversión y luego volver a la página principal, para volver a entrar en la actividad y registrar una nueva visita.

## ¿Por qué mis informes de [!UICONTROL Segmentación de experiencias] (XT) contienen métricas para las experiencias de control?

Las actividades XT siempre deben tener una experiencia de control. Si utiliza una actividad XT de manera similar a una actividad de [!UICONTROL prueba A/B], que es algo bastante común, los datos de experiencia de control le serán útiles. Puede ignorar los datos de experiencia de control si no los considera útiles en sus informes.

## ¿Por qué el número de visitas es menor en [!DNL Target] que en otras soluciones de [!DNL Adobe Experience Cloud]?{#section_7E626FDB417E41B8B58BBF30FB207409}

Los números de las métricas que recoge [!DNL Target] , como las visitas, siempre son inferiores a los números recogidos en otras soluciones [!DNL Experience Cloud] por varios motivos:

* [!DNL Target] solo cuenta las visitas de las personas que cumplen los requisitos de la actividad. Otras soluciones cuentan las visitas de las personas que muestran la página sea cual sea la actividad que los trajo a la página.
* Pueden darse casos en que distintas actividades compitan por la misma ubicación (que se excluyan mutuamente). Como resultado, los visitantes ven contenido distinto en una página web, lo cual afecta a los números de las métricas que [!DNL Target] recaba.

## ¿Por qué no hay datos disponibles en el informe de mi actividad?{#section_E4722F6445884130951DF79981C8289B}

Si el contenido de una actividad se entregó correctamente a los usuarios, pero el informe no contiene datos, compruebe si el entorno ([grupo de hosts](/help/administrating-target/hosts.md)) correcto está seleccionado en la configuración del informe.

Si tiene seleccionado un entorno de desarrollo, puede que vea el siguiente mensaje de error: “No hay datos disponibles para la configuración de informe seleccionada”.

Para cambiar el entorno en el informe de una actividad:

1. Haga clic en **[!UICONTROL Actividades]**, en la actividad que quiera de la lista y luego en la ficha **[!UICONTROL Informes.]**
1. Haga clic en el icono del engranaje para definir la configuración del informe.

   ![Cuadro de diálogo Configuración A/B](/help/c-reports/c-report-settings/assets/ab_settings_dialog.png)

   >[!NOTE]
   >
   >El icono del engranaje no está disponible para informes de [!UICONTROL Personalización automatizada] (AP).

1. En la lista desplegable **[!UICONTROL Entornos]**, seleccione **[!UICONTROL Producción]**.

   Puede que no haya datos de informe disponibles si ha seleccionado un entorno de desarrollo.

1. Haga clic en **[!UICONTROL Guardar]**.

Para obtener más información sobre los entornos, consulte [Hosts](/help/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).

## ¿Por qué la división del tráfico entre mis experiencias es desigual en mi actividad A/B o MVT? {#uneven}

Por ejemplo, configuro la división de tráfico en 50/50 o 25/25/25/25, pero veo una distribución muy diferente entre las experiencias en los informes. Hay varias razones explicables para los recuentos desiguales de visitantes en los informes [!DNL Target]:

* Cuando se inicia por primera vez una actividad [!DNL Target], la distribución del tráfico puede ser desigual debido a la arquitectura del nodo perimetral que [!DNL Target] utiliza para optimizar el envío de experiencias. La práctica recomendada es dar a una actividad tiempo para recopilar más datos y la distribución se normalizará. Para obtener más información sobre la arquitectura [!DNL Adobe Target] y los nodos de Edge, consulte [Cómo funciona Adobe Target](/help/c-intro/how-target-works.md).
* Si se encuentra en [!DNL Target] o [!DNL Analytics] y utiliza la métrica **[!UICONTROL Visitas]**, recuerde que [!DNL Target] es un sistema basado en visitantes y que la distribución del tráfico para una prueba A/B o MVT se asigna en el nivel del visitante. Por lo tanto, si examina los resultados de la actividad utilizando la métrica **[!UICONTROL Visitas]**, la distribución del tráfico puede parecer desigual porque algunos visitantes pueden tener varias visitas. Visitantes es la métrica estándar de normalización al evaluar el rendimiento de la actividad.
* La práctica recomendada para las pruebas A/B y MVT es mantener unidas las divisiones de tráfico. Cambiar la distribución del tráfico entre las experiencias (por ejemplo, del 10/90 al 50/50) durante una prueba puede provocar un número de visitantes desiguales entre las experiencias. Es posible que la experiencia con menos tráfico nunca se &quot;ponga al día&quot;.
* Si sigue las prácticas recomendadas anteriores y la división del tráfico no se normaliza con el tiempo, debe comprobar lo siguiente:

   * ¿Está utilizando la última biblioteca de at.js? Para obtener más información sobre la versión actual y las notas de la versión asociadas, consulte [Detalles de la versión de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

   * ¿Es una prueba de redireccionamiento? La sincronización incorrecta de etiquetas al activarse en la página puede provocar divisiones de tráfico desiguales, especialmente al utilizar [!DNL Analytics] como fuente de datos para una actividad [!DNL Target]. Para obtener más información sobre cómo solucionar la distribución desigual del tráfico en una actividad de redireccionamiento con Analytics for Target (A4T), consulte [Ofertas de redireccionamiento: preguntas más frecuentes sobre A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md).
