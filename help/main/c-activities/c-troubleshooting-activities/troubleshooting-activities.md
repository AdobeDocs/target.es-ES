---
keywords: solucionar problemas de target;resolución de problemas de target;contenido predeterminado;prueba no activa;actividad no activa;segmentación no funciona;pantallas de experiencias previas;no puedo crear actividades;no se pueden crear actividades;crear actividades;cambió la estructura de la página;se modificó la estructura de la página;mensaje de error;error al eliminar script de perfil;ajax no funciona
description: Encontrará sugerencias para la resolución de problemas en caso de que la actividad de Adobe  [!DNL Target]  no aparezca en el sitio.
title: ¿Cómo puedo solucionar problemas de actividades?
feature: Activities
exl-id: 6aa0486a-9ca3-4545-ae06-9b02e586d777
source-git-commit: f1cbc46323f71c2fa091cd2c9a3e49d34676e7a1
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 44%

---

# Resolución de problemas de actividades

Si su actividad de [!DNL Adobe Target] no aparece en su sitio, estas sugerencias para solucionar problemas le ayudarán.

>[!NOTE]
>
>Además de la siguiente información de solución de problemas, consulte [Solución de problemas de Target](/help/main/r-troubleshooting-target/troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839) para encontrar vínculos a temas de solución de problemas adicionales, preguntas frecuentes y otra información útil sobre la solución de problemas y otras funciones en [!DNL Adobe Target].

Las secciones siguientes contienen problemas que pueden surgir con las soluciones sugeridas.

## He creado una actividad con la IU de [!DNL Target] y no puedo actualizarla mediante la API.

Las actividades creadas con la interfaz de usuario [!DNL Target] deben actualizarse mediante la interfaz de usuario [!DNL Target]. Las actividades creadas mediante API deben actualizarse mediante esta. Si, originalmente, crea una actividad utilizando la API, por ejemplo, pero luego edita la actividad a través de la interfaz de usuario [!DNL Target], no se actualizan todos los cambios. Todos los cambios se almacenan en el servidor y se pueden actualizar realizando otra llamada de API.

Como práctica recomendada, intente actualizar la actividad mediante el mismo método (IU o API) que se utilizó para crear la actividad originalmente.

## Se muestra el contenido predeterminado.

Asegúrese de que la actividad se haya completado y activado.

## La actividad no se ejecuta.

**Validar:** Vaya a la ficha [!UICONTROL Overview] y vea si la prueba está marcada como inactiva o borrador.

**Opciones:**

* Active la prueba.
* Utilice los vínculos de vista previa para mostrar la prueba inactiva.

## No cumple los requisitos para las condiciones de segmentación de audiencia.

**Validar:** revise las condiciones de segmentación en la página de información general.

**Opciones:**

* Cumpla los requisitos e inténtelo de nuevo.
* Utilice los vínculos de vista previa para evitar las condiciones de segmentación.

## La página no cumple los requisitos para las condiciones de segmentación de páginas.

**Validar:** En la página [!UICONTROL Overview], determine si la página no cumple las condiciones de segmentación.

**Opciones:**

* Vaya a [!UICONTROL Visual Experience Composer] y haga clic en URL > Avanzado > página actual.

## Se muestra una experiencia anterior en lugar de la nueva experiencia.

**Validar:** pruebe una de las opciones siguientes e intente volver a visualizar la experiencia.

**Opciones:**

* Borre la caché y las cookies e inténtelo de nuevo.
* Pruebe con un navegador diferente.
* Utilice el modo privado o incógnito.

## Hace poco, se le añadió a [!DNL Target], pero no puede crear actividades.

**Validar:** Haga Clic En [!UICONTROL Create Activity]. Si la opción no está disponible, lo más probable es que no tenga los derechos suficientes para crear una actividad.

**Opciones:**

Una vez agregado como usuario en [!DNL Target], debe tener el rol [!UICONTROL Approver] para poder crear actividades.

* Solicite al administrador de su cuenta que le convierta en aprobador.
* Si usted es el administrador, asígnese usted mismo el rol [!UICONTROL Approver] de **[!UICONTROL Administration]** > **[!UICONTROL Users]** en [!DNL Target].

  Consulte [Asignarse a usted mismo la función de aprobador](/help/main/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7).

## La estructura de la página ha cambiado desde que se configuró la actividad.

**Validar:** Vaya a [!UICONTROL Visual Experience Composer] para la actividad existente. Busque cualquier mensaje de advertencia que indique que los selectores (o la estructura) han cambiado.

**Opciones:**

* Recompile la actividad.

Para obtener más información acerca de cómo las modificaciones de la página afectan la capacidad de [!DNL Target] para mostrar, vea [Escenarios de modificación de página](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## La estructura de la página se modifica durante la carga de la página (en tiempo de ejecución).

**Validar:** pregunte al desarrollador.

**Nota:** Para que [!DNL Target] reconozca dónde se deben aplicar los cambios de la actividad, evite insertar dinámicamente un elemento con la misma clase o modificar dinámicamente la clase de cualquier elemento del mismo nivel.

**Opciones:**

* Actualice el código de la página para identificar de forma exclusiva cada elemento que se pruebe (con un ID).
* Deje de modificar dinámicamente la clase o los elementos del mismo nivel como se describe más arriba.

Para obtener más información acerca de cómo las modificaciones de la página afectan la capacidad de [!DNL Target] para mostrar, vea [Escenarios de modificación de página](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## Otras actividades se ejecutan en la misma página.

**Validar:** Utilice la ficha [!UICONTROL Collisions] para ver si se están ejecutando otras actividades.

**Nota:** La ficha [!UICONTROL Collisions] no funciona con el módulo Prueba de plantilla.

**Opciones:**

* Aumente la prioridad de esta actividad.
* Reduzca la prioridad de otras actividades.
* Desactive otras actividades.

## Aparece un mensaje de error cuando elimina un script de perfil.

**Validar:** Al eliminar un script de perfil de [!DNL Target], se muestra el mensaje de error &quot;No se pudo eliminar el script de perfil&quot;.

**Opciones:**

Realice uno de los siguientes pasos:

* Vuelva a eliminar el script de perfil. Aparece el mensaje de proceso realizado correctamente.
* Espere unos 10 minutos para que se ejecute el importador de [!DNL Target]. El programa de importación actualiza la lista de scripts de perfil.

## Algunas llamadas de ajax de [!DNL Target] no están funcionando.

**Nota:** Varias llamadas ajax [!DNL Target] con el mismo nombre pero parámetros diferentes no funcionan en la misma página. Solo se realiza la primera llamada.

## Ha activado una actividad mediante la API [!DNL Target], pero la actividad muestra el estado [!UICONTROL Inactive] en la interfaz de usuario [!DNL Target].

Cuando se realizan determinadas acciones (por ejemplo, activar una actividad fuera de la interfaz de usuario empleando la API [!DNL Target]), los cambios pueden tardar hasta 10 minutos en propagarse a la interfaz.

## Después de la conversión de la actividad, el visitante no está en ninguna experiencia.

En casos excepcionales, si la métrica de conversión de la actividad para poder optar a una experiencia se envía en la misma solicitud que la calificación de actividad, es posible que el visitante no esté en ninguna experiencia una vez enviada la solicitud. En este caso, el visitante ve contenido predeterminado y el ID de experiencia capturado mediante tokens sería -1. [!DNL Adobe] no recomienda enviar la calificación y conversión de la actividad en la misma solicitud [!DNL Target].

Si desea enviar ambas métricas en la misma solicitud, puede usar [!UICONTROL Advanced Settings] para especificar que el visitante permanezca en la misma experiencia después de la conversión.
