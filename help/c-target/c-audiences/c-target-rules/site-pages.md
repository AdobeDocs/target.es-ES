---
keywords: site pages;target site pages;targeting;current page;target current page;previous page;target previous page;landing page;target landing page;http header
description: Puede destinatario visitantes que se encuentren en una página específica del sitio.
title: Páginas del sitio en Adobe Target
feature: audiences
topic: Standard
uuid: 1cf9fa94-dbec-4719-9a0a-79c1eb91a233
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 43%

---


# Páginas del sitio{#site-pages}

Puede destinatario visitantes que se encuentren en una página específica del sitio.

1. En la interfaz de [!DNL Target], haga clic en **[!UICONTROL Audiencias]** > **[!UICONTROL Crear audiencia]**.
1. Ponga un nombre a la audiencia.
1. Haga clic en **[!UICONTROL Agregar regla]** > **[!UICONTROL Páginas de sitio]**.

   ![Audiencia de páginas del sitio](assets/target_site_pages.png)

1. Haga clic en la lista desplegable **[!UICONTROL Seleccionar]** , seleccione una de las siguientes opciones y, a continuación, configure la regla como desee.

   Las opciones y los evaluadores disponibles en listas desplegables posteriores de la regla varían según la opción que elija. En la siguiente ilustración se muestran las opciones disponibles al elegir Página actual:

   ![Página actual](/help/c-target/c-audiences/c-target-rules/assets/current-page.png)

   Las siguientes opciones están disponibles en la lista desplegable inicial cuando elige [!UICONTROL Seleccionar].

   * **Página actual:** Página en la que se encuentra el usuario.

      Las siguientes opciones están disponibles en la segunda lista desplegable si elige esta opción:

      * URL (para obtener más información sobre cómo evalúa Destinatario las direcciones URL, consulte Preguntas más frecuentes sobre [Destinatarios y audiencias](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)).
      * Dominio
      * Consulta
      * Subdominio
      * Dominio de nivel superior
      * Ruta
      * Fragmento almohadilla (#)
   * **Página anterior:** la página en la que el usuario estaba antes de hacer clic para acceder a la página actual. (Para que se realice un seguimiento de la página, el usuario tiene que hacer clic en la página anterior para acceder a la página actual. No se hace un seguimiento de la página anterior si el usuario escribe una nueva dirección URL en el navegador). El contenido real de la página depende del diseño del sitio. Por ejemplo, si la página actual muestra información acerca de un producto específico, la página anterior puede ser una página de categorías en la que el visitante seleccione el elemento específico (por ejemplo, una página que muestre varias cámaras de un determinado tipo) o puede tratarse de la página principal que conduzca a la página final.

      Las siguientes opciones están disponibles en la segunda lista desplegable si elige esta opción:

      * URL (para obtener más información sobre cómo evalúa Destinatario las direcciones URL, consulte Preguntas más frecuentes sobre [Destinatarios y audiencias](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)).
      * Dominio
      * Consulta
      * Subdominio
      * Dominio de nivel superior
      * Ruta
   * **Página de aterrizaje:** la página de aterrizaje es la primera página que ve el visitante al acceder al sitio. Por ejemplo, si el visitante hace clic en un vínculo de Google que le lleva a la página de categorías, entonces la página de categorías es la página de aterrizaje. Si el vínculo lleva a la página principal, entonces ésta es la página de aterrizaje. Se recuerda la página de aterrizaje durante la sesión del visitante. Puede segmentar mucho más en el sitio según la página de aterrizaje del visitante correspondiente a la sesión.

      Las siguientes opciones están disponibles en la segunda lista desplegable si elige esta opción:

      * URL (para obtener más información sobre cómo evalúa Destinatario las direcciones URL, consulte Preguntas más frecuentes sobre [Destinatarios y audiencias](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)).
      * Dominio
      * Consulta
      * Subdominio
      * Dominio de nivel superior
      * Ruta
      * Fragmento almohadilla (#)

      >[!NOTE]
      >
      >El objeto `landing.url` se restablece en un cambio de subdominio o sustitución directa de la dirección URL.

   * **Encabezado HTTP:** Esta opción evalúa la información en el encabezado HTTP de la solicitud de Destinatario. Por ejemplo, si el encabezado HTTP contiene información de idioma, puede crear una regla que contenga la `Accept-Language: es` condición de visitantes de destinatario que accedan a la página en español.

      Las siguientes opciones están disponibles en la segunda lista desplegable si elige esta opción:

      * Accept
      * Accept-Charset
      * Accept-Encoding
      * Accept-Language
      * Autorización
      * Cache-Control
      * Conexión
      * Content-Length
      * Content-MDS
      * Content-Type
      * Fecha
      * Expect
      * De
      * Host
      * Si-Coincidencia
      * If-Modified-Since
      * Si-Ninguno-Coincidencia
      * Si-Intervalo
      * If-Unmodified-Since
      * Max-Forwards
      * Pragma
      * Autorización de proxy
      * Intervalo
      * Referer
      * TE
      * Actualización
      * User-Agent
      * Via
      * Advertencia

   Si elige Página actual, Página anterior o [!UICONTROL Página de aterrizaje], las opciones [!UICONTROL Dominio] y [!UICONTROL Consulta] estarán disponibles. Tenga en cuenta lo siguiente al elegir estas opciones:

   * **Dominio:** el dominio completo de la página. Al especificar un dominio, se recomienda utilizar “contains” (contiene). Por ejemplo, “Domain equals facebook.com” (Dominio igual a facebook.com) no aceptará `m.facebook.com` ni `www.facebook.com`. “Domain contains facebook.com” (Dominio contiene facebook.com) aceptará cualquier variante de facebook.com.
   * **Consulta:** el contenido de la dirección URL que hay después del primer signo de interrogación (?).

      `foo.html?e0a72cb2a2c7`





1. (Opcional) Haga clic en **[!UICONTROL Agregar regla]** y configure reglas adicionales para la audiencia.
1. Haga clic en **[!UICONTROL Guardar]**.

También puede crear audiencias de página del sitio empleando su propio “parámetro de consulta definido por el usuario” o “encabezado definido por el usuario”.

Utilice un:

* Parámetro de consulta si la regla seleccionada por el usuario es Página actual, Página de aterrizaje o Página anterior.
* Encabezado si la regla seleccionada por el usuario es un encabezado HTTP.

como se ilustra a continuación:

![](assets/site_pages.png)

## Resolución de problemas {#ts}

* Para que las audiencias de página de aterrizaje funcionen correctamente, las solicitudes deben tener el `mboxReferrer` parámetro establecido (para la API de Envío el `context.address.referringUrl` parámetro) que la biblioteca JavaScript de at.js toma de la página mediante el `document.referrer` atributo . Este `HTMLDocument` atributo devuelve el URI de la página desde la que el usuario ha navegado. El valor de este atributo es una cadena vacía cuando el usuario navega directamente a la página (no a través de un vínculo, sino, por ejemplo, a través de un marcador).

   Si este comportamiento no coincide con sus necesidades, considere la posibilidad de realizar una de las siguientes acciones:

   * Pase los parámetros [](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md) de mbox para [!DNL Target] usarlos con fines de segmentación.
   * Utilice una actividad [de prueba](/help/c-activities/t-test-ab/test-ab.md) A/B en lugar de una actividad de página de aterrizaje. Las actividades de prueba A/B no cambian experiencias para el mismo visitante.
   * En su lugar, utilice un perfil [de](/help/c-target/c-audiences/c-target-rules/visitor-profile.md) visitante.

* Cuando utilice evaluadores &quot;inicios/termina con&quot; en cadenas que contengan comas, tenga en cuenta que se evalúan como una matriz de valores, en la que se evalúa cada valor separado por comas. Por ejemplo, si tenemos el valor de un encabezado: `Accept-Language: en,zh;q=0.9,en-IN;q=0.8,zh-CN;q=0.7` calificará para condiciones como:
   * inicios con zh,
   * inicios con en,
   * termina con 0,7,
   * termina con 0,8.

## Vídeo de formación: Creación de audiencias

Este vídeo contiene información sobre el uso de las categorías de audiencias.

* Crear audiencias
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)
