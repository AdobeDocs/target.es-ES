---
keywords: remote offer;remote offer selection matrix;cached content;dynamic content
description: ¿Puedo utilizar ofertas remotas para alojar contenido externo?
title: Crear ofertas remotas
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: d966727239d982116e3cd1c2925cb1627e2954ea
workflow-type: tm+mt
source-wordcount: '845'
ht-degree: 59%

---


# Crear ofertas remotas

Utilice las ofertas remotas para alojar contenido fuera de [!DNL Adobe Target][!DNL Target] al que haga referencia y que entregue a los sitios web de los usuarios. Este contenido puede estar en un gestor de contenido (CMS) u otro sistema, ya sea por motivos de facilidad de uso o de seguridad.

>[!NOTE]
>
>Las ofertas remotas se pueden crear en la página Ofertas > Ofertas de código o en el [Compositor de experiencias basadas en Forms](/help/c-experiences/form-experience-composer.md). No se pueden crear ofertas remotas en el Compositor de experiencias visuales (VEC). El contenido se insertará en las ubicaciones de solicitud [!DNL Target], por lo que es muy probable que no sean apropiadas para una solicitud global [!DNL Target].
>
>[!DNL Target Classic] incluía funciones similares: [!UICONTROL Oferta en su sitio] y [!UICONTROL Oferta fuera de Test&amp;Target].

Algunos ejemplos de ofertas remotas son:

* Diferentes versiones de las ventas cruzadas
* Mensajes dinámicos de carro de compras
* Formularios
* Calculadoras
* Actualizaciones de la tasa de interés

## Crear una oferta remota desde la página Ofertas de código

1. Haga clic en **[!UICONTROL Ofertas]** y seleccione la pestaña **[!UICONTROL Ofertas de código]**.

   ![Ofertas > Ofertas de código](/help/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. Haga clic en **[!UICONTROL Crear]** > **[!UICONTROL Oferta remota]**.

   ![Cuadro de diálogo Crear Oferta remota](/help/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. Escriba un nombre descriptivo para la oferta.

   Un nombre descriptivo permite encontrar la oferta rápidamente en la biblioteca [!UICONTROL Activos].

1. Especifique el tipo de URL de redirección.

   Consulte [Tipo de dirección URL de redireccionamiento: En caché o dinámica](#url-type) a continuación para obtener más información.

1. Indique la dirección URL remota de la oferta remota.

1. Haga clic en **[!UICONTROL Guardar]**.

## Creación de una oferta remota mediante el Compositor de experiencias basadas en formularios

1. Al crear una actividad con el [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md), seleccione la ubicación en la que desea mostrar la sección **[!UICONTROL Contenido]**.

   ![Sección Contenido del Compositor de experiencias basadas en formularios](/help/c-experiences/c-manage-content/assets/form-based-content.png)

1. Haga clic en la lista desplegable **[!UICONTROL Contenido predeterminado]** y, a continuación, haga clic en **[!UICONTROL Cambiar Oferta remota]**.

   ![Cambiar la opción Oferta remota](/help/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. Haga clic en **[!UICONTROL Crear]** > **[!UICONTROL Oferta remota]**.

   ![Cuadro de diálogo Crear Oferta remota](/help/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. Escriba un nombre descriptivo para la oferta.

   Un nombre descriptivo permite encontrar la oferta rápidamente en la biblioteca [!UICONTROL Activos].

1. Especifique el tipo de URL de redirección.

   Consulte [Tipo de dirección URL de redireccionamiento: En caché o dinámica](#url-type) a continuación para obtener más información.

1. Indique la dirección URL remota de la oferta remota.

1. Haga clic en **[!UICONTROL Guardar]**.

## Tipo de dirección URL de redireccionamiento: En caché o dinámico {#url-type}

La siguiente información le ayuda a comprender las diferencias entre las dos opciones:

### Tipo de dirección URL en caché

El contenido de una oferta remota en caché se suministra desde [!DNL Target].

Cada dos horas, [!DNL Target] busca el contenido en la dirección URL remota y luego almacena el contenido dentro de [!DNL Target]. Cuando los visitantes cargan un sitio con una experiencia que incluye una oferta remota, la oferta se envía a través de [!DNL Target].

Las ofertas remotas en caché proporcionan una seguridad mejorada porque alguien que inició sesión en [!DNL Target] no puede cambiar el contenido. Para cambiar el contenido, la persona tendría que iniciar sesión en el sistema de gestión de contenido o en otro tipo sistema y cambiarlo desde ahí.

En una oferta remota en caché, puede especificar una dirección URL absoluta o relativa.

### Tipo de dirección URL dinámica

Una oferta remota dinámica se suministra desde el sistema de gestión de contenido o desde otro, no desde [!DNL Target].

Es posible que no quiera que el contenido se almacene en caché regularmente y que luego [!DNL Target] lo envíe cuando los visitantes carguen un sitio con una experiencia que incluya una oferta remota. En su lugar, desea llamar al sistema que aloja el contenido y posiblemente pasar información específica para que la oferta devuelta pueda ser dinámica (o diferente) para cada usuario. Por ejemplo, si un usuario inicia sesión en un sitio web de una tarjeta de crédito que incluye una experiencia con una oferta remota dinámica, podría pasar parámetros en la dirección URL relativos a la información de cuenta del usuario. Después, el sitio web podría dar información sobre el usuario, como el saldo de la cuenta.

Puede hacer clic en **[!UICONTROL Añadir parámetro]** para agregar una o más [!DNL Target] solicitudes o parámetros de solicitud.

## Prácticas recomendadas para utilizar ofertas remotas {#section_7718512D08E14121B6F6B8C38134F4BC}

Prácticas recomendadas para el uso de ofertas remotas en las actividades:

* Si la oferta reside en el mismo dominio que las solicitudes [!DNL Target], el uso de la opción [!UICONTROL Caché] permite utilizar direcciones URL relativas para describir la ubicación de la oferta.

   Esto supone que, cuando traslade la actividad de los servidores de ensayo a producción, el contenido pasará a ser accesible automáticamente, sin necesidad de cambiar la dirección URL manualmente.

* Si la prueba incluye datos que el servidor haya generado dinámicamente, tal vez [!UICONTROL Dinámica] sea la opción conveniente.
* Si solo planea comprobar la apariencia que tiene el contenido de la oferta remota existente, utilice el [!UICONTROL Compositor de experiencias visuales] para cambiar el aspecto del contenido que devuelve el sistema de gestión de contenido.
* Utilice la matriz de selección de Ofertas remotas (a continuación) para ayudarle a elegir la oferta más adecuada para su caso específico. Si tiene alguna pregunta, consulte con su representante de cuentas.

## Cómo funcionan las ofertas remotas dinámicas {#concept_CC2A969420B34364A9FA78C1CE251818}

Las ofertas remotas dinámicas utilizan la tecnología de su página dinámica para pasar los valores a la oferta.

La oferta se ejecuta después de que procese la página. Un iframe invisible recopila los datos, los copia del marco y los inserta en la página, cargando los valores pasados.

![](assets/remote_offer_howitworks_2.jpeg)

## Matriz de selección de oferta remota {#reference_B23BEDD29DDD47709A7651AFD27E776B}

La matriz de selección de ofertas remotas ayuda a decidir qué tipo de oferta remota utilizar: [!UICONTROL En caché] o [!UICONTROL Dinámica].

| Función | En caché | Dinámica |
|--- |--- |--- |
| Se actualiza cada vez que un visitante hace una solicitud | No | Sí |
| Actualizaciones de contenido | En caché cada 2 horas | Se actualiza de forma inmediata en cada solicitud |
| Tiempo de carga | Más rápido | Más lento debido al procesamiento de solicitudes |
| Se puede ver JavaScript en la página | Sí | No, pero se puede transmitir por URL |
| Las ofertas pueden incluir JavaScript | Sí | Sí |
| URL de la oferta | Absoluta o relativa | Relativo |
| Equipo solicitante | Servidores de Adobe | El equipo del visitante, que lleva las cookies del visitante |