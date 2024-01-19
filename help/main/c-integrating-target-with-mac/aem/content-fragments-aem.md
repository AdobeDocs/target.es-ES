---
keywords: experiencia;json;aem;adobe experience manager;exportar a adobe target;fragmentos de contenido;fragmentos;CF;cf;sin encabezado;personalización;experimentación
description: Aprenda a utilizar fragmentos de contenido de [!DNL Adobe Experience Manager] [!UICONTROL ] en actividades de [!DNL Adobe Target] .
title: ¿Cómo uso [!UICONTROL fragmentos de contenido] de [!DNL Adobe Experience Manager] (AEM)?
feature: Integrations
exl-id: 2057d9fe-c0f9-41d5-82e1-529db9ef7ca5
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 97%

---

# [!UICONTROL Fragmentos de contenido] de AEM

Use [!UICONTROL fragmentos de contenido] (CF) creados en [!DNL Adobe Experience Manager] (AEM) en actividades de [!DNL Target] para ayudar en la optimización o personalización.

## Consideraciones

Tenga en cuenta lo siguiente cuando trabaje con [!UICONTROL fragmentos de contenido] de AEM en [!DNL Target]:

* Esta función requiere que sea cliente de [!DNL Adobe Experience Manager as a Cloud Service]. Para obtener más información, consulte [Requisitos](#section_AE6F0971E1574B3AA324003599B96E5A) más adelante.
* Los [!UICONTROL Fragmentos de experiencias] y [!UICONTROL Fragmentos de contenido] están disponibles para los siguientes tipos de actividades:

   * [[!UICONTROL Prueba A/B]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Asignación automática]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Segmentación automática]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Segmentación de experiencias] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* Los [!UICONTROL Fragmentos de experiencias] y [!UICONTROL Fragmentos de contenido] no están disponibles para los siguientes tipos de actividades:

   * [[!UICONTROL Prueba multivariada] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* Puede consumir [!UICONTROL fragmentos de contenido] en actividades de [!DNL Target] solo con el [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md). *No* puede consumir [!UICONTROL fragmentos de contenido] en actividades de [!DNL Target] utilizando el [!UICONTROL Compositor de experiencias visuales] (VEC).

Para obtener más información acerca de los [!UICONTROL fragmentos de contenido] y [!UICONTROL fragmentos de experiencias] de AEM, consulte la información general de [[!UICONTROL fragmentos de experiencias] y [!UICONTROL fragmentos de contenido] de AEM](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Requisitos  {#requirements}

Debe utilizar [[!DNL AEM] as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html){target=_blank}. El representante de cuentas puede ayudar a garantizar el cumplimiento de los requisitos para usar esta función:

Póngase en contacto con el [Servicio de atención al cliente de Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para habilitar la integración y poder proporcionarle los datos de autenticación.

## Configuración y trabajo con [!UICONTROL fragmentos de contenido] en [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Para exportar [!UICONTROL fragmentos de contenido] para usarlos en [!DNL Target], debe realizar algunos pasos preliminares en AEM. Para obtener más información, consulte [Exportación de fragmentos de contenido a Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html?lang=es){target=_blank} en la *Documentación de Experience Manager as a Cloud Service*.

Para obtener información acerca del diseño, la creación, la depuración y la publicación de [!UICONTROL fragmentos de contenido], consulte [[!UICONTROL Fragmentos de contenido]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=es){target=_blank} and [Working with Content Fragments](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html?lang=es){target=_blank} in the [Experience Manager as a Cloud Service documentation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html?lang=es){target=_blank}.

## Uso de [!UICONTROL fragmentos de contenido] en actividades de [!DNL Target] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Después de realizar las tareas anteriores, el [!UICONTROL fragmento de contenido] se muestra en la página [!UICONTROL Ofertas] de [!DNL Target].

[!DNL Target] actualmente busca [!UICONTROL fragmentos de contenido] para importar cada diez minutos. El [!UICONTROL fragmento de contenido] importado debería estar disponible en [!DNL Target] en unos diez minutos, pero este lapso de tiempo debería ser menor en adelante.

El [!UICONTROL fragmento de contenido] se importa a [!DNL Target] como oferta JSON. La versión “principal” del [!UICONTROL fragmento de contenido] permanece en [!DNL AEM]. No puede editar el [!UICONTROL fragmento de contenido] en [!DNL Target].

Puede filtrar y buscar por [!UICONTROL XF HTML], [!UICONTROL XF JSON] y [!UICONTROL Fragmentos de contenido] para ayudarle a distinguir entre los distintos tipos de ofertas que se exportan a [!DNL Target].

![Filtrar por tipos de fragmento de contenido: HTML o JSON en la IU de Target](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Puede pasar el ratón por encima de un [!UICONTROL fragmento de contenido] en la lista. A continuación, haga clic en el ![Icono de información](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) del icono [!UICONTROL Ver] para ver información adicional acerca del [!UICONTROL fragmento de contenido], incluidos su [!UICONTROL ruta de AEM] y [!UICONTROL vínculo profundo de AEM]. Haga clic en la pestaña [!UICONTROL Uso de ofertas] para ver las actividades que hacen referencia a esta oferta.

![Elemento emergente de información de fragmento de contenido](/help/main/c-integrating-target-with-mac/aem/assets/cf-info-popup.png)

Puede consumir [!UICONTROL fragmentos de contenido] en actividades de [!DNL Target] solo con el [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md). *No* puede consumir [!UICONTROL fragmentos de contenido] en actividades de [!DNL Target] utilizando el [Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC). Los [!UICONTROL fragmentos de contenido] se exportan como JSON en [!DNL Target] y no se pueden usar en actividades creadas con el VEC.

>[!TIP]
>
>Usar inteligencia artificial, aprendizaje automático y recomendaciones con [!UICONTROL fragmentos de contenido]:
>
>* Para utilizar completamente las funcionalidades de IA y ML de [!DNL Target], puede seleccionar [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) o [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) al crear una actividad de [!UICONTROL prueba A/B].
>
>* Los [!UICONTROL fragmentos de contenido] no son compatibles con las actividades de [!DNL Recommendations]. Sin embargo, para usar [!UICONTROL fragmentos de contenido] para recomendaciones, puede crear una actividad de [!UICONTROL Prueba A/B] (incluidas [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática]) o una de [!UICONTROL Segmentación de experiencias] (XT) e [incluir recomendaciones como oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).

**Para consumir [!UICONTROL fragmentos de contenido] usando el [!UICONTROL Compositor de experiencias basadas en formularios]:**

1. En [!DNL Target], mientras crea o edita una experiencia en el [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), seleccione el lugar de la página donde desea insertar contenido de [!DNL AEM] y, a continuación, seleccione **[!UICONTROL Cambiar fragmento de contenido]** para mostrar la lista [!UICONTROL Elegir un fragmento de contenido].

   ![content_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   La lista [!UICONTROL Fragmento de contenido] muestra el contenido creado en [!DNL AEM] que ahora está disponible de forma nativa dentro de [!DNL Target].

1. Seleccione el [!UICONTROL fragmento de contenido] deseado y, a continuación, haga clic en **[!UICONTROL Guardar]**.
1. Termine de configurar la actividad.

## Información adicional

* [!DNL Target] actualmente busca [!UICONTROL fragmentos de contenido] para importar cada diez minutos. El [!UICONTROL fragmento de contenido] importado debería estar disponible en [!DNL Target] en unos diez minutos, pero este lapso de tiempo debería ser menor en adelante.
* El [!UICONTROL fragmento de contenido] se importa a [!DNL Target] como oferta JSON. La versión “principal” del [!UICONTROL fragmento de contenido] permanece en [!DNL AEM]. No puede editar el [!UICONTROL fragmento de contenido] en [!DNL Target].
* No puede crear [!UICONTROL fragmentos de contenido] con [!DNL Adobe I/O]. Cree [!UICONTROL fragmentos de contenido] usando AEM, como se explica más arriba.
* Si actualiza su [!UICONTROL fragmento de contenido] en AEM, [!UICONTROL este] debe publicarse y exportarse a [!DNL Target] nuevamente, para que [!DNL Target] pueda utilizar los cambios más recientes.
