---
description: Información sobre el uso de fragmentos de experiencia creados en Adobe Experience Manager (AEM) en actividades de Target para ayudar en la optimización o personalización.
keywords: experiencia;aem;adobe experience manager;exportar a adobe target;fragmentos de experiencia;fragmentos;XF
seo-description: Información sobre el uso de fragmentos de experiencia creados en Adobe Experience Manager (AEM) en actividades de Target para ayudar en la optimización o personalización.
seo-title: Fragmentos de experiencia de AEM
solution: Target
title: Fragmentos de experiencia de AEM
topic: Standard
uuid: 4dc2b5da-524f-4d6a-8ffc-8c3ac78cb39e
translation-type: tm+mt
source-git-commit: 35e22ec50ef1f128563ac255c202c14a0d674c03

---


# Fragmentos de experiencia de AEM{#aem-experience-fragments}

Información sobre el uso de fragmentos de experiencia creados en Adobe Experience Manager (AEM) en actividades de Target para ayudar en la optimización o personalización.

## Fragmentos de experiencia de AEM {#topic_1E1E4EA01F074349B2CF8785387B5FE8}

Información sobre el uso de fragmentos de experiencia creados en Adobe Experience Manager (AEM) en actividades de Target para ayudar en la optimización o personalización.

>[!NOTE]
>
>Esta función requiere que sea cliente de Adobe Experience Manager (AEM). Consulte [Requisitos](../../c-experiences/c-manage-content/aem-experience-fragments.md#section_AE6F0971E1574B3AA324003599B96E5A), a continuación, para obtener más información.

## Información general {#section_95A91830530F493B81C5C9CDB9B783EA}

El empleo en actividades de Target de fragmentos de experiencia creados en AEM le permite combinar la facilidad de uso y la potencia de AEM con potentes capacidades de Inteligencia automatizada (AI) y Aprendizaje automático (ML) en Target para probar y personalizar experiencias a escala. 

AEM aúna todos sus contenidos y recursos en una ubicación centralizada que potencia su estrategia de personalización. AEM le permite crear fácilmente contenido para equipos de escritorio, tabletas y dispositivos móviles en una misma ubicación y sin tener que escribir código. No es necesario crear páginas para cada dispositivo: AEM ajusta automáticamente la experiencia empleando su contenido.

Target le permite ofrecer experiencias personalizadas a escala empleando una combinación de enfoques de aprendizaje automático basados en reglas y dirigidos por AI que incorporan variables de comportamiento, contextuales y sin conexión. Target le permite configurar y ejecutar fácilmente actividades A/B y multivariable (MVT) para determinar las mejores ofertas, contenidos y experiencias.

Los fragmentos de experiencia representan un enorme paso adelante en el vínculo entre, por un lado, los creadores y gestores de contenido/experiencia y, por otro, los profesionales de la optimización y la personalización que dirigen mediante Target los resultados del negocio.

## Requisitos   {#section_AE6F0971E1574B3AA324003599B96E5A}

Debe contar con la funcionalidad de fragmentos de experiencia dentro de Target. Además, debe utilizar AEM 6.3 con el Service Pack apropiado o AEM 6.4 (o posterior). El representante de cuentas puede ayudar a garantizar el cumplimiento de los requisitos para usar esta función:

* Adobe Experience Manager 6.4 (o posterior).
* Adobe Experience Manager 6.3 SP2 (o posterior).
* Cuenta de Adobe Target Standard o Adobe Target Premium.
* Póngase en contacto con el Servicio de atención al cliente de Adobe Target para habilitar la integración y poder enviarle datos de autenticación.

## Creación y configuración de fragmentos de experiencia en AEM {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Para utilizar fragmentos de experiencia de AEM en Target, debe realizar los siguientes pasos:

### Paso 1: Integrar AEM y Target

Para obtener más información, consulte:

* **AEM 6.3:**[Participar en Adobe Analytics y Adobe Target](https://docs.adobe.com/docs/en/aem/6-3/administer/integration/marketing-cloud/opt-in.html) en la documentación de _Adobe Experience Manager 6.3_.
* **AEM 6.4:**[Participar en Adobe Analytics y Adobe Target](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/opt-in.html) en la documentación de _Adobe Experience Manager 6.4_.

### Paso 2: Crear el fragmento de experiencia

Los fragmentos de experiencia se crean en AEM. Para obtener más información, consulte:

* **AEM 6.3:**[Fragmentos de Experiencia](https://docs.adobe.com/docs/en/aem/6-3/author/experience-fragments.html) en la documentación de *Adobe Experience Manager 6.3*.
* **AEM 6.4:**[Fragmentos de Experiencia](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/experience-fragments.html) en la documentación de *Adobe Experience Manager 6.4*.

### Paso 3: Configurar AEM para que comparta el fragmento de experiencia con Target

1. En AEM, seleccione el fragmento de experiencia deseado en su carpeta contenedora y, a continuación, haga clic en [!UICONTROL Propiedades].
2. Haga clic en la pestaña [!UICONTROL Servicios de nube] y a continuación, en la lista desplegable [!UICONTROL Configuración de Servicio de nube], seleccione [!UICONTROL Adobe Target].

   >[!NOTE]
   >
   >El paso anterior supone que alguien en su organización ha creado la configuración de Adobe Target.

3. Haga clic en [!UICONTROL Guardar y cerrar].

### Paso 4: Publicar el fragmento de experiencia y exportarlo en Target

**AEM 6.3:**

1. En AEM, seleccione el fragmento de experiencia deseado, haga clic en la pestaña [!UICONTROL Publicar] y, a continuación, haga clic en el botón [!UICONTROL Publicar].
2. En AEM, seleccione el fragmento de experiencia deseado, haga clic en [!UICONTROL Exportar a Adobe Target] y, a continuación, haga clic en [!UICONTROL Aceptar].

   ![](assets/experience_fragment_export_to_target.png)

**AEM 6.4:**

1. Dentro de AEM, seleccione el fragmento de experiencia deseado, haga clic en [!UICONTROL Exportar a Adobe Target].

   ![](assets/experience_fragment_export_to_target.png)

2. En el cuadro de diálogo que aparece, seleccione [!UICONTROL Publicar] para publicar todos los activos dentro del fragmento de experiencia en [!DNL Target].

## Uso de fragmentos de experimento en actividades de Target {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Después de realizar las tareas anteriores, el fragmento de experiencia se muestra en la página [!UICONTROL Ofertas] de Target.

>[!NOTE]
>
>Target busca fragmentos de experiencia para importar cada diez minutos. El fragmento de experiencia importado debería estar disponible en Target en unos diez minutos, pero este plazo debería ser menor en adelante.

>[!IMPORTANT]
>
>El fragmento de experiencia se importa a Target como una oferta HTML. Tenga en cuenta que la versión del fragmento de experiencia “maestro” permanece en AEM. No puede editar el fragmento de experiencia en Target.

Puede situar el cursor sobre un fragmento de experiencia en la lista y luego hacer clic en el icono Ver ( ![](assets/icon_info.png)

) para ver información adicional sobre el fragmento de experiencia, incluida su dirección URL de entrega de oferta pública, su ruta de AEM y un vínculo para abrir el fragmento de experiencia dentro de AEM.

Puede consumir fragmentos de experiencia en actividades de Target empleando el Compositor de experiencias visuales (VEC) o el Compositor de experiencias basadas en formularios.

>[!NOTE]
>
>Para utilizar completamente la funcionalidad AI y ML de Target, puede seleccionar [Asignación automática](../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) o [Personalización automatizada](../../c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) al crear una prueba A/B.

**Para consumir fragmentos de experiencia usando el VEC:**

1. En Target, mientras crea o edita una experiencia en el   [Compositor de experiencias visuales](../../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), haga clic en la ubicación de la página donde desea insertar contenido AEM y, a continuación, seleccione **[!UICONTROL Intercambiar con fragmento de experiencia]** para mostrar la lista [!UICONTROL Elegir un fragmento de experiencia].

   >[!NOTE]
   >
   >La opción [!UICONTROL Intercambiar con fragmento de experiencia] no está disponible para imágenes. Si desea utilizar esta opción con una imagen, haga clic en el elemento contenedor que contenga la imagen deseada.

   La lista [!UICONTROL Fragmento de experiencia] muestra todo el contenido creado en AEM que ahora está disponible de forma nativa dentro de Target.

   ![](assets/experience_fragment_list.png)

1. Seleccione el fragmento de experiencia deseado y, a continuación, haga clic en **[!UICONTROL Guardar]**.
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

1. En Target, mientras crea o edita una experiencia en el   [Compositor de experiencias basadas en formularios](../../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), seleccione la ubicación de la página donde desea insertar contenido AEM y, a continuación, seleccione **[!UICONTROL Cambiar fragmento de experiencia]** para mostrar la lista [!UICONTROL Elegir un fragmento de experiencia].

   ![](assets/experience_fragment_list.png)

   La lista [!UICONTROL Fragmento de experiencia] muestra todo el contenido creado en AEM que ahora está disponible de forma nativa dentro de Target.

1. Seleccione el fragmento de experiencia deseado y, a continuación, haga clic en **[!UICONTROL Guardar]**.
1. Termine de configurar la actividad.

## Vídeo de formación: Uso de Fragmentos de experiencia de AEM con Adobe Target {#section_C0EDC54063464F41A182492D2045BC64}

El siguiente vídeo muestra cómo se configuran y utilizan los fragmentos de experiencia: [Uso de fragmentos de experiencia AEM con Adobe Target](https://helpx.adobe.com/experience-manager/kt/sites/using/experience-fragment-target-feature-video-use.html).
