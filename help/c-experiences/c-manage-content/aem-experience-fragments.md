---
keywords: experiencia;json;aem;adobe experience manager;exportar a adobe destinatario;fragmentos de experiencia;fragmentos;XF
description: Descubra cómo utilizar fragmentos de experiencia AEM en actividades de Adobe Target. Combine la facilidad de uso y el poder de AEM con potentes capacidades de IA y ML en Destinatario.
title: ¿Cómo se utilizan los fragmentos de experiencias de Adobe Experience Manager (AEM)?
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '1132'
ht-degree: 28%

---


# Fragmentos de experiencia de AEM

Información sobre el uso de fragmentos de experiencia creados en [!DNL Adobe Experience Manager] (AEM) en actividades [!DNL Target] para facilitar la optimización o personalización.

>[!NOTE]
>
>Esta función requiere que sea un cliente [!DNL Adobe Experience Manager] ([!DNL AEM]). Consulte [Requisitos](/help/c-experiences/c-manage-content/aem-experience-fragments.md#section_AE6F0971E1574B3AA324003599B96E5A), a continuación, para obtener más información.

## Información general {#section_95A91830530F493B81C5C9CDB9B783EA}

El uso de fragmentos de experiencia creados en [!DNL AEM] en actividades [!DNL Target] le permite combinar la facilidad de uso y la potencia de [!DNL AEM] con las potentes capacidades de Inteligencia automatizada (AI) y Aprendizaje automático (ML) en [!DNL Target] para probar y personalizar experiencias a escala.

[!DNL AEM] aúna todos sus contenidos y recursos en una ubicación centralizada que potencia su estrategia de personalización. [!DNL AEM] le permite crear fácilmente contenido para equipos de escritorio, tabletas y dispositivos móviles en una misma ubicación y sin tener que escribir código. No es necesario crear páginas para cada dispositivo. [!DNL AEM] ajusta automáticamente cada experiencia con el contenido.

[!DNL Target] le permite ofrecer experiencias personalizadas a escala empleando una combinación de enfoques de aprendizaje automático basados en reglas y dirigidos por AI que incorporan variables de comportamiento, contextuales y sin conexión. Con [!DNL Target] puede configurar y ejecutar fácilmente [Prueba A/B](/help/c-activities/t-test-ab/test-ab.md) y [actividades multivariadas](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) para determinar las mejores ofertas, contenido y experiencias.

Los fragmentos de experiencia representan un gran paso adelante para vincular a los creadores y administradores de contenido/experiencia con los profesionales de optimización y personalización que dirigen los resultados comerciales mediante [!DNL Target].

## Requisitos.   {#section_AE6F0971E1574B3AA324003599B96E5A}

Debe contar con la funcionalidad de fragmentos de experiencia dentro de [!DNL Target]. Además, debe utilizar [!DNL AEM] 6.3 con el Service Pack apropiado o [!DNL AEM] 6.4 (o posterior). El representante de cuentas puede ayudar a garantizar el cumplimiento de los requisitos para usar esta función:

* [!DNL Adobe Experience Manager] 6.4 (o posterior).
* [!DNL Adobe Experience Manager] 6.3 SP2 (o posterior).
* [!DNL Adobe Target Standard] o  [!DNL Adobe Target Premium] cuenta.
* Póngase en contacto con [Servicio de atención al cliente de Adobe Target](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para habilitar la integración y proporcionarle detalles de autenticación.

## Creación y configuración de fragmentos de experiencia en [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Para utilizar los fragmentos de experiencia [!DNL AEM] en [!DNL Target], debe realizar los siguientes pasos:

### Paso 1: Integrar [!DNL AEM] con [!DNL Target]

Para obtener más información, consulte:

* **[!DNL AEM]6.3**:  [Si opta por Adobe Analytics y Adobe ](https://docs.adobe.com/docs/en/aem/6-3/administer/integration/marketing-cloud/opt-in.html) Target en la  _documentación de Adobe Experience Manager 6.3_ .
* **[!DNL AEM]6.4**:  [Si opta por Adobe Analytics y Adobe ](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/opt-in.html) Target en la  _documentación de Adobe Experience Manager 6.4_ .
* **[!DNL AEM]6.5**:  [Si opta por Adobe Analytics y Adobe ](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/opt-in.html) Target en la  *documentación de Adobe Experience Manager 6.5* .

### Paso 2: Crear el fragmento de experiencia

Los fragmentos de experiencia se crean en [!DNL AEM]. Para obtener más información, consulte:

* **[!DNL AEM]6.3**:  [Fragmentos de experiencia ](https://docs.adobe.com/docs/en/aem/6-3/author/experience-fragments.html) en la  *documentación de* Adobe Experience Manager 6.3.
* **[!DNL AEM]6.4**:  [Fragmentos de experiencia ](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/experience-fragments.html) en la  *documentación de* Adobe Experience Manager 6.4.
* **[!DNL AEM]6.5**:  [Fragmentos de experiencia ](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/experience-fragments.html) en la  *documentación de* Adobe Experience Manager 6.5.

### Paso 3: Configure [!DNL AEM] para compartir el fragmento de experiencia con [!DNL Target]

1. Desde [!DNL AEM], seleccione el fragmento de experiencia deseado o su carpeta contenedora y haga clic en **[!UICONTROL Propiedades]**.
2. Haga clic en la pestaña **[!UICONTROL Servicios de nube]** y a continuación, en la lista desplegable **[!UICONTROL Configuración de Servicio de nube]**, seleccione **[!UICONTROL Adobe Target]**.

   >[!NOTE]
   >
   >El paso anterior supone que alguien de su organización ha creado la configuración [!DNL Adobe Target].

3. Haga clic en **[!UICONTROL Guardar y cerrar]**.

### Paso 4: Publicar el fragmento de experiencia y exportarlo en [!DNL Target]

Según la versión de [!DNL AEM], consulte los siguientes vínculos para obtener instrucciones paso a paso:

* **[!DNL AEM]6.3**:  [Exportación de un fragmento de experiencia a ](https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/experience-fragments-target.html) Target en la  *documentación de* Adobe Experience Manager 6.3.
* **[!DNL AEM]6.4**:  [Exportación de un fragmento de experiencia a ](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html) Target en la  *documentación de* Adobe Experience Manager 6.4.
* **[!DNL AEM]6.5**:  [Exportación de un fragmento de experiencia a ](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/experience-fragments-target.html) Target en la  *documentación de* Adobe Experience Manager 6.5.

## Uso de fragmentos de experiencia en actividades de Destinatario {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Después de realizar las tareas anteriores, el fragmento de experiencia se muestra en la página [!UICONTROL Ofertas] de [!DNL Target].

>[!NOTE]
>
>[!DNL Target] busca fragmentos de experiencia para importar cada diez minutos. El fragmento de experiencia importado debe estar disponible en [!DNL Target] en un plazo de diez minutos, pero este intervalo de tiempo debe acortarse a partir de ahora.

>[!IMPORTANT]
>
>El fragmento de experiencia se importa actualmente a [!DNL Target] como una oferta HTML. Tenga en cuenta que la versión &quot;principal&quot; del fragmento de experiencia permanece en [!DNL AEM]. No puede editar el fragmento de experiencia en [!DNL Target].

Puede pasar el ratón por encima de un fragmento de experiencia en la lista y, a continuación, hacer clic en el icono [!UICONTROL Vista] ![Vista](assets/icon_info.png) para ver información adicional sobre el fragmento de experiencia, incluida su dirección URL de envío de oferta pública y su ruta [!DNL AEM].

Puede consumir fragmentos de experiencia en actividades [!DNL Target] mediante el [Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) o el [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>Para utilizar completamente la funcionalidad [!DNL Target] AI y ML, puede seleccionar [Asignación automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) o [Asignación automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) al crear una prueba A/B.

**Para consumir fragmentos de experiencia con el VEC:**

1. En [!DNL Target], mientras crea o edita una experiencia en el [Compositor de experiencias visuales](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), haga clic en la ubicación de la página en la que desea insertar contenido [!DNL AEM] y, a continuación, seleccione la opción que desee para mostrar la lista [!UICONTROL Elija un fragmento de experiencias].

   * [!UICONTROL Insertar antes]
   * [!UICONTROL Insertar después]
   * [!UICONTROL Intercambiar con fragmento de experiencia]

   La lista [!UICONTROL Fragmento de experiencia][!DNL AEM] muestra todo el contenido creado en que ahora está disponible de forma nativa dentro de [!DNL Target].

   >[!NOTE]
   >
   >La opción [!UICONTROL Intercambiar con fragmento de experiencia] no está disponible para imágenes. Si desea utilizar esta opción con una imagen, haga clic en el elemento contenedor que contenga la imagen deseada.

   ![](assets/experience_fragment_list.png)

1. Seleccione el fragmento de experiencia deseado y haga clic en **[!UICONTROL Finalizado]**.
1. Termine de configurar la actividad.

   Para obtener más información acerca de la configuración de los distintos tipos de actividad, consulte los temas siguientes:

   * **Prueba A/B:** [Crear una prueba A/B](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **Asignación automática:** [Asignación automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Destinatario automático:Destinatario** [automático](/help/c-activities/auto-target/auto-target-to-optimize.md)
   * **Personalización automatizada (AP):** [Creación de una actividad de personalización automatizada](/help/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Segmentación de experiencias (XT):** [Crear una actividad de segmentación de experiencias](/help/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Prueba multivariable (MVT):** [Crear una prueba multivariable](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710)
   * **Recommendations:** [Crear una actividad de Recommendations](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

**Para consumir fragmentos de experiencia con el Compositor de experiencias basadas en formularios:**

1. En [!DNL Target], mientras crea o edita una experiencia en el [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), seleccione la ubicación en la página donde desee insertar contenido [!DNL AEM] y, a continuación, seleccione **[!UICONTROL Cambiar fragmento de experiencias]** para mostrar la lista [!UICONTROL Elegir un fragmento de experiencias].

   ![](assets/experience_fragment_list.png)

   La lista [!UICONTROL Fragmento de experiencia][!DNL AEM] muestra todo el contenido creado en que ahora está disponible de forma nativa dentro de [!DNL Target].

1. Seleccione el fragmento de experiencia deseado y, a continuación, haga clic en **[!UICONTROL Guardar]**.
1. Termine de configurar la actividad.

## Consideraciones {#considerations}

* [!DNL Target] busca fragmentos de experiencia para importar cada diez minutos. El fragmento de experiencia importado debe estar disponible en [!DNL Target] en un plazo de diez minutos, pero este intervalo de tiempo debe acortarse a partir de ahora.
* El fragmento de experiencia se importa actualmente a [!DNL Target] como una oferta HTML. Tenga en cuenta que la versión &quot;principal&quot; del fragmento de experiencia permanece en [!DNL AEM]. No puede editar el fragmento de experiencia en [!DNL Target].
* Puede importar ofertas JSON como fragmentos de experiencia en [!DNL Target]. Sin embargo, estas ofertas se importan como ofertas HTML. Actualmente, las ofertas JSON (fragmentos de experiencia) no son totalmente compatibles con la interfaz de usuario [!DNL Target].
* No se pueden crear fragmentos de experiencia con E/S de Adobe. Debe crear fragmentos de experiencia con AEM, como se explica más arriba.

## Vídeo de capacitación: Uso de fragmentos de experiencia AEM con Adobe Target ![Tutorial badge](/help/assets/overview.png) {#section_C0EDC54063464F41A182492D2045BC64}

El siguiente vídeo muestra cómo configurar y utilizar fragmentos de experiencia:

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>Se ha eliminado la función de vínculo profundo [!DNL AEM] analizada a las 4:54.

Para obtener más información, consulte [Uso de fragmentos de experiencia con Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html) en la página *Vídeos y Tutorials de AEM Sites*.
