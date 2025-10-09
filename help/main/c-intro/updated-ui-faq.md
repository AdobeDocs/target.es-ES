---
keywords: interfaz de usuario de target;interfaz de usuario;iu;preguntas más frecuentes;faq
description: Preguntas y respuestas acerca de la interfaz de usuario  [!DNL Target]t actualizada.
title: ¿Dónde puedo encontrar preguntas frecuentes acerca de la  [!DNL Target] IU actualizada?
feature: Overview
exl-id: 75db4791-ca51-472d-99dd-583f7a74b222
source-git-commit: 6cba2e93d61d3044d1bf7ce2f5bb6cc1f2d71e4a
workflow-type: tm+mt
source-wordcount: '1875'
ht-degree: 1%

---

# Preguntas frecuentes sobre la actualización de IU [!DNL Target]

Como novedad en 2025, la interfaz de usuario [!DNL Adobe Target] rediseñada ofrece una experiencia más limpia e intuitiva para todos los usuarios. Estas preguntas frecuentes tratan sobre las actualizaciones clave de la interfaz de usuario de [!DNL Target] y [!UICONTROL Visual Experience Composer] (VEC), incluidos los cambios de navegación, las ubicaciones de características y la eliminación de la opción de IU temporal. Tanto si es un experto en marketing, desarrollador o administrador, es su guía para una transición sin problemas y flujos de trabajo más inteligentes.

## ¿Se ha actualizado la cronología del cese de la compatibilidad con la versión de la interfaz de usuario de Target?

+++Ver detalles
El equipo [!DNL Target] ofrece una característica temporal que le permite cambiar entre la interfaz de usuario [!DNL Target] actualizada y la versión heredada con un botón de alternancia. Esta opción solo está disponible durante la fase final del despliegue de la interfaz de usuario.

![Alternar versión de IU de Target](/help/main/r-release-notes/assets/toggle.png)

Una vez completado el despliegue, se eliminará la opción y todos los usuarios harán la transición de forma permanente a la interfaz de usuario actualizada. [!DNL Adobe] recomienda planificar con anticipación, ya que esta función se eliminará gradualmente en breve.

### Cronología de desuso

Debido a problemas identificados recientemente, relacionados principalmente con personalizaciones complejas de clientes, el equipo [!DNL Target] ha ajustado la cronología de desuso:

* **17 de junio de 2025**: todas las organizaciones de IMS se han habilitado para la interfaz de usuario [!DNL Target] actualizada, ya sea para usuarios específicos o para toda la organización, para comenzar a probar la nueva experiencia.

* **30 de junio de 2025**: la [interfaz de usuario actualizada [!DNL Target] 4} se convirtió en la experiencia predeterminada para todas las organizaciones de IMS que han habilitado la opción de versión de interfaz de usuario.](/help/main/c-intro/understand-the-target-ui.md)

   * Los clientes que actualmente ven la IU heredada de forma predeterminada ahora ven la IU actualizada al iniciar sesión.
   * El conmutador Versión de la interfaz de usuario permanece disponible hasta finales de julio, lo que permite a los usuarios volver si es necesario.

  >[!IMPORTANT]
  >
  > [!DNL Adobe] recomienda encarecidamente usar la interfaz de usuario [!DNL Target] actualizada. Cambie a la interfaz de usuario heredada solo si se produce un problema de bloqueo debido a las [limitaciones del comportamiento del conmutador de alternancia](#limitations).

* **Del 15 de julio al 30 de julio de 2025**: la opción de versión de la interfaz de usuario se deshabilitará de forma permanente por fases. Las organizaciones de IMS afectadas ya no pueden volver a la IU heredada.

   * Las excepciones se examinan caso por caso.
   * Los retrasos en la desaprobación de la alternancia solo se conceden brevemente (unos días) mientras se resuelven los problemas del bloqueador.

Póngase en contacto con el servicio de atención al cliente de [Adobe](/help/main/cmp-resources-and-contact-information.md#/help/main/cmp-resources-and-contact-information.md) si tiene dudas o si prevé problemas durante esta transición.

### Limitaciones del comportamiento de alternancia de IU {#limitations}

La siguiente información describe las limitaciones que debe tener en cuenta al elegir utilizar la opción de versión:

* **Visibilidad de nuevas actividades**: las actividades creadas en la interfaz de usuario actualizada no serán visibles si vuelve a la interfaz de usuario heredada.
* **Edición de actividades existentes**: los cambios realizados en las actividades existentes (creadas originalmente en la interfaz de usuario heredada) al utilizar la interfaz de usuario actualizada se publican en el sitio web. Sin embargo, estas actualizaciones no están visibles en la interfaz de usuario heredada si vuelve; solo aparecen allí las últimas actualizaciones realizadas desde la interfaz de usuario heredada.
* **Consistencia de los detalles de la actividad**: los cambios más recientes, independientemente de la interfaz de usuario que utilice, se reflejarán en el sitio web activo. Sin embargo, la IU heredada solo muestra los cambios más recientes realizados desde esa versión. Esta situación puede causar confusión si las actividades editadas en la interfaz de usuario actualizada tienen un aspecto diferente al que se ve en la interfaz de usuario heredada.

### Recursos adicionales para obtener más información sobre la IU actualizada

* [[!DNL Target] Preguntas frecuentes sobre la actualización de la interfaz de usuario](/help/main/c-intro/updated-ui-faq.md): estas preguntas frecuentes tratan sobre las nuevas preguntas comunes acerca de la interfaz de usuario de [!DNL Target] y [!UICONTROL Visual Experience Composer] (VEC), incluidos los cambios de navegación, las ubicaciones de las características y la desaprobación de la opción de versión de la interfaz de usuario temporal. Tanto si es un experto en marketing, desarrollador o administrador, estas preguntas frecuentes le ayudan a realizar la transición sin problemas y a aprovechar al máximo la IU actualizada.
* [[!DNL Target Standard/Premium] 25.2.1 (17 de febrero de 2025) notas de la versión](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2): Proporciona un resumen de los cambios clave de la interfaz de usuario en [!DNL Target] para [!UICONTROL Activities], [!UICONTROL Recommendations] y [!UICONTROL Visual Experience Composer] (VEC).
* [[!DNL Target Standard/Premium] 25.1.1 (9 de enero de 2025) notas de la versión](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): Proporciona un resumen de los cambios clave de la interfaz de usuario en [!DNL Target] para [!UICONTROL Offers Library].
* [Comprender la [!DNL Target] IU](/help/main/c-intro/understand-the-target-ui.md): Proporciona una breve descripción general para ayudarle a familiarizarse con [!DNL Target] y proporciona vínculos para obtener información más detallada e instrucciones paso a paso.
* [[!UICONTROL Visual Experience Composer] cambios](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): La versión de [!DNL Adobe Target Standard/Premium] 25.2.1 (17 de febrero de 2015) presenta un [!UICONTROL Visual Experience Composer] (VEC) actualizado. Este artículo explica las diferencias entre las versiones heredadas y actualizadas del VEC.
* [[!UICONTROL Visual Experience Composer] opciones](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md): Este artículo explica la interfaz de usuario actualizada del VEC y sus opciones.

+++

## ¿Dónde puedo encontrar más información sobre la interfaz de usuario de [!DNL Target] actualizada?

+++Detalles
Los siguientes recursos proporcionan información para obtener más información sobre la interfaz de usuario de [!DNL Target] actualizada:

* [[!DNL Target Standard/Premium] 25.1.1 (9 de enero de 2025) notas de la versión](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): Proporciona un resumen de los cambios clave de la interfaz de usuario en [!DNL Target] para [!UICONTROL Offers Library].

* [Comprender la [!DNL Target] IU](/help/main/c-intro/understand-the-target-ui.md): Proporciona una breve descripción general para ayudarle a familiarizarse con [!DNL Target] y proporciona vínculos para obtener información más detallada e instrucciones paso a paso.

* [[!UICONTROL Visual Experience Composer] cambios](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): La versión de [!DNL Adobe Target Standard/Premium] 25.2.1 (17 de febrero de 2015) presenta un [!UICONTROL Visual Experience Composer] (VEC) actualizado. Este artículo explica las diferencias entre las versiones heredadas y actualizadas del VEC.

* [[!UICONTROL Visual Experience Composer] opciones](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md): Este artículo explica la interfaz de usuario actualizada del VEC y sus opciones.

+++

## ¿Está disponible la interfaz actualizada para todos los clientes actuales de [!DNL Target], [!UICONTROL Standard] y [!UICONTROL Premium]?

+++Detalles
La IU actualizada está disponible para todos los clientes de [!DNL Target], [!UICONTROL Standard] y [!UICONTROL Premium]. No se requiere ninguna licencia o SKU actualizada.

Para obtener más información sobre el despliegue y la desaprobación de la opción de versión de IU temporal, consulte [Actualizaciones con distinción de tiempo que necesita conocer](/help/main/r-release-notes/release-notes.md#time-sensitive).

+++

## ¿Se corregirá la lista actual de errores antes de que la IU heredada quede obsoleta?

+++Detalles
El equipo [!DNL Target] está abordando activamente los problemas relacionados con el nuevo despliegue de la interfaz de usuario. Las actualizaciones y mejoras en curso se detallan en las notas de la versión.

Para obtener más información sobre el despliegue y la desaprobación de la opción de versión de IU temporal, consulte [Actualizaciones con distinción de tiempo que necesita conocer](/help/main/r-release-notes/release-notes.md#time-sensitive).

+++

## ¿Pueden los clientes solicitar que la versión de la interfaz de usuario permanezca en sus cuentas si prefieren permanecer en la interfaz de usuario heredada?

+++Detalles
El conmutador de versión de interfaz de usuario es una característica temporal que le permite alternar entre la interfaz de usuario [!DNL Target] actualizada y la versión heredada mediante un botón de alternancia. Esta opción solo está disponible durante la fase final del despliegue de la interfaz de usuario. Una vez completado el despliegue, se eliminará la opción y todos los usuarios realizarán una transición permanente a la interfaz de usuario actualizada.

El uso de la opción de versión de la IU presenta varias limitaciones, como la visibilidad de las nuevas actividades, la edición de las actividades existentes y la coherencia de los detalles de la actividad.

Para obtener más información, consulte [Actualizaciones urgentes que necesita conocer](/help/main/r-release-notes/release-notes.md#time-sensitive).

++++

## ¿Puede [!DNL Adobe] retrasar nuestra migración a la interfaz de usuario actualizada hasta que se complete el despliegue completo?

+++Detalles
[!DNL Target] no ofrece la opción de retrasar o personalizar el tiempo de las migraciones a la interfaz de usuario. Los clientes se encuentran en transición por fases y la programación de despliegue está administrada por [!DNL Adobe]. Para obtener las últimas actualizaciones, consulte las notas de la versión.

El uso de la opción de versión de la IU presenta varias limitaciones, como la visibilidad de las nuevas actividades, la edición de las actividades existentes y la coherencia de los detalles de la actividad.

Para obtener más información, consulte [Actualizaciones urgentes que necesita conocer](/help/main/r-release-notes/release-notes.md#time-sensitive).

+++

## ¿Cómo gestiona el VEC actualizado las opciones de reorganizar, cambiar el tamaño, mover, ocultar y eliminar, y en qué se diferencian estas opciones del VEC heredado? {#options}

+++Detalles
**[!UICONTROL Rearrange*]*: en el VEC heredado, la opción de reorganizar usaba una superposición para permitir a los usuarios cambiar la posición de un elemento dentro de su grupo relacionado. El movimiento se limitaba a cambiar el orden entre los elementos del mismo nivel.

En el VEC actualizado, esta funcionalidad se optimiza mediante las acciones de avanzar y retroceder. Estos controles ajustan la posición de un elemento en el diseño, tanto horizontal como verticalmente, desplazándolo hacia adelante o hacia atrás en el orden de apilamiento.

**Cambiar tamaño**: la característica [!UICONTROL Resize] se encuentra en el panel [!UICONTROL Properties], en la sección [!UICONTROL Size]. Los usuarios pueden ajustar directamente la anchura y la altura de un elemento. La configuración avanzada incluye:

* Controles de anchura y altura mín./máx.
* Configuración de comportamiento de desbordamiento.
* Opciones de ajuste de objetos para elementos multimedia

Estas herramientas proporcionan un control preciso sobre las dimensiones de los elementos y el comportamiento del diseño.

**Mover**: la opción [!UICONTROL Move] se encuentra en el panel [!UICONTROL Properties], en la sección [!UICONTROL Position]. Esta opción permite a los usuarios:

* Establezca la posición del elemento (por ejemplo, absoluta, relativa, fija)
* Definición del índice Z para la creación de capas
* Elija un tipo de posicionamiento

El carril [!UICONTROL Properties] actualizado también admite estilos en línea personalizados, lo que ofrece flexibilidad cuando las opciones preestablecidas no satisfacen las necesidades de diseño.

**[!UICONTROL Hide]**: la característica [!UICONTROL Hide] se encuentra en el panel [!UICONTROL Properties]. Después de seleccionar un elemento, haga clic en [!UICONTROL Hide Element] para quitarlo de la vista sin eliminarlo. Esto resulta útil para administrar la visibilidad durante el diseño o la vista previa.

**[!UICONTROL Remove]**: se puede obtener acceso a la característica [!UICONTROL Remove] a través del panel [!UICONTROL Properties]. Después de seleccionar un elemento, haga clic en Quitar elemento para eliminarlo de la página. Esta acción elimina permanentemente el elemento del diseño.

+++

## ¿Puedo contraer los carriles [!UICONTROL Components], [!UICONTROL Modifications] y [!UICONTROL Properties] para poder ampliar el panel [!UICONTROL Design]? {#collapse}

+++Detalles

Sí, puede contraer estos raíles para permitirle expandir el lienzo [!UICONTROL Design] y facilitar la edición. A continuación se muestra cómo:

>[!NOTE]
>
>El icono [!UICONTROL Show Components] ( ![Mostrar icono de componentes](/help/main/assets/icons/Add.svg) ) y el icono [!UICONTROL Show Modifications] ( ![Mostrar carril de modificaciones](/help/main/assets/icons/History.svg) ) actúan como alternadores para mostrar las opciones adecuadas.

**Contraer el carril [!UICONTROL Components]**

Para contraer el carril [!UICONTROL Components] y ampliar el lienzo [!UICONTROL Design], mientras el carril [!UICONTROL Components] está abierto, haga clic en el icono ( ![Mostrar icono de componentes](/help/main/assets/icons/Add.svg) ).

**Contraer el carril [!UICONTROL Modifications]**

Para contraer el carril [!UICONTROL Modifications] y ampliar el lienzo [!UICONTROL Design], mientras el carril [!UICONTROL Modifications] está abierto, haga clic en el icono [!UICONTROL Show Modifications] ( ![Mostrar modificaciones](/help/main/assets/icons/History.svg) ).

**Contraer el carril [!UICONTROL Properties]**

Para contraer el carril [!UICONTROL Properties] y ampliar el lienzo [!UICONTROL Design], haga clic en el icono [!UICONTROL Show/Hide Properties] ( ![icono Propiedades](/help/main/assets/icons/Propertie.svg) ) a la derecha del carril para contraer o mostrar el carril [!UICONTROL Properties].

+++

## ¿Siguen estando disponibles los estados [!UICONTROL Save as Draft] y [!UICONTROL Syncing]?

+++Detalles
Con las últimas actualizaciones de la interfaz de usuario, los estados [!UICONTROL Save as Draft] y [!UICONTROL Syncing] ya no están disponibles. Para obtener más información, vea Estados en [Aplicar filtros a la lista de actividades](/help/main/c-activities/activities.md#filters) en *[!UICONTROL Activities overview]*.

+++

## ¿Cómo sé si una actividad se creó o editó en la interfaz de usuario heredada o en la actualizada?

+++Detalles
Las actividades creadas o editadas en la interfaz de usuario actualizada siguen el mismo flujo de trabajo guiado de tres pasos y pueden incluir metadatos o formato específicos de la interfaz de usuario que no están presentes en las actividades creadas anteriormente. Aunque no hay etiquetas visibles en la interfaz, las diferencias de diseño, estructura y opciones disponibles (como las funciones mejoradas de segmentación o vista previa) pueden indicar qué interfaz de usuario se ha utilizado. Para obtener una identificación detallada, consulte el historial de cambios de la actividad o sus registros de implementación.

+++

## ¿Cuáles son las diferencias entre la creación de ofertas en la interfaz de usuario heredada y la actualizada? ¿Se requieren atributos adicionales?

+++Detalles
La interfaz de usuario [!UICONTROL Offer Library] requiere definiciones de atributos coherentes para todas las ofertas. Al crear una oferta solo de actividad (ad hoc), los usuarios también deben especificar un nombre de oferta. Esta información aparece en [!UICONTROL Form-based Experience Composer], lo que facilita la identificación de ofertas sin revisar el código o el contenido.

+++

## ¿Qué ha pasado con los vínculos de vista previa de ofertas en la IU actualizada?

+++Detalles
Los vínculos de vista previa [!UICONTROL Experience Fragment] están disponibles en la ventana emergente [!UICONTROL Quick Info], que se muestra al hacer clic en el icono de información ( ![icono de información](/help/main/assets/icons/InfoOutline.svg) ) correspondiente al fragmento seleccionado.

+++

## Tengo que deshabilitar [!UICONTROL Enhanced Experience Composer] al editar actividades existentes con la interfaz de usuario actualizada. ¿Ha observado [!DNL Adobe] un comportamiento similar con otros clientes?

+++Detalles
Sí. Al usar [!DNL Adobe Experience Cloud] [!DNL Visual Editing Helper extension], es posible que tenga que deshabilitar [!UICONTROL Enhanced Experience Composer] (EEC)

Para obtener más información, consulte [extensión del Asistente de edición visual](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md).

+++

## ¿Puede decirme los detalles de las nuevas IP para la inclusión en la lista de permitidos?

+++Detalles
Para obtener más información acerca de las direcciones IP que puede lista de permitidos, consulte los siguientes artículos:

* **Compositor de experiencias mejorado (EEC)**: Consulte [El EEC no cargará una URL de control de calidad interna que no es accesible desde una IP pública](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md#section_D29E96911D5C401889B5EACE267F13CF) en *Resolución de problemas relacionados con el Compositor de experiencias mejorado*
* **[!UICONTROL Recommendations]**: vea [Direcciones IP que usan los servidores de procesamiento de fuentes de Recommendations](/help/main/c-recommendations/c-recommendations-faq/ip-addresses-marketing-cloud.md).

+++

## ¿El entorno se restablece al ensayo de forma predeterminada en la nueva interfaz de usuario de Recommendations?

+++Detalles
Ahora, los entornos predeterminados son los últimos que usa el cliente. Para cambiar de entorno, use el selector [!UICONTROL Environment] en la esquina superior derecha de la interfaz de usuario de [!UICONTROL Catalog Search].

![Conmutador de entorno](/help/main/c-intro/assets/environmnent.png)

+++

## ¿Cuán complejo es conectar [!DNL Adobe Analytics] o [!DNL Customer Journey Analytics] a [!DNL Target]?

+++Detalles
La integración de [!DNL Adobe Analytics] (AA) o [!DNL Customer Journey Analytics] (CJA) con [!DNL Target] puede variar de un esfuerzo moderado a avanzado, según la configuración actual. Si está usando [!DNL Adobe Experience Platform] y ha implementado [!DNL Platform Web SDK], la integración es más ágil. Sin embargo, las implementaciones heredadas que utilizan at.js o AppMeasurement pueden requerir una configuración adicional, que incluye:

* Habilitar la integración de [Analytics for Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md)
* Integrar [[!DNL Target] informes en [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md).
* Asignación de grupos de informes y vistas de datos
* Garantizar una resolución de identidad coherente (ECID)
* Validar la recopilación de datos y la configuración de atribución

+++
