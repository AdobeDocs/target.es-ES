---
keywords: actividades;actividad;tipos de actividad;editar actividad;editar;copiar
description: Obtenga información sobre las distintas formas de editar una actividad existente.
title: ¿Cómo edito una actividad?
feature: Activities
exl-id: 5f2a930a-9950-430e-a898-50af1f917ec1
source-git-commit: 53bac4b1e778fb760a37e7287e0d8dbbe3a56b47
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 22%

---

# Editar una actividad

Obtenga información sobre cómo editar actividades existentes en [!DNL Adobe Target]. Este artículo describe los diferentes métodos disponibles en la interfaz [!DNL Target] para modificar actividades. Ya sea que esté actualizando experiencias, ajustando reglas de segmentación o configurando metas, [!DNL Target] se asegura de que los cambios se guarden de forma segura antes de la activación.

[!DNL Target] proporciona varios lugares en la interfaz de usuario donde puede editar las actividades existentes. El proceso varía según el método que elija.

## Editar una actividad pasando sobre ella el cursor [!UICONTROL More Actions] en la página Actividades {#section_29EE2ECA6B88473A8F9AC5600FFBB174}

1. En la página **[!UICONTROL Activities]**, haga clic en el icono **[!UICONTROL More Actions]** ( ![icono Más acciones](/help/main/assets/icons/MoreSmall.svg) ) junto a la actividad que desea editar y, a continuación, haga clic en [!UICONTROL **Editar**].

   [!DNL Target] abre la actividad en [!UICONTROL Visual Experience Composer] (VEC) y usted ve la página [!UICONTROL Experiences] (el primer paso en el flujo de trabajo guiado de tres pasos).

1. Edite la actividad según desee con las [Opciones de VEC](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

1. Haga clic en **[!UICONTROL Next]** para avanzar al siguiente paso y realice las modificaciones necesarias.

1. Cuando llegue a la página **Objetivos y configuración**, tiene las siguientes opciones:

   * **[!UICONTROL Save & Close]:** Haga clic en **[!UICONTROL Save and Close]** para guardar los cambios y mostrar la página [!UICONTROL Overview] de la actividad.
   * **Guardar:** Haga clic en el icono **[!UICONTROL More Actions]** ( ![icono Más acciones](/help/main/assets/icons/MoreSmallListVert.svg) ), luego seleccione **[!UICONTROL Save]** para guardar los cambios y permanecer en el VEC donde podrá realizar más cambios. Espere a que se acabe de guardar antes de realizar cambios adicionales. Después de guardarse, VEC vuelve a cargarse con los cambios actualizados.

## Edite una actividad haciendo clic en su nombre desde la página [!UICONTROL Activities] {#section_176180DAD17E40CEA441903F39E0AA1C}

1. Para evitar tener que pasar por todo el flujo de trabajo, haga clic en la actividad deseada de la página [!UICONTROL Activities] para abrirla, seleccione una opción en la lista desplegable **[!UICONTROL Edit Activity]** y, a continuación, seleccione la opción deseada.

   * **Editar experiencias:** lo lleva directamente a la página [!UICONTROL Experiences] (el primer paso en el flujo de trabajo guiado de tres pasos).
   * **Editar segmentación**: lo lleva directamente a la página [!UICONTROL Targeting] (el segundo paso en el flujo de trabajo guiado de tres pasos).
   * **[!UICONTROL Goals & Settings]**: lo lleva directamente a la página [!UICONTROL Goals & Settings] (el tercer paso en el flujo de trabajo guiado de tres pasos).

1. Realice los cambios que desee y, a continuación, guarde la actividad.

   * **[!UICONTROL Save & Close]:** Haga clic en **[!UICONTROL Save and Close]** para guardar los cambios y mostrar la página [!UICONTROL Overview] de la actividad.
   * **Guardar:** Haga clic en el icono **[!UICONTROL More Actions]** ( ![icono Más acciones](/help/main/assets/icons/MoreSmallListVert.svg) ), luego seleccione **[!UICONTROL Save]** para guardar los cambios y permanecer en el VEC donde podrá realizar más cambios. Espere a que se acabe de guardar antes de realizar cambios adicionales. Después de guardarse, VEC vuelve a cargarse con los cambios actualizados.

## Copiar/editar una actividad al utilizar espacios de trabajo {#section_45A92E1DD3934523B07E71EF90C4F8B6}

Un espacio de trabajo permite que una organización asigne un conjunto de usuarios específico a un conjunto de propiedades concretas. En muchos aspectos, un espacio de trabajo es parecido a un grupo de informes en [!DNL Adobe Analytics].

>[!NOTE]
>
>Los espacios de trabajo forman parte de la funcionalidad [!UICONTROL Properties and Permissions] disponible como parte de la solución [!DNL Target Premium]. No están disponibles en [!DNL Target Standard] sin una licencia de [!DNL Target Premium].

Si forma parte de una organización multinacional, puede tener un espacio de trabajo para sus páginas web, propiedades o sitios europeos y otro para sus páginas web, propiedades o sitios estadounidenses. Si forma parte de una organización de varias marcas, puede contar con un espacio de trabajo independiente para cada una.

Para obtener más información acerca de los espacios de trabajo y la funcionalidad Permisos de usuario de Enterprise, consulte [Permisos de usuario de Enterprise](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#concept_E396B16FA2024ADBA27BC056138F9838).

Si tiene [!UICONTROL Enterprise User Permissions] habilitado en su entorno, puede copiar actividades en el mismo espacio de trabajo o en otro espacio de trabajo. No puede trasladar actualmente una actividad de un espacio de trabajo a otro. Para copiar una actividad en otro área de trabajo, en la página [!UICONTROL Activities], haga clic en el icono **[!UICONTROL More Actions]** ( ![icono Más acciones](/help/main/assets/icons/MoreSmall.svg) ) junto a la actividad que desee copiar y, a continuación, haga clic en [!UICONTROL **Copiar**].

Tenga en cuenta la siguiente información cuando utilice la funcionalidad de copiar/editar con espacios de trabajo:

* Si copia una actividad en el mismo espacio de trabajo o desde el espacio de trabajo predeterminado a un espacio de trabajo no predeterminado, se abrirá automáticamente el Asistente para actividades. En las copias entre espacios de trabajo, es posible que solo necesite actualizar las propiedades de la actividad.
* Cuando se copia una actividad de un espacio de trabajo no predeterminado a otro espacio de trabajo (ya sea predeterminado o no predeterminado), se abre el Asistente de actividad y se requiere alguna entrada manual para completar la configuración:
   * **[!UICONTROL Properties]**: las propiedades pueden diferir entre espacios de trabajo. Esta situación podría generar un déclencheur de advertencia:

      * En [!UICONTROL Form-Based Experience Composer], las advertencias se muestran directamente en la interfaz de usuario para una visibilidad inmediata.

        ![Advertencia de espacio de trabajo basado en formularios](/help/main/c-activities/assets/form-based-warning.png)

      * En el VEC, las advertencias se pueden ver al hacer clic en [!UICONTROL Configure] > [!UICONTROL Properties].

        ![advertencia de vec](/help/main/c-activities/assets/vec-warning.png)

        Para resolver este problema, haga clic en [!UICONTROL Add/Remove] de modo que solo se muestren las propiedades disponibles en el área de trabajo de destino para su selección.

   * **Audiencias y ofertas**: al copiar una actividad en un área de trabajo nueva, todas las audiencias y ofertas asociadas del área de trabajo original se duplican con el formato: `Entity Name Copy <Date>`.

     Detalles del comportamiento:

      * Las audiencias y ofertas copiadas no aparecen en las listas [!UICONTROL Audiences] y [!UICONTROL Offers] hasta que se guarda y se vuelve a abrir la actividad.
      * Estas entidades no se pueden editar inmediatamente después de copiarlas. Es posible que los clientes vean contenido vacío en el VEC para estos elementos durante la sesión de edición inicial.
      * Los clientes pueden reemplazar audiencias u ofertas copiadas con otras desde el espacio de trabajo de destino si es necesario.

     Este proceso garantiza una duplicación más fluida de las actividades entre espacios de trabajo al tiempo que mantiene la flexibilidad para la personalización.

     Al copiar una actividad, las audiencias combinadas, las audiencias que no son de destino y las ofertas que no se guardan en el espacio de trabajo actual o en el predeterminado deben reemplazarse manualmente.

     Sustituir manualmente estas audiencias combinadas, audiencias no segmentadas y ofertas garantiza que solo se utilicen entidades válidas y accesibles en la actividad copiada y evita errores durante la edición o el envío.

     ![Mensaje de advertencia](/help/main/c-activities/assets/copy.png)

>[!NOTE]
>
>Si su entorno no tiene habilitada la funcionalidad [!UICONTROL Enterprise User Permissions], todas las actividades se abren en el modo de edición antes de copiarse.

## Guardar una actividad como borrador {#section_968CD7A63027432EBD8FAE3A0F7404C3}

La característica [!UICONTROL Save as Draft] ya no está disponible. Para obtener más información, consulte *[!UICONTROL Status]* en [Aplicar filtros a la lista de actividades](/help/main/c-activities/activities.md#filters).

## Trabajar con actividades heredadas creadas en [!DNL Recommendations Classic] {#classic}

La lista [!UICONTROL Activities] muestra actividades creadas en varias fuentes, entre ellas [!DNL Recommendations Classic]. Las siguientes acciones están disponibles cuando se trabaja con actividades heredadas creadas en [!DNL Recommendations Classic]:

* [!UICONTROL Activate]
* [!UICONTROL Deactivate]
* [!UICONTROL Archive]
* [!UICONTROL Copy]
* [!UICONTROL Delete]

No puede editar una actividad de [!DNL Recommendations] directamente. Si desea editar la actividad, debe crear una copia de la misma con [!DNL Target Premium] y luego guardar la actividad recién creada. Esta actividad recién creada se puede editar según se necesite.