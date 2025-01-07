---
keywords: oferta remota;matriz de selección de ofertas remotas;contenido en caché;contenido dinámico;tipo de url
description: Aprenda a utilizar ofertas remotas en el Adobe  [!DNL Target] para alojar contenido externo (contenido en un CMS u otro sistema). Descubra por qué podría querer utilizar ofertas remotas.
title: ¿Cómo Puedo Crear Ofertas Remotas?
feature: Experiences and Offers
exl-id: 6a5283ee-c1fb-49f7-8e7f-c23ccde26ade
source-git-commit: e8201198dc6ac36e803153d5c6b345a30716204a
workflow-type: tm+mt
source-wordcount: '1017'
ht-degree: 29%

---

# Crear ofertas remotas

Utilice las ofertas remotas para alojar contenido fuera de [!DNL Adobe Target] al que [!DNL Target] haga referencia y que entregue a los sitios web de los usuarios. Este contenido puede encontrarse en un sistema de gestión de contenido (CMS) o de otro tipo por cuestiones de comodidad o de seguridad.

>[!NOTE]
>
>Las ofertas remotas se pueden crear en la página [!UICONTROL Offers] > [!UICONTROL Code Offers] o en el [Compositor de experiencias basadas en Forms](/help/main/c-experiences/form-experience-composer.md). No puede crear ni aplicar ofertas remotas en el Compositor de experiencias visuales (VEC). El contenido se insertará en las ubicaciones de solicitud [!DNL Target], por lo que es muy probable que no sean adecuadas para una solicitud [!DNL Target] global.
>
>[!DNL Target Classic] incluyó características similares: [!UICONTROL Offer on Your Site] y [!UICONTROL Offer Outside Test&Target].

Algunos ejemplos de ofertas remotas son:

* Diferentes versiones de las ventas cruzadas
* Mensajes dinámicos de carro de compras
* Formularios
* Calculadoras
* Actualizaciones de la tasa de interés
* Correos electrónicos
* Quioscos
* Asistentes de voz

## Prácticas recomendadas para utilizar ofertas remotas {#section_7718512D08E14121B6F6B8C38134F4BC}

Prácticas recomendadas para el uso de ofertas remotas en las actividades:

* Si la oferta reside en el mismo dominio que las solicitudes de [!DNL Target], el uso de la opción [!UICONTROL Cached] le permite utilizar direcciones URL relativas para describir la ubicación de la oferta.

  Esto supone que, cuando traslade la actividad de los servidores de ensayo a producción, el contenido pasará a ser accesible automáticamente, sin necesidad de cambiar la dirección URL manualmente.

* Si la prueba incluye datos generados dinámicamente por el servidor, la opción [!UICONTROL Dynamic] podría ser la correcta.
* Si planea probar solamente la apariencia del contenido de oferta remota existente, use [!UICONTROL Visual Experience Composer] para cambiar la apariencia del contenido devuelto desde el sistema de administración de contenido.
* Use la [Matriz de selección de ofertas remotas](#reference_B23BEDD29DDD47709A7651AFD27E776B) (abajo) para elegir la oferta más adecuada para su caso específico. Si tiene alguna pregunta, consulte con su representante de cuentas.

## Cree una oferta remota desde la página Ofertas de código

1. Haga clic en **[!UICONTROL Offers]** y luego seleccione la ficha **[!UICONTROL Code Offers]**.

   ![Ofertas > Ofertas de código](/help/main/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. Haga clic en **[!UICONTROL Create]** > **[!UICONTROL Remote Offer]**.

   ![Cuadro de diálogo Crear oferta remota](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. Escriba un nombre descriptivo para la oferta.

   Un nombre descriptivo le ayuda a usted y a otros a encontrar rápidamente la oferta en la biblioteca [!UICONTROL Assets].

1. Especifique el tipo de URL de redireccionamiento.

   Consulte [Tipo de URL de redireccionamiento: en caché o dinámica](#url-type) a continuación para obtener más información.

1. Especifique la dirección URL remota para la oferta remota.

1. Haga clic en **[!UICONTROL Save]**.

## Crear una oferta remota mediante el Compositor de experiencias basadas en formularios

1. Al crear una actividad con [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md), seleccione la ubicación para mostrar la sección **[!UICONTROL Content]**.

   ![Sección de contenido en el Compositor de experiencias basadas en formularios](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. Haga clic en la lista desplegable **[!UICONTROL Default Content]** y luego haga clic en **[!UICONTROL Change Remote Offer]**.

   ![Cambiar opción de oferta remota](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. Haga clic en **[!UICONTROL Create]** > **[!UICONTROL Remote Offer]**.

   ![Cuadro de diálogo Crear oferta remota](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. Escriba un nombre descriptivo para la oferta.

   Un nombre descriptivo le ayuda a usted y a otros a encontrar rápidamente la oferta en la biblioteca [!UICONTROL Assets].

1. Especifique el tipo de URL de redireccionamiento.

   Consulte [Tipo de URL de redireccionamiento: en caché o dinámica](#url-type) a continuación para obtener más información.

1. Especifique la dirección URL remota para la oferta remota.

1. Haga clic en **[!UICONTROL Save]**.

## Tipo de URL de redireccionamiento: en caché o dinámico {#url-type}

La siguiente información le ayuda a comprender las diferencias entre las dos opciones:

### URL en caché

El contenido de una oferta remota en caché se suministra desde [!DNL Target].

Cada dos horas, [!DNL Target] busca el contenido en la dirección URL remota y luego almacena el contenido dentro de [!DNL Target]. Cuando los visitantes cargan un sitio con una experiencia que incluye una oferta remota, la oferta se entrega por [!DNL Target].

Las ofertas remotas en caché proporcionan una seguridad mejorada porque alguien que inició sesión en [!DNL Target] no puede cambiar el contenido. Para cambiar el contenido, la persona tendría que iniciar sesión en el sistema de gestión de contenido o en otro tipo sistema y cambiarlo desde ahí.

En una oferta remota en caché, puede especificar una dirección URL absoluta o relativa.

### URL dinámica

Una oferta remota dinámica se suministra desde el sistema de administración de contenido o desde otro, no desde [!DNL Target].

Es posible que no quiera que el contenido se almacene en caché periódicamente y que luego [!DNL Target] lo entregue cada vez que los visitantes carguen un sitio con una experiencia que incluya una oferta remota. En su lugar, debe llamar al sistema que aloja el contenido y posiblemente pasar información específica para que la oferta devuelta pueda ser dinámica (o diferente) para cada usuario. Por ejemplo, si un usuario inicia sesión en un sitio web de una tarjeta de crédito que incluye una experiencia con una oferta remota dinámica, podría pasar parámetros en la dirección URL relativos a la información de cuenta del usuario. Después, el sitio web podría dar información sobre el usuario, como el saldo de la cuenta.

Puede hacer clic en **[!UICONTROL Add Parameter]** para agregar una o más [!DNL Target] solicitudes o parámetros de solicitud.

## Usar ofertas remotas en actividades

Debe aplicar ofertas remotas usando [!UICONTROL Form-Based Experience Composer]. Actualmente no se pueden aplicar ofertas remotas mediante el VEC.

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] es una interfaz no visual y de creación de ofertas que resulta útil para crear experiencias para utilizarlas en las actividades [!UICONTROL A/B Tests], [!UICONTROL Experience Targeting] (XT), [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Recommendations] cuando Visual Experience Composer no está disponible o su uso no es práctico. Por ejemplo, podría usar [!UICONTROL Form-Based Experience Composer] para crear experiencias que usen ofertas remotas.

1. Cree o edite una actividad en [!UICONTROL Form-Based Experience Composer].

   Consulte [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md) para obtener instrucciones detalladas paso a paso.

1. Especifique la ubicación deseada y añada los refinamientos de audiencia que sean necesarios.

1. Haga clic en la lista desplegable de la sección **[!UICONTROL Content]** y, a continuación, haga clic en **[!UICONTROL Change Remote Offer]**.

   ![Cambiar opción de oferta remota](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. Seleccione la oferta remota que desee en el cuadro de diálogo [!UICONTROL Select Remote Offer] y haga clic en **[!UICONTROL Done]**.

1. Termine de configurar la actividad.

## Funcionamiento de las ofertas remotas dinámicas {#concept_CC2A969420B34364A9FA78C1CE251818}

Las ofertas remotas dinámicas utilizan la tecnología de su página dinámica para pasar los valores a la oferta.

La oferta se ejecuta después de que procese la página. Un iframe invisible recopila los datos, los copia fuera del marco y los inserta en la página cargando los valores pasados.

![imagen remote_offer_howitworks_2](assets/remote_offer_howitworks_2.jpeg)

## Matriz de selección de ofertas remotas {#reference_B23BEDD29DDD47709A7651AFD27E776B}

La matriz de selección de ofertas remotas le ayuda a decidir qué tipo de oferta remota elegir: [!UICONTROL Cached] o [!UICONTROL Dynamic].

| Función | En caché | Dinámica |
|--- |--- |--- |
| Se actualiza cada vez que un visitante hace una solicitud | No | Sí |
| Actualizaciones de contenido | En caché cada 2 horas | Se actualiza de forma inmediata en cada solicitud |
| Tiempo de carga | Más rápido | Más lento debido al procesamiento de solicitudes |
| Se puede ver JavaScript en la página | Sí | No, pero se puede transmitir por URL |
| Las ofertas pueden incluir JavaScript | Sí | Sí |
| URL de la oferta | Absoluto o Relativo | Relativo |
| Equipo solicitante | Servidores de Adobe | El equipo del visitante, que lleva las cookies del visitante |

## Vídeo de formación: Compositor basado en formularios ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo proporciona una demostración del compositor basado en formularios, que puede utilizar para crear ofertas remotas.

* Crear una actividad con el Compositor de experiencias basadas en formularios
* Entender cuándo usar el Compositor de experiencias basadas en formularios o el Compositor de experiencias visuales
* Usar refinamientos para segmentar una ubicación

>[!VIDEO](https://video.tv.adobe.com/v/17390)
