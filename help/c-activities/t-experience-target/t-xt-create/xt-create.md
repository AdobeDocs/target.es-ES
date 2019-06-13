---
description: Use el Compositor de experiencias visuales para crear una actividad de segmentación de experiencias en una página con Target habilitado y para modificar partes de la página en Target.
seo-description: Use el Compositor de experiencias visuales para crear una actividad de segmentación de experiencias en una página con Target habilitado y modificar partes de la página en Adobe Target.
seo-title: Crear una actividad de segmentación de experiencias
solution: Target
subtopic: Prueba multivariable
title: Crear una actividad de segmentación de experiencias
topic: Standard
uuid: 6299982b-b1ba-4dd0-9c69-36a76680a3e1
translation-type: tm+mt
source-git-commit: f81d3ab49dc2cd01b4025f542d3174abf0a3c0d6

---


# Crear una actividad de segmentación de experiencias{#create-an-experience-targeting-activity}

Use el [!UICONTROL Compositor de experiencias visuales] (VEC) para crear una [!UICONTROL actividad de segmentación] de experiencias (XT) en una página con Target habilitado y modificar partes de la página dentro [!DNL Adobe Target]de.

1. En la lista [!UICONTROL Actividades], haga clic en **[!UICONTROL Crear actividad]** &gt; **[!UICONTROL Segmentación de experiencias]**.

   ![Crear actividad &gt; Segmentación de experiencias](/help/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >Los tipos de actividades disponibles dependen de su cuenta de Target. Algunos tipos de actividades podrían no aparecer en su lista. Por ejemplo, Personalización automatizada es una función [de Target Premium](/help/c-intro/intro.md#premium).

   Para obtener información sobre los tipos de actividades, consulte [Actividades](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03) y [tipos de actividades de Target](/help/c-activities/target-activities-guide.md).

1. Seleccione **[!UICONTROL Visual (Predeterminado)]**, si es necesario.

   ![Cuadro de diálogo Crear actividad de segmentación de experiencias](/help/c-activities/t-experience-target/t-xt-create/assets/form_url-new.png)

   Si prefiere usar el Compositor de experiencias basadas en formularios, seleccione esa opción. Consulte [Compositor de experiencias basadas en formularios](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html).

   >[!NOTE]
   >
   >Además del Compositor de experiencias visuales y el Compositor de experiencias basadas en formularios, Target ofrece el VEC de aplicación de una sola página y el VEC para aplicaciones móviles. Para obtener más información sobre los distintos compositores, consulte [Experiencias y ofertas](/help/c-experiences/experiences.md).

   Para obtener información acerca de la solución de problemas del VEC, en caso de problemas, consulte [Solución de problemas del Compositor de experiencias visuales](../../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md#reference_77743144F10143A3A89D56E116D296E4).

1. Especifique la URL [de la actividad](../../../c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90)y haga clic **[!UICONTROL en Siguiente]**.

   Si la cuenta se configura con una dirección URL predeterminada, esa dirección URL aparece de manera predeterminada. Puede cambiar la dirección URL predeterminada con otra dirección.

   Se abre el Compositor de experiencias visuales con la página especificada en la dirección URL.

   ![Actividad de segmentación de experiencias dentro del VEC](/help/c-activities/t-experience-target/t-xt-create/assets/xt-in-vec.png)

1. Escriba un nombre para la actividad en el espacio proporcionado.

   ![Campo Nombre](/help/c-activities/t-experience-target/t-xt-create/assets/xt_name-new.png)

   No se permite usar los caracteres siguientes en el nombre de una actividad:

   | Carácter | Descripción |
   |--- |--- |
   | `/` | Barra oblicua |
   | `?` | Signo de interrogación |
   | `#` | Signo de número |
   | `:` | Dos puntos |
   | `=` | Igual a |
   | `+` | Más |
   | `-` | Menos |
   | `@` | Arroba |

1. [Cree experiencias nuevas](../../../c-activities/t-experience-target/t-xt-create/xt-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00) cambiando los elementos de la página.



   De manera predeterminada, el compositor de experiencias visuales no permite realizar cambios en elementos que contengan JavaScript, como banners giratorios. Puede deshabilitar JavaScript si quiere poder modificar estos elementos con el Compositor de experiencias visuales.

   >[!NOTE]
   >
   >Si cambia la dirección URL después de realizar cambios en una página para una o más experiencias, la experiencia se restablecerá con la nueva página y se perderán los cambios que haya realizado.

   Al desplazar el cursor sobre los elementos de la página, estos se resaltarán. Los elementos resaltados se pueden modificar con el Compositor de experiencias.

   Si creó un mbox en la página mediante Target Classic (antes denominado Test&amp;Target), ese mbox aparece como un elemento que muestra el nombre del mbox y se puede modificar como cualquier otro elemento.

   >[!NOTE]
   >
   >Si entrega una imagen desde un origen distinto a la página principal (por ejemplo, una imagen alojada en akamai.net y entregada en dell.com), dicha imagen no se mostrará en la miniatura de la página mostrada en el diagrama de flujo.

1. Haga clic en **[!UICONTROL Siguiente]**.

   Se abrirá el diagrama de flujo.

   ![](assets/xt_diagram.png)

   El diagrama de flujo le guía durante el procedimiento para seleccionar una audiencia para la actividad y configurar las experiencias.
1. Pase el cursor sobre la audiencia, haga clic en el icono **[!UICONTROL Editar]** (tres elipses verticales), haga clic en **[!UICONTROL Cambiar audiencia]** y, a continuación, seleccione la audiencia para la primera experiencia de su actividad.

   ![](assets/xt_change_audience.png)

   Se mostrará la biblioteca de audiencias. La biblioteca de audiencias contiene las audiencias que se han definido anteriormente, entre las que se incluyen algunas audiencias comunes predefinidas como parte de Target. Seleccione una audiencia de la biblioteca o  [cree una audiencia nueva](../../../c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271). Para mostrar la misma experiencia a todos los participantes, seleccione Todos los visitantes.

   >[!NOTE]
   >
   >Además de seleccionar una audiencia existente, puede combinar varias audiencias para crear audiencias combinadas específicas en lugar de crear una nueva. Para obtener más información, consulte [Combinar varias audiencias](../../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

   Al crear una audiencia puede seleccionar una ubicación (mbox) y especificar parámetros para dicha ubicación. En Parámetros personalizados, seleccione el mbox y especifique los parámetros que desee.

   >[!NOTE]
   >
   >Las audiencias se importan automáticamente en segundo plano cuando abre la lista de audiencias y las audiencias importadas tienen más de diez minutos de antigüedad.

   Puede hacer clic en el icono [!UICONTROL Editar] (tres elipses verticales) que se muestra y, a continuación, hacer clic en [!UICONTROL Eliminar audiencia] para eliminar una audiencia existente.
1. Haga clic en **[!UICONTROL Añadir segmentación de experiencias]**.

   >[!NOTE]
   >
   >Si va a segmentar una experiencia a una audiencia, debe seleccionar la audiencia antes de añadir la experiencia. Aparecerá un mensaje para recordarle que elija una audiencia.

1. (Opcional) Haga clic en **[!UICONTROL Agregar]** y configure otras experiencias segmentadas.

   ![](assets/xt_add_xt.png)

   Haga clic en **[!UICONTROL Continuar]cuando haya completado este paso.**
1. Especifique los [objetivos y la configuración](../../../c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) para la actividad.

   ![](assets/xt_settings.png)

1. Haga clic en **[!UICONTROL Guardar y cerrar]**.
