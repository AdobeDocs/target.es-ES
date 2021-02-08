---
keywords: solucionar problemas de target;resolución de problemas de target;contenido predeterminado;prueba no activa;actividad no activa;segmentación no funciona;pantallas de experiencias previas;no puedo crear actividades;no se pueden crear actividades;crear actividades;cambió la estructura de la página;se modificó la estructura de la página;mensaje de error;error al eliminar script de perfil;ajax no funciona
description: Busque sugerencias de solución de problemas en caso de que la actividad de Adobe Target no aparezca en el sitio.
title: ¿Cómo puedo solucionar problemas de Actividades?
feature: Activities
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 78%

---


# Resolución de problemas de actividades

Si la actividad [!DNL Adobe Target] no aparece en el sitio, estas sugerencias para la solución de problemas le ayudarán a encontrar la solución.

>[!NOTE]
>
>Además de la siguiente información de solución de problemas, consulte [Solución de problemas de Target](/help/r-troubleshooting-target/troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839) para encontrar vínculos a temas de solución de problemas adicionales, preguntas frecuentes y otra información útil sobre la solución de problemas y otras funciones en [!DNL Adobe Target].

En las siguientes secciones puede encontrar ejemplos de problemas y sus posibles soluciones.

## He creado una actividad con la interfaz de usuario de Destinatario y no puedo actualizarla con la API.

Las actividades creadas con la interfaz de usuario de Destinatario se deben actualizar mediante la interfaz de usuario de Destinatario. Las actividades creadas mediante API deben actualizarse mediante API. Si originalmente crea una actividad con la API, por ejemplo, pero posteriormente edita la actividad mediante la interfaz de usuario de Destinatario, no se actualizan todos los cambios. Todos los cambios se almacenan en el servidor y se pueden actualizar realizando otra llamada de API.

Se recomienda actualizar la actividad con el mismo método (IU o API) que se utilizó para crear la actividad originalmente.

## Se muestra el contenido predeterminado.

Asegúrese de que su actividad está completa y se ha activado.

## La actividad no se ejecuta.

**Validar:** vaya a la pestaña Información general y compruebe si la prueba está marcada como inactiva o borrador.

**Opciones:**

* Active la prueba.
* Utilice los vínculos de vista previa para mostrar la prueba inactiva.

## No cumple los requisitos para las condiciones de segmentación de audiencia.

**Validar:** revise las condiciones de segmentación en la página de información general.

**Opciones:**

* Cumpla los requisitos e inténtelo de nuevo.
* Utilice los vínculos de vista previa para evitar las condiciones de segmentación.

## La página no cumple las condiciones de segmentación de página.

**Validar:** en la página Información general, determine si la página no cumple las condiciones de segmentación.

**Opciones:**

* Vaya al Compositor de experiencias visuales y haga clic en la dirección URL > Avanzadas > Página actual.

## Se muestra una experiencia anterior en lugar de la nueva experiencia.

**Validar:** pruebe una de las opciones siguientes e intente volver a visualizar la experiencia.

**Opciones:**

* Borre la caché y las cookies e inténtelo de nuevo.

* Pruebe con un navegador diferente.
* Utilice el modo privado o incógnito.

## Se agregó recientemente a Target pero no puede crear actividades.

**Validar:** haga clic en Crear actividad. Si la opción no está disponible, lo más probable es que no tenga los derechos suficientes para crear una actividad.

**Opciones:**

Una vez que se lo agrega como usuario en Target, necesita tener la función Aprobador para crear Actividades.

* Solicite al Administrador de la cuenta que lo convierta en Aprobador.
* Si es el administrador, asígnese la función Aprobador de **[!UICONTROL Administración]** > **[!UICONTROL Usuarios]** en Destinatario.

   Consulte [Asignarse a usted mismo la función de aprobador](/help/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7).

## La estructura de la página ha cambiado desde que se configuró la actividad.

**Validar:** vaya al Compositor de experiencias visuales para la actividad existente. Busque cualquier mensaje de advertencia que indique que los selectores (o la estructura) han cambiado.

**Opciones:**

* Recompile la actividad.

Para obtener más información sobre el modo en que las modificaciones de la página afectan a la capacidad de visualización de Target, consulte   [Escenarios de modificación de página](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## La estructura de la página se modifica durante la carga de la página (en tiempo de ejecución).

**Validar:** pregunte al desarrollador.

**Nota:** Para que Target pueda reconocer dónde deben aplicarse los cambios de la actividad, evite insertar dinámicamente cualquier elemento con la misma clase o modificar dinámicamente la clase de cualquier elemento del mismo nivel.

**Opciones:**

* Actualice el código de la página para que identifique de manera única cada elemento que se probará (mediante un ID).
* Deje de modificar dinámicamente la clase o los elementos del mismo nivel como se describe más arriba.

Para obtener más información sobre el modo en que las modificaciones de la página afectan a la capacidad de visualización de Target, consulte   [Escenarios de modificación de página](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## Mbox.js está sacando todo el código subsiguiente del encabezado y lo está incluyendo en el cuerpo.

**Validar:** vea el origen para determinar si hay alguna declaración después del archivo mbox.js, antes de la `</body>` etiqueta de cierre.

**Opciones:**

* Coloque mbox.js como el último elemento dentro de la sección `<head>`de la página.
* Utilice identificadores div únicos en los elementos de nivel más alto dentro del cuerpo.

## Otras actividades se ejecutan en la misma página.

**Validar:** utilice la pestaña Conflictos para ver qué otras actividades se están ejecutando.

**Nota:** La pestaña Conflictos no funciona con el módulo de comprobación de plantilla.

**Opciones:**

* Aumente la prioridad de esta actividad.
* Reduzca la prioridad de otras actividades.
* Desactive otras actividades.

## Aparece un mensaje de error cuando elimina un script de perfil.

**Validar:** al eliminar un script de perfil de Target Standard/Premium, se muestra el mensaje de error “No se ha podido eliminar el script de perfil”.

**Opciones:**

Realice uno de los siguientes pasos:

* Vuelva a eliminarlo. Aparece el mensaje de proceso realizado correctamente.
* Espere 10 minutos aproximadamente para que se ejecute el programa de importación de Target Standard/Premium. El programa de importación actualiza la lista de scripts de perfil.

## Algunas llamadas ajax [!DNL Target] no funcionan.

**Nota:**[!DNL Target] Varias llamadas de ajax con el mismo nombre de pero parámetros diferentes no funcionarán en la misma página. Solo se realizará la primera llamada.

## Ha activado una actividad mediante la API de Destinatario, pero la actividad muestra un estado de [!UICONTROL Inactivo] en la interfaz de usuario de Destinatario.

Cuando se realizan determinadas acciones (por ejemplo, activar una actividad fuera de la interfaz de usuario empleando la API de Target), los cambios pueden tardar hasta 10 minutos en propagarse a la interfaz.