---
description: Segmente a los visitantes que estén en una página concreta o que tengan un parámetro de mbox específico.
keywords: páginas de sitio;páginas de sitio Target;segmentación;página actual;página actual Target;página anterior;página anterior Target;página de destino;página de destino Target;mbox;mbox Target
seo-description: Puede segmentar visitantes que estén en una página específica o que tengan un parámetro de mbox específico mediante Adobe Target.
seo-title: Páginas de sitio en Adobe Target
solution: Target
title: Páginas del sitio
topic: Standard
uuid: 1cf9fa94-dbec-4719-9a0a-79c1eb91a233
translation-type: tm+mt
source-git-commit: d47772b35e371af4b6484ff59209de1c8482b712

---


# Páginas del sitio{#site-pages}

Puede segmentar visitantes que estén en una página específica o que tengan un parámetro de mbox específico.

>[!NOTE]
>
>Los tipos de página del sitio de audiencia y los operadores de comparación ahora coinciden con los tipos y los operadores de comparación de Target Classic. También puede crear audiencias de página del sitio empleando su propio “parámetro de consulta definido por el usuario” o “encabezado definido por el usuario”.

1. En la interfaz de [!DNL Target], haga clic en **[!UICONTROL Audiencias]** &gt; **[!UICONTROL Crear audiencia]**.
1. Ponga un nombre a la audiencia.
1. Haga clic en **[!UICONTROL Añadir regla]** &gt; **[!UICONTROL Páginas de sitio]**.

   ![Audiencia de páginas del sitio](assets/target_site_pages.png)

1. Haga clic en **[!UICONTROL Seleccionar]** y, a continuación, elija una de estas opciones:

   * **Página actual:** la página en la que se encuentra el usuario, que es la que contiene un mbox en la actividad. Si segmenta en el nivel de actividad, podría tratarse de una página con un mbox que utilice para definir las condiciones de entrada o una página que muestra contenido. Si define la segmentación según la experiencia, entonces la página actual es la página donde se encuentre el mbox de pantalla. Para definir la segmentación según la métrica de éxito o la conversión, entonces es la página donde se encuentren dichos mboxes.
   * **Página anterior:** la página en la que el usuario estaba antes de hacer clic para acceder a la página actual. (Para que se realice un seguimiento de la página, el usuario tiene que hacer clic en la página anterior para acceder a la página actual. No se hace un seguimiento de la página anterior si el usuario escribe una nueva dirección URL en el navegador). El contenido real de la página depende del diseño del sitio. Por ejemplo, si la página actual muestra información acerca de un producto específico, la página anterior puede ser una página de categorías en la que el visitante seleccione el elemento específico (por ejemplo, una página que muestre varias cámaras de un determinado tipo) o puede tratarse de la página principal que conduzca a la página final.
   * **Página de aterrizaje:** la página de aterrizaje es la primera página que ve el visitante al acceder al sitio. Por ejemplo, si el visitante hace clic en un vínculo de Google que le lleva a la página de categorías, entonces la página de categorías es la página de aterrizaje. Si el vínculo lleva a la página principal, entonces ésta es la página de aterrizaje. Se recuerda la página de aterrizaje durante la sesión del visitante. Puede segmentar mucho más en el sitio según la página de aterrizaje del visitante correspondiente a la sesión.

      >[!NOTE]
      >
      >El objeto `landing.url` se restablece en un cambio de subdominio o sustitución directa de la dirección URL.

   * **Mbox:** el mbox sobre el que está estableciendo el objetivo. Por ejemplo, si desea contar los pedidos con un total de 100 dólares o más, pasaría `orderTotal` como parámetro de mbox con esa segmentación especificada aquí.
   * **Dominio:** el dominio completo de la página. Al especificar un dominio, se recomienda utilizar “contains” (contiene). Por ejemplo, “Domain equals facebook.com” (Dominio igual a facebook.com) no aceptará `m.facebook.com` ni `www.facebook.com`. “Domain contains facebook.com” (Dominio contiene facebook.com) aceptará cualquier variante de facebook.com.
   * **Consulta:** el contenido de la dirección URL que hay después del primer signo de interrogación (?).

      `foo.html?e0a72cb2a2c7`

1. (Opcional) Haga clic en **[!UICONTROL Agregar regla]** y configure reglas adicionales para la audiencia.
1. Haga clic en **[!UICONTROL Guardar]**.

También puede crear audiencias de página del sitio empleando su propio “parámetro de consulta definido por el usuario” o “encabezado definido por el usuario”.

Utilice un:

* Parámetro de consulta si la regla seleccionada por el usuario es Página actual, Página de aterrizaje o Página anterior.
* Encabezado si la regla seleccionada por el usuario es Encabezado HTTP.

como se ilustra a continuación:

![](assets/site_pages.png)

## Resolución de problemas {#ts}

* Para que las audiencias de página de aterrizaje funcionen correctamente, las solicitudes deben tener el parámetro `mboxReferrer` mbox configurado correctamente. La biblioteca JavaScript de at.js se obtiene `mboxReferrer` de la página mediante `document.referrer`.

   Si estos parámetros no se configuran correctamente, un visitante podría abandonar una actividad después de navegar a una página posterior. Por ejemplo: si `document.referrer` se utiliza en la página de aterrizaje pero no en páginas posteriores, [!DNL Target] no se puede garantizar que el visitante permanezca en la actividad.

   Si se encuentra con esta situación, considere la posibilidad de realizar una de las siguientes acciones:

   * Asegúrese de que el sitio web se carga `document.referrer` correctamente.
   * Pase parámetros [](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md) de mbox para [!DNL Target] usarlos con fines de segmentación.
   * Utilice una actividad [de prueba](/help/c-activities/t-test-ab/test-ab.md) A/B en lugar de una actividad de página de aterrizaje. Las actividades de prueba A/B no cambian experiencias para el mismo visitante.
   * Utilice un perfil [de visitante](/help/c-target/c-audiences/c-target-rules/visitor-profile.md) en su lugar.

## Vídeo de formación: Creación de audiencias

Este vídeo contiene información sobre el uso de las categorías de audiencias.

* Crear audiencias
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392?captions=spa)
