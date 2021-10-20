---
keywords: experiencia;json;aem;adobe experience manager;exportar a adobe target;fragmentos de experiencias;fragmentos;XF
description: Aprenda a utilizar los fragmentos de experiencias de AEM en actividades de Adobe  [!DNL Target] . Combine la facilidad de uso y la potencia de AEM con las eficaces capacidades de IA y ML de  [!DNL Target].
title: ¿Cómo utilizo Fragmentos de experiencias de Adobe Experience Manager (AEM)?
feature: Experiences and Offers
exl-id: 3dd811a4-c7be-443d-a5ad-5b9adcaf1a2c
source-git-commit: 0d5d31a421acb595702e6420c74e969124cc3daf
workflow-type: ht
source-wordcount: '1125'
ht-degree: 100%

---

# Fragmentos de experiencia de AEM

Información acerca del uso de los fragmentos de experiencias creados en [!DNL Adobe Experience Manager] (AEM) en actividades de [!DNL Target] para ayudar en la optimización o personalización.

>[!NOTE]
>
>Esta función requiere que sea cliente de [!DNL Adobe Experience Manager] ([!DNL AEM]). Consulte [Requisitos](/help/c-experiences/c-manage-content/aem-experience-fragments.md#section_AE6F0971E1574B3AA324003599B96E5A), a continuación, para obtener más información.

## Información general {#section_95A91830530F493B81C5C9CDB9B783EA}

El empleo de fragmentos de experiencias creados en [!DNL AEM] en actividades de [!DNL Target] le permite combinar la facilidad de uso y la potencia de [!DNL AEM] con las eficientes capacidades de inteligencia automatizada (AI) y aprendizaje automático (ML) de [!DNL Target] para probar y personalizar experiencias a escala.

[!DNL AEM] aúna todos sus contenidos y recursos en una ubicación centralizada que potencia su estrategia de personalización. [!DNL AEM] le permite crear fácilmente contenido para equipos de escritorio, tabletas y dispositivos móviles en una misma ubicación y sin tener que escribir código. No es necesario crear páginas para cada dispositivo. [!DNL AEM] ajusta automáticamente cada experiencia con su contenido.

[!DNL Target] le permite ofrecer experiencias personalizadas a escala empleando una combinación de enfoques de aprendizaje automático basados en reglas y dirigidos por AI que incorporan variables de comportamiento, contextuales y sin conexión. Con [!DNL Target] puede configurar y ejecutar fácilmente actividades de pruebas [Pruebas A/B](/help/c-activities/t-test-ab/test-ab.md) y [multivariadas](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) para determinar las mejores ofertas, contenidos y experiencias.

Los fragmentos de experiencias representan un enorme paso adelante en el vínculo entre, por un lado, los creadores y gestores de contenido/experiencia y, por otro, los profesionales de la optimización y la personalización que mejoran los resultados empresariales con [!DNL Target].

## Requisitos.  {#section_AE6F0971E1574B3AA324003599B96E5A}

Debe contar con la funcionalidad de fragmentos de experiencia dentro de [!DNL Target]. Además, debe utilizar [!DNL AEM] 6.3 con el paquete de servicio apropiado o [!DNL AEM] 6.4 (o posterior). El representante de cuentas puede ayudar a garantizar el cumplimiento de los requisitos para usar esta función:

* [!DNL Adobe Experience Manager] 6.4 (o posterior).
* [!DNL Adobe Experience Manager] 6.3 SP2 (o posterior).
* Cuenta de [!DNL Adobe Target Standard] o [!DNL Adobe Target Premium].
* Póngase en contacto con el [Servicio de atención al cliente de Adobe Target](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para habilitar la integración y poder proporcionarle los datos de autenticación.

## Creación y configuración de fragmentos de experiencias en [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Para utilizar fragmentos de experiencias de [!DNL AEM] en [!DNL Target], debe realizar los siguientes pasos:

### Paso 1: Integrar [!DNL AEM] con [!DNL Target]

Para obtener más información, consulte:

* **Adobe I/O**: [integración con Adobe Target mediante Adobe I/O](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html?lang=es) en la documentación de la _Guía del usuario de administración_.
* **[!DNL AEM]6.3**: [participar en Adobe Analytics y Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=es) en la documentación de _Adobe Experience Manager 6.3_.
* **[!DNL AEM]6.4**: [participar en Adobe Analytics y Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=es) en la documentación de _Adobe Experience Manager 6.4_.
* **[!DNL AEM]6.5**: [participar en Adobe Analytics y Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=es) en la documentación de *Adobe Experience Manager 6.5*.

### Paso 2: Crear el fragmento de experiencia

Los fragmentos de experiencia se crean en [!DNL AEM]. Para obtener más información, consulte:

* **[!DNL AEM]6.3**: [fragmentos de experiencias](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=es) en la documentación de *Adobe Experience Manager 6.3*.
* **[!DNL AEM]6.4**: [fragmentos de experiencias](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=es) en la documentación de *Adobe Experience Manager 6.4*.
* **[!DNL AEM]6.5**: [fragmentos de experiencias](https://helpx.adobe.com/es/experience-manager/6-5/sites/authoring/using/experience-fragments.html) en la documentación de *Adobe Experience Manager 6.5*.

### Paso 3: Configurar [!DNL AEM] para que comparta el fragmento de experiencia con [!DNL Target]

1. En [!DNL AEM], seleccione el fragmento de experiencia deseado en su carpeta contenedora y, a continuación, haga clic en **[!UICONTROL Propiedades]**.
2. Haga clic en la pestaña **[!UICONTROL Servicios de nube]** y a continuación, en la lista desplegable **[!UICONTROL Configuración de Servicio de nube]**, seleccione **[!UICONTROL Adobe Target]**.

   >[!NOTE]
   >
   >El paso anterior supone que alguien en su organización ha creado la configuración de [!DNL Adobe Target].

3. Haga clic en **[!UICONTROL Guardar y cerrar]**.

### Paso 4: Publicar el fragmento de experiencia y exportarlo en [!DNL Target]

Según su versión de [!DNL AEM], consulte los siguientes vínculos para obtener instrucciones paso a paso:

* **[!DNL AEM]6.3**: [exportación de un fragmento de experiencia a Target](https://helpx.adobe.com/es/experience-manager/6-3/sites/administering/using/experience-fragments-target.html) en la documentación de *Adobe Experience Manager 6.3*.
* **[!DNL AEM]6.4**: [exportación de un fragmento de experiencia a Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html?lang=es) en la documentación de *Adobe Experience Manager 6.4*.
* **[!DNL AEM]6.5**: [exportación de un fragmento de experiencia a Target](https://helpx.adobe.com/es/experience-manager/6-5/sites/administering/using/experience-fragments-target.html) en la documentación de *Adobe Experience Manager 6.5*.

## Uso de fragmentos de experiencias en actividades de [!DNL Target] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Después de realizar las tareas anteriores, el fragmento de experiencia se muestra en la página [!UICONTROL Ofertas] de [!DNL Target].

>[!NOTE]
>
>[!DNL Target] busca fragmentos de experiencia para importar cada diez minutos. El fragmento de experiencia importado debería estar disponible en [!DNL Target] en unos diez minutos, pero este lapso de tiempo debería ser menor en adelante.

>[!IMPORTANT]
>
>El fragmento de experiencia se importa a [!DNL Target] como una oferta HTML. Tenga en cuenta que la versión del fragmento de experiencia “principal” permanece en [!DNL AEM]. No puede editar el fragmento de experiencia en [!DNL Target].

Puede pasar el ratón sobre un fragmento de experiencia en la lista y luego hacer clic en el icono de [!UICONTROL Ver] ![Ver icono](assets/icon_info.png) para ver información adicional acerca del fragmento de experiencia, incluida su dirección URL de entrega de oferta pública y su ruta de [!DNL AEM].

Puede consumir fragmentos de experiencias en actividades de [!DNL Target] empleando el [Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) o el [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>Para utilizar completamente las funcionalidades de AI y ML de [!DNL Target], puede seleccionar [Asignación automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) o [Asignación automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) al crear una prueba A/B.

**Para consumir fragmentos de experiencias usando el VEC:**

1. En [!DNL Target], mientras crea o edita una experiencia en el [Compositor de experiencias visuales](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), haga clic en la ubicación de la página donde desea insertar contenido [!DNL AEM] y, a continuación, seleccione la opción que desee para mostrar la lista [!UICONTROL Elegir un fragmento de experiencias].

   * [!UICONTROL Insertar antes]
   * [!UICONTROL Insertar después]
   * [!UICONTROL Intercambiar con fragmento de experiencia]

   La lista [!UICONTROL Fragmento de experiencia] muestra todo el contenido creado en [!DNL AEM] que ahora está disponible de forma nativa dentro de [!DNL Target].

   >[!NOTE]
   >
   >La opción [!UICONTROL Intercambiar con fragmento de experiencia] no está disponible para imágenes. Si desea utilizar esta opción con una imagen, haga clic en el elemento contenedor que contenga la imagen deseada.

   ![](assets/experience_fragment_list.png)

1. Seleccione el fragmento de experiencia deseado y, a continuación, haga clic en **[!UICONTROL Guardar]**.
1. Termine de configurar la actividad.

   Para obtener más información acerca de la configuración de los distintos tipos de actividad, consulte los temas siguientes:

   * **Prueba A/B:** [Crear una prueba A/B](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **Asignación automática:** [Asignación automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Segmentación automática:** [Segmentación automática](/help/c-activities/auto-target/auto-target-to-optimize.md)
   * **Personalización automatizada (AP):** [Creación de una actividad de personalización automatizada](/help/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Segmentación de experiencias (XT):** [Crear una actividad de segmentación de experiencias](/help/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Prueba multivariable (MVT):** [Crear una prueba multivariable](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710)
   * **Recommendations:** [Crear una actividad de Recommendations](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

**Para consumir fragmentos de experiencias usando el Compositor de experiencias basadas en formularios:**

1. En [!DNL Target], mientras crea o edita una experiencia en el [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), haga clic en el lugar de la página donde desea insertar contenido de [!DNL AEM] y, a continuación, seleccione **[!UICONTROL Cambiar fragmento de experiencia]** para mostrar la lista [!UICONTROL Elegir un fragmento de experiencia].

   ![](assets/experience_fragment_list.png)

   La lista [!UICONTROL Fragmento de experiencia] muestra todo el contenido creado en [!DNL AEM] que ahora está disponible de forma nativa dentro de [!DNL Target].

1. Seleccione el fragmento de experiencia deseado y, a continuación, haga clic en **[!UICONTROL Guardar]**.
1. Termine de configurar la actividad.

## Consideraciones {#considerations}

* [!DNL Target] busca fragmentos de experiencia para importar cada diez minutos. El fragmento de experiencia importado debería estar disponible en [!DNL Target] en unos diez minutos, pero este lapso de tiempo debería ser menor en adelante.
* El fragmento de experiencia se importa a [!DNL Target] como una oferta HTML. Tenga en cuenta que la versión del fragmento de experiencia “principal” permanece en [!DNL AEM]. No puede editar el fragmento de experiencia en [!DNL Target].
* No se pueden crear fragmentos de experiencias con Adobe IO. Debe crear fragmentos de experiencias mediante AEM, como se explica más arriba.

## Vídeo de formación: Uso de fragmentos de experiencias de AEM con Adobe Target ![Insignia de tutorial](/help/assets/overview.png) {#section_C0EDC54063464F41A182492D2045BC64}

El siguiente vídeo muestra cómo configurar y utilizar fragmentos de experiencias:

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>Se ha eliminado la función de enlace profundo de [!DNL AEM] discutida a las 4:54.

Para obtener más información, consulte [Uso de fragmentos de experiencias con Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html?lang=es) en la página *Vídeos y tutoriales de AEM Sites*.
