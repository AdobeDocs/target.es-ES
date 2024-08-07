---
keywords: resolución de problemas;discrepancias entre métricas;preguntas más frecuentes;informes;nuevo visitante;nuevos visitantes;visitante que regresa;visitantes que regresan;visita de retorno;nueva visita
description: Explore una lista de preguntas frecuentes y sus respuestas acerca de los informes de Adobe [!DNL Target] y.
title: ¿Dónde puedo encontrar respuestas a preguntas acerca de la creación de informes de  [!DNL Target] ?
feature: Reports
exl-id: 1a345a67-5050-4bd3-858d-99731d2c1dd3
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '1367'
ht-degree: 20%

---

# Preguntas más frecuentes sobre la creación de informes

Lista de las preguntas más frecuentes sobre los informes en [!DNL Adobe Target].

## ¿Cómo se cuentan las métricas Nuevos visitantes y Visitantes que regresan? {#methodology}

La primera visita de un visitante nuevo dura mientras el visitante esté activo en el sitio.
Si el usuario está inactivo durante 30 minutos o más, la sesión se restablece. Restablecer la sesión significa que este visitante se convierte en un visitante de retorno en la siguiente visita o que vuelve a estar activo después de 30 minutos de inactividad.
Si el visitante se desplaza por el sitio cada 29 minutos durante un día completo, se cuenta como un visitante nuevo durante todo el día. La sesión nunca se restableció porque el visitante nunca superó el umbral de 30 minutos.

La siguiente información explica con más detalle cómo se cuentan los nuevos visitantes y los visitantes que regresan. También se incluyen ejemplos que explican por qué la suma de estos dos segmentos no siempre suma el número total de visitantes.

### Visitantes nuevos

Los visitantes se incluyen en el segmento Nuevos visitantes si se cumple una de las siguientes condiciones:

* Es la primera vez que el visitante visita el sitio.
* Es la primera vez que el visitante visita el sitio desde que se borraron las cookies.
* Es la primera vez que el visitante visita el sitio desde que [expiró el perfil del visitante](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md).

### Visitantes que regresan

Los visitantes se incluyen en el segmento Visitante que regresa si el usuario ha visitado anteriormente el sitio, si lo ha abandonado durante un mínimo de 30 minutos y si ha vuelto con las mismas cookies. Siempre que un visitante regrese antes de que finalice la vida útil del perfil, este se considerará como visitante que regresa.

Supongamos que la duración del perfil está establecida en 14 días (valor predeterminado). Los visitantes se incluyen en el segmento Visitantes que regresan si se cumplen las siguientes condiciones:

* Un visitante visita el sitio por primera vez y se registra como un visitante nuevo.
* El visitante abandona el sitio, pero regresa seis días después.

Dado que la duración del perfil se establece en 14 días, este visitante se incluye en el segmento Visitantes que repiten. Si el visitante ha eliminado las cookies en ese periodo de seis días, se incluye en el segmento Nuevos visitantes.

### Ejemplos que explican discrepancias entre recuentos de métricas

**Ejemplo 1**: Si estos dos segmentos se aplican a una actividad, los segmentos Nuevos visitantes y Visitantes que regresan no siempre suman el número total de visitantes.

Consideremos el siguiente ejemplo, teniendo en cuenta las condiciones mencionadas anteriormente para Visitantes nuevos y Visitantes que regresan:

* Un visitante visita el sitio por primera vez y se cuenta como un visitante nuevo.
* El visitante regresa al sitio después de que se cumplan las condiciones para los visitantes que regresan y se cuenta como visitante que regresa.

Este visitante se cuenta como un visitante único en el recuento total de visitantes de la actividad, aunque se cuenta en los segmentos Visitantes nuevos y Visitantes que regresan.

**Ejemplo 2**: las discrepancias entre los recuentos de Visitantes nuevos y Visitantes que regresan también dependen de cómo configure las [métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md) de la actividad.

Por ejemplo:

Varios visitantes nuevos visitan el sitio y cumplen los requisitos para una actividad. Estos nuevos visitantes se contabilizan en el segmento Nuevos visitantes. Todos estos visitantes también registraron una visita a esa actividad.

Algunos visitantes accedieron a la métrica de conversión, que se configuró como &quot;Aumentar recuento y mantener al usuario en la actividad&quot;. Supongamos que algunos de estos usuarios acceden a la métrica de conversión varias veces y que la métrica de conversión no aumenta. Sin embargo, teniendo en cuenta esa configuración, algunos usuarios pueden acceder a la métrica de conversión y luego navegar de nuevo a la página de inicio, calificando para la actividad de nuevo para registrar una nueva visita.

## ¿Por qué mis informes de [!UICONTROL Experience Targeting] (XT) contienen métricas para las experiencias de control?

Las actividades XT siempre deben tener una experiencia de control. Si utiliza una actividad XT de manera similar a una actividad [!UICONTROL A/B Test], que es un escenario bastante común, los datos de experiencia de control le serán útiles. Puede ignorar los datos de experiencia de control si no los considera útiles en sus informes.

## ¿Por qué el número de visitas es menor en [!DNL Target] que en otras [!DNL Adobe Experience Cloud] soluciones? {#section_7E626FDB417E41B8B58BBF30FB207409}

Los números de las métricas que registra [!DNL Target], por ejemplo las visitas, siempre son inferiores a los números recogidos en otras soluciones de [!DNL Experience Cloud] por varios motivos:

* [!DNL Target] solo cuenta las visitas de las personas que cumplen los requisitos de la actividad. Otras soluciones cuentan las visitas de las personas que muestran la página sea cual sea la actividad que los trajo a la página.
* Pueden darse casos en que distintas actividades compitan por la misma ubicación (que se excluyan mutuamente). Como resultado, los visitantes ven contenido distinto en una página web, lo cual afecta a los números de las métricas que [!DNL Target] recaba.

## ¿Por qué no hay datos disponibles en el informe de mi actividad? {#section_E4722F6445884130951DF79981C8289B}

Si el contenido de una actividad se entregó correctamente a los visitantes, pero el informe no contiene datos, es posible que aparezca el siguiente mensaje de error: &quot;No hay datos disponibles para la configuración de informe seleccionada&quot;.

Los datos pueden no aparecer en los informes de actividad por varios motivos:

* No ha seleccionado el entorno correcto en la configuración del informe
* No tiene ningún tráfico asignado a la experiencia de control

### No ha seleccionado el entorno correcto en la configuración del informe:

Si el contenido de una actividad se entregó correctamente a los usuarios, pero el informe no contiene datos, compruebe si el entorno ([grupo de hosts](/help/main/administrating-target/hosts.md)) correcto está seleccionado en la configuración del informe.

Para cambiar el entorno en el informe de una actividad:

1. Haga clic en **[!UICONTROL Activities]**, haga clic en la actividad que desee en la lista y, a continuación, haga clic en la ficha **[!UICONTROL Reports]**.
1. Haga clic en el icono del engranaje para definir la configuración del informe.

   ![Cuadro de diálogo Configuración A/B](/help/main/c-reports/c-report-settings/assets/ab_settings_dialog.png)

1. En la lista desplegable **[!UICONTROL Environment]**, seleccione **[!UICONTROL Production]**.

   Puede que no haya datos de informe disponibles si ha seleccionado un entorno de desarrollo.

1. Haga clic en **[!UICONTROL Save]**.

Para obtener más información sobre los entornos, consulte [Hosts](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).

### No tiene ningún tráfico asignado a la experiencia de control

Si el contenido de una actividad se entregó correctamente a los usuarios, pero el informe no contiene datos, asegúrese de utilizar una experiencia con tráfico como experiencia de control.

1. Haga clic en **[!UICONTROL Activities]**, haga clic en la actividad que desee en la lista y, a continuación, haga clic en la ficha **[!UICONTROL Reports]**.
1. Haga clic en el icono del engranaje para definir la configuración del informe.

1. En la lista desplegable **[!UICONTROL Control]**, seleccione una experiencia que reciba tráfico.

1. Haga clic en **[!UICONTROL Save]**.

>[!NOTE]
>
>Para obtener más información sobre cómo actualizar una actividad [!UICONTROL Automated Personalization] (AP) y cambiar la experiencia de control a una experiencia que recibe tráfico, consulte [Seleccionar el control de la actividad de Automated Personalization o de Segmentación automática](/help/main/c-activities/t-automated-personalization/experience-as-control.md).


## ¿Por qué la división del tráfico entre mis experiencias es desigual en mi actividad A/B o MVT? {#uneven}

Por ejemplo, he establecido la división de tráfico en 50/50 o 25/25/25/25, pero veo una distribución muy diferente entre las experiencias en los informes. Hay varias razones explicables para recuentos de visitantes desiguales en los informes de [!DNL Target]:

* Cuando se inicia por primera vez una actividad [!DNL Target], la distribución del tráfico puede ser desigual debido a la arquitectura de nodos perimetrales que [!DNL Target] utiliza para optimizar la entrega de experiencias. La práctica recomendada es dar a una actividad un poco de tiempo para recopilar más datos y la distribución se normalizará. Para obtener más información sobre la arquitectura de [!DNL Adobe Target] y los nodos de Edge, consulte [Funcionamiento de Adobe Target](/help/main/c-intro/how-target-works.md).
* Si se encuentra en [!DNL Target] o [!DNL Analytics] y usa la métrica **[!UICONTROL Visits]**, recuerde que [!DNL Target] es un sistema basado en visitantes y que la distribución del tráfico para una prueba A/B o MVT se asigna en el nivel de visitante. Por lo tanto, si examina los resultados de la actividad con la métrica **[!UICONTROL Visits]**, la distribución del tráfico podría aparecer desigual porque algunos visitantes podrían tener varias visitas. Visitantes es la métrica de normalización estándar al evaluar el rendimiento de la actividad.
* La práctica recomendada para las pruebas A/B y MVT es mantener las divisiones de tráfico igualadas. Cambiar la distribución del tráfico entre experiencias (por ejemplo, de 90/10 a 50/50) durante una prueba puede generar visitantes desiguales entre experiencias. Es posible que la experiencia de menor tráfico nunca &quot;se ponga al día&quot;.
* Si está siguiendo las prácticas recomendadas anteriores y la división del tráfico no se normaliza con el tiempo, debe comprobar lo siguiente:

   * ¿Está utilizando la biblioteca at.js más reciente? Para obtener más información sobre la versión actual y las notas de la versión asociadas, consulte [Detalles de la versión de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank}.

   * ¿Es una prueba de redirección? La activación incorrecta de etiquetas en la página puede provocar divisiones de tráfico desiguales, especialmente cuando se usa [!DNL Analytics] como origen de datos para una actividad [!DNL Target]. Para obtener más información sobre cómo solucionar la distribución desigual del tráfico en una actividad de redireccionamiento con Analytics for Target (A4T), consulte [Ofertas de redireccionamiento: preguntas más frecuentes sobre A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md).
