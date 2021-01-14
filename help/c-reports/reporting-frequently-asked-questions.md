---
keywords: troubleshooting;metric discrepancies;FAQ;reports;new visitor;new visitors;returning visitor;returning visitors;return visit;new visit
description: Lista de las preguntas frecuentes sobre los informes en Adobe Target.
title: Preguntas frecuentes sobre los informes de Adobe Target
feature: Reports
translation-type: tm+mt
source-git-commit: 7b86db4b45f93a3c6169caf81c2cd52236bb5a45
workflow-type: tm+mt
source-wordcount: '1110'
ht-degree: 31%

---


# Preguntas más frecuentes sobre la creación de informes{#reporting-faq}

Lista de las preguntas más frecuentes sobre los informes en [!DNL Target].

## ¿Cómo se cuentan las métricas Nuevos Visitantes y Visitantes que regresan?

La siguiente información explica cómo se cuentan los Visitantes nuevos y los Visitantes que regresan y proporciona ejemplos de por qué la suma de estos dos segmentos no siempre suman el número total de visitantes.

### Visitantes nuevos

Un visitante se incluye en el segmento Nuevos Visitantes si se cumple una de las siguientes condiciones:

* Es la primera vez que el visitante visita el sitio.
* Es la primera vez que el visitante visita el sitio desde que borró las cookies.
* Es la primera vez que el visitante visita el sitio desde que la duración del perfil [Visitante](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md) ha caducado.

### Visitantes que regresan

El visitante se incluye en el segmento Visitantes que regresan si el usuario ya ha visitado el sitio, lo ha abandonado durante al menos 30 minutos y lo ha vuelto a visitar con las mismas cookies. Siempre que un visitante regrese mientras dure el perfil, se considerará un visitante recurrente.

Supongamos que la duración del perfil está establecida para 14 días (el valor predeterminado). Un visitante se incluye en el segmento Visitantes que regresan si se cumplen las siguientes condiciones:

* Un visitante visita el sitio por primera vez y se registra como un nuevo Visitante.
* El visitante abandona el sitio, pero regresa seis días después.

Debido a que la duración del perfil está establecida para 14 días, este visitante se incluye en el segmento Visitantes que se devuelven. Tenga en cuenta que si el visitante ha eliminado las cookies dentro de ese período de seis días, ese visitante se incluirá en el segmento Nuevos Visitantes.

### Ejemplos que explican discrepancias entre recuentos de métricas

**Ejemplo 1**: Si estos dos segmentos se aplican a una actividad, el segmento Nuevos Visitantes y el segmento Visitantes que regresan no siempre suman el número total de visitantes.

Considere el siguiente ejemplo, teniendo en cuenta las condiciones mencionadas anteriormente para Nuevos Visitantes y Visitantes de retorno:

* Un visitante visita el sitio por primera vez y se cuenta como un nuevo Visitante.
* El visitante regresa al sitio después de que se cumplan las condiciones para los Visitantes de devolución y se cuenta como un Visitante de devolución.

Este visitante se cuenta como un solo visitante en el recuento de visitantes global de la actividad aunque se cuente en los segmentos Nuevos Visitantes y Visitantes que regresan.

**Ejemplo 2**: Las discrepancias entre los recuentos de nuevos Visitantes y los Visitantes que regresan también dependen de cómo configure las métricas [ de ](/help/c-activities/r-success-metrics/success-metrics.md)éxito de la actividad.

Por ejemplo:

Varios visitantes nuevos visitan el sitio y están cualificados para una actividad. Estos nuevos visitantes se contabilizan en el segmento Nuevos Visitantes. Todos estos visitantes también registraron una visita a esa actividad.

Algunos visitantes visitan la métrica de conversión, que se configuró como &quot;Aumentar recuento y mantener al usuario en Actividad&quot;. Supongamos que algunos de estos usuarios visitan la métrica de conversión varias veces, la métrica de conversión no aumenta. Sin embargo, dado que la configuración, algunos usuarios pueden llegar a la métrica de conversión y luego volver a la página de inicio, volviendo a entrar en la actividad para registrar una nueva visita.

## ¿Por qué mis informes de [!UICONTROL Segmentación de experiencias] (XT) contienen métricas para las experiencias de control?

Las actividades XT siempre deben tener una experiencia de control. Si utiliza una actividad XT de manera similar a una actividad de [!UICONTROL prueba A/B], que es algo bastante común, los datos de experiencia de control le serán útiles. Puede ignorar los datos de experiencia de control si no los considera útiles en sus informes.

## ¿Por qué el número de visitas es menor en [!DNL Target] que en otras soluciones de [!DNL Adobe Experience Cloud]?{#section_7E626FDB417E41B8B58BBF30FB207409}

Los números de las métricas que recoge [!DNL Target], como las visitas, siempre serán menores que los números recogidos en otras soluciones de [!DNL Experience Cloud] por varios motivos:

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

## ¿Por qué el tráfico se divide entre mis experiencias de forma desigual en mi actividad A/B o MVT? {#uneven}

Por ejemplo, configuré la división de tráfico en 50/50 o 25/25/25/25 pero veo una distribución muy diferente entre las experiencias en el sistema de informes. Hay una serie de razones explicables para el recuento desigual de visitantes en el sistema de informes [!DNL Target]:

* Cuando se inicia por primera vez una actividad [!DNL Target], la distribución del tráfico puede ser desigual debido a la arquitectura de nodos Edge que [!DNL Target] utiliza para optimizar el envío de experiencias. Lo mejor es dar a una actividad tiempo para recopilar datos adicionales y la distribución se normalizará. Para obtener más información sobre la arquitectura [!DNL Adobe Target] y los nodos de Edge, consulte [Cómo funciona Adobe Target](/help/c-intro/how-target-works.md).
* Si se encuentra en [!DNL Target] o [!DNL Analytics] y utiliza la métrica **[!UICONTROL Visitas]**, recuerde que [!DNL Target] es un sistema basado en visitantes y que la distribución del tráfico para una prueba A/B o MVT está asignada en el nivel de visitante. Por lo tanto, si examina los resultados de la actividad mediante la métrica **[!UICONTROL Visitas]**, la distribución del tráfico puede parecer desigual porque ciertos visitantes pueden tener varias visitas. Visitantes es la métrica estándar de normalización al evaluar el rendimiento de la actividad.
* La práctica recomendada para las pruebas A/B y MVT es mantener unidas las divisiones de tráfico. Cambiar la distribución del tráfico entre experiencias (por ejemplo, de 90/10 a 50/50) durante una prueba puede provocar visitantes desiguales entre las experiencias. Es posible que la experiencia de tráfico más baja nunca &quot;se ponga al día&quot;.
* Si sigue las prácticas recomendadas anteriores y la división del tráfico no se normaliza con el tiempo, debe comprobar lo siguiente:

   * ¿Está utilizando la biblioteca at.js más reciente? Para obtener más información sobre la versión actual y las notas de la versión asociadas, consulte [Detalles de la versión de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

   * ¿Es una prueba de redirección? El tiempo incorrecto de activación de etiquetas en la página puede provocar divisiones de tráfico desiguales, especialmente al utilizar [!DNL Analytics] como fuente de datos para una actividad [!DNL Target]. Para obtener más información sobre cómo solucionar la distribución desigual del tráfico en una actividad de redireccionamiento con Analytics para Destinatario (A4T), consulte [ofertas de redireccionamiento: Preguntas más frecuentes sobre A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md).
