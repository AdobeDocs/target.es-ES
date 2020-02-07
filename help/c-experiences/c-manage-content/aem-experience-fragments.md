---
keywords: experience;json;aem;adobe experience manager;export to adobe target;experience fragments;fragments;XF
description: Información sobre el uso de fragmentos de experiencia creados en Adobe Experience Manager (AEM) en actividades de Adobe Target para facilitar la optimización o personalización.
title: Fragmentos de experiencia de Adobe Experience Manager (AEM) en Adobe Target
topic: Standard
uuid: 4dc2b5da-524f-4d6a-8ffc-8c3ac78cb39e
translation-type: tm+mt
source-git-commit: 1bd741f374c772aedc93bfae63105e1ce09be61a

---


# Fragmentos de experiencia de AEM{#aem-experience-fragments}

Information about using experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization.

>[!NOTE]
>
>This feature requires that you are an [!DNL Adobe Experience Manager] (AEM) customer. Consulte [Requisitos](../../c-experiences/c-manage-content/aem-experience-fragments.md#section_AE6F0971E1574B3AA324003599B96E5A), a continuación, para obtener más información.

## Información general {#section_95A91830530F493B81C5C9CDB9B783EA}

Using experience fragments created in AEM in [!DNL Target] activities lets you combine the ease-of-use and power of AEM with powerful Automated Intelligence (AI) and Machine Learning (ML) capabilities in [!DNL Target] to test and personalize experiences at scale.

AEM aúna todos sus contenidos y recursos en una ubicación centralizada que potencia su estrategia de personalización. AEM le permite crear fácilmente contenido para equipos de escritorio, tabletas y dispositivos móviles en una misma ubicación y sin tener que escribir código. No es necesario crear páginas para cada dispositivo. AEM ajusta automáticamente cada experiencia con el contenido.

[!DNL Target] le permite ofrecer experiencias personalizadas a escala empleando una combinación de enfoques de aprendizaje automático basados en reglas y dirigidos por AI que incorporan variables de comportamiento, contextuales y sin conexión. With [!DNL Target] you can easily set up and run [A/B Test](/help/c-activities/t-test-ab/test-ab.md) and [Multivariate](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) activities to determine the best offers, content, and experiences.

Experience fragments represent a huge step forward to link the content/experience creators and managers to the optimization and personalization professionals who are driving business outcomes using [!DNL Target].

## Requisitos.  {#section_AE6F0971E1574B3AA324003599B96E5A}

You must be provisioned with the experience fragments functionality within [!DNl Target]. Además, debe utilizar AEM 6.3 con el Service Pack apropiado o AEM 6.4 (o posterior). El representante de cuentas puede ayudar a garantizar el cumplimiento de los requisitos para usar esta función:

* Adobe Experience Manager 6.4 (o posterior).
* Adobe Experience Manager 6.3 SP2 (o posterior).
* Cuenta de Adobe Target Standard o Adobe Target Premium.
* Contact [Adobe Target Customer Care](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) to enable the integration and to provide you with authentication details.

## Creación y configuración de fragmentos de experiencia en AEM {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

In order to use AEM experience fragments in [!DNL Target], you must perform the following steps:

### Paso 1: Integrar AEM y Target

Para obtener más información, consulte:

* **AEM 6.3**: [Opción de Adobe Analytics y Adobe Target](https://docs.adobe.com/docs/en/aem/6-3/administer/integration/marketing-cloud/opt-in.html) en la documentación de _Adobe Experience Manager 6.3_ .
* **AEM 6.4**: [Opción de Adobe Analytics y Adobe Target](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/opt-in.html) en la documentación de _Adobe Experience Manager 6.4_ .
* **AEM 6.5**: [Opción de Adobe Analytics y Adobe Target](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/opt-in.html) en la documentación de *Adobe Experience Manager 6.5* .

### Paso 2: Crear el fragmento de experiencia

Los fragmentos de experiencia se crean en AEM. Para obtener más información, consulte:

* **AEM 6.3**: Fragmentos [de experiencia](https://docs.adobe.com/docs/en/aem/6-3/author/experience-fragments.html) en la documentación de *Adobe Experience Manager 6.3* .
* **AEM 6.4**: Fragmentos [de](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/experience-fragments.html) experiencia en la documentación de *Adobe Experience Manager 6.4* .
* **AEM 6.5**: Fragmentos [de experiencia](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/experience-fragments.html) en la documentación de *Adobe Experience Manager 6.5* .

### Paso 3: Configurar AEM para que comparta el fragmento de experiencia con Target

1. En AEM, seleccione el fragmento de experiencia deseado en su carpeta contenedora y, a continuación, haga clic en **[!UICONTROL Propiedades]**.
2. Haga clic en la pestaña **[!UICONTROL Servicios de nube]** y a continuación, en la lista desplegable **[!UICONTROL Configuración de Servicio de nube]**, seleccione **[!UICONTROL Adobe Target]**.

   >[!NOTE]
   >
   >The previous step assumes that someone in your organization has created the [!DNL Adobe Target] configuration.

3. Haga clic en **[!UICONTROL Guardar y cerrar]**.

### Paso 4: Publicar el fragmento de experiencia y exportarlo en Target

Según la versión de AEM, consulte los siguientes vínculos para obtener instrucciones paso a paso:

* **AEM 6.3**: [Exportación de un fragmento de experiencia a Target](https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/experience-fragments-target.html) en la documentación de *Adobe Experience Manager 6.3* .
* **AEM 6.4**: [Exportación de un fragmento de experiencia a Target](https://docs.adobe.com/content/help/en/experience-manager-64/administering/integration/experience-fragments-target.html) en la documentación de *Adobe Experience Manager 6.4* .
* **AEM 6.5**: [Exportación de un fragmento de experiencia a Target](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/experience-fragments-target.html) en la documentación de *Adobe Experience Manager 6.5* .

## Uso de fragmentos de Experiencia en actividades de Target {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Después de realizar las tareas anteriores, el fragmento de experiencia se muestra en la página [!UICONTROL Ofertas] de Target.

>[!NOTE]
>
>[!DNL Target] busca fragmentos de experiencia para importar cada diez minutos. The imported experience fragment should be available in [!DNL Target] within ten minutes, but this time frame should shorten going forward.

>[!IMPORTANT]
>
>The experience fragment is currently imported into [!DNL Target] as an HTML offer. Tenga en cuenta que la versión del fragmento de experiencia “maestro” permanece en AEM. No puede editar el fragmento de experiencia en Target.

You can hover over an experience fragment in the list, then click the View icon ![View icon](assets/icon_info.png) to see additional information about the experience fragment, including its public offer delivery URL, its AEM path, and a deep link to open the experience fragment inside of AEM.

You can consume Experience Fragments in [!DNL Target] activities using the [Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) or the [Form-Based Experience Composer](/help/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>To fully utilize the [!DNL Target] AI and ML functionality, you can select [Auto-Allocate](../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) or [Auto-Allocate](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) while creating an A/B Test.

**Para consumir fragmentos de experiencia usando el VEC:**

1. In [!DNL Target], while creating or editing an experience in the [Visual Experience Composer](../../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), click the location on the page where you want to insert AEM content, then select the desired option to display the [!UICONTROL Choose an Experience Fragment] list.

   * [!UICONTROL Insertar antes]
   * [!UICONTROL Insertar después]
   * [!UICONTROL Intercambiar con fragmento de experiencia]
   La lista [!UICONTROL Fragmento de experiencia] muestra todo el contenido creado en AEM que ahora está disponible de forma nativa dentro de [!DNL Target].

   >[!NOTE]
   >
   >La opción [!UICONTROL Intercambiar con fragmento de experiencia] no está disponible para imágenes. Si desea utilizar esta opción con una imagen, haga clic en el elemento contenedor que contenga la imagen deseada.

   ![](assets/experience_fragment_list.png)

1. Select the desired experience fragment, then click **[!UICONTROL Done]**.
1. Termine de configurar la actividad.

   Para obtener más información acerca de la configuración de los distintos tipos de actividad, consulte los temas siguientes:

   * **Prueba A/B:** [Crear una prueba A/B](../../c-activities/t-test-ab/t-test-create-ab/test-create-ab.md#task_68C8079BF9FF4625A3BD6680D554BB72)
   * **Asignación automática:** [Asignación automática](../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Segmentación automática:** [Segmentación automática para experiencias personalizadas](../../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3)
   * **Personalización automatizada (AP):** [Creación de una actividad de personalización automatizada](../../c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Segmentación de experiencias (XT):** [Crear una actividad de segmentación de experiencias](../../c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Prueba multivariable (MVT):** [Crear una prueba multivariable](../../c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710)
   * **Recommendations:** [Crear una actividad de Recommendations](../../c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

**Para consumir fragmentos de experiencia usando el Compositor de experiencias basadas en formularios:**

1. In [!DNl Target], while creating or editing an experience in the [Form-Based Experience Composer](../../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), select the location on the page where you want to insert AEM content, then select **[!UICONTROL Change Experience Fragment]** to display the [!UICONTROL Choose an Experience Fragment] list.

   ![](assets/experience_fragment_list.png)

   La lista [!UICONTROL Fragmento de experiencia] muestra todo el contenido creado en AEM que ahora está disponible de forma nativa dentro de [!DNL Target].

1. Seleccione el fragmento de experiencia deseado y, a continuación, haga clic en **[!UICONTROL Guardar]**.
1. Termine de configurar la actividad.

## Consideraciones {#considerations}

* [!DNL Target] busca fragmentos de experiencia para importar cada diez minutos. The imported experience fragment should be available in [!DNL Target] within ten minutes, but this time frame should shorten going forward.
* The experience fragment is currently imported into [!DNL Target] as an HTML offer. Tenga en cuenta que la versión del fragmento de experiencia “maestro” permanece en AEM. No puede editar el fragmento de experiencia en [!DNL Target].
* Puede importar ofertas JSON como fragmentos de experiencia en [!DNL Target]. Sin embargo, estas ofertas se importan como ofertas HTML. Actualmente, las ofertas JSON (fragmentos de experiencia) no son totalmente compatibles con la [!DNL Target] interfaz de usuario.

## ![Tutorial badge](/help/assets/overview.png) Training video: Uso de fragmentos de experiencia de AEM con Adobe Target {#section_C0EDC54063464F41A182492D2045BC64}

El siguiente vídeo muestra cómo configurar y utilizar fragmentos de experiencia:

>[!VIDEO](https://video.tv.adobe.com/v/22383)

Para obtener más información, consulte [Uso de fragmentos de experiencia con Adobe Target](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html) en la página de vídeos y tutoriales *de sitios de* AEM.
