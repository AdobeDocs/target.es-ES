---
keywords: páginas de sitio;páginas de sitio de destino;segmentación;página actual;página actual de destino;página anterior;página anterior de destino;página de destino;página de destino de destino;encabezado http
description: Obtenga información sobre cómo segmentar visitantes mediante [!DNL Adobe Target] que se encuentran en una página específica del sitio.
title: ¿Puedo segmentar visitantes según las páginas del sitio?
feature: Audiences
exl-id: 4c770b7b-775f-4483-aced-43f18a9a68c1
source-git-commit: 1383088bb2f6be0432e6f140400d8723048c8530
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 25%

---

# Páginas del sitio

Puede segmentar visitantes mediante [!DNL Adobe Target] que acceden a una página específica del sitio.

1. En la interfaz de [!DNL Target], haga clic en **[!UICONTROL Audiencias]** > **[!UICONTROL Crear audiencia]**.
1. Asigne un nombre a la audiencia y añada una descripción opcional.
1. Arrastrar y soltar **[!UICONTROL Páginas del sitio]** en el panel de audience builder.

   ![Audiencia de páginas del sitio](assets/target_site_pages.png)

1. Haga clic en **[!UICONTROL Seleccionar]** , seleccione una de las siguientes opciones y, a continuación, configure la regla como desee.

   Las opciones y los evaluadores disponibles en las siguientes listas desplegables de la regla varían según la opción que elija. La siguiente ilustración muestra las opciones disponibles si elige [!UICONTROL Página actual]:

   ![Página actual](assets/current-page.png)

   Las siguientes opciones están disponibles en la lista desplegable inicial cuando elige [!UICONTROL Seleccionar].

   * **[!UICONTROL Página actual]:** La página que está viendo el usuario.

      Las siguientes opciones están disponibles en la segunda lista desplegable si elige esta opción:

      * [!UICONTROL URL] (Para obtener más información acerca de cómo [!DNL Target] evalúa las direcciones URL, consulte [Preguntas frecuentes sobre objetivos y audiencias](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL Dominio]
      * [!UICONTROL Consulta]
      * [!UICONTROL Subdominio]
      * [!UICONTROL Dominio de nivel superior]
      * [!UICONTROL Ruta]
      * [!UICONTROL Fragmento almohadilla (#)]
   * **[!UICONTROL Página anterior]:** La página que vio el usuario antes de hacer clic en para acceder a la página actual. El usuario debe hacer clic desde la página anterior hasta la página actual para que se realice el seguimiento de la página. La página anterior no se rastrea si el usuario escribe una nueva dirección URL en el explorador. El contenido real de la página depende del diseño del sitio. Por ejemplo, si la página actual muestra información sobre un producto específico, la página anterior podría ser una página de categoría en la que el visitante seleccione el artículo específico. Por ejemplo, una página que muestra varias cámaras de un tipo determinado, o puede ser la página de inicio que lleva a la página final.

      Las siguientes opciones están disponibles en la segunda lista desplegable si elige esta opción:

      * [!UICONTROL URL] (Para obtener más información sobre cómo Target evalúa las direcciones URL, consulte [Preguntas frecuentes sobre objetivos y audiencias](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL Dominio]
      * [!UICONTROL Consulta]
      * [!UICONTROL Subdominio]
      * [!UICONTROL Dominio de nivel superior]
      * [!UICONTROL Ruta]
   * **Página de aterrizaje:** la página de aterrizaje es la primera página que ve el visitante al acceder al sitio. Por ejemplo, si el visitante hace clic en un vínculo de Google que le lleva a la página de categorías, entonces la página de categorías es la página de aterrizaje. Si el vínculo lleva a la página principal, entonces ésta es la página de aterrizaje. Se recuerda la página de aterrizaje durante la sesión del visitante. Puede segmentar mucho más en el sitio según la página de aterrizaje del visitante correspondiente a la sesión.

      Las siguientes opciones están disponibles en la segunda lista desplegable si elige esta opción:

      * [!UICONTROL URL] (Para obtener más información sobre cómo Target evalúa las direcciones URL, consulte [Preguntas frecuentes sobre objetivos y audiencias](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL Dominio]
      * [!UICONTROL Consulta]
      * [!UICONTROL Subdominio]
      * [!UICONTROL Dominio de nivel superior]
      * [!UICONTROL Ruta]
      * [!UICONTROL Fragmento almohadilla (#)]

      >[!NOTE]
      >
      >El objeto `landing.url` se restablece en un cambio de subdominio o sustitución directa de la dirección URL.

   * **[!UICONTROL Encabezado HTTP]:** Esta opción evalúa la información en el encabezado HTTP del [!DNL Target] solicitud. Por ejemplo, si el encabezado HTTP contiene información de idioma, puede crear una regla que contenga la variable `Accept-Language: es` condición para dirigirse a los visitantes que acceden a la página en español.

      Las siguientes opciones están disponibles en la segunda lista desplegable si elige esta opción:

      * [!UICONTROL Accept]
      * [!UICONTROL Accept-Charset]
      * [!UICONTROL Accept-Encoding]
      * [!UICONTROL Accept-Language]
      * [!UICONTROL Autorización]
      * [!UICONTROL Cache-Control]
      * [!UICONTROL Conexión]
      * [!UICONTROL Content-Length]
      * [!UICONTROL Content-MDS]
      * [!UICONTROL Content-Type]
      * [!UICONTROL Fecha]
      * [!UICONTROL Esperar]
      * [!UICONTROL De]
      * [!UICONTROL Host]
      * [!UICONTROL If-Match]
      * [!UICONTROL If-Modified-Since]
      * [!UICONTROL Si-Ninguno-Coincidencia]
      * [!UICONTROL Si-Rango]
      * [!UICONTROL If-Unmodified-Since]
      * [!UICONTROL Avances máx.]
      * [!UICONTROL Pragma]
      * [!UICONTROL Autorización de proxy]
      * [!UICONTROL Intervalo]
      * [!UICONTROL Referente]
      * [!UICONTROL TE]
      * [!UICONTROL Actualización]
      * [!UICONTROL User-Agent]
      * [!UICONTROL Mediante]
      * [!UICONTROL Advertencia]

   Si elige [!UICONTROL Página actual], [!UICONTROL Página anterior], o [!UICONTROL Página de aterrizaje], el [!UICONTROL Dominio] y [!UICONTROL Consulta] opciones están disponibles. Tenga en cuenta lo siguiente al elegir estas opciones:

   * **Dominio:** el dominio completo de la página. Al especificar un dominio, se recomienda utilizar “contains” (contiene). Por ejemplo, &quot;Dominio igual a facebook.com&quot; no acepta `m.facebook.com` o `www.facebook.com`. &quot;El dominio contiene facebook.com&quot; acepta cualquier variante de facebook.com.
   * **Consulta:** el contenido de la dirección URL que hay después del primer signo de interrogación (?).

      `foo.html?e0a72cb2a2c7`





1. (Opcional) Configure reglas adicionales para la audiencia.
1. Haga clic en **[!UICONTROL Finalizado]**.

También puede crear audiencias de página del sitio empleando su propio “parámetro de consulta definido por el usuario” o “encabezado definido por el usuario”.

Utilice un:

* Parámetro de consulta si la regla seleccionada por el usuario es [!UICONTROL Página actual], [!UICONTROL Página de aterrizaje], o [!UICONTROL Página anterior]
* Header si la regla seleccionada por el usuario es un encabezado HTTP

## Resolución de problemas {#ts}

* Para que las audiencias de página de aterrizaje funcionen correctamente, las solicitudes deben tener `mboxReferrer` conjunto de parámetros (para la API de envío, la variable `context.address.referringUrl` ) que la biblioteca JavaScript de at.js toma de la página utilizando `document.referrer` atributo. Esta `HTMLDocument` devuelve el URI de la página desde la que el usuario ha navegado. El valor de este atributo es una cadena vacía cuando el usuario navega directamente a la página (no a través de un vínculo, sino, por ejemplo, a través de un marcador).

   Si este comportamiento no coincide con sus necesidades, considere la posibilidad de realizar una de las siguientes acciones:

   * Aprobado [Parámetros de mbox](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/global-mbox/pass-parameters-to-global-mbox.html?lang=es){target=_blank} hasta [!DNL Target] para su uso con fines de segmentación.
   * Utilice un [Actividad de prueba A/B](/help/main/c-activities/t-test-ab/test-ab.md) en lugar de una actividad de página de aterrizaje. Las actividades de prueba A/B no cambian de experiencia para el mismo visitante.
   * Utilice un [perfil del visitante](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md) en su lugar.

* Cuando se utilizan evaluadores &quot;comienza/termina con&quot; en cadenas que contienen comas, estas cadenas se evalúan como una matriz de valores, en la que se evalúa cada valor separado por una coma. Por ejemplo, si tiene el valor de un encabezado: `Accept-Language: en,zh;q=0.9,en-IN;q=0.8,zh-CN;q=0.7` cumple los requisitos para condiciones como las siguientes:
   * empieza por zh,
   * empieza por en,
   * termina con 0,7,
   * termina con 0,8.

## Vídeo de formación: Creación de audiencias

Este vídeo contiene información sobre el uso de las categorías de audiencias.

* Crear audiencias
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)
