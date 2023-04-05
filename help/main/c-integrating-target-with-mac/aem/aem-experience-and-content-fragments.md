---
keywords: aem;experience manager;adobe experience manager;integrar;integración;fragmentos de experiencia;fragmentos de contenido
description: Aprenda a utilizar fragmentos de experiencia y contenido de [!DNL Adobe Experience Manager] en actividades de [!DNL Adobe Target] .
title: ¿Cómo utilizo [!UICONTROL fragmentos de experiencia] y [!UICONTROL fragmentos de contenido] de  [!DNL Adobe Experience Manager] (AEM)?
feature: Integrations
source-git-commit: 0135831b56c48b0adca49e843c5ddd6574358aa4
workflow-type: ht
source-wordcount: '396'
ht-degree: 100%

---

# Información general de [!UICONTROL fragmentos de experiencias] y [!UICONTROL fragmentos de contenido] de AEM

Usar [!UICONTROL fragmentos de experiencias] (XF) y [!UICONTROL fragmentos de contenido] (CF) creados en [!DNL Adobe Experience Manager] (AEM) en actividades de [!DNL Target] para ayudar en la optimización o personalización.

>[!NOTE]
>
>Tenga en cuenta lo siguiente cuando trabaje con [!UICONTROL fragmentos de experiencias] y [!UICONTROL fragmentos de contenido] de AEM en [!DNL Target]:
> 
>* Estas funciones requieren que sea cliente de [!DNL Adobe Experience Manager] (AEM). Asegúrese de cumplir los requisitos para cada tipo de fragmento: [Fragmento de experiencia](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md#requirements) o [Fragmento de contenido](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md#requirements).
>
>* Estas funciones están disponibles para los siguientes tipos de actividades: [!UICONTROL Prueba A/B], [!UICONTROL Asignación automática], [!UICONTROL Segmentación automática], [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Segmentación de experiencias] (XT). Esta función no está disponible en actividades de [!UICONTROL Prueba multivariada] (MVT) y [!UICONTROL Recomendaciones].
>* Puede consumir [!UICONTROL Fragmentos de experiencias] en actividades de [!DNL Target] empleando el [Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) o el [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md).
>
>* Puede consumir [!UICONTROL Fragmentos de contenido] solo en el [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md).


El empleo de [!UICONTROL Fragmentos de experiencias] y [!UICONTROL Fragmentos de contenido] creados en [!DNL AEM] en actividades de [!DNL Target] le permite combinar la facilidad de uso y la potencia de [!DNL AEM] con eficaces capacidades de inteligencia artificial (IA) y de aprendizaje automático (ML) en [!DNL Target] para probar y personalizar experiencias a escala.

[!DNL AEM] aúna todos sus contenidos y recursos en una ubicación centralizada que potencia su estrategia de personalización. [!DNL AEM] le permite crear fácilmente contenido para equipos de escritorio, tabletas y dispositivos móviles en una misma ubicación y sin tener que escribir código. No es necesario crear páginas para cada dispositivo. [!DNL AEM] ajusta automáticamente cada experiencia de cada dispositivo con su contenido.

[!DNL Target] le permite ofrecer experiencias personalizadas a escala empleando una combinación de enfoques de aprendizaje automático basados en reglas y dirigidos por IA que incorporan variables de comportamiento, contextuales y sin conexión. Con [!DNL Target] puede configurar y ejecutar fácilmente actividades de [Pruebas A/B](/help/main/c-activities/t-test-ab/test-ab.md) y [Multivariadas](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) para determinar las mejores ofertas, contenidos y experiencias.

Los [!UICONTROL Fragmentos de experiencias] y los [!UICONTROL Fragmentos de contenido] representan un enorme paso adelante en el vínculo entre, por un lado, los creadores y gestores de contenido/experiencia y, por otro, los profesionales de la optimización y la personalización que mejoran los resultados empresariales con [!DNL Target].

## ¿Cuál es la diferencia entre [!UICONTROL Fragmentos de experiencias] y [!UICONTROL Fragmentos de contenido]?

Los [!UICONTROL Fragmentos de experiencias] y [!UICONTROL Fragmentos de contenido] de [!DNL Adobe Experience Manager] pueden parecer similares en la superficie, pero cada tipo desempeña funciones clave en diferentes casos de uso.

Para obtener más información acerca de cómo los [!UICONTROL Fragmentos de contenido] y [!UICONTROL Fragmentos de experiencias] son similares pero diferentes y cuándo y cómo usar cada uno, vea [Comprensión de los [!UICONTROL fragmentos de contenido] y [!UICONTROL fragmentos de experiencias]](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/content-fragments/understand-content-fragments-and-experience-fragments.html?lang=es){target=_blank} in the [AEM Sites videos and tutorials guide](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/overview.html?lang=es){target=_blank}.