---
keywords: oferta remota;contenido en caché;contenido dinámico;tipo de url
description: Descubra cómo aprovechar ofertas remotas en  [!DNL Target]  para alojar contenido externo de un CMS u otros sistemas.
title: ¿Cómo Puedo Crear Ofertas Remotas?
feature: Experiences and Offers
exl-id: 6a5283ee-c1fb-49f7-8e7f-c23ccde26ade
TQID: https://experienceleague.adobe.com/maKcis5ROOKMcc3-axxGv1qJIQzC6o-Qc-Cjl8clQ1I
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d095671a-1355-40aa-8b5f-06c33c68080bid: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1145
ht-degree: 24%

---

# Crear ofertas remotas

Use ofertas remotas para alojar contenido fuera de [!DNL Adobe Target], lo que permite que [!DNL Target] haga referencia a este contenido y lo envíe a los sitios web de los usuarios. Este contenido puede residir en un sistema de administración de contenido (CMS) u otro sistema por motivos de facilidad de uso o seguridad.

Las ofertas remotas se pueden crear en la página [!UICONTROL Ofertas] > [!UICONTROL Ofertas de código] o en el [Compositor de experiencias basadas en Forms](/help/main/c-experiences/form-experience-composer.md). No puede crear ni aplicar ofertas remotas en el [!UICONTROL Compositor de experiencias visuales] (VEC). El contenido se inserta en las ubicaciones de solicitud [!DNL Target], por lo que es muy probable que estas ubicaciones no sean apropiadas para una solicitud [!DNL Target] global.

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

* Si su oferta reside en el mismo dominio que las solicitudes de [!DNL Target], el uso de la opción [!UICONTROL En caché] le permite utilizar direcciones URL relativas para describir la ubicación de la oferta.

  Esto significa que, cuando mueve la actividad de los servidores de ensayo a la producción, el contenido es accesible automáticamente sin tener que cambiar la URL manualmente.

* Si la prueba incluye datos que el servidor haya generado dinámicamente, tal vez [!UICONTROL Dinámica] sea la opción conveniente.
* Si solo planea comprobar la apariencia que tiene el contenido de la oferta remota existente, utilice el [!UICONTROL Compositor de experiencias visuales] para cambiar el aspecto del contenido que devuelve el sistema de gestión de contenido.
* Use la [Matriz de selección de ofertas remotas](#reference_B23BEDD29DDD47709A7651AFD27E776B) (abajo) para elegir la oferta más adecuada para su caso específico. Si tiene alguna pregunta, consulte con su representante de cuentas.

## Crear una oferta remota desde la página [!UICONTROL Ofertas de código]

1. Haga clic en **[!UICONTROL Ofertas]** y seleccione la pestaña **[!UICONTROL Ofertas de código]**.

1. Haga clic en **[!UICONTROL Crear oferta]** > **[!UICONTROL Oferta remota]**.

1. En el cuadro de diálogo [!UICONTROL Crear oferta remota], proporcione un nombre descriptivo para la oferta.

   Un nombre descriptivo le ayudará a usted y a otros a encontrar rápidamente la oferta en la biblioteca [!UICONTROL Ofertas].

1. (Condicional) Si tiene una [cuenta de Target Premium](/help/main/c-intro/intro.md#premium), seleccione el [espacio de trabajo](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC) que desee.

1. Especifique el tipo de URL de redireccionamiento.

   Consulte [Tipo de URL de redireccionamiento: [!UICONTROL En caché en el sitio] o [!UICONTROL Dinámico en el sitio]](#url-type) a continuación para obtener más información.

1. Especifique la dirección URL remota absoluta para la oferta remota.

1. Haga clic en **[!UICONTROL Crear]**.

## Crear una oferta remota mediante [!UICONTROL Compositor de experiencias basadas en formularios]

1. Al crear una actividad con el [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md), seleccione la ubicación para mostrar la sección **[!UICONTROL Contenido]**.
1. Haga clic en la lista desplegable **[!UICONTROL Contenido]**, haga clic en el icono **[!UICONTROL Lista]** ( ![Lista](/help/main/assets/icons/MoreSmallList.svg) ) y, a continuación, haga clic en **[!UICONTROL Cambiar oferta remota]**.

1. Haga clic en **[!UICONTROL Crear oferta]** > **[!UICONTROL Oferta remota]**.

1. Escriba un nombre descriptivo para la oferta.

   Un nombre descriptivo permite encontrar la oferta rápidamente en la biblioteca [!UICONTROL Activos].

1. (Condicional) Si tiene una [cuenta de Target Premium](/help/main/c-intro/intro.md#premium), seleccione el [espacio de trabajo](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC) que desee.

1. Especifique el tipo de URL de redireccionamiento.

   Consulte [Tipo de URL de redireccionamiento: [!UICONTROL En caché en el sitio] o [!UICONTROL Dinámico en el sitio]](#url-type) a continuación para obtener más información.

1. Especifique la dirección URL remota para la oferta remota.

1. Haga clic en **[!UICONTROL Crear]**.

## Tipo de URL de redireccionamiento: [!UICONTROL en caché] o [!UICONTROL dinámico en el sitio] {#url-type}

La siguiente información le ayuda a comprender las diferencias entre las dos opciones:

### [!UICONTROL Dirección URL almacenada en caché] in situ

El contenido de una oferta remota en caché se suministra desde [!DNL Target].

Cada dos horas, [!DNL Target] busca el contenido en la dirección URL remota y luego almacena el contenido dentro de [!DNL Target]. Cuando los visitantes cargan un sitio con una experiencia que incluye una oferta remota, [!DNL Target] ofrece la oferta.

Las ofertas remotas en caché proporcionan una seguridad mejorada porque alguien que inició sesión en [!DNL Target] no puede cambiar el contenido. Para cambiar el contenido, la persona tendría que iniciar sesión en el sistema de gestión de contenido o en otro tipo de sistema y cambiarlo desde allí.

En una oferta remota en caché, puede especificar una dirección URL absoluta o relativa.

### [!UICONTROL Dirección URL dinámica en el sitio]

Una oferta remota dinámica se suministra desde el sistema de administración de contenido o desde otro, no desde [!DNL Target].

Es posible que no quiera que el contenido se almacene en caché periódicamente y que luego [!DNL Target] lo entregue cada vez que los visitantes carguen un sitio con una experiencia que incluya una oferta remota. En su lugar, debe llamar al sistema que aloja el contenido y posiblemente pasar información específica para que la oferta devuelta pueda ser dinámica (o diferente) para cada usuario. Por ejemplo, si un usuario inicia sesión en un sitio web de una tarjeta de crédito que incluye una experiencia con una oferta remota dinámica, podría pasar parámetros en la dirección URL relativos a la información de cuenta del usuario. Después, el sitio web podría dar información sobre el usuario, como el saldo de la cuenta.

Puede hacer clic en **[!UICONTROL Agregar parámetro]** para agregar una o más [!DNL Target] solicitudes o parámetros de solicitud.

## Usar ofertas remotas en actividades

Aplicar ofertas remotas usando [!UICONTROL Compositor de experiencias basadas en formularios]. Actualmente no puede aplicar ofertas remotas usando el [!UICONTROL Compositor de experiencias visuales] (VEC).

[!DNL Adobe Target] [!UICONTROL Compositor de experiencias basadas en formularios] es una interfaz no visual y de creación de ofertas que resulta útil para crear experiencias para utilizarlas en [!UICONTROL pruebas A/B], [!UICONTROL Segmentación de experiencias] (XT), [!UICONTROL Automated Personalization] (AP) y actividades de [!UICONTROL Recommendations] cuando [!UICONTROL Compositor de experiencias visuales] no está disponible o su uso no es práctico. Por ejemplo, podría usar [!UICONTROL Compositor de experiencias basadas en formularios] para crear experiencias que usen ofertas remotas.

1. Cree o edite una actividad en [!UICONTROL Compositor de experiencias basadas en formularios].

   Consulte [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md) para obtener instrucciones detalladas paso a paso.

1. Especifique la ubicación deseada y añada los refinamientos de audiencia que sean necesarios.

1. Haga clic en la lista desplegable **[!UICONTROL Contenido]**, haga clic en el icono **[!UICONTROL Lista]** ( ![Lista](/help/main/assets/icons/MoreSmallList.svg) ) y, a continuación, haga clic en **[!UICONTROL Cambiar oferta remota]**.

1. Seleccione la oferta remota que desee en el cuadro de diálogo [!UICONTROL Cambiar oferta remota] y luego haga clic en **[!UICONTROL Crear oferta]** > **[!UICONTROL Oferta remota]**.

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

La matriz de selección de ofertas remotas le ayuda a decidir qué tipo de oferta remota elegir: [!UICONTROL En caché] o [!UICONTROL Dinámica in situ].

| Función | Almacenamiento en caché in situ | Dinámico in situ |
|--- |--- |--- |
| Se actualiza cada vez que un visitante hace una solicitud | No | Sí |
| Actualizaciones de contenido | En caché cada dos horas | Se actualiza de forma inmediata en cada solicitud |
| Tiempo de carga | Más rápido | Más lento debido al procesamiento de solicitudes |
| Se puede ver JavaScript en la página | Sí | No, pero se puede transmitir por URL |
| Las ofertas pueden incluir JavaScript | Sí | Sí |
| URL de la oferta | Absoluto o Relativo | Relativo |
| Equipo solicitante | Servidores de Adobe | El equipo del visitante, que lleva las cookies del visitante |
