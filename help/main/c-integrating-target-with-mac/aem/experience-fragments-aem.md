---
keywords: experiencia;json;aem;adobe experience manager;exportar a adobe target;fragmentos de experiencias;fragmentos;XF
description: Aprenda a usar  [!DNL Adobe Experience Manager] [!UICONTROL Experience Fragments] en  [!DNL Adobe Target] actividades.
title: ¿Cómo Uso  [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Experience Fragments]?
feature: Integrations
exl-id: 400d0cde-e435-4cac-9bf0-64a6cad98995
source-git-commit: 51e484d54f4d318ea59fdfdb16d1ed7014abdfdb
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 31%

---

# AEM [!UICONTROL Experience Fragments]

Utilice [!UICONTROL Experience Fragments] (XF) creados en [!DNL Adobe Experience Manager] (AEM) en [!DNL Target] actividades para ayudar en la optimización y personalización.

## Consideraciones

Tenga en cuenta lo siguiente al trabajar con AEM [!UICONTROL Experience Fragments] en [!DNL Target]:

* Esta función requiere que sea cliente de [!DNL Adobe Experience Manager] (AEM). Para obtener más información, consulte [Requisitos](#section_AE6F0971E1574B3AA324003599B96E5A) más adelante.
* [!UICONTROL Experience Fragments] y [!UICONTROL Content Fragments] están disponibles para los siguientes tipos de actividades:

   * [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Experience Targeting] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL Experience Fragments] y [!UICONTROL Content Fragments] no están disponibles para los siguientes tipos de actividades:

   * [[!UICONTROL Multivariate Test] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* Puede consumir [!UICONTROL Experience Fragments] en [!DNL Target] actividades usando [Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) y [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md).

Para obtener más información acerca de AEM [!UICONTROL Experience Fragments] y [!UICONTROL Content Fragments], consulte [Información general sobre AEM [!UICONTROL Experience Fragments] y los fragmentos de contenido](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Requisitos {#requirements}

Debe contar con la funcionalidad [!UICONTROL Experience Fragments] dentro de [!DNL Target]. Además, debe utilizar [!DNL AEM] as a Cloud Service o [!DNL AEM] 6.4 (o posterior). El representante de cuentas puede ayudar a garantizar el cumplimiento de los requisitos para usar esta función:

* [!DNL Adobe Experience Manager] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5
* [!DNL Adobe Experience Manager] 6.4
* Cuenta de [!DNL Adobe Target Standard] o [!DNL Adobe Target Premium]

[!DNL Adobe Experience Manager] 6.3 y 6.4 han llegado al final de su vida útil y ya no son compatibles (excepto para los clientes que compraron soporte ampliado).

Póngase en contacto con el [Servicio de atención al cliente de Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para habilitar la integración y poder proporcionarle los datos de autenticación.

## Creando y configurando [!UICONTROL Experience Fragments] en [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Para usar [!DNL AEM] [!UICONTROL Experience Fragments] en [!DNL Target], debe realizar los siguientes pasos:

### Paso 1: Integrar [!DNL AEM] con [!DNL Target]

Para obtener más información, consulte:

* **AEM as a Cloud Service**: [Integración con Adobe Target](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target){target=_blank} en la guía de *Experience Manager as a Cloud Service*.
* **Adobe Developer**: [Integración con Adobe Target mediante Adobe I/0](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-target-ims-adobe-io.html){target=_blank} en la *Guía del usuario de administración*.
* **[!DNL AEM]6.5**: [participar en Adobe Analytics y Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=es){target=_blank} en la documentación de *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4**: [participar en Adobe Analytics y Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=es){target=_blank} en la documentación de *Adobe Experience Manager 6.4*.

### Paso 2: Crear el fragmento de experiencia

[!UICONTROL Experience Fragments] se han creado en [!DNL AEM]. Para obtener más información, consulte:

* **AEM as a Cloud Service**: [[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=es){target=_blank} en la guía de *Experience Manager as a Cloud Service*.
* **[!DNL AEM]6.5**: [[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=es){target=_blank} en la documentación de *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4**: [[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=es){target=_blank} en la documentación de *Adobe Experience Manager 6.4*.

### Paso 3: Configurar [!DNL AEM] para que comparta [!UICONTROL Experience Fragment] con [!DNL Target]

1. En [!DNL AEM], seleccione el(la) [!UICONTROL Experience Fragment] deseado(a) o su carpeta contenedora y luego haga clic en **[!UICONTROL Properties]**.
2. Haga clic en la ficha **[!UICONTROL Cloud Services]** y, a continuación, en la lista desplegable **[!UICONTROL Cloud Service Configuration]**, seleccione **[!UICONTROL Adobe Target]**.

   El paso anterior supone que alguien en su organización ha creado la configuración de [!DNL Adobe Target].

3. Haga clic en **[!UICONTROL Save & Close]**.

### Paso 4: Publicar [!UICONTROL Experience Fragment] y exportarlo en [!DNL Target]

Según su versión de [!DNL AEM], consulte los siguientes vínculos para obtener instrucciones paso a paso:

* **AEM as a Cloud Service**: [Exportando [!UICONTROL Experience Fragments] a Adobe Target](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target?lang=en){target=_blank} en la guía de *Experience Manager as a Cloud Service*.
* **[!DNL AEM]6.5**: [exportación de un fragmento de experiencia a Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=es){target=_blank} en la documentación de *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4**: [exportación de un fragmento de experiencia a Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html?lang=es){target=_blank} en la documentación de *Adobe Experience Manager 6.4*.

## Usando [!UICONTROL Experience Fragments] en [!DNL Target] actividades {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Después de realizar las tareas anteriores, [!UICONTROL Experience Fragment] se muestra en la página [!UICONTROL Offers] de [!DNL Target].

[!DNL Target] busca actualmente [!UICONTROL Experience Fragments] para importar cada diez minutos. El objeto [!UICONTROL Experience Fragment] importado debería estar disponible en [!DNL Target] en un plazo de diez minutos, pero este lapso de tiempo debería ser menor en adelante.

[!UICONTROL Experience Fragment] se ha importado en [!DNL Target] como una oferta HTML o JSON. La versión &quot;principal&quot; de [!UICONTROL Experience Fragment] permanece en [!DNL AEM]. No puede editar [!UICONTROL Experience Fragment] en [!DNL Target].

Puede filtrar y buscar por [!UICONTROL HTML XFs] y [!UICONTROL JSON XFs] para distinguir entre [!UICONTROL Experience Fragment] tipos que se exportan a [!DNL Target].

![Filtrar por tipos de Fragmento de experiencia: HTML o JSON en la IU de Target](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Puede pasar el ratón sobre un(a) [!UICONTROL Experience Fragment] de la lista y, a continuación, hacer clic en el icono [!UICONTROL View] ![icono de información](/help/main/assets/icons/InfoOutline.svg) para ver información adicional sobre [!UICONTROL Experience Fragment], incluida su información de [!UICONTROL Name], [!UICONTROL Type], [!UICONTROL Offer ID], [!UICONTROL Offer path] y últimas modificaciones. Haga clic en [!UICONTROL [!UICONTROL View Full Details]] para ver las actividades que hacen referencia a esta oferta.

![Elemento emergente de información de Fragmento de experiencia](/help/main/c-integrating-target-with-mac/aem/assets/xf-info-popup.png)

Puede consumir [!UICONTROL Experience Fragments] en [!DNL Target] actividades usando [Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) y [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md).

>[!TIP]
>
>Use inteligencia artificial, aprendizaje automático y recomendaciones con [!UICONTROL Experience Fragments]:
>
>* Para utilizar completamente las funcionalidades de IA y ML de [!DNL Target], puede seleccionar [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) o [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) al crear una actividad.
>
>* [!UICONTROL Experience Fragments] no son compatibles con las actividades [!DNL Recommendations]. Sin embargo, para usar [!UICONTROL Experience Fragments] para Recommendations, puede crear una actividad [!UICONTROL A/B Test] (que incluye [!UICONTROL Auto-Allocate] y [!UICONTROL Auto-Target]) o una actividad [!UICONTROL Experience Targeting] (XT) e [incluir recomendaciones como oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).

**Para consumir [!UICONTROL Experience Fragments] usando el VEC:**

1. En [!DNL Target], mientras crea o edita una experiencia en el [Compositor de experiencias visuales](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), haga clic en la ubicación de la página donde desea insertar contenido de [!DNL AEM] y, a continuación, haga clic en **[!UICONTROL Replace Content]** > **[!UICONTROL Experience Fragment]** para mostrar el cuadro de diálogo [!UICONTROL Experience Fragment].

   El cuadro de diálogo [!UICONTROL Experience Fragment] muestra el contenido creado en [!DNL AEM] que ahora está disponible de forma nativa dentro de [!DNL Target].

   >[!NOTE]
   >
   >La opción [!UICONTROL Replace Content] no está disponible para imágenes. Si desea utilizar esta opción con una imagen, haga clic en el elemento contenedor que contenga la imagen deseada.

   ![experience_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

1. Seleccione el(la) [!UICONTROL Experience Fragment] que desee y luego haga clic en **[!UICONTROL Add]**.
1. Termine de configurar la actividad.

   Para obtener más información acerca de la configuración de los distintos tipos de actividad, consulte los temas siguientes:

   * **Prueba A/B:** [Crear una prueba A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **Asignación automática:** [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Segmentación automática:** [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Personalización automatizada (AP):** [Creación de una actividad de personalización automatizada](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Segmentación de experiencias (XT):** [Crear una actividad de segmentación de experiencias](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Recomendaciones en una actividad de Prueba A/B o XT:** [Recomendaciones como oferta](/help/main/c-recommendations/recommendations-as-an-offer.md)

   [!UICONTROL Experience Fragments] exportado como JSON en [!DNL Target] no se puede usar en actividades creadas con el VEC; solo HTML [!UICONTROL Experience Fragments] es compatible con actividades basadas en VEC. Si desea usar JSON [!UICONTROL Experience Fragments], utilícelos en actividades creadas con [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md).

**Para consumir [!UICONTROL Experience Fragments] usando [!UICONTROL Form-based Experience Composer]:**

1. En [!DNL Target], mientras crea o edita una experiencia en el [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), seleccione la ubicación de la página donde desea insertar contenido de [!DNL AEM], haga clic en el icono **[!UICONTROL More Details]** ( ![icono Más detalles](/help/main/assets/icons/MoreSmall.svg) ) y, a continuación, seleccione **[!UICONTROL Change Experience Fragment]** para mostrar el cuadro de diálogo [!UICONTROL Change Experience Fragment].

   ![experience_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

   El cuadro de diálogo [!UICONTROL Experience Fragment] muestra el contenido creado en [!DNL AEM] que ahora está disponible de forma nativa dentro de [!DNL Target].

1. Seleccione el(la) [!UICONTROL Experience Fragment] que desee y luego haga clic en **[!UICONTROL Add]**.
1. Termine de configurar la actividad.

## Información adicional

* [!DNL Target] busca actualmente [!UICONTROL Experience Fragments] para importar cada diez minutos. El objeto [!UICONTROL Experience Fragment] importado debería estar disponible en [!DNL Target] en un plazo de diez minutos, pero este lapso de tiempo debería ser menor en adelante.
* [!UICONTROL Experience Fragment] se ha importado en [!DNL Target] como una oferta HTML o JSON. La versión &quot;principal&quot; de [!UICONTROL Experience Fragment] permanece en [!DNL AEM]. No puede editar [!UICONTROL Experience Fragment] en [!DNL Target].
* No puede crear [!UICONTROL Experience Fragments] con [!DNL Adobe Developer]. Cree [!UICONTROL Experience Fragments] mediante AEM, como se explicó anteriormente.
* Si actualiza su [!UICONTROL Experience Fragment] en AEM, el [!UICONTROL Experience Fragment] debe publicarse y exportarse de nuevo a [!DNL Target] para que [!DNL Target] pueda utilizar los cambios más recientes.

## Eliminando clientlibs y HTML superfluos de [!UICONTROL Experience Fragments] exportados a [!UICONTROL Target]

Al usar ofertas [!UICONTROL Experience Fragment] con [!DNL Target] en una página entregada por AEM, la página de destino ya contiene las bibliotecas de cliente necesarias. Tenga en cuenta también que tampoco son necesarios los elementos HTML prescindibles de la oferta.

A veces, páginas completas de HTML envuelven a [!UICONTROL Experience Fragment] y causan problemas. Asegúrese de que [!UICONTROL Experience Fragment] sea una parte pequeña de HTML y no una página de HTML completa con HTML, HEAD, BODY, etc.

Para obtener más información, vea la siguiente publicación de blog: [AEM 6.5: Quitar clientlibs de [!UICONTROL Experience Fragments] exportados a Target](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser/){target=_blank}.

## Vídeo de formación: Uso de AEM [!UICONTROL Experience Fragments] con [!DNL Adobe Target]

El siguiente vídeo muestra cómo configurar y utilizar [!UICONTROL Experience Fragments]:

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>Se ha eliminado la característica de vínculo profundo [!DNL AEM] que se discutió en 4:54.

Para obtener información más detallada, consulte [Uso de [!UICONTROL Experience Fragments] con Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html?lang=es) en la página *Vídeos y tutoriales de AEM Sites*.
