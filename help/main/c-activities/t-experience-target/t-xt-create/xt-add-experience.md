---
keywords: crear experiencia;crear;experiencia;prioridad;audiencia;experiencia;compositor de experiencias visuales
description: Aprenda a utilizar el  [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) para crear y editar experiencias en su página en una actividad de [!UICONTROL Experience Targeting] (XT).
title: ¿Cómo puedo crear experiencias en una actividad de [!UICONTROL Experience Targeting]?
feature: Experience Targeting
exl-id: ec3fcd93-5557-4f69-8f9c-4d00569188ad
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '897'
ht-degree: 24%

---

# Crear experiencia en actividades [!UICONTROL Experience Targeting] (XT)

El [!UICONTROL Visual Experience Composer] (VEC) de [!DNL Adobe Target] proporciona una interfaz visual para editar las experiencias en su página en una actividad [!UICONTROL Experience Targeting] (XT).

1. Seleccione los elementos que desee cambiar y realice los cambios necesarios.

   Mientras [crea una actividad [!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md), el paso uno del flujo de trabajo guiado de tres partes ([!UICONTROL Experiences]) muestra la audiencia [!UICONTROL Experience A] predeterminada con [!UICONTROL All Visitors].

   ![Audiencia de todos los visitantes](/help/main/c-activities/t-experience-target/t-xt-create/assets/all-visitors-new.png)

   Los cambios que realice ahora se aplican a [!UICONTROL Experience A]. En un paso inferior, haga clic en **[!UICONTROL Add Experience Targeting]** para crear experiencias adicionales.

   Al pasar el ratón por encima de los elementos de la página, estos se resaltan. Los elementos resaltados se pueden modificar con el VEC. Para obtener una lista de las acciones que se pueden realizar en un elemento para cambiar la experiencia, consulte [Opciones del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   >[!NOTE]
   >
   >De manera predeterminada, el VEC no permite realizar cambios en elementos que contengan JavaScript, como banners giratorios. Puede deshabilitar JavaScript para alterar esos elementos mediante el VEC.

1. Para crear experiencias adicionales, haga clic en **[!UICONTROL Add]** ( ![Botón Agregar](/help/main/assets/icons/Add.svg) ).

   Se muestra el cuadro de diálogo [!UICONTROL Add Audience]. Para segmentar una experiencia a una audiencia, seleccione la audiencia antes de añadir la experiencia.

   La biblioteca de audiencias contiene las audiencias que se han definido anteriormente, entre las que se incluyen algunas audiencias comunes predefinidas como parte de [!DNL Target]. Puede seleccionar una audiencia de la biblioteca o [crear una audiencia nueva](/help/main/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271).

   Además de seleccionar una audiencia existente, puede combinar varias audiencias para crear audiencias combinadas bajo demanda en lugar de crear una nueva. Para obtener más información, consulte [Combinar varias audiencias](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

   Al crear una audiencia, puede seleccionar una ubicación y especificar parámetros para esa ubicación. En [!UICONTROL Custom] ([!UICONTROL Create Audience] > [!UICONTROL Custom]), seleccione la ubicación y especifique los parámetros que desee.

   >[!NOTE]
   >
   >Las audiencias se importan automáticamente en segundo plano cuando abre la lista de audiencias y las audiencias importadas tienen más de diez minutos de antigüedad.

1. Seleccione una o más audiencias para segmentar con la experiencia y luego haga clic en **[!UICONTROL Assign Audience]**.

   La experiencia B ahora aparece en la ilustración anterior y está dirigida a la audiencia adecuada.

1. Seleccione los elementos que desee cambiar para esta experiencia y realice los cambios necesarios, tal como se explica en el paso 1 anterior.

1. Repita los pasos anteriores para crear más experiencias segmentadas, según sea necesario.

1. Haga clic en **[!UICONTROL Next]** cuando termine de diseñar las experiencias.

   Se muestra el diagrama de actividad:

   ![Diagrama de segmentación de XT](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-refresh.png)

   >[!NOTE]
   >
   >Puede enviar una imagen desde un origen distinto a la página principal (por ejemplo, una imagen alojada en `akamai.net` y entregada el `adobe.com`). Las imágenes alojadas en otra parte no se muestran en la miniatura de la página mostrada en el diagrama de flujo.

1. (Condicional) Arrastre y suelte los pares de audiencia y experiencia mientras crea o edita [!UICONTROL Experience Targeting] actividades para colocar los pares en el orden deseado.

   Haga clic en el icono Reordenar ( ![Icono Reordenar](/help/main/assets/icons/Reorder.svg) ) para mostrar la columna [!UICONTROL Experiences] a la derecha y, a continuación, reorganice las experiencias como desee.

   Las experiencias de los visitantes se evalúan en orden, de arriba abajo.

   [!UICONTROL Experience Targeting] supone que ese orden importa. Si un visitante entra en el primer par de audiencia y experiencia, se ofrece la primera experiencia.

   Por ejemplo, suponga que no sabía que el orden importaba al crear una actividad [!UICONTROL Experience Targeting]. Más tarde, durante la prueba, se dará cuenta de que los visitantes que cree que deberían cumplir los requisitos para las experiencias B o C cumplen los requisitos para la experiencia A. Esta situación podría deberse a que las audiencias no se excluyen mutuamente y no están en el orden adecuado (por ejemplo, experiencia A = Estados Unidos, experiencia B = San Francisco y experiencia C = California). En este escenario, todos los usuarios de Estados Unidos cumplen los requisitos para la experiencia A, incluso si están en San Francisco o en otro lugar de California. Puede reordenar los pares de audiencia y experiencia de más restrictivo a menos restrictivo (San Francisco > California > Estados Unidos) sin volver a crear toda la actividad.

   Si tiene una audiencia [!UICONTROL All Visitors], asegúrese de que no sea la primera audiencia en el diagrama. Se puede usar una experiencia segmentada a &quot;[!UICONTROL All Visitors]&quot; como la última experiencia de la actividad [!UICONTROL Experience Targeting] para &quot;captar&quot; a los visitantes que no han participado de otras experiencias.

## Cambiar el nombre, editar, duplicar o eliminar una experiencia

Haga clic en una experiencia en el diagrama de una actividad [!UICONTROL Experience Targeting] para mostrar la columna [!UICONTROL Experiences] a la derecha.

![Opciones de Cambiar nombre y editar](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience_edit-refresh.png)

Elija entre las siguientes opciones, según sea necesario:

* **[!UICONTROL Rename]**: escriba el nombre deseado en el campo [!UICONTROL Name].
* **[!UICONTROL Edit]**: haga clic en el icono Editar ( ![Editar icono](/help/main/assets/icons/Edit.svg) ) y realice los cambios que desee.
* **[!UICONTROL Duplicate]**: copie una experiencia en una actividad [!UICONTROL Experience Targeting] para que pueda realizar cambios menores sin tener que volver a crear la experiencia completa. Haga clic en el icono [!UICONTROL Duplicate] ( ![Icono duplicado](/help/main/assets/icons/Duplicate.svg) ) y, a continuación, edite la experiencia según sea necesario.
* **[!UICONTROL Delete]**: haga clic en el icono [!UICONTROL Delete] (![Eliminar icono](/help/main/assets/icons/Delete.svg) ) y confirme la eliminación.

## Vídeos de formación:

Los siguientes vídeos contienen más información sobre los conceptos mencionados en este artículo.

### De prueba A/B a [!UICONTROL Experience Targeting]

En este vídeo se describe cómo llevar las pruebas A/B al siguiente nivel con [!UICONTROL Experience Targeting] (XT).

* Describa el flujo de trabajo guiado de tres pasos para configurar una actividad [!UICONTROL Experience Targeting]
* Describa cómo distribuir contenido específico de una ubicación a audiencias de diferentes áreas geográficas
* Describe cómo se reordenan las experiencias para asegurar que cada contenido se envíe a la audiencia correcta

>[!VIDEO](https://video.tv.adobe.com/v/38303?captions=spa)

### Tipos de actividad (9:03)

En este vídeo se describen los tipos de actividades disponibles en [!DNL Target]. Se habla sobre [!UICONTROL Experience Targeting] a partir del minuto 5:15.

* Describe los tipos de actividades incluidas en [!DNL Adobe Target]
* Seleccionar el tipo de actividad adecuado para lograr los objetivos
* Describir el flujo de trabajo guiado de tres pasos que sirve para todos los tipos de actividad

>[!VIDEO](https://video.tv.adobe.com/v/30103?captions=spa)

### Usando [!UICONTROL Visual Experience Composer]

Este vídeo proporciona información sobre el uso de las opciones [!UICONTROL Experience Targeting] (VEC).

* Cambiar el contenido de una página
* Cambiar el diseño de una página

>[!VIDEO](https://video.tv.adobe.com/v/17399)
