---
keywords: oferta de redireccionamiento;crear oferta de redireccionamiento;añadir oferta de html;Pasar todos los parámetros de URL en el redireccionamiento
description: Aprenda a crear ofertas de redireccionamiento para guiar fácilmente a los navegadores a nuevas páginas.
title: ¿Cómo Se Crean Ofertas De Redireccionamiento?
feature: Experiences and Offers
exl-id: b7b960cb-5057-455b-8fab-86dd37343a04
TQID: https://experienceleague.adobe.com/-kFkgCCbzb34aNAxW-Q1CqmyK9rETL0qVMQeEP9JtrY
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: c93393a4-e558-47e1-992e-c91ed4d480ce
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 16fb7a1902ea76cab56a93fa141a32a3c6bc4467
workflow-type: tm+mt
source-wordcount: 1190
ht-degree: 24%

---

# Crear ofertas de redireccionamiento

Aprenda a crear ofertas de redireccionamiento para guiar fácilmente a los navegadores a nuevas páginas.

Es posible que tenga dos páginas completamente distintas para probarlas, en lugar de simplemente cambiar partes de contenido dentro de una página. En este caso, la prueba A/B compara la página A con la B. Configure una actividad [!UICONTROL Prueba A/B] con dos experiencias: una que apunte a la página A predeterminada y otra que redirija a la página B. La oferta está configurada para redirigir al visitante a una página diferente.

>[!NOTE]
>
> * Las ofertas de redireccionamiento se pueden crear en la página [!UICONTROL Ofertas] > [!UICONTROL Ofertas de código] o en el [Compositor de experiencias basadas en Forms](/help/main/c-experiences/form-experience-composer.md). No puede crear ni aplicar ofertas de redireccionamiento en el [!UICONTROL Compositor de experiencias visuales] (VEC). El contenido se inserta en las ubicaciones de solicitud [!DNL Target], por lo que es muy probable que estas ubicaciones no sean apropiadas para una solicitud [!DNL Target] global.
>
>* No puede usar ofertas de redireccionamiento en mboxes de AJAX (`mboxUpdate`).
>
>* Para redireccionar ofertas en actividades que usan [[!UICONTROL Analytics como fuente de informes]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), su implementación debe cumplir con ciertos requisitos mínimos. Además, hay información importante que debe conocer. Ver [Ofertas de redireccionamiento: preguntas más frecuentes sobre A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
>
>* Para obtener información sobre la configuración de una experiencia de redireccionamiento, consulte [Redireccionar a una URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA).

La oferta de redireccionamiento ejecuta código JavaScript para redirigir el navegador. Utiliza el método `window.location.replace();`, de modo que la página desde la cual se redirige al visitante no se almacene en el historial del explorador. Este proceso permite a los visitantes utilizar el botón Atrás en sus navegadores.

>[!NOTE]
>
>Si desea pasar el valor de referente de la página de aterrizaje, utilice una oferta de HTML en lugar de una oferta de redireccionamiento.

## Crear una oferta de redireccionamiento desde la página [!UICONTROL Ofertas de código]

1. Haga clic en **[!UICONTROL Ofertas]** y seleccione la pestaña **[!UICONTROL Ofertas de código]**.
1. Haga clic en **[!UICONTROL Crear oferta]** > **[!UICONTROL Oferta de redireccionamiento]**.
1. Escriba un nombre descriptivo para la oferta.

   Un nombre descriptivo permite encontrar la oferta rápidamente en la biblioteca [!UICONTROL Activos].

1. (Condicional) Si tiene una [cuenta de Target Premium](/help/main/c-intro/intro.md#premium), seleccione el [espacio de trabajo](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC) que desee.

1. Especifique la dirección URL del contenido único o del destino al que desea redirigir. Esta URL debe ser una URL absoluta.

   >[!NOTE]
   >
   >Las ofertas de redireccionamiento generan un bucle infinito si la URL de redireccionamiento también califica al usuario para la misma actividad. Para evitarlo, agregue un parámetro de consulta a la dirección URL de redireccionamiento (por ejemplo, `?redirect=true`). A continuación, en la audiencia de actividad o en la regla de plantilla, compruebe que este parámetro de consulta no esté presente. Esto garantiza que el usuario no vuelva a ser calificado para la actividad después de ser redirigido.

1. Seleccione las opciones que quiera para personalizar la oferta de redireccionamiento:

   * **[!UICONTROL Incluir todos los parámetros de URL]:** Active esta opción si desea que todos los parámetros de URL presentes en la página anterior se propaguen a la página a la que se redirige.

     Por ejemplo, imagine que quiere redirigir a las personas que están en una página para hombres directamente a una página de categoría de camisetas para hombres. También desea que se pasen los parámetros dinámicos en la dirección URL, ya que este método es la forma de rastrear si las personas llegaron al sitio por correo electrónico, anuncio de banner, anuncio de búsqueda o de forma orgánica. Al habilitar esta opción, su oferta de redireccionamiento en la página `https://www.mycompany.com/mens.html?emailId=123` se convierte automáticamente en `https://www.mycompany.com/mensShirts.html?emailId=123` cuando todo lo que ingresó en el cuadro URL fue `https://www.mycompany.com/mensShirts.html`.

   * **[!UICONTROL Se requiere pasar el id. de sesión de mbox]:** para redireccionar a un dominio diferente. Deslice el botón de alternancia para habilitar esta opción si desea que `sessionId` se incluya automáticamente en la redirección. Esta opción solo es necesaria cuando está probando los clics de un correo electrónico o los clics de un dominio a otro. El parámetro `sessionId` coincide con la cookie del visitante para que pueda realizarse un seguimiento del visitante y mostrar el contenido adecuado.

     Si utiliza la configuración de cookies de origen y de terceros, no necesita pasar el ID de sesión de mbox al cruzar dominios. Este identificador se conserva en la cookie de terceros, por lo que no es necesario en la dirección URL.

1. Haga clic en **[!UICONTROL Crear]**.

>[!IMPORTANT]
>
>Consulte con su consultor de implementación antes de iniciar estas pruebas.

## Cree una oferta de redireccionamiento usando [!UICONTROL Compositor de experiencias basadas en formularios]

1. Al crear una actividad con el [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md), seleccione la ubicación para mostrar la sección **[!UICONTROL Contenido]**.
1. Haga clic en la lista desplegable **[!UICONTROL Contenido]**, haga clic en el icono **[!UICONTROL Lista]** ( ![Lista](/help/main/assets/icons/MoreSmallList.svg) ) y, a continuación, haga clic en **[!UICONTROL Cambiar oferta de redirección]**.
1. Haga clic en **[!UICONTROL Crear oferta]** > **[!UICONTROL Oferta de redireccionamiento]**.
1. Escriba un nombre descriptivo para la oferta.

   Un nombre descriptivo permite encontrar la oferta rápidamente en la biblioteca [!UICONTROL Activos].

1. Especifique la dirección URL del contenido único o del destino al que desea redirigir. Esta URL debe ser una URL absoluta.

   >[!NOTE]
   >
   >Las ofertas de redireccionamiento generan un bucle infinito si la URL de redireccionamiento también califica al usuario para la misma actividad. Para evitarlo, agregue un parámetro de consulta a la dirección URL de redireccionamiento (por ejemplo, `?redirect=true`). A continuación, en la audiencia de actividad o en la regla de plantilla, compruebe que este parámetro de consulta no esté presente. Esto garantiza que el usuario no vuelva a ser calificado para la actividad después de ser redirigido.

1. Seleccione las opciones que quiera para personalizar la oferta de redireccionamiento:

   * **[!UICONTROL Incluir todos los parámetros de URL]:** Deslice el botón de alternancia para habilitar esta opción si desea que todos los parámetros de URL presentes en la página anterior se propaguen en la página a la que se redirige.

     Por ejemplo, imagine que quiere redirigir a las personas que están en una página para hombres directamente a una página de categoría de camisetas para hombres. También desea que se pasen los parámetros dinámicos en la dirección URL, ya que este método es la forma de rastrear si las personas llegaron al sitio por correo electrónico, anuncio de banner, anuncio de búsqueda o de forma orgánica. Al habilitar esta opción, su oferta de redireccionamiento en la página `https://www.mycompany.com/mens.html?emailId=123` se convierte automáticamente en `https://www.mycompany.com/mensShirts.html?emailId=123` cuando todo lo que ingresó en el cuadro URL fue `https://www.mycompany.com/mensShirts.html`.

   * **[!UICONTROL Se requiere pasar el id. de sesión de mbox]:** para redireccionar a un dominio diferente. Deslice el botón de alternancia para habilitar esta opción si desea que `sessionId` se incluya automáticamente en la redirección. Esta opción solo es necesaria cuando está probando los clics de un correo electrónico o los clics de un dominio a otro. El parámetro `sessionId` coincide con la cookie del visitante para que pueda realizarse un seguimiento del visitante y mostrar el contenido adecuado.

     Si utiliza la configuración de cookies de origen y de terceros, no necesita pasar el ID de sesión de mbox al cruzar dominios. Este identificador se conserva en la cookie de terceros, por lo que no es necesario en la dirección URL.

1. Haga clic en **[!UICONTROL Crear]**.

>[!IMPORTANT]
>
>Consulte con su consultor de implementación antes de iniciar estas pruebas.

## Usar ofertas de redireccionamiento en actividades

Aplique ofertas de redireccionamiento utilizando [[!UICONTROL Compositor de experiencias basadas en formularios]](/help/main/c-experiences/form-experience-composer.md). Actualmente no puede aplicar ofertas de redireccionamiento usando el [!UICONTROL Compositor de experiencias visuales] (VEC).

[!DNL Adobe Target] [!UICONTROL Compositor de experiencias basadas en formularios] es una interfaz no visual y de creación de ofertas que resulta útil para crear experiencias para utilizarlas en [!UICONTROL pruebas A/B], [!UICONTROL Segmentación de experiencias] (XT), [!UICONTROL Automated Personalization] (AP) y actividades de [!UICONTROL Recommendations] cuando [!UICONTROL Compositor de experiencias visuales] no está disponible o su uso no es práctico. Por ejemplo, podría usar [!UICONTROL Compositor de experiencias basadas en formularios] para crear experiencias que usen ofertas de redireccionamiento.

1. Cree o edite una actividad en [!UICONTROL Compositor de experiencias basadas en formularios].

   Consulte [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md) para obtener instrucciones detalladas paso a paso.

1. Especifique la ubicación deseada y añada los refinamientos de audiencia que sean necesarios.

1. Haga clic en la lista desplegable **[!UICONTROL Contenido]**, haga clic en el icono **[!UICONTROL Lista]** ( ![Lista](/help/main/assets/icons/MoreSmallList.svg) ) y, a continuación, haga clic en **[!UICONTROL Cambiar oferta de redirección]**.
1. Seleccione la oferta de redireccionamiento deseada del cuadro de diálogo [!UICONTROL Seleccionar oferta de redireccionamiento] y, a continuación, haga clic en **[!UICONTROL Agregar]**.
1. Termine de configurar la actividad.
