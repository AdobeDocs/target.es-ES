---
keywords: opciones del compositor de experiencias visuales;opciones del compositor de experiencias;opciones de experiencia;decisión de oferta;offer decisioning;ajo;optimizador de recorridos
description: Obtenga información sobre cómo añadir una decisión de oferta creada en [!DNL Adobe Journey Optimizer] a una actividad.
title: ¿Cómo Se Utilizan Las Decisiones De Oferta?
feature: Integrations
exl-id: cec46d5c-bb5e-4cc9-8785-370f158d3f8e
source-git-commit: 7c15a0795e94b6c6317cb5b4018899be71f03a40
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 1%

---

# Uso de decisiones de oferta

Uso [!DNL Adobe Target] con [!DNL Adobe Journey Optimizer] ofrece decisiones para determinar y entregar la siguiente mejor oferta para sus visitantes en la web y dispositivos móviles.

Añadir decisiones de oferta creadas en [!DNL Adobe Journey Optimizer] hasta [!DNL Target] actividades (manual) [!UICONTROL Prueba A/B] o [!UICONTROL Segmentación de experiencias]) mediante el complemento [!UICONTROL Compositor de experiencias visuales] (VEC) o el [!UICONTROL Compositor basado en formularios] para probar y entregar ofertas personalizadas a los visitantes en sus canales de entrada con tecnología [!DNL Target].

Para obtener más información acerca de [!DNL Adobe Journey Optimizer] y decisiones de oferta, consulte los siguientes temas en la *[!DNL Journey Optimizer]* documentación:

* [Introducción a Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html)

* [Acerca de Administración de decisiones](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html)

## Requisitos previos  

Para usar decisiones de oferta en [!DNL Target], necesita lo siguiente:

* [!DNL Adobe Target Standard] o [!DNL Adobe Target Premium] implementado con la variable [SDK web de Adobe Experience Platform](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}.

   La función no está disponible al implementar [!DNL Target] con at.js u otro [!DNL Target] SDK.

* [!DNL Adobe Journey Optimizer Ultimate] (AJO + Offer decisioning) o [!DNL Adobe Experience Platform] y el [!UICONTROL Offer decisioning] complemento del servicio de aplicaciones.

## Ejemplos de uso

Los siguientes ejemplos son casos de uso de cómo se puede utilizar el [!DNL Target]/[!DNL Adobe Journey Optimizer] integración para utilizar decisiones de oferta en [!DNL Target] actividades:

### Comercialización deportiva

Como experto en marketing de una liga deportiva, desea personalizar el contenido de su página de inicio (tanto en el escritorio como en el sitio web móvil). Desea personalizar el contenido en función de varias dimensiones y presentar una oferta para la mercancía de la franquicia relacionada con la tienda. Está interesado en:

* El equipo favorito del visitante
* Actividad reciente del atleta/jugador (por ejemplo, movimiento del equipo, actualizaciones de contrato o lesiones)

Por ejemplo, desea ofrecer una experiencia personalizada para cada una de las siguientes regiones: Dortmund, Frankfurt y Bochum, y para los usuarios que son seguidores implícitos y explícitos de estos equipos. Como métricas, le interesa ver las visitas y los clics en el sitio de productos.

Desea diseñar un [!UICONTROL Prueba A/B] actividad (división 50/50) entre la experiencia predeterminada y la experiencia personalizada (que incluye una decisión de oferta con ofertas para cada región y equipo). Desea utilizar esta actividad para determinar la conversión y el alza de la experiencia personalizada en comparación con el control.

### Plataformas de transmisión de juegos

Como experto en marketing de una organización de juegos, le interesa ofrecer una oferta personalizada para una plataforma de transmisión de juegos para usuarios de equipos de escritorio y móviles de diferentes regiones geográficas: Alemania, Francia, México y Brasil. Cuando un visitante accede al sitio web de escritorio o móvil desde una de esas ubicaciones geográficas, quiere ofrecer una oferta de transmisión de juegos en línea en el idioma local y con el precio correspondiente en la moneda local.

Entrada [!DNL Adobe Journey Optimizer], puede crear una oferta personalizada de página principal a pantalla completa para cada una de las regiones segmentadas, además de una oferta de reserva con una página principal a pantalla completa predeterminada. A continuación, puede crear una decisión de oferta que incorpore estas ofertas y sus reglas de idoneidad. A continuación, en [!DNL Target], puede crear un [!DNL Experience Targeting] (XT) e inserte esa decisión de oferta en su sitio web de escritorio o móvil para ofrecer la experiencia personalizada a los visitantes.

## Cree una experiencia que utilice una decisión de oferta:

1. Al editar o crear un manual [!UICONTROL Prueba A/B] o [!UICONTROL Segmentación de experiencias] (XT) actividad en la [!UICONTROL Compositor de experiencias visuales] (VEC), haga clic en un elemento de página para mostrar el [menú opciones](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   ![Menú Opciones del Compositor de experiencias visuales](assets/options-menu1.png)

   >[!NOTE]
   >
   >También puede crear una experiencia que utilice [!UICONTROL Decisiones de oferta] en el [[!UICONTROL Compositor de experiencias basadas en formularios]](/help/main/c-experiences/form-experience-composer.md).

1. Clic **[!UICONTROL Insertar antes]**, **[!UICONTROL Insertar después]**, o **[!UICONTROL Reemplazar contenido]**, luego haga clic en **[!UICONTROL Decisión de oferta]**.

   El [!UICONTROL Decisión de oferta] está disponible al editar o crear [manual [!UICONTROL Prueba A/B]](/help/main/c-activities/t-test-ab/test-ab.md#types) o [[!UICONTROL Segmentación de experiencias]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) solo actividades de. Esta opción no está disponible para otros tipos de actividades. Las opciones disponibles en el menú varían según el elemento seleccionado.

   ![Menú Opciones del Compositor de experiencias visuales](assets/options-menu.png)

1. En el **[!UICONTROL Agregar decisión de oferta]** , seleccione la zona protegida y la ubicación deseadas.

   A [espacio aislado](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/overview.html){target=_blank} in the [!DNL Adobe Experience Platform] lets you partition your instance into virtual environments. For example, you might have a production environment and a staging environment. A [placement](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/create-components/creating-placements.html){target=_blank} in [!DNL Adobe Journey Optimizer] ayuda a garantizar que el contenido de oferta correcto se muestre en la ubicación correcta.

   ![Listas desplegables Zona protegida y Ubicaciones en el cuadro de diálogo Agregar decisión de oferta](/help/main/c-integrating-target-with-mac/ajo/assets/sandbox-placement.png)

1. Seleccione la decisión de oferta que desee y haga clic en **[!UICONTROL Crear]**.

   ![Decisión de oferta seleccionada en el cuadro de diálogo Agregar decisión de oferta](assets/offer-decision.png)

   Su sitio web se muestra en el VEC, donde puede ver la decisión de oferta recién creada en la [!UICONTROL Modificaciones] en el lado derecho. Puede pasar el ratón sobre la modificación y hacer clic en [!UICONTROL Previsualizar] para examinar la decisión de oferta.

   ![Icono de vista previa](assets/preview-icon.png)

   Puede examinar las distintas ofertas contenidas en la oferta haciendo clic en el icono correspondiente en la parte inferior de la [!UICONTROL Previsualización de oferta] , incluida la oferta de reserva. Una oferta de reserva es la oferta predeterminada que se muestra cuando un visitante no cumple los requisitos para ninguna de las ofertas personalizadas de la colección.

   ![Previsualización de oferta](assets/offer-preview.png)

1. Termine de crear la actividad completando el [!UICONTROL Segmentación] y [!UICONTROL Objetivos y configuración] pasos del flujo de trabajo guiado de tres partes.

   >[!IMPORTANT]
   >
   >Para garantizar que la variable [!DNL Target] la actividad está personalizada. asegúrese de que las fechas de inicio y finalización de la actividad actual estén sincronizadas con las fechas de inicio y finalización de la decisión de oferta en [!DNL Adobe Journey Optimizer]. Si la variable [!DNL Target] las fechas de inicio y finalización están fuera del intervalo de fechas de inicio y finalización de la decisión de oferta, el valor predeterminado [!DNL Target] el contenido se muestra a los visitantes.

   ![Mensaje de advertencia de decisión de oferta](/help/main/c-integrating-target-with-mac/ajo/assets/offer-decision-warning.png)

## Notas y limitaciones

Tenga en cuenta la siguiente información al trabajar con decisiones de oferta:

* La integración de offer decisioning funciona para [!DNL Target] implementaciones basadas en [SDK web de Adobe Experience Platform](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}. Esta función no está disponible al implementar [!DNL Target] con at.js u otro [!DNL Target] SDK.

* La integración de Target y Adobe Journey Optimizer es compatible con [manual [!UICONTROL Prueba A/B]](/help/main/c-activities/t-test-ab/test-ab.md#types) y [[!UICONTROL Segmentación de experiencias]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) solo actividades de. Esta función no está disponible para otros tipos de actividades.

* Las ofertas con el tipo de contenido text/html no admiten la entrega de contenido deliveryURL. La dirección URL de envío se admite a través del Compositor de experiencias basadas en formularios solo cuando el cliente es responsable de recuperar y maquetar explícitamente el contenido.

* [!DNL Target] La creación de informes de no proporciona informes de nivel de decisión de oferta.

* Visualización [Vínculos de control de calidad](/help/main/c-activities/c-activity-qa/activity-qa.md) para [!DNL Target] las experiencias que contienen decisiones de oferta afectan a la restricción de frecuencia establecida en [!DNL Adobe Journey Optimizer] para las decisiones de oferta.
