---
keywords: experiencia;json;aem;adobe experience manager;exportar a adobe target;fragmentos de experiencias;fragmentos;XF
description: Aprenda a utilizar [!DNL Adobe Experience Manager] fragmentos de experiencia en [!DNL Adobe Target] actividades.
title: Cómo Uso [!DNL Adobe Experience Manager] (AEM) ¿Fragmentos de experiencias?
feature: Experiences and Offers
exl-id: 3dd811a4-c7be-443d-a5ad-5b9adcaf1a2c
source-git-commit: 8eab87951f860d07f6f05a53f81e94c56e7563c8
workflow-type: tm+mt
source-wordcount: '1277'
ht-degree: 55%

---

# Fragmentos de experiencia de AEM

Utilizar fragmentos de experiencia creados en [!DNL Adobe Experience Manager] (AEM) [!DNL Target] actividades para ayudar en la optimización o personalización.

>[!NOTE]
>
>Esta función requiere que [!DNL Adobe Experience Manager] (AEM) cliente. Para obtener más información, consulte [Requisitos](#section_AE6F0971E1574B3AA324003599B96E5A) más abajo.

Uso de fragmentos de experiencia creados en [!DNL AEM] en [!DNL Target] actividades le permite combinar la facilidad de uso y la potencia de [!DNL AEM] con potentes capacidades de inteligencia artificial (IA) y aprendizaje automático (ML) en [!DNL Target] para probar y personalizar experiencias a escala.

[!DNL AEM] aúna todos sus contenidos y recursos en una ubicación centralizada que potencia su estrategia de personalización. [!DNL AEM] le permite crear fácilmente contenido para equipos de escritorio, tabletas y dispositivos móviles en una misma ubicación y sin tener que escribir código. No es necesario crear páginas para cada dispositivo. [!DNL AEM] ajusta automáticamente cada experiencia con su contenido.

[!DNL Target] le permite ofrecer experiencias personalizadas a escala empleando una combinación de enfoques de aprendizaje automático basados en reglas y dirigidos por AI que incorporan variables de comportamiento, contextuales y sin conexión. con [!DNL Target], puede configurar y ejecutar fácilmente [Prueba A/B](/help/main/c-activities/t-test-ab/test-ab.md) y [Multivariable](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) para determinar las mejores ofertas, contenidos y experiencias.

Los fragmentos de experiencias representan un enorme paso adelante en el vínculo entre, por un lado, los creadores y gestores de contenido/experiencia y, por otro, los profesionales de la optimización y la personalización que mejoran los resultados empresariales con [!DNL Target].

## Requisitos.  {#section_AE6F0971E1574B3AA324003599B96E5A}

Debe contar con la funcionalidad de fragmentos de experiencia dentro de [!DNL Target]. Además, debe utilizar [!DNL AEM] as a Cloud Service o [!DNL AEM] 6.4 (o posterior). El representante de cuentas puede ayudar a garantizar el cumplimiento de los requisitos para usar esta función:

* [!DNL Adobe Experience Manager ] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5.
* [!DNL Adobe Experience Manager] 6.4.
* Cuenta de [!DNL Adobe Target Standard] o [!DNL Adobe Target Premium].

>[!NOTE]
>
>[!DNL Adobe Experience Manager] Las versiones 6.3 y 6.4 han llegado al final de su vida útil y ya no son compatibles (excepto para los clientes que compraron soporte ampliado).

Póngase en contacto con el [Servicio de atención al cliente de Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para habilitar la integración y poder proporcionarle los datos de autenticación.

## Creación y configuración de fragmentos de experiencias en [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Para utilizar fragmentos de experiencias de [!DNL AEM] en [!DNL Target], debe realizar los siguientes pasos:

### Paso 1: Integrar [!DNL AEM] con [!DNL Target]

Para obtener más información, consulte:

* **AEM as a Cloud Service**: [Integración con Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target.html){target=_blank} en la sección *Experience Manager as a Cloud Service* guía.
* **Adobe I/O**: [Integración con Adobe Target mediante Adobe I/0](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html?lang=es){target=_blank} en la sección *Guía del usuario sobre administración* documentación.
* **[!DNL AEM]6,5**: [Inclusión en Adobe Analytics y Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=es){target=_blank} en la sección *Adobe Experience Manager 6.5* documentación.
* **[!DNL AEM]6,4**: [Inclusión en Adobe Analytics y Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=es){target=_blank} en la sección *Adobe Experience Manager 6.4* documentación.

### Paso 2: Crear el fragmento de experiencia

Los fragmentos de experiencia se crean en [!DNL AEM]. Para obtener más información, consulte:

* **AEM as a Cloud Service**: [Fragmentos de experiencias](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=en){target=_blank} en la sección *Experience Manager as a Cloud Service* guía.
* **[!DNL AEM]6,5**: [Fragmentos de experiencias](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=es){target=_blank} en la sección *Adobe Experience Manager 6.5* documentación.
* **[!DNL AEM]6,4**: [Fragmentos de experiencias](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=es){target=_blank} en la sección *Adobe Experience Manager 6.4* documentación.

### Paso 3: Configurar [!DNL AEM] para que comparta el fragmento de experiencia con [!DNL Target]

1. En [!DNL AEM], seleccione el fragmento de experiencia deseado en su carpeta contenedora y, a continuación, haga clic en **[!UICONTROL Propiedades]**.
2. Haga clic en la pestaña **[!UICONTROL Servicios de nube]** y a continuación, en la lista desplegable **[!UICONTROL Configuración de Servicio de nube]**, seleccione **[!UICONTROL Adobe Target]**.

   >[!NOTE]
   >
   >El paso anterior supone que alguien en su organización ha creado la configuración de [!DNL Adobe Target].

3. Haga clic en **[!UICONTROL Guardar y cerrar]**.

### Paso 4: Publicar el fragmento de experiencia y exportarlo en [!DNL Target]

Según su versión de [!DNL AEM], consulte los siguientes vínculos para obtener instrucciones paso a paso:

* **AEM as a Cloud Service**: [Exportación de fragmentos de experiencias a Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target.html?lang=en){target=_blank} en la sección *Experience Manager as a Cloud Service* guía.
* **[!DNL AEM]6,5**: [Exportación de un fragmento de experiencia a Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=en){target=_blank} en la sección *Adobe Experience Manager 6.5* documentación.
* **[!DNL AEM]6,4**: [Exportación de un fragmento de experiencia a Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html?lang=es){target=_blank} en la sección *Adobe Experience Manager 6.4* documentación.

## Uso de fragmentos de experiencias en actividades de [!DNL Target] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Después de realizar las tareas anteriores, el fragmento de experiencia se muestra en la página [!UICONTROL Ofertas] de [!DNL Target].

>[!NOTE]
>
>* [!DNL Target] busca fragmentos de experiencia para importar cada diez minutos. El fragmento de experiencia importado debería estar disponible en [!DNL Target] en unos diez minutos, pero este lapso de tiempo debería ser menor en adelante.
>
>* El fragmento de experiencia se importa en [!DNL Target] como oferta de HTML. La versión &quot;principal&quot; del fragmento de experiencia permanece en [!DNL AEM]. No puede editar el fragmento de experiencia en [!DNL Target].


Puede pasar el ratón sobre un fragmento de experiencia en la lista y luego hacer clic en el icono de [!UICONTROL Ver] ![Ver icono](assets/icon_info.png) para ver información adicional acerca del fragmento de experiencia, incluida su dirección URL de entrega de oferta pública y su ruta de [!DNL AEM].

Puede consumir fragmentos de experiencias en actividades de [!DNL Target] empleando el [Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) o el [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>Para usar completamente el [!DNL Target] funcionalidad AI y ML, puede seleccionar [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) o [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) al crear una prueba A/B.
>
>Los fragmentos de experiencias no son compatibles con [!DNL Recommendations] actividades. Sin embargo, para utilizar fragmentos de experiencia en recomendaciones, puede crear un [!UICONTROL Prueba A/B] actividad (incluida [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática]) o un [!UICONTROL Segmentación de experiencias] (XT) y [incluir recomendaciones como oferta](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

**Para consumir fragmentos de experiencias usando el VEC:**

1. En [!DNL Target], mientras crea o edita una experiencia en el [Compositor de experiencias visuales](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), haga clic en la ubicación de la página donde desea insertar contenido [!DNL AEM] y, a continuación, seleccione la opción que desee para mostrar la lista [!UICONTROL Elegir un fragmento de experiencias].

   * [!UICONTROL Insertar antes]
   * [!UICONTROL Insertar después]
   * [!UICONTROL Intercambiar con fragmento de experiencia]

   La variable [!UICONTROL Fragmento de experiencia] muestra el contenido creado en [!DNL AEM] que ahora está disponible de forma nativa desde [!DNL Target].

   >[!NOTE]
   >
   >La opción [!UICONTROL Intercambiar con fragmento de experiencia] no está disponible para imágenes. Si desea utilizar esta opción con una imagen, haga clic en el elemento contenedor que contenga la imagen deseada.

   ![](assets/experience_fragment_list.png)

1. Seleccione el fragmento de experiencia deseado y, a continuación, haga clic en **[!UICONTROL Guardar]**.
1. Termine de configurar la actividad.

   Para obtener más información acerca de la configuración de los distintos tipos de actividad, consulte los temas siguientes:

   * **Prueba A/B:** [Crear una prueba A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **Asignación automática:** [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Segmentación automática:** [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Personalización automatizada (AP):** [Creación de una actividad de personalización automatizada](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Segmentación de experiencias (XT):** [Crear una actividad de segmentación de experiencias](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Prueba multivariable (MVT):** [Crear una prueba multivariable](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710)
   * **Recommendations:** [Crear una actividad de Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

**Para consumir fragmentos de experiencias usando el Compositor de experiencias basadas en formularios:**

1. En [!DNL Target], mientras crea o edita una experiencia en el [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), haga clic en el lugar de la página donde desea insertar contenido de [!DNL AEM] y, a continuación, seleccione **[!UICONTROL Cambiar fragmento de experiencia]** para mostrar la lista [!UICONTROL Elegir un fragmento de experiencia].

   ![](assets/experience_fragment_list.png)

   La variable [!UICONTROL Fragmento de experiencia] muestra el contenido creado en [!DNL AEM] que ahora está disponible de forma nativa desde [!DNL Target].

1. Seleccione el fragmento de experiencia deseado y, a continuación, haga clic en **[!UICONTROL Guardar]**.
1. Termine de configurar la actividad.

## Consideraciones {#considerations}

* [!DNL Target] busca fragmentos de experiencia para importar cada diez minutos. El fragmento de experiencia importado debería estar disponible en [!DNL Target] en unos diez minutos, pero este lapso de tiempo debería ser menor en adelante.
* El fragmento de experiencia se importa en [!DNL Target] como oferta de HTML. La versión &quot;principal&quot; del fragmento de experiencia permanece en [!DNL AEM]. No puede editar el fragmento de experiencia en [!DNL Target].
* No puede crear fragmentos de experiencia utilizando [!DNL Adobe I/O]. Cree fragmentos de experiencia con AEM, tal como se explica más arriba.
* Si actualiza el fragmento de experiencia en AEM, el fragmento de experiencia debe publicarse y exportarse a [!DNL Target] nuevamente así [!DNL Target] puede utilizar los cambios más recientes.

## Eliminación de bibliotecas de cliente de fragmentos de experiencias exportados a Target

Al utilizar una oferta de fragmento de experiencia con [!DNL Target] en una página entregada por AEM, la página de destino ya contiene todas las bibliotecas de cliente necesarias. Además, no es necesario el HTML superfluo de la oferta XF.

Para obtener más información, consulte [esta publicación de blog](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser){target=_blank}.

## Vídeo de formación: Uso de AEM fragmentos de experiencia con [!DNL Adobe Target]

El siguiente vídeo muestra cómo configurar y utilizar fragmentos de experiencias:

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>Se ha eliminado la función de enlace profundo de [!DNL AEM] discutida a las 4:54.

Para obtener información más detallada, consulte [Uso de fragmentos de experiencias con Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html?lang=es) en el *Vídeos y Tutorials de AEM Sites* página.
