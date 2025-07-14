---
keywords: actividades;actividad;tipos de actividad;editar actividad;editar
description: Obtenga información sobre las distintas formas de editar una actividad existente.
title: ¿Cómo edito una actividad?
feature: Activities
exl-id: 5f2a930a-9950-430e-a898-50af1f917ec1
source-git-commit: c445775bc96623f9742f648a82ed9b4e64bd463a
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 41%

---

# Editar una actividad

Obtenga información sobre cómo editar actividades existentes en [!DNL Adobe Target]. Este artículo describe los diferentes métodos disponibles en la interfaz [!DNL Target] para modificar actividades. Ya sea que esté actualizando experiencias, ajustando reglas de segmentación o configurando metas, [!DNL Target] se asegura de que los cambios se guarden de forma segura antes de la activación.

[!DNL Target] proporciona varios lugares en la interfaz de usuario donde puede editar las actividades existentes. El proceso varía según el método que elija.

## Editar una actividad pasando sobre ella el cursor [!UICONTROL More Actions] en la página Actividades {#section_29EE2ECA6B88473A8F9AC5600FFBB174}

1. En la página **[!UICONTROL Activities]**, haga clic en el icono **[!UICONTROL More Actions]** ( ![icono Más acciones](/help/main/assets/icons/MoreSmall.svg) ) junto a la actividad que desea editar y, a continuación, haga clic en [!UICONTROL **Editar**].

   Target abre la actividad en [!UICONTROL Visual Experience Composer] (VEC) y usted ve la página [!UICONTROL Experiences] (el primer paso en el flujo de trabajo guiado de tres pasos).

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

## Trabajar con actividades heredadas creadas en [!DNL Recommendations Classic] {#classic}

La lista [!UICONTROL Activities] muestra actividades creadas en varias fuentes, entre ellas [!DNL Recommendations Classic]. Las siguientes acciones están disponibles cuando se trabaja con actividades heredadas creadas en [!DNL Recommendations Classic]:

* [!UICONTROL Activate]
* [!UICONTROL Deactivate]
* [!UICONTROL Archive]
* [!UICONTROL Copy]
* [!UICONTROL Delete]

No puede editar una actividad de [!DNL Recommendations] directamente. Si desea editar la actividad, debe crear una copia de la misma con [!DNL Target Premium] y luego guardar la actividad recién creada. Esta actividad recién creada se puede editar según se necesite.

## Guardar una actividad como borrador {#section_968CD7A63027432EBD8FAE3A0F7404C3}

La función Guardar como borrador ya no está disponible. Para obtener más información, consulte *[!UICONTROL Status]* en [Aplicar filtros a la lista de actividades](/help/main/c-activities/activities.md#filters).

## Copia/edición de una actividad al utilizar espacios de trabajo {#section_45A92E1DD3934523B07E71EF90C4F8B6}

Un espacio de trabajo permite que una organización asigne un conjunto de usuarios específico a un conjunto de propiedades concretas. En muchos aspectos, un espacio de trabajo es parecido a un grupo de informes en [!DNL Adobe Analytics].

>[!NOTE]
>
>Los espacios de trabajo son parte de la funcionalidad Propiedades y Permisos que está disponible como parte de la solución de [!DNL Target Premium]. No están disponibles en [!DNL Target Standard] sin una licencia de [!DNL Target Premium].

Si forma parte de una organización multinacional, puede tener un espacio de trabajo para sus páginas web, propiedades o sitios europeos y otro para sus páginas web, propiedades o sitios estadounidenses. Si forma parte de una organización de varias marcas, puede contar con un espacio de trabajo independiente para cada una.

Para obtener más información acerca de los espacios de trabajo y la funcionalidad Permisos de usuario de Enterprise, consulte [Permisos de usuario de Enterprise](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#concept_E396B16FA2024ADBA27BC056138F9838).

Si tiene Permisos de usuario de Enterprise habilitados en su entorno, puede copiar actividades en el mismo espacio de trabajo o en otro espacio de trabajo. No puede trasladar actualmente una actividad de un espacio de trabajo a otro. Para copiar una actividad en otro área de trabajo, en la página [!UICONTROL Activities], haga clic en el icono **[!UICONTROL More Actions]** ( ![icono Más acciones](/help/main/assets/icons/MoreSmall.svg) ) junto a la actividad que desee copiar y, a continuación, haga clic en [!UICONTROL **Copiar**].

Tenga en cuenta la siguiente información cuando utilice la funcionalidad de copiar/editar con espacios de trabajo:

* Cuando copia una actividad en el mismo espacio de trabajo, el primer paso del flujo de creación de la actividad recién copiada se abre en modo de edición.
* Cuando copia una actividad en un espacio de trabajo diferente, la actividad se copia en el otro espacio de trabajo sin abrirlo en el flujo de creación de actividades. Después de que la actividad se haya copiado correctamente, aparece un mensaje que indica que la actividad se copió con éxito e incluye un vínculo para abrir la nueva actividad.

Si su entorno no tiene habilitada la funcionalidad Permisos de usuario de Enterprise, todas las actividades se abren en el modo de edición antes de copiarse.