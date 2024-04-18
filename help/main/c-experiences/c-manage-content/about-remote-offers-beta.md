---
keywords: oferta remota;contenido en caché;contenido dinámico;tipo de url
description: Aprenda a utilizar ofertas remotas en [!DNL Target] para alojar contenido externo (contenido en un CMS u otro sistema).
title: ¿Cómo Puedo Crear Ofertas Remotas?
feature: Experiences and Offers
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#beta newtab=true" tooltip="¿Qué son las funciones beta en  [!DNL Adobe Target]?"
hide: true
hidefromtoc: true
source-git-commit: bd7e6cc206f0d38ee6672c37d836e40b8831da1c
workflow-type: tm+mt
source-wordcount: '1087'
ht-degree: 21%

---

# Crear ofertas remotas

Utilice las ofertas remotas para alojar contenido fuera de [!DNL Adobe Target] al que [!DNL Target] haga referencia y que entregue a los sitios web de los usuarios. Este contenido puede encontrarse en un sistema de gestión de contenido (CMS) o en otro, por motivos de comodidad o de seguridad.

>[!NOTE]
>
>Este artículo contiene información sobre las actualizaciones de [!DNL Target] interfaz de usuario que actualmente forma parte de un programa beta. El [!DNL Adobe Target] A menudo, el equipo de habilita nuevas funciones para clientes seleccionados con fines de prueba y comentarios. Una vez completado el periodo de prueba, estas funciones se habilitarán para todos los clientes en el futuro [!DNL Target Standard/Premium] Versiones de y anunciadas en las notas de la versión.

Las ofertas remotas se pueden crear en [!UICONTROL Offers] > [!UICONTROL Code Offers] o en la [Compositor de experiencias basadas en Forms](/help/main/c-experiences/form-experience-composer.md). No puede crear ni aplicar ofertas remotas en [!UICONTROL Visual Experience Composer] (VEC). El contenido se inserta en [!DNL Target] ubicaciones de solicitudes, por lo que es muy probable que estas ubicaciones no sean adecuadas para una [!DNL Target] solicitud.

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

* Si la oferta reside en el mismo dominio que [!DNL Target] solicitudes, usando el [!UICONTROL Cached] Esta opción permite utilizar direcciones URL relativas para describir la ubicación de la oferta.

  Esto significa que, cuando mueve la actividad de los servidores de ensayo a la producción, el contenido es accesible automáticamente sin tener que cambiar la URL manualmente.

* Si la prueba incluye datos generados dinámicamente por el servidor, la variable [!UICONTROL Dynamic] podría ser la opción correcta.
* Si tiene pensado probar únicamente el aspecto del contenido de la oferta remota existente, utilice la variable [!UICONTROL Visual Experience Composer] para cambiar la apariencia del contenido que devuelve el sistema de administración de contenido.
* Utilice el [Matriz de selección de ofertas remotas](#reference_B23BEDD29DDD47709A7651AFD27E776B) (a continuación) para ayudarle a elegir la oferta más adecuada para su caso específico. Si tiene alguna pregunta, consulte con su representante de cuentas.

## Cree una oferta remota desde el [!UICONTROL Code Offers] página

1. Clic **[!UICONTROL Offers]**, luego seleccione la **[!UICONTROL Code Offers]** pestaña.

   ![Ofertas > Ofertas de código](/help/main/c-experiences/c-manage-content/assets/offers-code-offers-new.png)

1. Clic **[!UICONTROL Create Offer]** > **[!UICONTROL Remote Offer]**.

   ![Cuadro de diálogo Crear oferta remota](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui_new.png)

1. Escriba un nombre descriptivo para la oferta.

   Un nombre descriptivo le ayuda a usted y a otros a encontrar rápidamente la oferta en la [!UICONTROL Assets] biblioteca.

1. (Condicional) Si tiene un [Cuenta de Target Premium](/help/main/c-intro/intro.md#premium), seleccione el [workspace](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC).

1. Especifique el tipo de URL de redireccionamiento.

   Consulte [Tipo de URL de redireccionamiento: en caché o dinámico](#url-type) para obtener más información.

1. Especifique la dirección URL remota absoluta para la oferta remota.

1. Haga clic en **[!UICONTROL Create]**.

## Cree una oferta remota utilizando [!UICONTROL Form-Based Experience Composer]

1. Al crear una actividad con [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md), seleccione la ubicación para mostrar el **[!UICONTROL Content]** sección.

   ![Sección Contenido del Compositor de experiencias basadas en formularios](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. Haga clic en **[!UICONTROL Default Content]** y haga clic en. **[!UICONTROL Change Remote Offer]**.

   ![Opción Cambiar oferta remota](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. Clic **[!UICONTROL Create]** > **[!UICONTROL Remote Offer]**.

   ![Cuadro de diálogo Crear oferta remota](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. Escriba un nombre descriptivo para la oferta.

   Un nombre descriptivo le ayuda a usted y a otros a encontrar rápidamente la oferta en la [!UICONTROL Assets] biblioteca.

1. Especifique el tipo de URL de redireccionamiento.

   Consulte [Tipo de URL de redireccionamiento: en caché o dinámico](#url-type) para obtener más información.

1. Especifique la dirección URL remota para la oferta remota.

1. Haga clic en **[!UICONTROL Save]**.

## Tipo de URL de redireccionamiento: en caché o dinámico {#url-type}

La siguiente información le ayuda a comprender las diferencias entre las dos opciones:

### URL en caché

El contenido de una oferta remota en caché se proporciona desde [!DNL Target].

Cada dos horas, [!DNL Target] obtiene el contenido en la dirección URL remota y, a continuación, almacena el contenido en [!DNL Target]. Cuando los visitantes cargan un sitio con una experiencia que incluye una oferta remota, [!DNL Target] ofrece la oferta.

Las ofertas remotas en caché proporcionan una seguridad mejorada porque alguien ha iniciado sesión en [!DNL Target] no puede cambiar el contenido. Para cambiar el contenido, alguien tendría que registrar , u otro sistema, y cambiar el contenido allí.

En una oferta remota en caché, puede especificar una dirección URL absoluta o relativa.

### URL dinámica

Las ofertas remotas dinámicas se proporcionan desde el sistema de gestión de contenido o desde otro, no desde [!DNL Target].

Es posible que no desee que el contenido se almacene en caché periódicamente y que luego lo envíe [!DNL Target] cada vez que los visitantes carguen un sitio con una experiencia que incluya una oferta remota. En su lugar, debe llamar al sistema que aloja el contenido y posiblemente pasar información específica para que la oferta devuelta pueda ser dinámica (o diferente) para cada usuario. Por ejemplo, si un usuario inicia sesión en un sitio web de una tarjeta de crédito que incluye una experiencia con una oferta remota dinámica, podría pasar parámetros en la dirección URL relativos a la información de cuenta del usuario. Después, el sitio web podría dar información sobre el usuario, como el saldo de la cuenta.

Puede hacer clic en **[!UICONTROL Add Parameter]** para agregar una o más [!DNL Target] solicitudes o parámetros de solicitud.

## Usar ofertas remotas en actividades

Debe aplicar ofertas remotas utilizando [!UICONTROL Form-Based Experience Composer]. Actualmente no se pueden aplicar ofertas remotas usando el [!UICONTROL Visual Experience Composer] (VEC).

El [!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] es una interfaz no visual de creación de ofertas y experiencias que resulta útil para crear experiencias para utilizarlas en [!UICONTROL A/B Tests], [!UICONTROL Experience Targeting] (XT), [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Recommendations] actividades cuando la variable [!UICONTROL Visual Experience Composer] no está disponible o su uso no es práctico. Por ejemplo, puede utilizar la variable [!UICONTROL Form-Based Experience Composer] para crear experiencias que utilicen ofertas remotas.

1. Cree o edite una actividad en [!UICONTROL Form-Based Experience Composer].

   Consulte [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md) para obtener instrucciones detalladas paso a paso.

1. Especifique la ubicación deseada y añada los refinamientos de audiencia que sean necesarios.

1. Haga clic en la lista desplegable en la **[!UICONTROL Content]** y haga clic en **[!UICONTROL Change Remote Offer]**.

   ![Opción Cambiar oferta remota](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. Seleccione la oferta remota que desee en [!UICONTROL Select Remote Offer] y haga clic en **[!UICONTROL Done]**.

1. Termine de configurar la actividad.

## Funcionamiento de las ofertas remotas dinámicas {#concept_CC2A969420B34364A9FA78C1CE251818}

Las ofertas remotas dinámicas utilizan la tecnología de su página dinámica para pasar los valores a la oferta.

La oferta se ejecuta después de que procese la página. Un iFrame invisible recopila los datos, los copia fuera del marco y los inserta en la página cargando los valores pasados.

![imagen remote_offer_howitworks_2](assets/remote_offer_howitworks_2.jpeg)

1. El explorador del visitante solicita una página de su servidor.

2. El explorador procesa la página, incluidos los mboxes.

3. `mboxCreate` la llamada de incluye los parámetros necesarios para procesar contenido dinámico.

4. [!DNL Target] devuelve la dirección URL con la ubicación del contenido dinámico y sus parámetros. Establece un iFrame en el área de mbox.

5. El explorador solicita la URL y se procesa en la página.

## Matriz de selección de ofertas remotas {#reference_B23BEDD29DDD47709A7651AFD27E776B}

La matriz de selección de ofertas remotas le ayuda a decidir qué tipo de oferta remota elegir: [!UICONTROL Cached] o [!UICONTROL Dynamic].

| Función | En caché | Dinámica |
|--- |--- |--- |
| Se actualiza cada vez que un visitante hace una solicitud | No | Sí |
| Actualizaciones de contenido | En caché cada dos horas | Se actualiza de forma inmediata en cada solicitud |
| Tiempo de carga | Más rápido | Más lento debido al procesamiento de solicitudes |
| Se puede ver JavaScript en la página | Sí | No, pero se puede transmitir por URL |
| Las ofertas pueden incluir JavaScript | Sí | Sí |
| URL de la oferta | Absoluto o Relativo | Relativo |
| Equipo solicitante | Servidores de Adobe | El equipo del visitante, que lleva las cookies del visitante |

## Vídeo de formación: Compositor basado en formularios ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo proporciona una demostración de la [!UICONTROL Form-Based Experience Composer], que puede utilizar para crear ofertas remotas.

* Cree una actividad con la variable [!UICONTROL Form-Based Experience Composer]
* Comprender cuándo usar [!UICONTROL Form-Based Experience Composer] frente al [!UICONTROL Visual Experience Composer]
* Usar refinamientos para segmentar una ubicación

>[!VIDEO](https://video.tv.adobe.com/v/17390)