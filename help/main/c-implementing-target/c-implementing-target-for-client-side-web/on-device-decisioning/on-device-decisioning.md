---
keywords: implementación;biblioteca javascript;js;atjs;toma de decisiones en el dispositivo;en la toma de decisiones del dispositivo;at.js;en el dispositivo;en el dispositivo
description: Aprenda a tomar decisiones en el dispositivo con la biblioteca at.js
title: ¿Cómo funciona la toma de decisiones en el dispositivo con la biblioteca JavaScript at.js?
feature: at.js
role: Developer
exl-id: 5ad6032b-9865-4c80-8800-705673657286
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '3552'
ht-degree: 18%

---

# Toma de decisiones en el dispositivo para at.js

A partir de la versión 2.5.0, at.js ofrece la toma de decisiones en el dispositivo. La toma de decisiones en el dispositivo le permite almacenar en caché su [Prueba A/B](/help/main/c-activities/t-test-ab/test-ab.md) y [Segmentación de experiencias](/help/main/c-activities/t-experience-target/experience-target.md) (XT) actividades en el explorador para realizar decisiones en memoria sin bloquear una solicitud de red al [!DNL Adobe Target] Red perimetral.

[!DNL Target] también ofrece la flexibilidad de proporcionar la experiencia más relevante y actualizada a partir de sus actividades de experimentación y personalización impulsada por el aprendizaje automático (basado en ML) a través de una llamada al servidor en vivo. En otras palabras, cuando el rendimiento es más importante, puede elegir utilizar la toma de decisiones en el dispositivo. Sin embargo, cuando se necesita la experiencia más relevante, actualizada y basada en ML, se puede realizar una llamada al servidor.

## ¿Cuáles son las ventajas de la toma de decisiones en dispositivos?

Las ventajas de la toma de decisiones en dispositivos incluyen:

* **Ofrezca decisiones y experiencias increíblemente rápidas.** La creación de bloques y la toma de decisiones se realizan en la memoria y en el navegador para evitar el bloqueo de solicitudes de red.
* **Mejore el rendimiento de las aplicaciones.** Ejecute experimentos y ofrezca personalización a sus clientes y usuarios sin poner en peligro las experiencias del usuario final.
* **Mejore la puntuación de calidad del sitio de Google.** Con la toma de decisiones en la memoria, mejore la puntuación de calidad del sitio de Google de su negocio en línea para que los consumidores puedan descubrirla más.
* **Obtenga información sobre análisis en tiempo real.** Obtenga información sobre el rendimiento de su actividad en tiempo real mediante [Analytics para Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) Informes (A4T). A4T le permite girar su estrategia en momentos críticos.

## Funciones compatibles

El SDK de Adobe Target JS ofrece a los clientes la flexibilidad de elegir entre rendimiento y actualización de los datos para tomar decisiones. En otras palabras, si el envío del contenido personalizado más relevante y atractivo a través del aprendizaje automático es lo más importante para usted, se debe realizar una llamada al servidor en directo. Pero cuando el rendimiento es más crítico, se debe tomar una decisión en el dispositivo y en la memoria. Para que funcione la toma de decisiones en el dispositivo, consulte la lista de funciones compatibles:

* Tipos de actividades. 
* Segmentación de audiencia
* Método de asignación

Para obtener más información, consulte [Funciones compatibles con la toma de decisiones en dispositivos](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/supported-features/).

## ¿Cómo funciona la toma de decisiones en el dispositivo?

Cuando implementa e inicializa at.js con la toma de decisiones en el dispositivo habilitada, una [artículo de regla](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/rule-artifact/){target=_blank} que incluye la toma de decisiones en el dispositivo para actividades A/B y XT, audiencias y recursos, se descarga de la CDN de Akamai más cercana a su visitante y se almacena en caché localmente en el explorador del visitante. Cuando se realiza una solicitud desde at.js para recuperar una experiencia, la decisión sobre qué experiencia se debe devolver se toma en memoria, según los metadatos codificados en el artefacto de regla en caché.

## Método de decisión

Con la toma de decisiones en el dispositivo, [!DNL Target] introduce una nueva configuración denominada [!UICONTROL Método de decisión]. La variable [!UICONTROL Método de decisión] la configuración dicta cómo at.js ofrece sus experiencias. [!UICONTROL Método de decisión] tiene tres valores:

* [!UICONTROL Solo del lado del servidor]
* [!UICONTROL Solo en el dispositivo]
* [!UICONTROL Híbrido]

### Solo del lado del servidor

[!UICONTROL Solo del lado del servidor] es el método de toma de decisiones predeterminado que se establece por defecto cuando at.js 2.5.0+ se implementa y despliega en las propiedades web.

Usar [!UICONTROL solo del lado del servidor] como configuración predeterminada significa que todas las decisiones se toman en la red perimetral de [!DNL Target], lo que implica una llamada al servidor de bloqueo. Este método puede introducir la latencia incremental, pero también ofrece beneficios importantes, como la posibilidad de aplicar las capacidades de aprendizaje automático de Target, que incluyen actividades de [Recommendations](/help/main/c-recommendations/recommendations.md), [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) y [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

Además, la mejora de sus experiencias personalizadas mediante el uso del perfil de usuario de Target, que se mantiene en todas las sesiones y canales, puede proporcionar potentes resultados para su empresa.

Por último, [!UICONTROL solo del lado del servidor] permite utilizar Adobe Experience Cloud y ajustar las audiencias a las que se puede dirigir mediante segmentos de Audience Manager y Adobe Analytics.

El diagrama siguiente ilustra la interacción entre su visitante, el explorador, at.js 2.5.0+ y la red Adobe Target Edge. Este diagrama de flujo captura los visitantes nuevos y los visitantes que regresan.

![Diagrama de flujo solo del lado del servidor](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/server-side-only.png)

La siguiente lista corresponde a los números del diagrama:

| Paso   | Descripción |
| --- | --- |
| 1 | La variable [!DNL Experience Cloud Visitor ID] se recupera del [Servicio de identidad de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en). |
| 2 | La biblioteca de at.js carga de forma sincronizada y oculta el cuerpo del documento.<br>   La biblioteca at.js también se puede cargar de forma asíncrona con un fragmento de ocultamiento previo opcional implementado en la página. |
| 3 | La biblioteca at.js oculta el cuerpo para evitar parpadeos. |
| 4 | Se realiza una solicitud de carga de página que incluye todos los parámetros configurados, como (ECID, ID de cliente, parámetros personalizados, perfil de usuario, etc.). |
| 5 | Se ejecutan los scripts de perfiles y se incluyen en el Almacenamiento de perfiles.<br>El Almacenamiento de perfiles solicita audiencias de la Biblioteca de audiencias que cumplan los requisitos (por ejemplo, audiencias compartidas de [!DNL Adobe Analytics], [!DNL Adobe Audience Manager], etc.).<br>Se envían los atributos del cliente al Almacenamiento de perfiles en un procesamiento de lotes. |
| 6 | El Almacenamiento de perfiles se utiliza para la calificación de audiencias y la creación de contenedores para filtrar actividades. |
| 7 | El contenido resultante se selecciona una vez que la experiencia se determina desde el lanzamiento [!DNL Target] actividades. |
| 8 | La biblioteca at.js oculta los elementos correspondientes de la página que están asociados a la experiencia que se debe representar. |
| 9 | La biblioteca at.js muestra el cuerpo para que el resto de la página se pueda cargar para que el visitante la vea. |
| 10 | La biblioteca at.js manipula el DOM para representar la experiencia desde la red perimetral de Target. |
| 11 | La experiencia se procesa para el visitante. |
| 12 | Se carga toda la página web. |
| 13 | Se envían los datos de [!DNL Analytics] a los servidores de recopilación de datos. |
| 14 | Se comparan los datos de destino con [!DNL Analytics] Los datos a través del SDID y se procesan en la variable [!DNL Analytics] almacenamiento de informes. Por lo tanto, los datos de [!DNL Analytics] se pueden visualizar tanto en [!DNL Analytics] como en [!DNL Target] mediante los informes de [!UICONTROL Analytics for Target] (A4T). |

### Solo en el dispositivo

[!UICONTROL Solo en el dispositivo] es el método de toma de decisiones que debe configurarse en at.js 2.5.0+ cuando las decisiones en el dispositivo deben utilizarse solo en sus páginas web.

La toma de decisiones en el dispositivo puede ofrecer sus experiencias y actividades de personalización a una velocidad asombrosa, ya que las decisiones se toman a partir de un artefacto de reglas en caché que contiene todas las actividades que cumplen los requisitos para la toma de decisiones en el dispositivo.

Para obtener más información sobre las actividades que cumplen los requisitos para la toma de decisiones en el dispositivo, consulte [Funciones compatibles con la toma de decisiones en dispositivos](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/supported-features/).

Este método de toma de decisiones solo debe usarse si el rendimiento es muy crítico en todas las páginas que requieren decisiones de [!DNL Target]. Además, tenga en cuenta que, cuando se selecciona este método de toma de decisiones, las actividades de [!DNL Target] que no cumplen los requisitos para la toma de decisiones en el dispositivo no se entregarán ni ejecutarán. La biblioteca at.js 2.5.0+ está configurada para buscar solo el artefacto de reglas en caché para tomar decisiones.

El diagrama siguiente ilustra la interacción entre su visitante, el explorador, at.js 2.5.0+ y la CDN de Akamai. La CDN de Akamai almacena en caché el artefacto de reglas para la primera visita del visitante. Para la primera visita a la página de un visitante nuevo, el artefacto de reglas JSON debe descargarse de la CDN de Akamai para almacenarse en caché localmente en el explorador del visitante. Una vez descargado el artefacto de reglas JSON, la decisión se toma inmediatamente sin bloquear la llamada de red. El diagrama de flujo siguiente captura los visitantes nuevos.

![Diagrama de flujo solo en el dispositivo](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-only.png)

La siguiente lista corresponde a los números del diagrama:

>[!NOTE]
>
>[!DNL Adobe Target] Los servidores de administración califican todas las actividades que cumplen los requisitos para la toma de decisiones en el dispositivo, generan el artefacto de reglas JSON y lo propagan a la CDN de Akamai. Las actividades se supervisan continuamente en busca de actualizaciones para generar un nuevo artefacto de reglas JSON que se propagará a la CDN de Akamai.

| Paso   | Descripción |
| --- | --- |
| 1 | La variable [!DNL Experience Cloud Visitor ID] se recupera del [Servicio de identidad de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | La biblioteca de at.js carga de forma sincronizada y oculta el cuerpo del documento.<br>La biblioteca at.js también se puede cargar de forma asíncrona con un fragmento de ocultamiento previo opcional implementado en la página. |
| 3 | La biblioteca at.js oculta el cuerpo para evitar parpadeos. |
| 4 | La biblioteca at.js realiza una solicitud para recuperar el artefacto de regla JSON de la CDN de Akamai más cercana al visitante. |
| 5 | La CDN de Akamai responde con el artefacto de regla JSON. |
| 6 | El artefacto de regla JSON se almacena en caché localmente en el explorador del visitante. |
| 7 | La biblioteca at.js interpreta el artefacto de regla JSON y ejecuta la decisión de recuperar la experiencia y oculta los elementos probados. |
| 8 | La biblioteca at.js muestra el cuerpo para que el resto de la página se pueda cargar para que el visitante la vea. |
| 9 | La biblioteca at.js manipula el DOM para procesar la experiencia desde el artefacto de regla JSON en caché. |
| 10 | La experiencia se procesa para el visitante. |
| 11 | Se carga toda la página web. |
| 12 | Se envían los datos de [!DNL Analytics] a los servidores de recopilación de datos. Se comparan los datos de destino con [!DNL Analytics] Los datos a través del SDID y se procesan en la variable [!DNL Analytics] almacenamiento de informes. [!DNL Analytics][!DNL Analytics]Por lo tanto, los datos de se pueden visualizar tanto en como en mediante los informes de Analytics for Target (A4T).[!DNL Target] |

El diagrama siguiente ilustra la interacción entre su visitante, el explorador, at.js 2.5.0+ y el artefacto de regla JSON almacenado en caché para la visita posterior o la visita recurrente a la página del visitante. Como el artefacto de reglas JSON ya está almacenado en caché y disponible en el explorador, la decisión se toma inmediatamente sin bloquear la llamada de red. Este diagrama de flujo captura los visitantes que regresan o la navegación de página subsiguientes.

![Diagrama de flujo solo en el dispositivo para navegación de página subsiguiente y visitas repetidas](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-only-subsequent.png)

La siguiente lista corresponde a los números del diagrama:

>[!NOTE]
>
>[!DNL Adobe Target] Los servidores de administración califican todas las actividades que cumplen los requisitos para la toma de decisiones en el dispositivo, generan el artefacto de reglas JSON y lo propagan a la CDN de Akamai. Las actividades se supervisan continuamente en busca de actualizaciones para generar un nuevo artefacto de reglas JSON que se propagará a la CDN de Akamai.

| Paso   | Descripción |
| --- | --- |
| 1 | La variable [!DNL Experience Cloud Visitor ID] se recupera del [Servicio de identidad de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | La biblioteca de at.js carga de forma sincronizada y oculta el cuerpo del documento.<br>La biblioteca at.js también se puede cargar de forma asíncrona con un fragmento de ocultamiento previo opcional implementado en la página. |
| 3 | La biblioteca at.js oculta el cuerpo para evitar parpadeos. |
| 4 | La biblioteca at.js interpreta el artefacto de regla JSON y ejecuta la decisión en la memoria para recuperar la experiencia. |
| 5 | Los elementos probados están ocultos. |
| 6 | La biblioteca at.js muestra el cuerpo para que el resto de la página se pueda cargar para que el visitante la vea. |
| 7 | La biblioteca at.js manipula el DOM para procesar la experiencia desde el artefacto de regla JSON en caché. |
| 8 | La experiencia se procesa para el visitante. |
| 9 | Se carga toda la página web. |
| 10 | Se envían los datos de [!DNL Analytics] a los servidores de recopilación de datos. Se comparan los datos de destino con [!DNL Analytics] Los datos a través del SDID y se procesan en la variable [!DNL Analytics] almacenamiento de informes. Por lo tanto, los datos de [!DNL Analytics] se pueden visualizar tanto en [!DNL Analytics] como en [!DNL Target] mediante los informes de [!UICONTROL Analytics for Target] (A4T). |

### Híbrido

[!UICONTROL Híbrido] es el método de toma de decisiones que debe establecerse en at.js 2.5.0+ cuando se deben ejecutar tanto la toma de decisiones en el dispositivo como las actividades que requieren una llamada de red a la red de Adobe Target Edge.

Cuando administra actividades de toma de decisiones en el dispositivo y actividades del lado del servidor, puede resultar un poco complicado y tedioso pensar en cómo implementar y aprovisionar [!DNL Target] en sus páginas. Con el método de toma de decisiones hibrido, [!DNL Target] sabe cuándo debe realizar una llamada al servidor a la red de Adobe Target Edge para actividades que requieren ejecución del lado del servidor y también cuándo ejecutar únicamente decisiones en el dispositivo.

El artefacto de reglas JSON incluye metadatos para informar a at.js de si un mbox tiene una actividad del lado del servidor en ejecución o una actividad de toma de decisiones en el dispositivo. Este método de toma de decisiones garantiza que las actividades que desea que se entreguen rápido se realicen mediante la toma de decisiones en el dispositivo y que, para las actividades que requieren una personalización basada en ML más potente, dichas actividades se realicen a través de la red de Adobe Target Edge.

El diagrama siguiente ilustra la interacción entre su visitante, el explorador, at.js 2.5.0+, la CDN de Akamai y la red perimetral de Adobe Target para un visitante nuevo que visita su página por primera vez. La conclusión de este diagrama es que el artefacto de reglas JSON se descarga asincrónicamente mientras las decisiones se toman a través de la red Adobe Target Edge.

Este enfoque garantiza que el tamaño del artefacto, que puede incluir muchas actividades, no influya negativamente en la latencia de la decisión. La descarga sincrónica de las reglas JSON y la posterior toma de la decisión también pueden tener efectos adversos para la latencia y pueden ser incoherentes. Por lo tanto, el método de toma de decisiones híbrido es una recomendación de práctica recomendada para realizar siempre una llamada del lado del servidor para la decisión de un nuevo visitante, y como el artefacto de reglas JSON se almacena en caché en paralelo. Para cualquier visita de página posterior y visitas de retorno, las decisiones se toman de la caché y en la memoria a través del artefacto de reglas JSON.

![Diagrama de flujo híbrido de un visitante nuevo](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/hybrid-first-time-visitor.png)

La siguiente lista corresponde a los números del diagrama:

>[!NOTE]
>
>[!DNL Adobe Target] Los servidores de administración califican todas las actividades que cumplen los requisitos para la toma de decisiones en el dispositivo, generan el artefacto de reglas JSON y lo propagan a la CDN de Akamai. Las actividades se supervisan continuamente en busca de actualizaciones para generar un nuevo artefacto de reglas JSON que se propagará a la CDN de Akamai.

| Paso   | Descripción |
| --- | --- |
| 1 | La variable [!DNL Experience Cloud Visitor ID] se recupera del [Servicio de identidad de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | La biblioteca de at.js carga de forma sincronizada y oculta el cuerpo del documento.<br>La biblioteca at.js también se puede cargar de forma asíncrona con un fragmento de ocultamiento previo opcional implementado en la página. |
| 3 | La biblioteca at.js oculta el cuerpo para evitar parpadeos. |
| 4 | Se realiza una solicitud de carga de página en la red perimetral de Adobe Target, que incluye todos los parámetros configurados como (ECID, ID de cliente, parámetros personalizados, perfil de usuario, etc.). |
| 5 | En paralelo, at.js realiza una solicitud para recuperar el artefacto de regla JSON de la CDN de Akamai más cercana al visitante. |
| 6 | (Adobe Target Edge Network) Los scripts de perfil se ejecutan y luego se alimentan en el Almacenamiento de perfiles. El Almacenamiento de perfiles solicita audiencias de la Biblioteca de audiencias que cumplan los requisitos (por ejemplo, audiencias compartidas de [!DNL Adobe Analytics], [!DNL Adobe Audience Manager], etc.). |
| 7 | La CDN de Akamai responde con el artefacto de regla JSON. |
| 8 | El Almacenamiento de perfiles se utiliza para la calificación de audiencias y la creación de contenedores para filtrar actividades. |
| 9 | El contenido resultante se selecciona una vez que la experiencia se determina desde el lanzamiento [!DNL Target] actividades. |
| 10 | La biblioteca at.js oculta los elementos correspondientes de la página que están asociados a la experiencia que se debe representar. |
| 11 | La biblioteca at.js muestra el cuerpo para que el resto de la página se pueda cargar para que el visitante la vea. |
| 12 | La biblioteca at.js manipula el DOM para representar la experiencia desde la red perimetral de Target. |
| 13 | La experiencia se procesa para el visitante. |
| 14 | Se carga toda la página web. |
| 15 | Se envían los datos de [!DNL Analytics] a los servidores de recopilación de datos. Se comparan los datos de destino con [!DNL Analytics] Los datos a través del SDID y se procesan en la variable [!DNL Analytics] almacenamiento de informes. Por lo tanto, los datos de [!DNL Analytics] se pueden visualizar tanto en [!DNL Analytics] como en [!DNL Target] mediante los informes de [!UICONTROL Analytics for Target] (A4T). |

El diagrama siguiente ilustra la interacción entre su visitante, el explorador, at.js 2.5.0+ y el artefacto de reglas JSON almacenadas en caché para una navegación de página posterior o una visita de retorno. En este diagrama, céntrese únicamente en el caso de uso que se haya tomado una decisión en el dispositivo para la siguiente navegación o visita de retorno de página. Tenga en cuenta que, según las actividades que estén activas para determinadas páginas, se puede realizar una llamada del lado del servidor para ejecutar decisiones del lado del servidor.

![Diagrama de flujo híbrido para la navegación de página subsiguiente y visitas repetidas](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/hybrid-subsequent.png)

La siguiente lista corresponde a los números del diagrama:

>[!NOTE]
>
>[!DNL Adobe Target] Los servidores de administración califican todas las actividades que cumplen los requisitos para la toma de decisiones en el dispositivo, generan el artefacto de reglas JSON y lo propagan a la CDN de Akamai. Las actividades se supervisan continuamente en busca de actualizaciones para generar un nuevo artefacto de reglas JSON que se propagará a la CDN de Akamai.

| Paso   | Descripción |
| --- | --- |
| 1 | La variable [!DNL Experience Cloud Visitor ID] se recupera del [Servicio de identidad de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | La biblioteca de at.js carga de forma sincronizada y oculta el cuerpo del documento.<br>La biblioteca at.js también se puede cargar de forma asíncrona con un fragmento de ocultamiento previo opcional implementado en la página. |
| 3 | La biblioteca at.js oculta el cuerpo para evitar parpadeos. |
| 4 | Se realiza una solicitud para recuperar una experiencia. |
| 5 | La biblioteca at.js confirma que el artefacto de regla JSON ya se ha almacenado en caché y ejecuta la decisión en la memoria de recuperar la experiencia. |
| 6 | Los elementos probados están ocultos. |
| 7 | La biblioteca at.js muestra el cuerpo para que el resto de la página se pueda cargar para que el visitante la vea. |
| 8 | La biblioteca at.js manipula el DOM para procesar la experiencia desde el artefacto de regla JSON en caché. |
| 9 | La experiencia se procesa para el visitante. |
| 10 | Se carga toda la página web. |
| 11 | Se envían los datos de [!DNL Analytics] a los servidores de recopilación de datos. Se comparan los datos de destino con [!DNL Analytics] Los datos a través del SDID y se procesan en la variable [!DNL Analytics] almacenamiento de informes. Por lo tanto, los datos de [!DNL Analytics] se pueden visualizar tanto en [!DNL Analytics] como en [!DNL Target] mediante los informes de [!UICONTROL Analytics for Target] (A4T). |

## ¿Cómo se habilita la toma de decisiones en el dispositivo?

La toma de decisiones en el dispositivo está disponible para todos los [!DNL Target] clientes que utilizan At.js 2.5.0 o posterior.

Para habilitar la toma de decisiones en el dispositivo:

>[!NOTE]
>
>Debe tener la variable [!UICONTROL Administrador] o [!UICONTROL Aprobador] [función de usuario](/help/main/administrating-target/c-user-management/user-management.md) para habilitar o deshabilitar la opción de decisiones en el dispositivo.

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Implementación]** > **[!UICONTROL Detalles de la cuenta]**.
1. En **[!UICONTROL Detalles de la cuenta]**, deslice la **[!UICONTROL Toma de decisiones en el dispositivo]** cambie a la posición &quot;activado&quot;.

   ![Alternativa de toma de decisiones en el dispositivo](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-toggle.png)

   La variable[!UICONTROL Incluya en el artefacto todas las actividades cualificadas para la toma de decisiones en el dispositivo]&quot; se muestra si activa la toma de decisiones en el dispositivo.
1. (Condicional) Deslice el conmutador a la posición &quot;Activado&quot; si desea que todas las actividades de Target activas que cumplen los requisitos para la toma de decisiones en el dispositivo se incluyan automáticamente en el artefacto.

   Si deja esta opción desactivada, debe volver a crear y activar cualquier actividad de toma de decisiones en el dispositivo para que se incluya en el artefacto de reglas generadas. En otras palabras, cualquier actividad en estado activo antes de activar el [!UICONTROL Toma de decisiones en el dispositivo] no se incluyen en el artefacto de reglas.

Después de habilitar la variable [!UICONTROL Toma de decisiones en el dispositivo] alternar, [!DNL Target] comienza a generar y propagar [artefactos de regla](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/rule-artifact/){target=_blank} para su cliente.

>[!IMPORTANT]
>
>Asegúrese de activar el conmutador antes de inicializar el SDK para Adobe Target para utilizar la toma de decisiones en el dispositivo. Los artefactos de regla primero deben generarse y propagarse a las CDN de Akamai para que funcione la toma de decisiones en el dispositivo. La propagación puede tardar entre cinco y diez minutos en generarse el primer artefacto de regla y propagarse a la CDN de Akamai.

## ¿Cómo configuro at.js 2.5.0+ para utilizar la toma de decisiones en el dispositivo?

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Implementación]** > **[!UICONTROL Detalles de la cuenta]**.
1. En **[!UICONTROL Métodos de implementación]** > **[!UICONTROL Método de implementación principal]**, haga clic en **[!UICONTROL Editar]** junto a la versión de at.js (debe ser at.js 2.5.0 o posterior).

   ![Editar la configuración del método de implementación principal](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/main-implementation-method.png)

   >[!IMPORTANT]
   >
   >Antes de cambiar esta configuración predeterminada, consulte con ClientCare para que no afecte a su implementación actual.

1. Seleccione el método de decisión que desee:

   * [!UICONTROL Solo del lado del servidor]
   * [!UICONTROL Solo en el dispositivo]
   * [!UICONTROL Híbrido]

   ![Editar el panel de configuración de at.js](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/global-settings.png)

### Configuración global

Puede configurar una [!UICONTROL Método de decisión] para todo [!DNL Target] decisiones. Los distintos métodos de decisión son [!UICONTROL Solo en el lado del servidor], [!UICONTROL Solo en el dispositivo]y [!UICONTROL Híbrido]. El método de toma de decisiones seleccionado en la interfaz de usuario de Target está configurado en `window.targetGlobalSettings` en el `decisioningMethod` campo . Obtenga más información sobre `decisioningMethod` en [targetGlobalSettings()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/).

```javascript
<head> 
    <script type="text/javascript">

        window.targetGlobalSettings = { 
            clientCode: "yourClientCodeHere", 
            imsOrgId: "imsOrgId@AdobeOrg", 
            decisioningMethod: "on-device"

        }; 
    </script>

    <script type="text/javascript" src="at.js"></script> 
</head>
```

### Configuración personalizada

Si configura la variable `decisioningMethod` en `window.targetGlobalSettings`, pero desea anular la variable `decisioningMethod` para cada decisión de Adobe Target según su caso de uso, puede realizar este procedimiento especificando `decisioningMethod` en at.js2.5.0+ [getOffers()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/)Llamada de {target=_blank}.

```javascript
adobe.target.getOffers({ 

  decisioningMethod:"on-device", 
  request: { 
    execute: { 
      mboxes: [ 
        { 
          index: 0, 
          name: "homepage" 
        } 
      ] 
    } 
 } 
});
```

>[!NOTE]
>
>Para utilizar &quot;en el dispositivo&quot; o &quot;híbrido&quot; como método de decisión en la llamada getOffers(), asegúrese de que la configuración global tenga `decisioningMethod` como &quot;en el dispositivo&quot; o &quot;híbrido&quot;. La biblioteca at.js 2.5.0 o posterior debe saber si desea descargar y almacenar en caché el artefacto de reglas JSON inmediatamente después de cargarse en la página. Si el método de toma de decisiones de la configuración global se establece en &quot;lado del servidor&quot; y el método de decisión &quot;en el dispositivo&quot; o &quot;híbrido&quot; se pasa a la llamada getOffers() , at.js 2.5.0+ no tendría el artefacto de regla JSON almacenado en caché para ejecutar sus decisiones en el dispositivo.

### TTL de caché de artefactos

[!DNL Target] representa las actividades que cumplen los requisitos para la toma de decisiones en el dispositivo como un artefacto que consta de metadatos, reglas y condiciones. Este artefacto se almacena en caché en la CDN de Akamai. Durante la primera visita del usuario, el explorador del usuario descarga y almacena en caché el artefacto que representa las actividades de toma de decisiones en el dispositivo.

En visitas posteriores al sitio, el explorador comprueba automáticamente si debe descargar una versión más reciente del artefacto. Esta comprobación añade latencia. El TTL de caché de artefactos define el número de minutos que no desea que el navegador compruebe si hay un artefacto actualizado desde la última descarga correcta. Cuanto más largo sea el lapso de tiempo, mejor será el rendimiento. Cuanto más corto sea el lapso de tiempo, mejor será la actualización de los datos, pero con el costo de una latencia añadida.

## ¿Cómo sé que una actividad es elegible para la toma de decisiones en el dispositivo?

Después de crear una actividad apta para la toma de decisiones en el dispositivo, una etiqueta que lee [!UICONTROL Elegibilidad para la toma de decisiones en dispositivos], está visible en el informe [!UICONTROL Información general] página.

![Etiqueta apta para la toma de decisiones en el dispositivo en la página Información general de la actividad.](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-eligible-label.png)

Esta etiqueta no significa que la actividad siempre se entregue mediante la toma de decisiones en el dispositivo. Solo cuando at.js 2.5.0+ esté configurado para utilizar la toma de decisiones en el dispositivo, se ejecutará esta actividad en el dispositivo. Si at.js 2.5.0+ no está configurado para usar en el dispositivo, esta actividad se enviará a través de una llamada al servidor realizada desde at.js.

Puede filtrar todas las actividades que sean aptas para la toma de decisiones en el dispositivo en la variable [!UICONTROL Actividades] a través de la variable [!UICONTROL Elegibilidad para la toma de decisiones en dispositivos] filtro.

![Filtro apto para la toma de decisiones en el dispositivo en la página Actividades .](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-filter.png)

>[!NOTE]
>
>Después de crear y activar una actividad apta para la toma de decisiones en el dispositivo, puede tardar entre cinco y diez minutos en incluirse en el artefacto de reglas que se genera y propaga a los puntos de presencia de la CDN de Akamai.

## Resumen de los pasos para garantizar que mis actividades de toma de decisiones en el dispositivo se entreguen a través de At.js 2.5.0+?

1. Acceda a la interfaz de usuario de Adobe Target y vaya a **[!UICONTROL Administración]** > **[!UICONTROL Implementación]** > **[!DNL Account Details]** para habilitar la variable **[!UICONTROL Toma de decisiones en el dispositivo]** alternar.
1. Active la variable **&quot;[!UICONTROL Incluya en el artefacto todas las actividades cualificadas para la toma de decisiones en el dispositivo]&quot;** alternar.

   La primera generación de artefactos de reglas JSON puede tardar hasta 10 minutos.

1. Cree y active un [tipo de actividad compatible con la toma de decisiones en el dispositivo](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/supported-features/)y compruebe que es apto para la toma de decisiones en el dispositivo.
1. Configure las variables **[!UICONTROL Método de decisión]** para **[!UICONTROL &quot;Híbrido&quot;]** o **[!UICONTROL &quot;Solo en el dispositivo&quot;]** a través de la interfaz de usuario de la configuración de at.js .
1. Descargue e implemente At.js 2.5.0+ en sus páginas.
