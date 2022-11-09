---
keywords: solucionar problemas de target;resolución de problemas de target;contenido predeterminado;prueba no activa;actividad no activa;segmentación no funciona;pantallas de experiencias previas;no puedo crear actividades;no se pueden crear actividades;crear actividades;cambió la estructura de la página;se modificó la estructura de la página;mensaje de error;error al eliminar script de perfil;ajax no funciona
description: Encontrará sugerencias para la resolución de problemas en caso de que la actividad de Adobe  [!DNL Target]  no aparezca en el sitio.
title: ¿Cómo puedo solucionar problemas de actividades?
feature: Activities
exl-id: 6aa0486a-9ca3-4545-ae06-9b02e586d777
source-git-commit: f1cbc46323f71c2fa091cd2c9a3e49d34676e7a1
workflow-type: tm+mt
source-wordcount: '863'
ht-degree: 50%

---

# Resolución de problemas de actividades

Si su actividad de [!DNL Adobe Target] no aparece en su sitio, estas sugerencias para solucionar problemas le ayudarán.

>[!NOTE]
>
>Además de la siguiente información de solución de problemas, consulte [Solución de problemas de Target](/help/main/r-troubleshooting-target/troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839) para encontrar vínculos a temas de solución de problemas adicionales, preguntas frecuentes y otra información útil sobre la solución de problemas y otras funciones en [!DNL Adobe Target].

Las secciones siguientes contienen problemas que pueden encontrar con las soluciones sugeridas.

## He creado una actividad con la IU de [!DNL Target] y no puedo actualizarla mediante la API.

Actividades creadas con [!DNL Target] La interfaz de usuario debe actualizarse mediante la variable [!DNL Target] IU. Las actividades creadas mediante API deben actualizarse mediante esta. Si, originalmente, crea una actividad utilizando la API, por ejemplo, pero luego edita la actividad a través de la [!DNL Target] No todos los cambios se actualizan en la interfaz de usuario. Todos los cambios se almacenan en el servidor y se pueden actualizar realizando otra llamada de API.

Como práctica recomendada, intente actualizar la actividad mediante el mismo método (IU o API) que se utilizó para crear la actividad originalmente.

## Se muestra el contenido predeterminado.

Asegúrese de que la actividad esté completa y se haya activado.

## La actividad no se ejecuta.

**Validar:** Vaya a [!UICONTROL Información general] y compruebe si la prueba está marcada como inactiva o borrador.

**Opciones:**

* Active la prueba.
* Utilice los vínculos de vista previa para mostrar la prueba inactiva.

## No cumple los requisitos para las condiciones de segmentación de audiencia.

**Validar:** revise las condiciones de segmentación en la página de información general.

**Opciones:**

* Cumpla los requisitos e inténtelo de nuevo.
* Utilice los vínculos de vista previa para evitar las condiciones de segmentación.

## La página no cumple los requisitos para las condiciones de segmentación de páginas.

**Validar:** En el [!UICONTROL Información general] , determine si la página no cumple las condiciones de segmentación.

**Opciones:**

* Vaya a la [!UICONTROL Compositor de experiencias visuales], haga clic en URL > Avanzadas > página actual.

## Se muestra una experiencia anterior en lugar de la nueva experiencia.

**Validar:** pruebe una de las opciones siguientes e intente volver a visualizar la experiencia.

**Opciones:**

* Borre la caché y las cookies e inténtelo de nuevo.
* Pruebe con un navegador diferente.
* Utilice el modo privado o incógnito.

## Hace poco, se le añadió a [!DNL Target], pero no puede crear actividades.

**Validar:**[!UICONTROL  haga clic en Crear actividad]. Si la opción no está disponible, lo más probable es que no tenga los derechos suficientes para crear una actividad.

**Opciones:**

Después de agregarlo como usuario en [!DNL Target], debe tener la variable [!UICONTROL Aprobador] para crear actividades.

* Solicite al administrador de su cuenta que lo apruebe.
* Si es el administrador, asígnese usted mismo el [!UICONTROL Aprobador] función de **[!UICONTROL Administración]** > **[!UICONTROL Usuarios]** en [!DNL Target].

   Consulte [Asignarse a usted mismo la función de aprobador](/help/main/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7).

## La estructura de la página ha cambiado desde que se configuró la actividad.

**Validar:**[!UICONTROL  vaya al Compositor de experiencias visuales para la actividad existente. ] Busque cualquier mensaje de advertencia que indique que los selectores (o la estructura) han cambiado.

**Opciones:**

* Recompile la actividad.

Para obtener más información sobre cómo afectan las modificaciones de la página [!DNL Target]La capacidad de visualización de , consulte [Escenarios de modificación de página](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## La estructura de la página se modifica durante la carga de la página (en tiempo de ejecución).

**Validar:** pregunte al desarrollador.

**Nota:** Para [!DNL Target] para reconocer dónde se deben aplicar los cambios de actividad, evite insertar dinámicamente un elemento con la misma clase o modificar dinámicamente la clase de cualquier elemento del mismo nivel.

**Opciones:**

* Actualice el código de la página para que identifique de forma exclusiva cada elemento que se pruebe (mediante un ID).
* Deje de modificar dinámicamente la clase o los elementos del mismo nivel como se describe más arriba.

Para obtener más información sobre cómo afectan las modificaciones de la página [!DNL Target]La capacidad de visualización de , consulte [Escenarios de modificación de página](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## Otras actividades se ejecutan en la misma página.

**Validar:** Utilice la variable [!UICONTROL Conflictos] para ver si se están ejecutando otras actividades.

**Nota:**[!UICONTROL  La pestaña Conflictos no funciona con el módulo de comprobación de plantilla.]

**Opciones:**

* Aumente la prioridad de esta actividad.
* Reduzca la prioridad de otras actividades.
* Desactive otras actividades.

## Aparece un mensaje de error cuando elimina un script de perfil.

**Validar:**[!DNL Target] al eliminar un script de perfil de , se muestra el mensaje de error “No se ha podido eliminar el script de perfil”.

**Opciones:**

Realice uno de los siguientes pasos:

* Vuelva a eliminar el script de perfil. Aparece el mensaje de proceso realizado correctamente.
* Espere unos 10 minutos para que el [!DNL Target] importador que se va a ejecutar. El programa de importación actualiza la lista de scripts de perfil.

## Algunas llamadas de ajax de [!DNL Target] no están funcionando.

**Nota:** Ajax múltiple [!DNL Target] llamadas con el mismo nombre pero parámetros diferentes no funcionan en la misma página. Solo se realiza la primera llamada.

## Ha activado una actividad mediante la API de [!DNL Target], pero la actividad aparece con el estado [!UICONTROL Inactivo] en la IU de [!DNL Target].

Cuando se realizan determinadas acciones, como activar una actividad fuera de la interfaz de usuario mediante la función [!DNL Target] , la actualización puede tardar hasta diez minutos en propagarse a la interfaz de usuario.

## Después de la conversión de la actividad, el visitante no está en ninguna experiencia.

En casos excepcionales, si la métrica de conversión de la actividad para cumplir los requisitos de una experiencia se envía en la misma solicitud que la calificación de la actividad, es posible que el visitante no esté en ninguna experiencia después de que se envíe la solicitud. En este caso, el visitante ve el contenido predeterminado y el ID de experiencia capturado mediante tokens sería -1. [!DNL Adobe] no recomienda enviar la calificación y conversión de la actividad en el mismo [!DNL Target] solicitud.

Si desea enviar ambas métricas en la misma solicitud, puede utilizar [!UICONTROL Configuración avanzada] para especificar que el visitante permanecerá en la misma experiencia después de la conversión.
