---
description: Si su actividad no aparece en su sitio, estas sugerencias para solucionar problemas le ayudarán a encontrar una solución.
keywords: solucionar problemas de target;resolución de problemas de target;contenido predeterminado;prueba no activa;actividad no activa;segmentación no funciona;pantallas de experiencias previas;no puedo crear actividades;no se pueden crear actividades;crear actividades;cambió la estructura de la página;se modificó la estructura de la página;mensaje de error;error al eliminar script de perfil;ajax no funciona
seo-description: Si su actividad no aparece en su sitio, estas sugerencias para solucionar problemas le ayudarán a encontrar una solución.
seo-title: Resolución de problemas de actividades
solution: Target
title: Resolución de problemas de actividades
topic: Advanced,Standard,Classic
uuid: 5b22c369-0efc-48c0-a0dc-0179b18536fe
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Resolución de problemas de actividades{#troubleshoot-activities}

Si su actividad no aparece en su sitio, estas sugerencias para solucionar problemas le ayudarán a encontrar una solución.

>[!NOTE]
>
>Además de la siguiente información de solución de problemas, consulte [Solución de problemas de Target](../../r-troubleshooting-target/troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839) para encontrar vínculos a temas de solución de problemas adicionales, preguntas frecuentes y otra información útil sobre la solución de problemas y otras funciones en [!DNL Adobe Target].

En las siguientes secciones puede encontrar ejemplos de problemas y sus posibles soluciones.

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

* Vaya al Compositor de experiencias visuales y haga clic en la dirección URL &gt; Avanzadas &gt; Página actual.

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
* Si usted es el Administrador, asígnese usted mismo la función Aprobador desde Configuración &gt; Usuarios en Target Standard.

   Consulte [Asignarse a usted mismo la función de aprobador](../../administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7).

## La estructura de la página ha cambiado desde que se configuró la actividad.

**Validar:** vaya al Compositor de experiencias visuales para la actividad existente. Busque cualquier mensaje de advertencia que indique que los selectores (o la estructura) han cambiado.

**Opciones:**

* Recompile la actividad.

Para obtener más información sobre el modo en que las modificaciones de la página afectan a la capacidad de visualización de Target, consulte   [Escenarios de modificación de página](../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## La estructura de la página se modifica durante la carga de la página (en tiempo de ejecución).

**Validar:** pregunte al desarrollador.

**Nota:** Para que Target pueda reconocer dónde deben aplicarse los cambios de la actividad, evite insertar dinámicamente cualquier elemento con la misma clase o modificar dinámicamente la clase de cualquier elemento del mismo nivel.

**Opciones:**

* Actualice el código de la página para que identifique de manera única cada elemento que se probará (mediante un ID).
* Deje de modificar dinámicamente la clase o los elementos del mismo nivel como se describe más arriba.

Para obtener más información sobre el modo en que las modificaciones de la página afectan a la capacidad de visualización de Target, consulte   [Escenarios de modificación de página](../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## Mbox.js está sacando todo el código subsiguiente del encabezado y lo está incluyendo en el cuerpo.

**Validar:** vea el origen para determinar si hay alguna declaración después del archivo mbox.js, antes de la </body> etiqueta de cierre.

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

## Algunas llamadas de mbox ajax no están funcionando.

**Nota:** Varias llamadas de mbox ajax con el mismo nombre de mbox pero parámetros diferentes no funcionarán en la misma página. Solo se realizará la primera llamada.

## Ha activado una actividad mediante la API de Target, pero la actividad aparece con el estado Inactivo en la interfaz de usuario de Target.

Cuando se realizan determinadas acciones (por ejemplo, activar una actividad fuera de la interfaz de usuario empleando la API de Target), los cambios pueden tardar hasta 10 minutos en propagarse a la interfaz.