---
keywords: experiencia;json;aem;adobe experience manager;exportar a adobe target;fragmentos de experiencias;fragmentos;XF
description: Aprenda a usar [!DNL Adobe Experience Manager] [!UICONTROL Fragmentos de experiencias] en [!DNL Adobe Target] actividades.
title: ¿Cómo Uso  [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Fragmentos De Experiencia]?
feature: Integrations
exl-id: 400d0cde-e435-4cac-9bf0-64a6cad98995
TQID: https://experienceleague.adobe.com/-W1ELJx0ajes6BPEVIiS8q6ebmRLTTgIrxvGMUEWEaM
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
topic_v2:
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1446
ht-degree: 32%

---

# [!UICONTROL Fragmentos de experiencias] de AEM

Use [!UICONTROL Fragmentos de experiencias] (XF) creados en [!DNL Adobe Experience Manager] (AEM) en [!DNL Target] actividades para ayudar en la optimización y personalización.

## Consideraciones

Tenga en cuenta lo siguiente al trabajar con AEM [!UICONTROL Fragmentos de experiencias] en [!DNL Target]:

* Esta función requiere que sea cliente de [!DNL Adobe Experience Manager] (AEM). Para obtener más información, consulte [Requisitos](#section_AE6F0971E1574B3AA324003599B96E5A) más adelante.
* [!UICONTROL Fragmentos de experiencias] y [!UICONTROL Fragmentos de contenido] están disponibles para los siguientes tipos de actividades:

   * [[!UICONTROL Prueba A/B]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Asignación automática]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Segmentación automática]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Segmentación de experiencias] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL Fragmentos de experiencias] y [!UICONTROL Fragmentos de contenido] no están disponibles para los siguientes tipos de actividades:

   * [[!UICONTROL Prueba multivariada] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* Puede consumir [!UICONTROL Fragmentos de experiencias] en [!DNL Target] actividades usando el [Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) y el [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md).

Para obtener más información sobre los [!UICONTROL fragmentos de experiencias] y [!UICONTROL fragmentos de contenido] de AEM, consulte [Fragmentos de experiencias[[!UICONTROL 6 de AEM y la descripción general de los fragmentos de contenido]](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).]

## Requisitos {#requirements}

Debe contar con la funcionalidad [!UICONTROL Fragmentos de experiencias] dentro de [!DNL Target]. Además, debe utilizar [!DNL AEM] as a Cloud Service o [!DNL AEM] 6.4 (o posterior). El representante de cuentas puede ayudar a garantizar el cumplimiento de los requisitos para usar esta función:

* [!DNL Adobe Experience Manager] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5
* [!DNL Adobe Experience Manager] 6.4
* Cuenta de [!DNL Adobe Target Standard] o [!DNL Adobe Target Premium]

[!DNL Adobe Experience Manager] 6.3 y 6.4 han llegado al final de su vida útil y ya no son compatibles (excepto para los clientes que compraron soporte ampliado).

Póngase en contacto con el [Servicio de atención al cliente de Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para habilitar la integración y poder proporcionarle los datos de autenticación.

## Creando y configurando [!UICONTROL fragmentos de experiencias] en [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Para usar [!DNL AEM] [!UICONTROL Fragmentos de experiencias] en [!DNL Target], debe realizar los siguientes pasos:

### Paso 1: Integrar [!DNL AEM] con [!DNL Target]

Para obtener más información, consulte:

* **AEM as a Cloud Service**: [Integración con Adobe Target](https://experienceleague.adobe.com/es/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target){target=_blank} en la guía de *Experience Manager as a Cloud Service*.
* **Adobe Developer**: [Integración con Adobe Target mediante Adobe I/0](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-target-ims-adobe-io.html?lang=es){target=_blank} en la *Guía del usuario de administración*.
* **[!DNL AEM]6.5**: [participar en Adobe Analytics y Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=es){target=_blank} en la documentación de *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4**: [participar en Adobe Analytics y Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=es){target=_blank} en la documentación de *Adobe Experience Manager 6.4*.

### Paso 2: Crear el fragmento de experiencia

[!UICONTROL Los fragmentos de experiencias] se han creado en [!DNL AEM]. Para obtener más información, consulte:

* **AEM as a Cloud Service**: [[!UICONTROL Fragmentos de experiencias]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=es){target=_blank} en la guía de *Experience Manager as a Cloud Service*.
* **[!DNL AEM]6.5**: [[!UICONTROL Fragmentos de experiencia]](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=es){target=_blank} en la documentación de *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4**: [[!UICONTROL Fragmentos de experiencia]](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=es){target=_blank} en la documentación de *Adobe Experience Manager 6.4*.

### Paso 3: Configurar [!DNL AEM] para que comparta [!UICONTROL Fragmento de experiencia] con [!DNL Target]

1. En [!DNL AEM], seleccione el [!UICONTROL Fragmento de experiencia] deseado o su carpeta contenedora y luego haga clic en **[!UICONTROL Propiedades]**.
2. Haga clic en la ficha **[!UICONTROL Cloud Services]** y, a continuación, en la lista desplegable **[!UICONTROL Configuración de Cloud Service]**, seleccione **[!UICONTROL Adobe Target]**.

   El paso anterior supone que alguien en su organización ha creado la configuración de [!DNL Adobe Target].

3. Haga clic en **[!UICONTROL Guardar y cerrar]**.

### Paso 4: Publicar [!UICONTROL Fragmento de experiencia] y exportarlo en [!DNL Target]

Según su versión de [!DNL AEM], consulte los siguientes vínculos para obtener instrucciones paso a paso:

* **AEM as a Cloud Service**: [Exportando [!UICONTROL fragmentos de experiencias] a Adobe Target](https://experienceleague.adobe.com/es/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target?lang=en){target=_blank} en la guía de *Experience Manager as a Cloud Service*.
* **[!DNL AEM]6.5**: [exportación de un fragmento de experiencia a Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=es){target=_blank} en la documentación de *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4**: [exportación de un fragmento de experiencia a Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html?lang=es){target=_blank} en la documentación de *Adobe Experience Manager 6.4*.

## Usando [!UICONTROL fragmentos de experiencias] en [!DNL Target] actividades {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Después de realizar las tareas anteriores, [!UICONTROL Fragmento de experiencia] se muestra en la página [!UICONTROL Ofertas] de [!DNL Target].

[!DNL Target] busca [!UICONTROL Fragmentos de experiencia] para importar cada diez minutos. El [!UICONTROL fragmento de experiencia] importado debería estar disponible en [!DNL Target] en un plazo de diez minutos, pero este lapso de tiempo debería ser menor en adelante.

El [!UICONTROL fragmento de experiencia] se ha importado a [!DNL Target] como una oferta HTML o JSON. La versión &quot;principal&quot; del [!UICONTROL Fragmento de experiencia] permanece en [!DNL AEM]. No puede editar el [!UICONTROL Fragmento de experiencia] en [!DNL Target].

Puede filtrar y buscar por [!UICONTROL XF de HTML] y [!UICONTROL XF de JSON] para ayudarle a distinguir entre los tipos de [!UICONTROL fragmento de experiencia] que se exportan a [!DNL Target].

![Filtrar por tipos de Fragmento de experiencia: HTML o JSON en la IU de Target](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Puede pasar el ratón sobre un [!UICONTROL Fragmento de experiencia] de la lista y luego hacer clic en el icono [!UICONTROL Ver] ![Icono de información](/help/main/assets/icons/InfoOutline.svg) para ver información adicional sobre el [!UICONTROL Fragmento de experiencia], incluido su [!UICONTROL Nombre], [!UICONTROL Tipo], [!UICONTROL ID de oferta], [!UICONTROL Ruta de oferta] e información de las últimas modificaciones. Haga clic en [!UICONTROL [!UICONTROL Ver detalles completos]] para ver las actividades que hacen referencia a esta oferta.

![Elemento emergente de información de Fragmento de experiencia](/help/main/c-integrating-target-with-mac/aem/assets/xf-info-popup.png)

Puede consumir [!UICONTROL Fragmentos de experiencias] en [!DNL Target] actividades usando el [Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) y el [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md).

>[!TIP]
>
>Use inteligencia artificial, aprendizaje automático y recomendaciones con [!UICONTROL Fragmentos de experiencias]:
>
>* Para utilizar completamente las funcionalidades de IA y ML de [!DNL Target], puede seleccionar [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) o [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) al crear una actividad.
>
>* [!UICONTROL Los fragmentos de experiencias] no son compatibles con las actividades [!DNL Recommendations]. Sin embargo, para usar [!UICONTROL Fragmentos de experiencias] para Recommendations, puede crear una actividad de [!UICONTROL Prueba A/B] (que incluye [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática]) o una actividad de [!UICONTROL Segmentación de experiencias] (XT) e [incluir recomendaciones como oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).

**Para consumir [!UICONTROL Fragmentos de experiencia] usando el VEC:**

1. En [!DNL Target], mientras crea o edita una experiencia en el [Compositor de experiencias visuales](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), haga clic en la ubicación de la página donde desea insertar contenido de [!DNL AEM] y, a continuación, haga clic en **[!UICONTROL Reemplazar contenido]** > **[!UICONTROL Fragmento de experiencias]** para mostrar el cuadro de diálogo [!UICONTROL Fragmento de experiencias].

   El cuadro de diálogo [!UICONTROL Fragmento de experiencia] muestra el contenido creado en [!DNL AEM] que ahora está disponible de forma nativa dentro de [!DNL Target].

   >[!NOTE]
   >
   >La opción [!UICONTROL Reemplazar contenido] no está disponible para imágenes. Si desea utilizar esta opción con una imagen, haga clic en el elemento contenedor que contenga la imagen deseada.

   ![experience_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

1. Seleccione el [!UICONTROL Fragmento de experiencia] que desee y haga clic en **[!UICONTROL Agregar]**.
1. Termine de configurar la actividad.

   Para obtener más información acerca de la configuración de los distintos tipos de actividad, consulte los temas siguientes:

   * **Prueba A/B:** [Crear una prueba A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **Asignación automática:** [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Segmentación automática:** [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Personalización automatizada (AP):** [Creación de una actividad de personalización automatizada](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Segmentación de experiencias (XT):** [Crear una actividad de segmentación de experiencias](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Recomendaciones en una actividad de Prueba A/B o XT:** [Recomendaciones como oferta](/help/main/c-recommendations/recommendations-as-an-offer.md)

   Los [!UICONTROL fragmentos de experiencias] exportados como JSON en [!DNL Target] no se pueden usar en actividades creadas con el VEC; solo los [!UICONTROL fragmentos de experiencias] de HTML son compatibles con actividades basadas en VEC. Si desea usar [!UICONTROL Fragmentos de experiencias] de JSON, utilícelos en actividades creadas con [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md).

**Para consumir [!UICONTROL Fragmentos de experiencia] usando el [!UICONTROL Compositor de experiencias basadas en formularios]:**

1. En [!DNL Target], mientras crea o edita una experiencia en el [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), seleccione la ubicación de la página donde desea insertar contenido de [!DNL AEM], haga clic en el icono **[!UICONTROL Más detalles]** ( ![icono Más detalles](/help/main/assets/icons/MoreSmall.svg) ) y, a continuación, seleccione **[!UICONTROL Cambiar fragmento de experiencia]** para mostrar el cuadro de diálogo [!UICONTROL Cambiar fragmento de experiencia].

   ![experience_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

   El cuadro de diálogo [!UICONTROL Fragmento de experiencia] muestra el contenido creado en [!DNL AEM] que ahora está disponible de forma nativa dentro de [!DNL Target].

1. Seleccione el [!UICONTROL Fragmento de experiencia] que desee y haga clic en **[!UICONTROL Agregar]**.
1. Termine de configurar la actividad.

## Información adicional

* [!DNL Target] busca [!UICONTROL Fragmentos de experiencia] para importar cada diez minutos. El [!UICONTROL fragmento de experiencia] importado debería estar disponible en [!DNL Target] en un plazo de diez minutos, pero este lapso de tiempo debería ser menor en adelante.
* El [!UICONTROL fragmento de experiencia] se ha importado a [!DNL Target] como una oferta HTML o JSON. La versión &quot;principal&quot; del [!UICONTROL Fragmento de experiencia] permanece en [!DNL AEM]. No puede editar el [!UICONTROL Fragmento de experiencia] en [!DNL Target].
* No puede crear [!UICONTROL Fragmentos de experiencias] con [!DNL Adobe Developer]. Cree [!UICONTROL fragmentos de experiencias] con AEM, tal como se explicó anteriormente.
* Si actualiza el [!UICONTROL Fragmento de experiencia] en AEM, el [!UICONTROL Fragmento de experiencia] debe publicarse y exportarse de nuevo a [!DNL Target] para que [!DNL Target] pueda usar los cambios más recientes.

## Eliminando clientlibs y HTML prescindibles de [!UICONTROL Fragmentos de experiencia] exportados a [!UICONTROL Target]

Al usar [!UICONTROL ofertas de fragmento de experiencia] con [!DNL Target] en una página entregada por AEM, la página de destino ya contiene las bibliotecas de cliente necesarias. Tenga en cuenta también que tampoco son necesarios los elementos HTML prescindibles de la oferta.

A veces, páginas completas de HTML envuelven [!UICONTROL Fragmento de experiencia] y causan problemas. Asegúrese de que [!UICONTROL Fragmento de experiencia] sea un fragmento pequeño de HTML y no una página de HTML completa con HTML, HEAD, BODY, etc.

Para obtener más información, consulte la siguiente publicación de blog: [AEM 6.5: Eliminación de clientlibs de [!UICONTROL Fragmentos de experiencias] exportados a Target](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser/){target=_blank}.

## Vídeo de formación: Uso de [!UICONTROL Fragmentos de experiencias] de AEM con [!DNL Adobe Target]

El siguiente vídeo muestra cómo configurar y utilizar [!UICONTROL Fragmentos de experiencias]:

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>Se ha eliminado la característica de vínculo profundo [!DNL AEM] que se discutió en 4:54.

Para obtener información más detallada, consulta [Uso de [!UICONTROL fragmentos de experiencias] con Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html?lang=es) en la página *Vídeos y tutoriales de AEM Sites*.
