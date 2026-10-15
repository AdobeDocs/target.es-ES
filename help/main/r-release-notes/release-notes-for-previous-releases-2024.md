---
keywords: Notas de la versión;notas de la versión preliminar;mejoras futuras;correcciones futuras;funciones futuras;próxima versión
description: Vea una lista de funciones, mejoras y correcciones incluidas en versiones anteriores de Adobe Target.
title: ¿Qué funciones se incluyen en versiones anteriores?
feature: Release Notes
source-git-commit: 53cd01d2406b8a2f8560fe380ebb5044872e6711
workflow-type: tm+mt
source-wordcount: '1232'
ht-degree: 16%
---
# Notas de la versión para versiones anteriores

Notas de la versión para versiones anteriores de [!DNL Adobe Target], incluidas las notas de la versión para [!DNL Target Standard/Premium], la plataforma [!DNL Target] y las bibliotecas Javascript de [!DNL Target] (at.js).

Las notas de la versión se enumeran en orden descendente por mes y año de publicación.

>[!NOTE]
>
>Consulte [Notas de la versión de Target (actual)](/help/main/r-release-notes/release-notes.md#reference_8FE40B43A5A34DDF8F26A53D55EE036A) para obtener información sobre las versiones de Target del mes actual (plataforma y Target Standard/Premium).

## Notas de la versión: 2024

### [!DNL Adobe Experience Platform Web SDK] `__view__` optimización del ámbito (22 de octubre de 2024)

Entre el 22 de julio de 2024 y el 15 de agosto de 2024, el equipo de [!DNL Target] optimizó el ámbito de `__view__`, lo que mejoró la precisión de los informes de impresión de actividad, visitas y visitantes. Esta optimización pretende capturar automáticamente los datos de los informes para las propuestas procesadas automáticamente y debe ser transparente para la mayoría de las cuentas.

Todos los clientes nuevos de [!DNL Adobe Experience Platform Web SDK] tendrán habilitada esta optimización. Sin embargo, los clientes que migraron desde at.js y no han seguido los pasos de implementación a continuación tienen la optimización deshabilitada. Instamos a estos clientes a revisar sus implementaciones antes del 3 de febrero de 2025. Después de esta fecha, habilitaremos la optimización para todos los clientes. Si no se revisan y ajustan las implementaciones para entonces, los informes podrían verse afectados, como se menciona a continuación. Póngase en contacto con [!DNL Adobe Customer Care] si necesita confirmar si la implementación se ve afectada o si necesita más tiempo para ajustar la implementación.

>[!IMPORTANT]
>
>Si no puede completar la revisión de la implementación y resolver cualquier problema antes del 3 de febrero de 2025, puede solicitar una extensión única de seis meses. Asegúrese de que su solicitud se haya enviado antes del 31 de enero de 2025. Adobe revisará y decidirá sobre su solicitud.

Para beneficiarse de esta optimización en caso de procesamiento manual de propuestas, revise su [[!DNL Platform Web SDK implementation]](https://experienceleague.adobe.com/es/docs/target-dev/developer/client-side/aep/aep-web-sdk-overview){target=_blank} para asegurarse de que está enviando notificaciones después de procesar manualmente experiencias o cuando utilice el método `applyPropositions` (o la acción [!DNL Launch] correspondiente como ayudante) para procesar experiencias.

Los escenarios más comunes en los que las experiencias se procesan manualmente incluyen:

* Uso de ofertas JSON
* Usando un ámbito de decisión personalizado en una actividad creada en [[!UICONTROL Compositor de experiencias basadas en formularios]](/help/main/c-experiences/form-experience-composer.md)
* No se usa `renderDecisions: true` al recuperar una actividad creada con el [!UICONTROL Compositor de experiencias basadas en formularios] que usa el ámbito global `__view__`

Si las notificaciones no se implementan como se documenta en [Procesar contenido personalizado](https://experienceleague.adobe.com/es/docs/experience-platform/web-sdk/personalization/rendering-personalization-content){target=_blank} en la guía de *Recopilación de datos*, es posible que falten datos de informes en [!DNL Target] y en [Informes de Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). En algunos casos, es posible que observe una división de tráfico incorrecta porque no se capturan los datos del sistema de informes. O, en otros casos, informar del mismo evento repetidamente.

Según la implementación, compruebe el impacto de los informes de [!DNL Analytics] y A4T.

[!DNL Platform Web SDK] admite dos tipos de implementación para procesar experiencias y personalizaciones:

* **Una sola llamada para personalización y medición.**

  Inicialmente recomendado, el método de una sola llamada para [!DNL Platform Web SDK] está programado para quedar obsoleto y pasar a ser el método de llamada dividida. Adobe aconseja a todas las nuevas implementaciones que utilicen el nuevo método de llamada dividida y recomienda que los clientes existentes también realicen la transición al método de llamada dividida.

  Si sigue usando el método de una sola llamada, es posible que observe los siguientes cambios inesperados en los informes de [!DNL Analytics]:

  * Un descenso en devoluciones.
  * Las visitas de A4T y [!UICONTROL Vista de página] no se han vinculado, lo que dificulta la realización de determinados desgloses y correlaciones en los informes de A4T con [!DNL Analytics] eVars y eventos.

* **Dividir llamadas (también conocidas como eventos de principio y final de página).**

  Este tipo de implementación es el nuevo [enfoque de implementación de llamada dividida](https://experienceleague.adobe.com/es/docs/experience-platform/web-sdk/use-cases/top-bottom-page-events){target=_blank} recomendado por [!DNL Adobe]. Con este enfoque, la nueva optimización no afecta a los informes de [!DNL Analytics] ni A4T.

Si tiene preguntas, comuníquese con el [Servicio de atención al cliente de Adobe](/help/main/cmp-resources-and-contact-information.md##reference_ACA3391A00EF467B87930A450050077C). (KB-2179)

### Versión 2.11.6 de at.js (lunes, 29 de septiembre de 2024)

* Se ha corregido un problema que impedía que [!DNL Target] funcionara correctamente con ofertas de redireccionamiento dentro del [!UICONTROL Compositor de experiencias visuales] (VEC) o [!UICONTROL Compositor de experiencias basadas en formularios].

Para obtener más información sobre las versiones de at.js, consulte [detalles de la versión de at.js](https://experienceleague.adobe.com/es/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions){target=_blank} en la *Guía para desarrolladores de Adobe Target*.

### Informes de [!DNL Target] en [!DNL Adobe Customer Journey Analytics] (8 de mayo de 2024)

La integración entre [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/es/docs/customer-journey-analytics){target=_blank} y [!DNL Target] proporciona potentes herramientas de análisis y ahorro de tiempo para su programa de optimización.

Las principales ventajas de utilizar [!DNL Customer Journey Analytics] como fuente de creación de informes para [!DNL Target] son:

* Los especialistas en marketing pueden aplicar de forma dinámica métricas de éxito de [!DNL Customer Journey Analytics] a informes de actividad de [!DNL Target] en cualquier momento. No es necesario especificarlo todo antes de ejecutar la actividad.
* Los especialistas en mercadotecnia pueden aprovechar las características de [!DNL Customer Journey Analytics], como el [Panel de experimentación](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-workspace/panels/experimentation){target=_blank}, para analizar más a fondo la personalización de su sitio web.

Para obtener más información, consulte Informes de [Target en Adobe Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md).

### Extensión del ayudante de [!UICONTROL Compositor de experiencias visuales] (23 de abril de 2024)

La extensión de ayuda heredada del Compositor de experiencias visuales [!DNL Target] se creó con Manifiesto V2. [!DNL Google] anunció que ya no permitirá extensiones creadas con Manifest V2 a partir de junio de 2024. Para obtener más información, consulte [[!UICONTROL Compositor de experiencias visuales] extensión de ayuda](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md).

[!DNL Adobe] recomienda que los clientes cambien a la nueva extensión [Ayuda de edición visual](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) lo antes posible.

### Actualizaciones para `Browser:iPad` y `Browser:iPhone` en los atributos de audiencia de [!UICONTROL Browser] (30 de abril de 2024)

| Actualizaciones | Detalles |
|--- |--- |
| [!UICONTROL Explorador:iPad] y [!UICONTROL Explorador:iPhone] actualizados en [Atributos del explorador](/help/main/c-target/c-audiences/c-target-rules/browser.md) usados al crear audiencias. | [!DNL Adobe Target] le permite [segmentar cualquiera de los atributos de categoría](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), incluidos los visitantes que usan [opciones de explorador o explorador](/help/main/c-target/c-audiences/c-target-rules/browser.md) específicas cuando visitan la página.<P>A partir de [!DNL Target] Standard/Premium 24.3.1 (del 4 al 6 de marzo de 2024), las audiencias integradas creadas con la interfaz de usuario de Target, como `Browser:iPad` y `Browser:iPhone`, se actualizarán para realizar el direccionamiento adecuado de [!DNL iPad] y [!DNL iPhone] mediante `profile.mobile.deviceVendor`, `profile.mobile.isMobilePhone` y `profile.mobile.isTablet`.<P>Esta actualización no requiere ninguna acción por parte de los clientes.<p><B>Importante</b>: Para que los clientes realicen el direccionamiento adecuado de [!DNL iPad] y [!DNL iPhone] en scripts de perfil (y segmentos de JavaScript), el cliente debe realizar cambios manuales antes del **30 de abril de 2024**. Para ver ejemplos de configuraciones alternativas que deben cambiarse manualmente, consulte [Actualizaciones para [!DNL iPad] y [!DNL iPhone] en [!UICONTROL Explorador] atributos de audiencia](/help/main/c-target/c-audiences/c-target-rules/browser.md#updates). |

### Extensión [!UICONTROL Ayuda de edición visual] (14 de marzo de 2024)

Esta versión incluye las siguientes mejoras y correcciones para la extensión [[!DNL Adobe Experience Cloud Editing Helper]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) de [!DNL Google Chrome]:

* Se ha mejorado el mecanismo de carga del iFrame al realizar la creación en los sitios web de los clientes.
* Se ha corregido un problema que hacía que la extensión duplicara cookies al realizar la creación en el [!UICONTROL Compositor de experiencias visuales] (VEC).

### [!DNL Target] Standard/Premium 24.3.1 (4-6 de marzo de 2024)

Esta versión incluye las siguientes mejoras y correcciones:

* Se ha corregido la lógica que calcula el número de selectores únicos en una actividad. (TGT-47878)
* Se ha corregido un problema que provocaba que las actividades [!UICONTROL Multivariate] (MVT) configuradas con los informes de [!UICONTROL Analytics for Target] (A4T) no se mostraran correctamente. (TGT-47490)
* Se ha mejorado el mensaje de advertencia que se muestra en los informes cuando se utiliza una experiencia sin tráfico como experiencia de control. (TGT-47537)
* Se han añadido muchas correcciones de back-end y localización.

### [!DNL Target] Standard/Premium 24.1.1 (22, 23, 24 y 25 de enero de 2024)

Esta versión incluye las siguientes mejoras y correcciones:

* Las actividades de [!UICONTROL Analytics for Target] (A4T) con métricas de objetivo de ingresos no mostraban &quot;Ingresos&quot; como nombre de columna y la métrica de ingresos no se mostraba en formato ($) en los informes. Se trataba de un problema estético que se ha corregido. (TGT-46995)
* Se ha corregido un problema que hacía que los intervalos de fecha de los informes no funcionaran correctamente. (TGT-47396)
* Se ha corregido un problema que provocaba que se mostrara un estado incorrecto en la página [!UICONTROL Todas las actividades] después de que los clientes activaran o desactivaran una actividad mediante el icono [!UICONTROL Más acciones]. (TGT-47367)
* Se ha corregido un problema que hacía que el informe [!UICONTROL Atributos importantes] no se mostrara para un solo cliente. (TGT-47272)
* Se ha corregido un problema que provocaba que se mostrara un mensaje “Carga útil no válida” cuando un único cliente intentaba habilitar “Requerir autenticación”. (TGT-47195)
* Se han actualizado varias cadenas localizadas en la IU de [!DNL Target].
