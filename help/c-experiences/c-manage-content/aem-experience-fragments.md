---
keywords: experiencia;json;aem;adobe experience manager;exportar a adobe target;fragmentos de experiencia;fragmentos;XF
description: Aprenda a utilizar AEM fragmentos de experiencia en actividades de Adobe [!DNL Target] . Combine la facilidad de uso y la potencia de AEM con potentes capacidades de IA y ML en [!DNL Target].
title: ¿Cómo utilizo los fragmentos de experiencia de Adobe Experience Manager (AEM)?
feature: Experiencias y ofertas
exl-id: 3dd811a4-c7be-443d-a5ad-5b9adcaf1a2c
source-git-commit: 603d98a972d1b421dae2047b70d65d0037b7a068
workflow-type: tm+mt
source-wordcount: '1155'
ht-degree: 28%

---

# Fragmentos de experiencia de AEM

Información sobre el uso de fragmentos de experiencia creados en [!DNL Adobe Experience Manager] (AEM) en actividades [!DNL Target] para ayudar en la optimización o personalización.

>[!NOTE]
>
>Esta función requiere que sea cliente de [!DNL Adobe Experience Manager] ([!DNL AEM]). Consulte [Requisitos](/help/c-experiences/c-manage-content/aem-experience-fragments.md#section_AE6F0971E1574B3AA324003599B96E5A), a continuación, para obtener más información.

## Información general {#section_95A91830530F493B81C5C9CDB9B783EA}

El uso de fragmentos de experiencia creados en [!DNL AEM] en [!DNL Target] actividades permite combinar la facilidad de uso y la potencia de [!DNL AEM] con potentes capacidades de Inteligencia automatizada (AI) y Aprendizaje automático (ML) en [!DNL Target] para probar y personalizar experiencias a escala.

[!DNL AEM] aúna todos sus contenidos y recursos en una ubicación centralizada que potencia su estrategia de personalización. [!DNL AEM] le permite crear fácilmente contenido para equipos de escritorio, tabletas y dispositivos móviles en una misma ubicación y sin tener que escribir código. No es necesario crear páginas para cada dispositivo. [!DNL AEM] ajusta automáticamente cada experiencia con su contenido.

[!DNL Target] le permite ofrecer experiencias personalizadas a escala empleando una combinación de enfoques de aprendizaje automático basados en reglas y dirigidos por AI que incorporan variables de comportamiento, contextuales y sin conexión. Con [!DNL Target] puede configurar y ejecutar fácilmente [Prueba A/B](/help/c-activities/t-test-ab/test-ab.md) y [Actividades multivariadas](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) para determinar las mejores ofertas, contenidos y experiencias.

Los fragmentos de experiencia representan un gran paso adelante para vincular a los creadores y administradores de contenido/experiencia con los profesionales de optimización y personalización que dirigen los resultados comerciales mediante [!DNL Target].

## Requisitos.  {#section_AE6F0971E1574B3AA324003599B96E5A}

Debe contar con la funcionalidad de fragmentos de experiencia dentro de [!DNL Target]. Además, debe utilizar [!DNL AEM] 6.3 con el Service Pack apropiado o [!DNL AEM] 6.4 (o posterior). El representante de cuentas puede ayudar a garantizar el cumplimiento de los requisitos para usar esta función:

* [!DNL Adobe Experience Manager] 6.4 (o posterior).
* [!DNL Adobe Experience Manager] 6.3 SP2 (o posterior).
* [!DNL Adobe Target Standard] o  [!DNL Adobe Target Premium] cuenta.
* Póngase en contacto con el [Servicio de atención al cliente de Adobe Target](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para habilitar la integración y proporcionarle detalles de autenticación.

## Creación y configuración de fragmentos de experiencia en [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Para utilizar [!DNL AEM] fragmentos de experiencia en [!DNL Target], debe realizar los siguientes pasos:

### Paso 1: Integrar [!DNL AEM] con [!DNL Target]

Para obtener más información, consulte:

* **Adobe I/O**:  [Integración con Adobe Target mediante Adobe I/0](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html) en la  _Guía del usuario de_ administración.
* **[!DNL AEM]6.3**:  [Inclusión en Adobe Analytics y Adobe ](https://docs.adobe.com/docs/en/aem/6-3/administer/integration/marketing-cloud/opt-in.html) Target en la documentación de  _Adobe Experience Manager 6.3_ .
* **[!DNL AEM]6.4**:  [Inclusión en Adobe Analytics y Adobe ](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/opt-in.html) Target en la documentación de  _Adobe Experience Manager 6.4_ .
* **[!DNL AEM]6.5**:  [Inclusión en Adobe Analytics y Adobe ](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/opt-in.html) Target en la documentación de  *Adobe Experience Manager 6.5* .

### Paso 2: Crear el fragmento de experiencia

Los fragmentos de experiencia se crean en [!DNL AEM]. Para obtener más información, consulte:

* **[!DNL AEM]6.3**:  [Fragmentos ](https://docs.adobe.com/docs/en/aem/6-3/author/experience-fragments.html) de experiencias en la documentación de  *Adobe Experience Manager 6.3* .
* **[!DNL AEM]6.4**:  [Fragmentos ](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/experience-fragments.html) de experiencias en la documentación de  *Adobe Experience Manager 6.4* .
* **[!DNL AEM]6.5**:  [Fragmentos ](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/experience-fragments.html) de experiencias en la documentación de  *Adobe Experience Manager 6.5* .

### Paso 3: Configure [!DNL AEM] para compartir el fragmento de experiencia con [!DNL Target]

1. Desde [!DNL AEM], seleccione el fragmento de experiencia deseado o su carpeta contenedora y, a continuación, haga clic en **[!UICONTROL Propiedades]**.
2. Haga clic en la pestaña **[!UICONTROL Servicios de nube]** y a continuación, en la lista desplegable **[!UICONTROL Configuración de Servicio de nube]**, seleccione **[!UICONTROL Adobe Target]**.

   >[!NOTE]
   >
   >El paso anterior supone que alguien en su organización ha creado la configuración [!DNL Adobe Target].

3. Haga clic en **[!UICONTROL Guardar y cerrar]**.

### Paso 4: Publicar el fragmento de experiencia y exportarlo en [!DNL Target]

Según su versión de [!DNL AEM], consulte los siguientes vínculos para obtener instrucciones paso a paso:

* **[!DNL AEM]6.3**:  [Exportación de un fragmento de experiencia a ](https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/experience-fragments-target.html) Target en la documentación de  *Adobe Experience Manager 6.3* .
* **[!DNL AEM]6.4**:  [Exportación de un fragmento de experiencia a ](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html) Target en la documentación de  *Adobe Experience Manager 6.4* .
* **[!DNL AEM]6.5**:  [Exportación de un fragmento de experiencia a ](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/experience-fragments-target.html) Target en la documentación de  *Adobe Experience Manager 6.5* .

## Uso de fragmentos de experiencia en actividades [!DNL Target] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Después de realizar las tareas anteriores, el fragmento de experiencia se muestra en la página [!UICONTROL Ofertas] de [!DNL Target].

>[!NOTE]
>
>[!DNL Target] busca fragmentos de experiencia para importar cada diez minutos. El fragmento de experiencia importado debe estar disponible en [!DNL Target] en diez minutos, pero este lapso de tiempo debe acortarse en adelante.

>[!IMPORTANT]
>
>El fragmento de experiencia se importa actualmente a [!DNL Target] como una oferta HTML. Tenga en cuenta que la versión &quot;principal&quot; del fragmento de experiencia permanece en [!DNL AEM]. No puede editar el fragmento de experiencia en [!DNL Target].

Puede pasar el ratón sobre un fragmento de experiencia en la lista y luego hacer clic en el icono [!UICONTROL Ver] ![Ver icono](assets/icon_info.png) para ver información adicional sobre el fragmento de experiencia, incluida su dirección URL de envío de oferta pública y su ruta [!DNL AEM].

Puede consumir fragmentos de experiencia en actividades [!DNL Target] utilizando el [Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) o el [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>Para utilizar completamente la funcionalidad [!DNL Target] AI y ML, puede seleccionar [Asignación automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) o [Asignación automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) al crear una prueba A/B.

**Para consumir fragmentos de experiencia usando el VEC:**

1. En [!DNL Target], mientras crea o edita una experiencia en el [Compositor de experiencias visuales](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), haga clic en la ubicación de la página donde desea insertar contenido [!DNL AEM] y, a continuación, seleccione la opción que desee para mostrar la lista [!UICONTROL Elegir un fragmento de experiencia].

   * [!UICONTROL Insertar antes]
   * [!UICONTROL Insertar después]
   * [!UICONTROL Intercambiar con fragmento de experiencia]

   La lista [!UICONTROL Fragmento de experiencia][!DNL AEM] muestra todo el contenido creado en que ahora está disponible de forma nativa dentro de [!DNL Target].

   >[!NOTE]
   >
   >La opción [!UICONTROL Intercambiar con fragmento de experiencia] no está disponible para imágenes. Si desea utilizar esta opción con una imagen, haga clic en el elemento contenedor que contenga la imagen deseada.

   ![](assets/experience_fragment_list.png)

1. Seleccione el fragmento de experiencia deseado y haga clic en **[!UICONTROL Listo]**.
1. Termine de configurar la actividad.

   Para obtener más información acerca de la configuración de los distintos tipos de actividad, consulte los temas siguientes:

   * **Prueba A/B:** [Crear una prueba A/B](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **Asignación automática:** [Asignación automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Segmentación automática:** [Segmentación automática](/help/c-activities/auto-target/auto-target-to-optimize.md)
   * **Personalización automatizada (AP):** [Creación de una actividad de personalización automatizada](/help/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Segmentación de experiencias (XT):** [Crear una actividad de segmentación de experiencias](/help/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Prueba multivariable (MVT):** [Crear una prueba multivariable](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710)
   * **Recommendations:** [Crear una actividad de Recommendations](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

**Para consumir fragmentos de experiencia usando el Compositor de experiencias basadas en formularios:**

1. En [!DNL Target], mientras crea o edita una experiencia en el [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), seleccione la ubicación en la página donde desea insertar contenido [!DNL AEM] y, a continuación, seleccione **[!UICONTROL Cambiar fragmento de experiencia]** para mostrar la lista [!UICONTROL Elegir un fragmento de experiencia].

   ![](assets/experience_fragment_list.png)

   La lista [!UICONTROL Fragmento de experiencia][!DNL AEM] muestra todo el contenido creado en que ahora está disponible de forma nativa dentro de [!DNL Target].

1. Seleccione el fragmento de experiencia deseado y, a continuación, haga clic en **[!UICONTROL Guardar]**.
1. Termine de configurar la actividad.

## Consideraciones {#considerations}

* [!DNL Target] busca fragmentos de experiencia para importar cada diez minutos. El fragmento de experiencia importado debe estar disponible en [!DNL Target] en diez minutos, pero este lapso de tiempo debe acortarse en adelante.
* El fragmento de experiencia se importa actualmente a [!DNL Target] como una oferta HTML. Tenga en cuenta que la versión &quot;principal&quot; del fragmento de experiencia permanece en [!DNL AEM]. No puede editar el fragmento de experiencia en [!DNL Target].
* Puede importar ofertas JSON como fragmentos de experiencia en [!DNL Target]. Sin embargo, estas ofertas se importan como ofertas HTML. Actualmente, las ofertas JSON (fragmentos de experiencia) no son totalmente compatibles con la interfaz de usuario de [!DNL Target] .
* No se pueden crear fragmentos de experiencia con Adobe IO. Debe crear fragmentos de experiencia mediante AEM, como se explica más arriba.

## Vídeo de formación: Uso de AEM fragmentos de experiencia con Adobe Target ![Tutorial badge](/help/assets/overview.png) {#section_C0EDC54063464F41A182492D2045BC64}

El siguiente vídeo muestra cómo configurar y utilizar fragmentos de experiencia:

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>Se ha eliminado la función de enlace profundo [!DNL AEM] discutida a las 4:54.

Para obtener más información, consulte [Uso de fragmentos de experiencias con Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html) en la página *Vídeos y Tutorials de AEM Sites*.
