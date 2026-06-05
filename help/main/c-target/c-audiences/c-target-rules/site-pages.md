---
keywords: páginas de sitio;páginas de sitio de destino;segmentación;página actual;página actual de destino;página anterior;página anterior de destino;página de destino;página de destino de destino;encabezado http
description: Aprenda a segmentar visitantes que usen  [!DNL Adobe Target] que se encuentran en una página específica del sitio.
title: ¿Puedo segmentar visitantes según las páginas del sitio?
feature: Audiences
exl-id: 4c770b7b-775f-4483-aced-43f18a9a68c1
TQID: https://experienceleague.adobe.com/ROMKabnbH3yE-W61IQk9CtNpKMg7zA6-qdxu272EVOI
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 929
ht-degree: 19%

---

# Páginas del sitio

Puede segmentar visitantes mediante [!DNL Adobe Target] que tengan acceso a una página específica del sitio.

1. En la interfaz [!DNL Target], haga clic en **[!UICONTROL Audiencias]** > **[!UICONTROL Crear audiencia]**.
1. Asigne un nombre a la audiencia y añada una descripción opcional.
1. Arrastre y suelte **[!UICONTROL Páginas de sitio]** en el panel Generador de audiencias.

   ![Público de páginas del sitio](assets/target_site_pages.png)

1. Haga clic en la lista desplegable **[!UICONTROL Seleccionar]**, seleccione una de las siguientes opciones y, a continuación, configure la regla como desee.

   Las opciones y los evaluadores disponibles en las siguientes listas desplegables de la regla varían según la opción que elija. La siguiente ilustración muestra las opciones disponibles si elige [!UICONTROL Página actual]:

   ![Página actual](assets/current-page.png)

   Las siguientes opciones están disponibles en la lista desplegable inicial al elegir [!UICONTROL Seleccionar].

   * **[!UICONTROL Página actual]:** Página que el usuario está viendo.

     Las siguientes opciones están disponibles en la segunda lista desplegable si elige esta opción:

      * [!UICONTROL URL] (para obtener más información sobre cómo evalúa [!DNL Target] las URL, consulte [Preguntas frecuentes sobre objetivos y audiencias](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)).
      * [!UICONTROL Dominio]
      * [!UICONTROL Consulta]
      * [!UICONTROL Subdominio]
      * [!UICONTROL Dominio de nivel superior]
      * [!UICONTROL Ruta]
      * [!UICONTROL Fragmento almohadilla (#)]

   * **[!UICONTROL Página anterior]:** Página que el usuario vio antes de hacer clic en la página actual. El usuario debe hacer clic desde la página anterior hasta la página actual para que se realice el seguimiento de la página. La página anterior no se rastrea si el usuario escribe una nueva dirección URL en el explorador. El contenido real de la página depende del diseño del sitio. Por ejemplo, si la página actual muestra información sobre un producto específico, la página anterior podría ser una página de categoría en la que el visitante seleccione el artículo específico. Por ejemplo, una página que muestra varias cámaras de un tipo determinado, o puede ser la página de inicio que lleva a la página final.

     Las siguientes opciones están disponibles en la segunda lista desplegable si elige esta opción:

      * [!UICONTROL URL] (para obtener más información sobre cómo Target evalúa las URL, consulte [Preguntas más frecuentes sobre objetivos y audiencias](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)).
      * [!UICONTROL Dominio]
      * [!UICONTROL Consulta]
      * [!UICONTROL Subdominio]
      * [!UICONTROL Dominio de nivel superior]
      * [!UICONTROL Ruta]

   * **[!UICONTROL Página de aterrizaje]:** La página de aterrizaje es la primera página que ve el visitante al acceder al sitio. Por ejemplo, si el visitante hace clic en un vínculo de Google que le lleva a la página de categorías, entonces la página de categorías es la página de aterrizaje. Si el vínculo lleva a la página principal, entonces ésta es la página de aterrizaje. Se recuerda la página de aterrizaje durante la sesión del visitante. Puede segmentar mucho más en el sitio según la página de aterrizaje del visitante correspondiente a la sesión.

     Las siguientes opciones están disponibles en la segunda lista desplegable si elige esta opción:

      * [!UICONTROL URL] (para obtener más información sobre cómo Target evalúa las URL, consulte [Preguntas más frecuentes sobre objetivos y audiencias](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)).
      * [!UICONTROL Dominio]
      * [!UICONTROL Consulta]
      * [!UICONTROL Subdominio]
      * [!UICONTROL Dominio de nivel superior]
      * [!UICONTROL Ruta]
      * [!UICONTROL Fragmento almohadilla (#)]

     >[!NOTE]
     >
     >El objeto `landing.url` se restablece en un cambio de subdominio o sustitución directa de la dirección URL.

   * **[!UICONTROL Encabezado HTTP]:** Esta opción evalúa la información en el encabezado HTTP de la solicitud [!DNL Target]. Por ejemplo, si el encabezado HTTP contiene información del idioma, puede crear una regla que contenga la condición `Accept-Language: es` para dirigirse a los visitantes que accedan a la página en español.

     Las siguientes opciones están disponibles en la segunda lista desplegable si elige esta opción:

      * [!UICONTROL Aceptar]
      * [!UICONTROL Accept-Charset]
      * [!UICONTROL Aceptar-Codificación]
      * [!UICONTROL Accept-Language]
      * [!UICONTROL Autorización]
      * [!UICONTROL Control de caché]
      * [!UICONTROL Conexión]
      * [!UICONTROL Longitud de contenido]
      * [!UICONTROL Contenido-MDS]
      * [!UICONTROL Tipo de contenido]
      * [!UICONTROL Fecha]
      * [!UICONTROL Esperar]
      * [!UICONTROL De]
      * [!UICONTROL Host]
      * [!UICONTROL If-Match]
      * [!UICONTROL Si-Modificado-Desde]
      * [!UICONTROL Si-Ninguno-Coincide]
      * [!UICONTROL Si-Intervalo]
      * [!UICONTROL Si-No modificado-Desde]
      * [!UICONTROL Reenvíos máximos]
      * [!UICONTROL Pragma]
      * [!UICONTROL Autorización de proxy]
      * [!UICONTROL Intervalo]
      * [!UICONTROL Referente]
      * [!UICONTROL TE]
      * [!UICONTROL Actualizar]
      * [!UICONTROL User-Agent]
      * [!UICONTROL Mediante]
      * [!UICONTROL Advertencia]

   Si elige [!UICONTROL Página actual], [!UICONTROL Página anterior] o [!UICONTROL Página de aterrizaje], las opciones [!UICONTROL Dominio] y [!UICONTROL Consulta] están disponibles. Tenga en cuenta lo siguiente al elegir estas opciones:

   * **Dominio:** el dominio completo de la página. Al especificar un dominio, se recomienda utilizar “contains” (contiene). Por ejemplo, &quot;Dominio igual a facebook.com&quot; no acepta `m.facebook.com` ni `www.facebook.com`. &quot;El dominio contiene facebook.com&quot; acepta cualquier variante de facebook.com.
   * **Consulta:** El contenido de la dirección URL después del primer signo de interrogación (?).

     `foo.html?e0a72cb2a2c7`

1. (Opcional) Configure reglas adicionales para la audiencia.
1. Haga clic en **[!UICONTROL Finalizado]**.

También puede crear públicos de página del sitio empleando su propio “parámetro de consulta definido por el usuario” o “encabezado definido por el usuario”.

Utilice un:

* Parámetro de consulta si la regla seleccionada por el usuario es [!UICONTROL Página actual], [!UICONTROL Página de aterrizaje] o [!UICONTROL Página anterior]
* Header si la regla seleccionada por el usuario es un encabezado HTTP

## Resolución de problemas {#ts}

* Para que las audiencias de página de aterrizaje funcionen correctamente, las solicitudes deben tener el parámetro `mboxReferrer` establecido (para la API de entrega, el parámetro `context.address.referringUrl`) que la biblioteca JavaScript de at.js toma de la página con el atributo `document.referrer`. Este atributo `HTMLDocument` devuelve el URI de la página desde la que el usuario ha navegado. El valor de este atributo es una cadena vacía cuando el usuario navega directamente a la página (no a través de un vínculo, sino, por ejemplo, a través de un marcador).

  Si este comportamiento no coincide con sus necesidades, considere la posibilidad de realizar una de las siguientes acciones:

   * Pase [parámetros de mbox](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/global-mbox/pass-parameters-to-global-mbox.html?lang=es){target=_blank} a [!DNL Target] para usarlos con fines de segmentación.
   * Use una [actividad de prueba A/B](/help/main/c-activities/t-test-ab/test-ab.md) en lugar de una actividad de página de aterrizaje. Las actividades de prueba A/B no cambian de experiencia para el mismo visitante.
   * En su lugar, usa un [perfil del visitante](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md).

* Cuando se utilizan evaluadores &quot;comienza/termina con&quot; en cadenas que contienen comas, estas cadenas se evalúan como una matriz de valores, en la que se evalúa cada valor separado por una coma. Por ejemplo, si tiene el valor para un encabezado: `Accept-Language: en,zh;q=0.9,en-IN;q=0.8,zh-CN;q=0.7`, cumple los requisitos para condiciones como las siguientes:
   * empieza por zh,
   * empieza por en,
   * termina con 0,7,
   * termina con 0,8.

## Vídeo de formación: Creación de públicos

Este vídeo contiene información sobre el uso de las categorías de audiencias.

* Crear públicos
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)
