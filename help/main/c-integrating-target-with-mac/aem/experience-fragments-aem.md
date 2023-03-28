---
keywords: experiencia;json;aem;adobe experience manager;exportar a adobe target;fragmentos de experiencias;fragmentos;XF
description: Aprenda a utilizar [!DNL Adobe Experience Manager] [!UICONTROL Fragmentos de experiencias] en [!DNL Adobe Target] actividades.
title: Cómo Uso [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Fragmentos de experiencias]?
feature: Integrations
source-git-commit: 0135831b56c48b0adca49e843c5ddd6574358aa4
workflow-type: tm+mt
source-wordcount: '1346'
ht-degree: 32%

---

# AEM [!UICONTROL Fragmentos de experiencias]

Uso [!UICONTROL Fragmentos de experiencias] (XF) creados en [!DNL Adobe Experience Manager] (AEM) [!DNL Target] actividades para ayudar en la optimización o personalización.

>[!NOTE]
>
>Tenga en cuenta lo siguiente cuando trabaje con AEM [!UICONTROL Fragmentos de experiencias] en [!DNL Target]:
> 
>* Esta función requiere que [!DNL Adobe Experience Manager] (AEM) cliente. Para obtener más información, consulte [Requisitos](#section_AE6F0971E1574B3AA324003599B96E5A) más abajo.
>* Esta función está disponible para los siguientes tipos de actividades: [!UICONTROL Prueba A/B], [!UICONTROL Asignación automática], [!UICONTROL Segmentación automática], [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Segmentación de experiencias] (XT). Esta función no está disponible en [!UICONTROL Prueba multivariable] (MVT) y [!UICONTROL Recommendations] actividades.
>
>* Puede consumir [!UICONTROL Fragmentos de experiencias] en [!DNL Target] actividades que usan la variable [Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) o [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md).


Para obtener más información sobre AEM [!UICONTROL Fragmentos de experiencias] y fragmentos de contenido, consulte [AEM [!UICONTROL Fragmentos de experiencias] Información general sobre y fragmentos de contenido](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Requisitos.  {#requirements}

Debe estar aprovisionado con la variable [!UICONTROL Fragmentos de experiencias] funcionalidad dentro de [!DNL Target]. Además, debe utilizar [!DNL AEM] as a Cloud Service o [!DNL AEM] 6.4 (o posterior). El representante de cuentas puede ayudar a garantizar el cumplimiento de los requisitos para usar esta función:

* [!DNL Adobe Experience Manager ] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5.
* [!DNL Adobe Experience Manager] 6.4.
* Cuenta de [!DNL Adobe Target Standard] o [!DNL Adobe Target Premium].

[!DNL Adobe Experience Manager] Las versiones 6.3 y 6.4 han llegado al final de su vida útil y ya no son compatibles (excepto para los clientes que compraron soporte ampliado).

Póngase en contacto con el [Servicio de atención al cliente de Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para habilitar la integración y poder proporcionarle los datos de autenticación.

## Creación y configuración [!UICONTROL Fragmentos de experiencias] en [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Para usar [!DNL AEM] [!UICONTROL Fragmentos de experiencias] en [!DNL Target], debe realizar los siguientes pasos:

### Paso 1: Integrar [!DNL AEM] con [!DNL Target]

Para obtener más información, consulte:

* **AEM as a Cloud Service**: [Integración con Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target.html){target=_blank} en el *Experience Manager as a Cloud Service* guía.
* **Adobe I/O**: [integración con Adobe Target mediante Adobe I/O](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html?lang=es){target=_blank} en la documentación de la *Guía del usuario de administración*.
* **[!DNL AEM]6.5**: [participar en Adobe Analytics y Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=es){target=_blank} en la documentación de *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4**: [participar en Adobe Analytics y Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=es){target=_blank} en la documentación de *Adobe Experience Manager 6.4*.

### Paso 2: Crear el fragmento de experiencia

[!UICONTROL Fragmentos de experiencias] se crean en [!DNL AEM]. Para obtener más información, consulte:

* **AEM as a Cloud Service**: [[!UICONTROL Fragmentos de experiencias]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=en){target=_blank} en el *Experience Manager as a Cloud Service* guía.
* **[!DNL AEM]6.5**: [[!UICONTROL fragmentos de experiencias]](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=es){target=_blank} en la documentación de *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4**: [[!UICONTROL fragmentos de experiencias]](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=es){target=_blank} en la documentación de *Adobe Experience Manager 6.4*.

### Paso 3: Configurar [!DNL AEM] para compartir el fragmento de experiencia con [!DNL Target]

1. Desde [!DNL AEM], seleccione el fragmento de experiencia deseado o su carpeta contenedora y, a continuación, haga clic en **[!UICONTROL Propiedades]**.
2. Haga clic en la pestaña **[!UICONTROL Servicios de nube]** y a continuación, en la lista desplegable **[!UICONTROL Configuración de Servicio de nube]**, seleccione **[!UICONTROL Adobe Target]**.

   El paso anterior supone que alguien en su organización ha creado la configuración de [!DNL Adobe Target].

3. Haga clic en **[!UICONTROL Guardar y cerrar]**.

### Paso 4: Publicar el fragmento de experiencia y exportarlo a [!DNL Target]

Según su versión de [!DNL AEM], consulte los siguientes vínculos para obtener instrucciones paso a paso:

* **AEM as a Cloud Service**: [Exportación [!UICONTROL Fragmentos de experiencias] a Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target.html?lang=en){target=_blank} en el *Experience Manager as a Cloud Service* guía.
* **[!DNL AEM]6.5**: [exportación de un fragmento de experiencia a Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=en){target=_blank} en la documentación de *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4**: [exportación de un fragmento de experiencia a Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html?lang=es){target=_blank} en la documentación de *Adobe Experience Manager 6.4*.

## Uso [!UICONTROL Fragmentos de experiencias] en [!DNL Target] actividades {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Después de realizar las tareas anteriores, el fragmento de experiencias se muestra en la [!UICONTROL Ofertas] en [!DNL Target].

[!DNL Target] está buscando [!UICONTROL Fragmentos de experiencias] para importar cada diez minutos. El fragmento de experiencia importado debe estar disponible en [!DNL Target] en diez minutos, pero este lapso de tiempo debería acortarse en el futuro.

El fragmento de experiencia se importa en [!DNL Target] como HTML o oferta JSON. La versión &quot;principal&quot; del fragmento de experiencia permanece en [!DNL AEM]. No puede editar el fragmento de experiencia en [!DNL Target].

Puede filtrar y buscar por [!UICONTROL XF de HTML] y [!UICONTROL XF JSON] para ayudarle a distinguir entre los tipos de fragmento de experiencia que se exportan a [!DNL Target].

![Filtrar por tipos de fragmento de experiencia: HTML o JSON en la interfaz de usuario de Target](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Puede situar el cursor sobre un fragmento de experiencia en la lista y luego hacer clic en el botón [!UICONTROL Ver] icono ![Icono de información](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) para ver información adicional sobre el fragmento de experiencias, incluido su [!UICONTROL Nombre], [!UICONTROL Tipo], [!UICONTROL ID de oferta], [!UICONTROL Ruta de oferta]y la información de las últimas modificaciones. Haga clic en el [!UICONTROL Uso de ofertas] para ver las actividades que hacen referencia a esta oferta.

![Ventana emergente de información de fragmento de experiencia](/help/main/c-integrating-target-with-mac/aem/assets/xf-info-popup.png)

Puede consumir [!UICONTROL Fragmentos de experiencias] en [!DNL Target] actividades que usan la variable [Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) o [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md).


>[!TIP]
>
>Usar inteligencia artificial, aprendizaje automático y recomendaciones con [!UICONTROL Fragmentos de experiencias]:
>
>* Para usar completamente el [!DNL Target] funcionalidad AI y ML, puede seleccionar [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) o [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) al crear una prueba A/B.
>
>* [!UICONTROL Fragmentos de experiencias] no son compatibles con [!DNL Recommendations] actividades. Sin embargo, para usar [!UICONTROL Fragmentos de experiencias] para recomendaciones, puede crear un [!UICONTROL Prueba A/B] actividad (incluida [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática]) o un [!UICONTROL Segmentación de experiencias] (XT) y [incluir recomendaciones como oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).


**Para consumir fragmentos de experiencia usando el VEC:**

1. En [!DNL Target], mientras crea o edita una experiencia en el [Compositor de experiencias visuales](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), haga clic en la ubicación de la página donde desea insertar contenido [!DNL AEM] y, a continuación, seleccione la opción que desee para mostrar la lista [!UICONTROL Elegir un fragmento de experiencias].

   * [!UICONTROL Insertar antes]
   * [!UICONTROL Insertar después]
   * [!UICONTROL Intercambiar con fragmento de experiencia]

   La variable [!UICONTROL Fragmento de experiencia] muestra el contenido creado en [!DNL AEM] que ahora está disponible de forma nativa desde [!DNL Target].

   >[!NOTE]
   >
   >La opción [!UICONTROL Intercambiar con fragmento de experiencia] no está disponible para imágenes. Si desea utilizar esta opción con una imagen, haga clic en el elemento contenedor que contenga la imagen deseada.

   ![imagen experience_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

1. Seleccione el fragmento de experiencia deseado y haga clic en **[!UICONTROL Listo]**.
1. Termine de configurar la actividad.

   Para obtener más información acerca de la configuración de los distintos tipos de actividad, consulte los temas siguientes:

   * **Prueba A/B:** [Crear una prueba A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **Asignación automática:** [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Segmentación automática:** [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Personalización automatizada (AP):** [Creación de una actividad de personalización automatizada](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Segmentación de experiencias (XT):** [Crear una actividad de segmentación de experiencias](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Recommendations en una prueba A/B o una actividad XT:** [Recommendations como oferta](/help/main/c-recommendations/recommendations-as-an-offer.md)

   [!UICONTROL Fragmentos de experiencias] exportado como JSON en [!DNL Target] no se puede usar en actividades creadas con el VEC; solo HTML [!UICONTROL Fragmentos de experiencias] son compatibles con las actividades basadas en VEC. Si desea utilizar JSON [!UICONTROL Fragmentos de experiencias], utilícelos en las actividades creadas con la variable [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md).

**Para consumir fragmentos de experiencia usando el Compositor de experiencias basadas en formularios:**

1. En [!DNL Target], mientras crea o edita una experiencia en el [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), haga clic en el lugar de la página donde desea insertar contenido de [!DNL AEM] y, a continuación, seleccione **[!UICONTROL Cambiar fragmento de experiencia]** para mostrar la lista [!UICONTROL Elegir un fragmento de experiencia].

   ![imagen experience_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

   La variable [!UICONTROL Fragmento de experiencia] muestra el contenido creado en [!DNL AEM] que ahora está disponible de forma nativa desde [!DNL Target].

1. Seleccione el fragmento de experiencia deseado y haga clic en **[!UICONTROL Guardar]**.
1. Termine de configurar la actividad.

## Consideraciones {#considerations}

* [!DNL Target] está buscando [!UICONTROL Fragmentos de experiencias] para importar cada diez minutos. El fragmento de experiencia importado debe estar disponible en [!DNL Target] en diez minutos, pero este lapso de tiempo debería acortarse en el futuro.
* El fragmento de experiencia se importa en [!DNL Target] como HTML o oferta JSON. La versión &quot;principal&quot; del fragmento de experiencia permanece en [!DNL AEM]. No puede editar el fragmento de experiencia en [!DNL Target].
* No se puede crear [!UICONTROL Fragmentos de experiencias] using [!DNL Adobe I/O]. Crear [!UICONTROL Fragmentos de experiencias] usando AEM, como se explica más arriba.
* Si actualiza el fragmento de experiencia en AEM, el fragmento de experiencia debe publicarse y exportarse a [!DNL Target] nuevamente así [!DNL Target] puede utilizar los cambios más recientes.

## Eliminación de las bibliotecas de cliente y el HTML superfluo de [!UICONTROL Fragmentos de experiencias] exportado a [!UICONTROL Target]

Al utilizar ofertas de fragmentos de experiencias con [!DNL Target] en una página entregada por AEM, la página de destino ya contiene todas las bibliotecas de cliente necesarias. Tenga en cuenta también que tampoco son necesarios los elementos HTML prescindibles de la oferta.

A veces, páginas HTML enteras envuelven el fragmento de experiencias y causan problemas. Asegúrese de que el fragmento de experiencia sea un pequeño HTML y no una página de HTML completa con HTML, HEAD, BODY, etc.

Para obtener más información, consulte la siguiente entrada de blog: [AEM 6.5: Eliminación de las bibliotecas de cliente de [!UICONTROL Fragmentos de experiencias] exportado a Target](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser){target=_blank}.

## Vídeo de formación: Uso de AEM [!UICONTROL Fragmentos de experiencias] con [!DNL Adobe Target]

El siguiente vídeo muestra cómo configurar y utilizar [!UICONTROL Fragmentos de experiencias]:

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>Se ha eliminado la función de enlace profundo de [!DNL AEM] discutida a las 4:54.

Para obtener información más detallada, consulte [Uso [!UICONTROL Fragmentos de experiencias] con Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html?lang=es) en el *Vídeos y Tutorials de AEM Sites* página.