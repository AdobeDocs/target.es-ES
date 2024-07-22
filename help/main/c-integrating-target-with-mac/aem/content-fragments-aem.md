---
keywords: experiencia;json;aem;adobe experience manager;exportar a adobe target;fragmentos de contenido;fragmentos;CF;cf;sin encabezado;personalización;experimentación
description: Aprenda a usar  [!DNL Adobe Experience Manager] [!UICONTROL Content Fragments] en  [!DNL Adobe Target] actividades.
title: AEM ¿Cómo Se Usa  [!DNL Adobe Experience Manager] () [!UICONTROL Content Fragments]?
feature: Integrations
exl-id: 2057d9fe-c0f9-41d5-82e1-529db9ef7ca5
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 21%

---

# AEM [!UICONTROL Content Fragments]

AEM Utilice [!UICONTROL Content Fragments] (CF) creados en [!DNL Adobe Experience Manager] () en [!DNL Target] actividades para ayudar en la personalización y experimentación sin encabezado.

## Consideraciones

AEM Tenga en cuenta lo siguiente cuando trabaje con el cliente [!UICONTROL Content Fragments] en [!DNL Target]:

* Esta función requiere que sea cliente de [!DNL Adobe Experience Manager as a Cloud Service]. Para obtener más información, consulte [Requisitos](#section_AE6F0971E1574B3AA324003599B96E5A) más adelante.
* [!UICONTROL Experience Fragments] y [!UICONTROL Content Fragments] están disponibles para los siguientes tipos de actividades:

   * [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Experience Targeting] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL Experience Fragments] y [!UICONTROL Content Fragments] no están disponibles para los siguientes tipos de actividades:

   * [[!UICONTROL Multivariate Test] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* Solo puede consumir [!UICONTROL Content Fragments] en [!DNL Target] actividades usando el [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md). Usted *no puede* consumir [!UICONTROL Content Fragments] en [!DNL Target] actividades usando el [!UICONTROL Visual Experience Composer] (VEC).

AEM AEM Para obtener más información acerca de la información general de [!UICONTROL Content Fragments] y [!UICONTROL Experience Fragments], consulte [Información general de [!UICONTROL Experience Fragments] y [!UICONTROL Content Fragments] de la ](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Requisitos {#requirements}

Debe utilizar [[!DNL AEM] as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=es){target=_blank}. El representante de cuentas puede ayudar a garantizar el cumplimiento de los requisitos para usar esta función:

Póngase en contacto con el [Servicio de atención al cliente de Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para habilitar la integración y poder proporcionarle los datos de autenticación.

## Configurando y trabajando con [!UICONTROL Content Fragments] en [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

AEM Para exportar [!UICONTROL Content Fragments] para su uso en [!DNL Target] actividades, debe realizar algunos pasos preliminares en la creación de informes de la. Para obtener más información, consulte [Exportación de fragmentos de contenido a Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html?lang=es){target=_blank} en la *Documentación de Experience Manager as a Cloud Service*.

Para obtener información sobre cómo diseñar, crear, depurar y publicar [!UICONTROL Content Fragments], consulte [[!UICONTROL Content Fragments]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=es){target=_blank} y [Trabajar con fragmentos de contenido](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html?lang=es){target=_blank} en la [documentación as a Cloud Service del Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html?lang=es){target=_blank}.

## Usando [!UICONTROL Content Fragments] en [!DNL Target] actividades {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Después de realizar las tareas anteriores, [!UICONTROL Content Fragment] se muestra en la página [!UICONTROL Offers] de [!DNL Target].

[!DNL Target] busca actualmente [!UICONTROL Content Fragments] para importar cada diez minutos. El objeto [!UICONTROL Content Fragment] importado debería estar disponible en [!DNL Target] en un plazo de diez minutos, pero este lapso de tiempo debería ser menor en adelante.

[!UICONTROL Content Fragment] se importó en [!DNL Target] como una oferta JSON. La versión &quot;principal&quot; de [!UICONTROL Content Fragment] permanece en [!DNL AEM]. No puede editar [!UICONTROL Content Fragment] en [!DNL Target].

Puede filtrar y buscar por [!UICONTROL HTML XFs], [!UICONTROL JSON XFs] y [!UICONTROL Content Fragments] para ayudarle a distinguir entre los distintos tipos de ofertas que se exportan a [!DNL Target].

![Filtrar por tipos de fragmento de contenido: HTML o JSON en la IU de Target](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Puede pasar el ratón sobre un(a) [!UICONTROL Content Fragment] de la lista y, a continuación, hacer clic en el icono [!UICONTROL View] ![icono de información](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) para ver información adicional sobre [!UICONTROL Content Fragment], incluidos sus [!UICONTROL AEM path] y [!UICONTROL AEM deep link]. Haga clic en la ficha [!UICONTROL Offer Usage] para ver las actividades que hacen referencia a esta oferta.

![Elemento emergente de información de fragmento de contenido](/help/main/c-integrating-target-with-mac/aem/assets/cf-info-popup.png)

Solo puede consumir [!UICONTROL Content Fragments] en [!DNL Target] actividades usando el [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md). Usted *no puede* consumir [!UICONTROL Content Fragments] en [!DNL Target] actividades usando el [Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC). [!UICONTROL Content Fragments] se exportan como JSON en [!DNL Target] y no se pueden usar en actividades creadas con el VEC.

>[!TIP]
>
>Use inteligencia artificial, aprendizaje automático y recomendaciones con [!UICONTROL Content Fragments]:
>
>* Para usar completamente la funcionalidad AI y ML de [!DNL Target], puede seleccionar [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) o [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) al crear una actividad [!UICONTROL A/B Test].
>
>* [!UICONTROL Content Fragments] no son compatibles con las actividades [!DNL Recommendations]. Sin embargo, para usar [!UICONTROL Content Fragments] para Recommendations, puede crear una actividad [!UICONTROL A/B Test] (que incluye [!UICONTROL Auto-Allocate] y [!UICONTROL Auto-Target]) o una actividad [!UICONTROL Experience Targeting] (XT) e [incluir recomendaciones como oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).

**Para consumir [!UICONTROL Content Fragments] usando [!UICONTROL Form-based Experience Composer]:**

1. En [!DNL Target], mientras crea o edita una experiencia en el [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), seleccione la ubicación de la página donde desea insertar contenido de [!DNL AEM] y, a continuación, seleccione **[!UICONTROL Change Content Fragment]** para mostrar la lista [!UICONTROL Choose a Content Fragment].

   ![content_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   La lista [!UICONTROL Content Fragment] muestra el contenido creado en [!DNL AEM] que ahora está disponible de forma nativa dentro de [!DNL Target].

1. Seleccione el(la) [!UICONTROL Content Fragment] que desee y luego haga clic en **[!UICONTROL Save]**.
1. Termine de configurar la actividad.

## Información adicional

* [!DNL Target] busca actualmente [!UICONTROL Content Fragments] para importar cada diez minutos. El objeto [!UICONTROL Content Fragment] importado debería estar disponible en [!DNL Target] en un plazo de diez minutos, pero este lapso de tiempo debería ser menor en adelante.
* [!UICONTROL Content Fragment] se importó en [!DNL Target] como una oferta JSON. La versión &quot;principal&quot; de [!UICONTROL Content Fragment] permanece en [!DNL AEM]. No puede editar [!UICONTROL Content Fragment] en [!DNL Target].
* No puede crear [!UICONTROL Content Fragments] con [!DNL Adobe I/O]. AEM Cree [!UICONTROL Content Fragments] mediante el uso de la función de búsqueda, tal como se explica más arriba.
* AEM Si actualiza su [!UICONTROL Content Fragment] en la, el [!UICONTROL Content Fragment] debe publicarse y exportarse de nuevo a [!DNL Target] para que [!DNL Target] pueda utilizar los cambios más recientes.
