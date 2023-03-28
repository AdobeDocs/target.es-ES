---
keywords: experiencia;json;aem;adobe experience manager;exportar a adobe target;fragmentos de contenido;fragmentos;CF;cf
description: Aprenda a utilizar [!DNL Adobe Experience Manager] [!UICONTROL Fragmentos de contenido] en [!DNL Adobe Target] actividades.
title: Cómo Uso [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Fragmentos de contenido]?
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip="What are Target Beta release features?"
feature: Integrations
source-git-commit: a29a52c38e80781697a9925bc1dd88bf9d99ebe1
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# AEM [!UICONTROL Fragmentos de contenido]

Uso [!UICONTROL Fragmentos de contenido] (CF) creados en [!DNL Adobe Experience Manager] (AEM) [!DNL Target] actividades para ayudar en la optimización o personalización.

>[!NOTE]
>
>Está previsto que esta función se publique el 6 de abril de 2023.


>[!NOTE]
>
>Tenga en cuenta lo siguiente cuando trabaje con AEM [!UICONTROL Fragmentos de contenido] en [!DNL Target]:
> 
>* Esta función requiere que [!DNL Adobe Experience Manager] (AEM) cliente. Para obtener más información, consulte [Requisitos](#section_AE6F0971E1574B3AA324003599B96E5A) más abajo.
>
>* Esta función está disponible para los siguientes tipos de actividades: [!UICONTROL Prueba A/B], [!UICONTROL Asignación automática], [!UICONTROL Segmentación automática], [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Segmentación de experiencias] (XT). Esta función no está disponible en [!UICONTROL Prueba multivariable] (MVT) y [!UICONTROL Recommendations] actividades.
>
>* Puede consumir [!UICONTROL Fragmentos de contenido] en [!DNL Target] actividades que usan la variable [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md) solo. No puede consumir [!UICONTROL Fragmentos de contenido] usando la variable [!UICONTROL Compositor de experiencias visuales] (VEC).


Para obtener más información sobre AEM [!UICONTROL Fragmentos de contenido] y [!UICONTROL Fragmentos de experiencias], consulte [AEM [!UICONTROL Fragmentos de experiencias] y [!UICONTROL Fragmentos de contenido] información general](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Requisitos.  {#requirements}

Debe estar aprovisionado con la variable [!UICONTROL Fragmentos de contenido] funcionalidad dentro de [!DNL Target]. Además, debe utilizar [!DNL AEM] as a Cloud Service. El representante de cuentas puede ayudar a garantizar el cumplimiento de los requisitos para usar esta función:

Póngase en contacto con el [Servicio de atención al cliente de Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para habilitar la integración y poder proporcionarle los datos de autenticación.

## Configuración y trabajo con [!UICONTROL Fragmentos de contenido] en [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Para exportar [!UICONTROL Fragmentos de contenido] para usar en [!DNL Target] , debe realizar algunos pasos preliminares en AEM. Para obtener más información, consulte [Exportación de fragmentos de contenido a Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html){target=_blank} en el *Documentación as a Cloud Service del Experience Manager*. Tenga en cuenta que este vínculo estará disponible el día de la versión (6 de abril de 2023)

Para obtener información sobre el diseño, la creación, la depuración y la publicación [!UICONTROL Fragmentos de contenido], consulte [[!UICONTROL Fragmentos de contenido]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=en){target=_blank} and [Working with Content Fragments](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html){target=_blank} in the [Experience Manager as a Cloud Service documentation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html){target=_blank}.

## Uso [!UICONTROL Fragmentos de contenido] en [!DNL Target] actividades {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Después de realizar las tareas anteriores, la variable [!UICONTROL Fragmento de contenido] se muestra en la [!UICONTROL Ofertas] en [!DNL Target].

[!DNL Target] está buscando [!UICONTROL Fragmentos de contenido] para importar cada diez minutos. La importación [!UICONTROL Fragmento de contenido] debe estar disponible en [!DNL Target] en diez minutos, pero este lapso de tiempo debería acortarse en el futuro.

La variable [!UICONTROL Fragmento de contenido] se importa a [!DNL Target] como oferta JSON. that [!UICONTROL Fragmento de contenido] La versión &quot;principal&quot; permanece en [!DNL AEM]. No se puede editar la variable [!UICONTROL Fragmento de contenido] en [!DNL Target].

Puede filtrar y buscar por [!UICONTROL XF de HTML], [!UICONTROL XF JSON]y [!UICONTROL Fragmentos de contenido] para ayudarle a distinguir entre los distintos tipos de ofertas que se exportan a [!DNL Target].

![Filtrar por tipos de fragmento de contenido: HTML o JSON en la interfaz de usuario de Target](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Puede pasar el ratón por encima de un [!UICONTROL Fragmento de contenido] en la lista y, a continuación, haga clic en la [!UICONTROL Ver] icono ![Icono de información](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) para ver información adicional sobre la variable [!UICONTROL Fragmento de contenido], incluido su [!UICONTROL AEM ruta] y [!UICONTROL AEM vínculo profundo]. Haga clic en el [!UICONTROL Uso de ofertas] para ver las actividades que hacen referencia a esta oferta.

![Elemento emergente de información de fragmento de contenido](/help/main/c-integrating-target-with-mac/aem/assets/cf-info-popup.png)

Puede consumir [!UICONTROL Fragmentos de contenido] en [!DNL Target] actividades que usan la variable [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md) solo. You *cannot* consume [!UICONTROL Fragmentos de contenido] en [!DNL Target] actividades que usan la variable [Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC). [!UICONTROL Fragmentos de contenido] se exportan como JSON en [!DNL Target] y no se pueden usar en actividades creadas con el VEC.

>[!TIP]
>
>Usar inteligencia artificial, aprendizaje automático y recomendaciones con [!UICONTROL Fragmentos de contenido]:
>
>* Para usar completamente el [!DNL Target] funcionalidad AI y ML, puede seleccionar [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) o [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) al crear una prueba A/B.
>
>* [!UICONTROL Fragmentos de contenido] no son compatibles con [!DNL Recommendations] actividades. Sin embargo, para usar [!UICONTROL Fragmentos de contenido] para recomendaciones, puede crear un [!UICONTROL Prueba A/B] actividad (incluida [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática]) o un [!UICONTROL Segmentación de experiencias] (XT) y [incluir recomendaciones como oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).


**Para consumir [!UICONTROL Fragmentos de contenido] usando la variable [!UICONTROL Compositor de experiencias basadas en formularios]:**

1. En [!DNL Target], mientras crea o edita una experiencia en la [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), seleccione la ubicación en la página donde desea insertar [!DNL AEM] contenido y, a continuación, seleccione **[!UICONTROL Cambiar fragmento de contenido]** para mostrar el [!UICONTROL Elegir un fragmento de contenido] lista.

   ![imagen content_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   La variable [!UICONTROL Fragmento de contenido] muestra el contenido creado en [!DNL AEM] que ahora está disponible de forma nativa desde [!DNL Target].

1. Seleccione el [!UICONTROL Fragmento de contenido]y haga clic en **[!UICONTROL Guardar]**.
1. Termine de configurar la actividad.

## Consideraciones {#considerations}

* [!DNL Target] está buscando [!UICONTROL Fragmentos de contenido] para importar cada diez minutos. La importación [!UICONTROL Fragmento de contenido] debe estar disponible en [!DNL Target] en diez minutos, pero este lapso de tiempo debería acortarse en el futuro.
* La variable [!UICONTROL Fragmento de contenido] se importa a [!DNL Target] como oferta JSON. La variable [!UICONTROL Fragmento de contenido] La versión &quot;principal&quot; permanece en [!DNL AEM]. No se puede editar la variable [!UICONTROL Fragmento de contenido] en [!DNL Target].
* No se puede crear [!UICONTROL Fragmentos de contenido] using [!DNL Adobe I/O]. Crear [!UICONTROL Fragmentos de contenido] usando AEM, como se explica más arriba.
* Si actualiza su [!UICONTROL Fragmento de contenido] en AEM, la variable [!UICONTROL Fragmento de contenido] debe publicarse y exportarse a [!DNL Target] nuevamente así [!DNL Target] puede utilizar los cambios más recientes.