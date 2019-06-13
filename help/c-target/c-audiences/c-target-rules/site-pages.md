---
description: Segmente a los visitantes que estén en una página concreta o que tengan un parámetro de mbox específico.
keywords: páginas de sitio;páginas de sitio Target;segmentación;página actual;página actual Target;página anterior;página anterior Target;página de destino;página de destino Target;mbox;mbox Target
seo-description: Segmente a los visitantes que estén en una página concreta o que tengan un parámetro de mbox específico.
seo-title: Páginas del sitio
solution: Target
title: Páginas del sitio
topic: Standard
uuid: 1cf9fa94-dbec-4719-9a0a-79c1eb91a233
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Páginas del sitio{#site-pages}

Segmente a los visitantes que estén en una página concreta o que tengan un parámetro de mbox específico.

>[!NOTE]
>
>Los tipos de página del sitio de audiencia y los operadores de comparación ahora coinciden con los tipos y los operadores de comparación de Target Classic. También puede crear audiencias de página del sitio empleando su propio “parámetro de consulta definido por el usuario” o “encabezado definido por el usuario”.

1. En la interfaz de [!DNL Target], haga clic en **[!UICONTROL Audiencias]** &gt; **[!UICONTROL Crear audiencia]**.
1. Ponga un nombre a la audiencia.
1. Haga clic en **[!UICONTROL Añadir regla]** &gt; **[!UICONTROL Páginas de sitio]**.

   ![](assets/target_site_pages.png)

1. Haga clic en **[!UICONTROL Seleccionar]** y, a continuación, elija una de estas opciones:

   * **Página actual:** la página en la que se encuentra el usuario, que es la que contiene un mbox en la actividad. Si segmenta en el nivel de actividad, podría tratarse de una página con un mbox que utilice para definir las condiciones de entrada o una página que muestra contenido. Si define la segmentación según la experiencia, entonces la página actual es la página donde se encuentre el mbox de pantalla. Para definir la segmentación según la métrica de éxito o la conversión, entonces es la página donde se encuentren dichos mboxes.
   * **Página anterior:** la página en la que el usuario estaba antes de hacer clic para acceder a la página actual. (Para que se realice un seguimiento de la página, el usuario tiene que hacer clic en la página anterior para acceder a la página actual. No se hace un seguimiento de la página anterior si el usuario escribe una nueva dirección URL en el navegador). El contenido real de la página depende del diseño del sitio. Por ejemplo, si la página actual muestra información acerca de un producto específico, la página anterior puede ser una página de categorías en la que el visitante seleccione el elemento específico (por ejemplo, una página que muestre varias cámaras de un determinado tipo) o puede tratarse de la página principal que conduzca a la página final.
   * **Página de aterrizaje:** la página de aterrizaje es la primera página que ve el visitante al acceder al sitio. Por ejemplo, si el visitante hace clic en un vínculo de Google que le lleva a la página de categorías, entonces la página de categorías es la página de aterrizaje. Si el vínculo lleva a la página principal, entonces ésta es la página de aterrizaje. Se recuerda la página de aterrizaje durante la sesión del visitante. Puede segmentar mucho más en el sitio según la página de aterrizaje del visitante correspondiente a la sesión.

      >[!NOTE]
      >
      >El objeto `landing.url` se restablece en un cambio de subdominio o sustitución directa de la dirección URL.

   * **Mbox:** el mbox sobre el que está estableciendo el objetivo. Por ejemplo, si desea contar los pedidos con un total de 100 dólares o más, pasaría `orderTotal` como parámetro de mbox con esa segmentación especificada aquí.
   * **Dominio:** el dominio completo de la página. Al especificar un dominio, se recomienda utilizar “contains” (contiene). Por ejemplo, “Domain equals facebook.com” (Dominio igual a facebook.com) no aceptará `m.facebook.com` ni `www.facebook.com`. “Domain contains facebook.com” (Dominio contiene facebook.com) aceptará cualquier variante de facebook.com.
   * **Consulta:** el contenido de la dirección URL que hay después del primer signo de interrogación (?). En este ejemplo de URL, la consulta aparece destacada en negrita.

      `foo.html?e0a72cb2a2c7`

1. (Opcional) Haga clic en **[!UICONTROL Agregar regla]** y configure reglas adicionales para la audiencia.
1. Haga clic en **[!UICONTROL Guardar]**.

También puede crear audiencias de página del sitio empleando su propio “parámetro de consulta definido por el usuario” o “encabezado definido por el usuario”.

Utilice un:

* Parámetro de consulta si la regla seleccionada por el usuario es Página actual, Página de aterrizaje o Página anterior.
* Encabezado si la regla seleccionada por el usuario es Encabezado HTTP.

como se ilustra a continuación:

![](assets/site_pages.png)

## Vídeo de formación: Creación de audiencias

Este vídeo contiene información sobre el uso de las categorías de audiencias.

* Crear audiencias
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)
