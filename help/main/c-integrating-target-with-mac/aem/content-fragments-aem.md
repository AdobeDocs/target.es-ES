---
keywords: experiencia;json;aem;adobe experience manager;exportar a adobe target;fragmentos de contenido;fragmentos;CF;cf;sin encabezado;personalización;experimentación
description: Aprenda a usar [!DNL Adobe Experience Manager] [!UICONTROL Fragmentos de contenido] en [!DNL Adobe Target] actividades.
title: ¿Cómo Uso  [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Fragmentos De Contenido]?
feature: Integrations
exl-id: 2057d9fe-c0f9-41d5-82e1-529db9ef7ca5
TQID: https://experienceleague.adobe.com/tb500kFSZoR3czs10Gs3EIOWEX2ybnd7tSWwDmWSMWQ
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
topic_v2:
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 775
ht-degree: 20%

---

# [!UICONTROL Fragmentos de contenido] de AEM

Use [!UICONTROL Fragmentos de contenido] (CF) creados en [!DNL Adobe Experience Manager] (AEM) en [!DNL Target] actividades para ayudar en la personalización y experimentación sin encabezado.

## Consideraciones

Tenga en cuenta lo siguiente al trabajar con AEM [!UICONTROL Fragmentos de contenido] en [!DNL Target]:

* Esta función requiere que sea cliente de [!DNL Adobe Experience Manager as a Cloud Service]. Para obtener más información, consulte [Requisitos](#section_AE6F0971E1574B3AA324003599B96E5A) más adelante.
* [!UICONTROL Fragmentos de experiencias] y [!UICONTROL Fragmentos de contenido] están disponibles para los siguientes tipos de actividades:

   * [[!UICONTROL Prueba A/B]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Asignación automática]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Segmentación automática]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Segmentación de experiencias] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL Fragmentos de experiencias] y [!UICONTROL Fragmentos de contenido] no están disponibles para los siguientes tipos de actividades:

   * [[!UICONTROL Prueba multivariada] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* Solo puede consumir [!UICONTROL fragmentos de contenido] en [!DNL Target] actividades usando el [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md). Usted *no puede* consumir [!UICONTROL fragmentos de contenido] en [!DNL Target] actividades usando el [!UICONTROL Compositor de experiencias visuales] (VEC).

Para obtener más información sobre [!UICONTROL Fragmentos de contenido] y [!UICONTROL Fragmentos de experiencia] de AEM, consulte [Fragmentos de experiencia[[!UICONTROL 6 y [!UICONTROL Fragmentos de contenido] de AEM]](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).]

## Requisitos {#requirements}

Debe estar usando [[!DNL AEM] as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=es){target=_blank}. El representante de cuentas puede ayudar a garantizar el cumplimiento de los requisitos para usar esta función:

Póngase en contacto con el [Servicio de atención al cliente de Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para habilitar la integración y poder proporcionarle los datos de autenticación.

## Configurando y trabajando con [!UICONTROL fragmentos de contenido] en [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Para exportar [!UICONTROL fragmentos de contenido] para usarlos en [!DNL Target] actividades, debe realizar algunos pasos preliminares en AEM. Para obtener más información, consulte [Exportación de fragmentos de contenido a Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html?lang=es){target=_blank} en la *documentación de Experience Manager as a Cloud Service*.

Para obtener información sobre cómo diseñar, crear, depurar y publicar [!UICONTROL fragmentos de contenido], consulte [[!UICONTROL Fragmentos de contenido]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=es){target=_blank} y [Trabajar con fragmentos de contenido](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html?lang=es){target=_blank} en la [documentación de Experience Manager as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html?lang=es){target=_blank}.

## Usando [!UICONTROL fragmentos de contenido] en [!DNL Target] actividades {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Después de realizar las tareas anteriores, [!UICONTROL Fragmento de contenido] se muestra en la página [!UICONTROL Ofertas] de [!DNL Target].

[!DNL Target] busca [!UICONTROL Fragmentos de contenido] para importar cada diez minutos. El [!UICONTROL fragmento de contenido] importado debería estar disponible en [!DNL Target] en un plazo de diez minutos, pero este lapso de tiempo debería ser menor en adelante.

El [!UICONTROL fragmento de contenido] se ha importado a [!DNL Target] como una oferta JSON. La versión &quot;principal&quot; del fragmento de contenido [!UICONTROL 1 permanece en [!DNL AEM]. &#x200B;]No puede editar el [!UICONTROL Fragmento de contenido] en [!DNL Target].

Puede filtrar y buscar por [!UICONTROL XF de HTML], [!UICONTROL XF de JSON] y [!UICONTROL Fragmentos de contenido] para ayudarle a distinguir entre los distintos tipos de ofertas que se exportan a [!DNL Target].

![Filtrar por tipos de fragmento de contenido: HTML o JSON en la IU de Target](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Puede pasar el ratón sobre un [!UICONTROL Fragmento de experiencia] de la lista y luego hacer clic en el icono [!UICONTROL Ver] ![Icono de información](/help/main/assets/icons/InfoOutline.svg) para ver información adicional sobre el [!UICONTROL Fragmento de contenido], incluido su [!UICONTROL Nombre], [!UICONTROL Tipo], [!UICONTROL ID de oferta], [!UICONTROL Ruta de oferta] e información de las últimas modificaciones. Haga clic en [!UICONTROL [!UICONTROL Ver detalles completos]] para ver las actividades que hacen referencia a esta oferta.

Solo puede consumir [!UICONTROL fragmentos de contenido] en [!DNL Target] actividades usando el [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md). Usted *no puede* consumir [!UICONTROL fragmentos de contenido] en [!DNL Target] actividades usando el [Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC). [!UICONTROL Los fragmentos de contenido] se exportan como JSON en [!DNL Target] y no se pueden usar en actividades creadas con el VEC.

>[!TIP]
>
>Use inteligencia artificial, aprendizaje automático y recomendaciones con [!UICONTROL fragmentos de contenido]:
>
>* Para usar completamente la funcionalidad de inteligencia artificial y aprendizaje automático [!DNL Target], puedes seleccionar [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) o [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) al crear una actividad de [!UICONTROL Prueba A/B].
>
>* [!UICONTROL Los fragmentos de contenido] no son compatibles con las actividades [!DNL Recommendations]. Sin embargo, para usar [!UICONTROL Fragmentos de contenido] para Recommendations, puede crear una actividad de [!UICONTROL Prueba A/B] (que incluye [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática]) o una actividad de [!UICONTROL Segmentación de experiencias] (XT) e [incluir recomendaciones como oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).

**Para consumir [!UICONTROL Fragmentos de contenido] usando el [!UICONTROL Compositor de experiencias basadas en formularios]:**

1. En [!DNL Target], mientras crea o edita una experiencia en el [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), seleccione la ubicación de la página donde desea insertar contenido de [!DNL AEM] y, a continuación, seleccione **[!UICONTROL Cambiar fragmento de contenido]** para mostrar la lista [!UICONTROL Elegir un fragmento de contenido].

   ![content_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   La lista [!UICONTROL Fragmento de contenido] muestra el contenido creado en [!DNL AEM] que ahora está disponible de forma nativa dentro de [!DNL Target].

1. Seleccione el [!UICONTROL Fragmento de contenido] deseado y luego haga clic en **[!UICONTROL Guardar]**.
1. Termine de configurar la actividad.

## Información adicional

* [!DNL Target] busca [!UICONTROL Fragmentos de contenido] para importar cada diez minutos. El [!UICONTROL fragmento de contenido] importado debería estar disponible en [!DNL Target] en un plazo de diez minutos, pero este lapso de tiempo debería ser menor en adelante.
* El [!UICONTROL fragmento de contenido] se ha importado a [!DNL Target] como una oferta JSON. La versión &quot;principal&quot; del fragmento de contenido [!UICONTROL 1 permanece en [!DNL AEM]. &#x200B;]No puede editar el [!UICONTROL Fragmento de contenido] en [!DNL Target].
* No puede crear [!UICONTROL Fragmentos de contenido] usando [!DNL Adobe I/O]. Cree [!UICONTROL fragmentos de contenido] mediante AEM, tal como se explicó anteriormente.
* Si actualiza el [!UICONTROL Fragmento de contenido] en AEM, el [!UICONTROL Fragmento de contenido] debe publicarse y exportarse de nuevo a [!DNL Target] para que [!DNL Target] pueda usar los cambios más recientes.
