---
keywords: oferta remota;contenido en caché;contenido dinámico;tipo de url
description: Descubra cómo aprovechar ofertas remotas en  [!DNL Target]  para alojar contenido externo de un CMS u otros sistemas.
title: ¿Cómo Puedo Crear Ofertas Remotas?
feature: Experiences and Offers
exl-id: 6a5283ee-c1fb-49f7-8e7f-c23ccde26ade
source-git-commit: 856396264c4a7b7e3370cd268e7f010092e2eae2
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 19%

---

# Crear ofertas remotas

Use ofertas remotas para alojar contenido fuera de [!DNL Adobe Target], lo que permite que [!DNL Target] haga referencia a este contenido y lo envíe a los sitios web de los usuarios. Este contenido puede residir en un sistema de administración de contenido (CMS) u otro sistema por motivos de facilidad de uso o seguridad.

Las ofertas remotas se pueden crear en la página [!UICONTROL Offers] > [!UICONTROL Code Offers] o en el [Compositor de experiencias basadas en Forms](/help/main/c-experiences/form-experience-composer.md). No puede crear ni aplicar ofertas remotas en [!UICONTROL Visual Experience Composer] (VEC). El contenido se inserta en las ubicaciones de solicitud [!DNL Target], por lo que es muy probable que estas ubicaciones no sean apropiadas para una solicitud [!DNL Target] global.

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

* Las ofertas remotas son compatibles con:

   * Actividades A/B
   * Actividades de segmentación de experiencias (XT)
   * Flujos de trabajo basados en formularios

* Las ofertas remotas no son compatibles con:

   * [Funciones Premium](/help/main/c-intro/intro.md#premium) (Automated Personalization (AP), Segmentación automática y Recommendations)
   * Multivariate Testing (MVT), debido a la dependencia del VEC, que no admite ofertas remotas.

* Si la oferta reside en el mismo dominio que las solicitudes de [!DNL Target], el uso de la opción [!UICONTROL Cached] le permite utilizar direcciones URL relativas para describir la ubicación de la oferta.

  Esto significa que, cuando mueve la actividad de los servidores de ensayo a la producción, el contenido es accesible automáticamente sin tener que cambiar la URL manualmente.

* Si la prueba incluye datos generados dinámicamente por el servidor, la opción [!UICONTROL Dynamic] podría ser la correcta.
* Si planea probar solamente la apariencia del contenido de oferta remota existente, use [!UICONTROL Visual Experience Composer] para cambiar la apariencia del contenido devuelto desde el sistema de administración de contenido.
* Use la [Matriz de selección de ofertas remotas](#reference_B23BEDD29DDD47709A7651AFD27E776B) (abajo) para elegir la oferta más adecuada para su caso específico. Si tiene alguna pregunta, consulte con su representante de cuentas.

## Crear una oferta remota desde la página [!UICONTROL Code Offers]

1. Haga clic en **[!UICONTROL Offers]** y luego seleccione la ficha **[!UICONTROL Code Offers]**.

1. Haga clic en **[!UICONTROL Create Offer]** > **[!UICONTROL Remote Offer]**.

1. En el cuadro de diálogo [!UICONTROL Create Remote Offer], proporcione un nombre descriptivo para la oferta.

   Un nombre descriptivo le ayuda a usted y a otros a encontrar rápidamente la oferta en la biblioteca [!UICONTROL Offers].

1. (Condicional) Si tiene una [cuenta de Target Premium](/help/main/c-intro/intro.md#premium), seleccione el [espacio de trabajo](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC) que desee.

1. Especifique el tipo de URL de redireccionamiento.

   Consulte [Tipo de URL de redireccionamiento: [!UICONTROL Onsite Cached] o [!UICONTROL Onsite Dynamic]](#url-type) a continuación para obtener más información.

1. Especifique la dirección URL remota absoluta para la oferta remota.

1. Haga clic en **[!UICONTROL Create]**.

## Crear una oferta remota utilizando [!UICONTROL Form-Based Experience Composer]

1. Al crear una actividad con [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md), seleccione la ubicación para mostrar la sección **[!UICONTROL Content]**.
1. Haga clic en la lista desplegable **[!UICONTROL Content]**, luego en el icono **[!UICONTROL List]** ( ![Lista](/help/main/assets/icons/MoreSmallList.svg) ) y, por último, en **[!UICONTROL Change Remote Offer]**.

1. Haga clic en **[!UICONTROL Create Offer]** > **[!UICONTROL Remote Offer]**.

1. Escriba un nombre descriptivo para la oferta.

   Un nombre descriptivo le ayuda a usted y a otros a encontrar rápidamente la oferta en la biblioteca [!UICONTROL Assets].

1. (Condicional) Si tiene una [cuenta de Target Premium](/help/main/c-intro/intro.md#premium), seleccione el [espacio de trabajo](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC) que desee.

1. Especifique el tipo de URL de redireccionamiento.

   Consulte [Tipo de URL de redireccionamiento: [!UICONTROL Onsite Cached] o [!UICONTROL Onsite Dynamic]](#url-type) a continuación para obtener más información.

1. Especifique la dirección URL remota para la oferta remota.

1. Haga clic en **[!UICONTROL Create]**.

## Tipo de dirección URL de redireccionamiento: [!UICONTROL Onsite Cached] o [!UICONTROL Onsite Dynamic] {#url-type}

La siguiente información le ayuda a comprender las diferencias entre las dos opciones:

### URL [!UICONTROL Onsite Cached]

El contenido de una oferta remota en caché se suministra desde [!DNL Target].

Cada dos horas, [!DNL Target] busca el contenido en la dirección URL remota y luego almacena el contenido dentro de [!DNL Target]. Cuando los visitantes cargan un sitio con una experiencia que incluye una oferta remota, [!DNL Target] ofrece la oferta.

Las ofertas remotas en caché proporcionan una seguridad mejorada porque alguien que inició sesión en [!DNL Target] no puede cambiar el contenido. Para cambiar el contenido, la persona tendría que iniciar sesión en el sistema de gestión de contenido o en otro tipo de sistema y cambiarlo desde allí.

En una oferta remota en caché, puede especificar una dirección URL absoluta o relativa.

### URL [!UICONTROL Onsite Dynamic]

Una oferta remota dinámica se suministra desde el sistema de administración de contenido o desde otro, no desde [!DNL Target].

Es posible que no quiera que el contenido se almacene en caché periódicamente y que luego [!DNL Target] lo entregue cada vez que los visitantes carguen un sitio con una experiencia que incluya una oferta remota. En su lugar, debe llamar al sistema que aloja el contenido y posiblemente pasar información específica para que la oferta devuelta pueda ser dinámica (o diferente) para cada usuario. Por ejemplo, si un usuario inicia sesión en un sitio web de una tarjeta de crédito que incluye una experiencia con una oferta remota dinámica, podría pasar parámetros en la dirección URL relativos a la información de cuenta del usuario. Después, el sitio web podría dar información sobre el usuario, como el saldo de la cuenta.

Puede hacer clic en **[!UICONTROL Add Parameter]** para agregar una o más [!DNL Target] solicitudes o parámetros de solicitud.

## Usar ofertas remotas en actividades

Aplicar ofertas remotas utilizando [!UICONTROL Form-Based Experience Composer]. Actualmente no puede aplicar ofertas remotas usando el [!UICONTROL Visual Experience Composer] (VEC).

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] es una interfaz no visual y de creación de ofertas que resulta útil para crear experiencias para utilizarlas en las actividades [!UICONTROL A/B Tests], [!UICONTROL Experience Targeting] (XT), [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Recommendations] cuando [!UICONTROL Visual Experience Composer] no está disponible o su uso no es práctico. Por ejemplo, podría usar [!UICONTROL Form-Based Experience Composer] para crear experiencias que usen ofertas remotas.

1. Cree o edite una actividad en [!UICONTROL Form-Based Experience Composer].

   Consulte [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md) para obtener instrucciones detalladas paso a paso.

1. Especifique la ubicación deseada y añada los refinamientos de audiencia que sean necesarios.

1. Haga clic en la lista desplegable **[!UICONTROL Content]**, luego en el icono **[!UICONTROL List]** ( ![Lista](/help/main/assets/icons/MoreSmallList.svg) ) y, por último, en **[!UICONTROL Change Remote Offer]**.

1. Seleccione la oferta remota que desee en el cuadro de diálogo [!UICONTROL Change Remote Offer] y haga clic en **[!UICONTROL Create Offer]** > **[!UICONTROL Remote Offer]**.

1. Termine de configurar la actividad.

## Funcionamiento de las ofertas remotas dinámicas {#concept_CC2A969420B34364A9FA78C1CE251818}

Las ofertas remotas dinámicas utilizan la tecnología de su página dinámica para pasar los valores a la oferta.

La oferta se ejecuta después de que procese la página. Un iFrame invisible recopila los datos, los copia fuera del marco y los inserta en la página cargando los valores pasados.

![imagen remote_offer_howitworks_2](assets/remote_offer_howitworks_2.jpeg)

1. El explorador del visitante solicita una página de su servidor.

2. El explorador procesa la página, incluidos los mboxes.

3. La llamada a `mboxCreate` incluye los parámetros necesarios para procesar contenido dinámico.

4. [!DNL Target] devuelve una dirección URL con la ubicación del contenido dinámico y sus parámetros. Establece un iFrame en el área de mbox.

5. El explorador solicita la dirección URL y procesa la página.

## Matriz de selección de ofertas remotas {#reference_B23BEDD29DDD47709A7651AFD27E776B}

La matriz de selección de ofertas remotas le ayuda a decidir qué tipo de oferta remota elegir: [!UICONTROL Onsite Cached] o [!UICONTROL Onsite Dynamic].

| Función | Almacenamiento en caché in situ | Dinámico in situ |
|--- |--- |--- |
| Se actualiza cada vez que un visitante hace una solicitud | No | Sí |
| Actualizaciones de contenido | En caché cada dos horas | Se actualiza de forma inmediata en cada solicitud |
| Tiempo de carga | Más rápido | Más lento debido al procesamiento de solicitudes |
| Se puede ver JavaScript en la página | Sí | No, pero se puede transmitir por URL |
| Las ofertas pueden incluir JavaScript | Sí | Sí |
| URL de la oferta | Absoluto o Relativo | Relativo |
| Equipo solicitante | Servidores de Adobe | El equipo del visitante, que lleva las cookies del visitante |
