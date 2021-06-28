---
keywords: solucionar problemas de target;resolución de problemas de target;contenido predeterminado;prueba no activa;actividad no activa;segmentación no funciona;pantallas de experiencias previas;no puedo crear actividades;no se pueden crear actividades;crear actividades;cambió la estructura de la página;se modificó la estructura de la página;mensaje de error;error al eliminar script de perfil;ajax no funciona
description: Encontrará sugerencias para la resolución de problemas en caso de que la actividad de Adobe  [!DNL Target]  no aparezca en el sitio.
title: ¿Cómo puedo solucionar problemas de actividades?
feature: Actividades
exl-id: 6aa0486a-9ca3-4545-ae06-9b02e586d777
source-git-commit: f028d2b439fee5c2a622748126bb0a34d550a395
workflow-type: tm+mt
source-wordcount: '780'
ht-degree: 100%

---

# Resolución de problemas de actividades

Si su actividad de [!DNL Adobe Target] no aparece en su sitio, estas sugerencias para solucionar problemas le ayudarán.

>[!NOTE]
>
>Además de la siguiente información de solución de problemas, consulte [Solución de problemas de Target](/help/r-troubleshooting-target/troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839) para encontrar vínculos a temas de solución de problemas adicionales, preguntas frecuentes y otra información útil sobre la solución de problemas y otras funciones en [!DNL Adobe Target].

En las siguientes secciones puede encontrar ejemplos de problemas y sus posibles soluciones.

## He creado una actividad con la IU de [!DNL Target] y no puedo actualizarla mediante la API.

Las actividades creadas con la IU de Target deben actualizarse mediante esta. Las actividades creadas mediante API deben actualizarse mediante esta. Si, originalmente, crea una actividad utilizando la API, por ejemplo, pero luego edita la actividad a través de la IU de Target, no se actualizan todos los cambios. Todos los cambios se almacenan en el servidor y se pueden actualizar realizando otra llamada de API.

Como práctica recomendada, intente actualizar la actividad mediante el mismo método (IU o API) que se utilizó para crear la actividad originalmente.

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

## Hace poco, se le añadió a [!DNL Target], pero no puede crear actividades.

**Validar:** haga clic en Crear actividad. Si la opción no está disponible, lo más probable es que no tenga los derechos suficientes para crear una actividad.

**Opciones:**

Una vez que se lo agrega como usuario en Target, necesita tener la función Aprobador para crear Actividades.

* Solicite al Administrador de la cuenta que lo convierta en Aprobador.
* Si usted es el Administrador, asígnese usted mismo la función Aprobador desde **[!UICONTROL Administración]** > **[!UICONTROL Usuarios]** en Target.

   Consulte [Asignarse a usted mismo la función de aprobador](/help/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7).

## La estructura de la página ha cambiado desde que se configuró la actividad.

**Validar:** vaya al Compositor de experiencias visuales para la actividad existente. Busque cualquier mensaje de advertencia que indique que los selectores (o la estructura) han cambiado.

**Opciones:**

* Recompile la actividad.

Para obtener más información sobre el modo en que las modificaciones de la página afectan a la capacidad de visualización de Target, consulte  [Escenarios de modificación de página](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## La estructura de la página se modifica durante la carga de la página (en tiempo de ejecución).

**Validar:** pregunte al desarrollador.

**Nota:** Para que Target pueda reconocer dónde deben aplicarse los cambios de la actividad, evite insertar dinámicamente cualquier elemento con la misma clase o modificar dinámicamente la clase de cualquier elemento del mismo nivel.

**Opciones:**

* Actualice el código de la página para que identifique de manera única cada elemento que se probará (mediante un ID).
* Deje de modificar dinámicamente la clase o los elementos del mismo nivel como se describe más arriba.

Para obtener más información sobre el modo en que las modificaciones de la página afectan a la capacidad de visualización de Target, consulte  [Escenarios de modificación de página](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

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

## Algunas llamadas de ajax de [!DNL Target] no están funcionando.

**Nota:** Varias llamadas de ajax de [!DNL Target] con el mismo nombre de pero parámetros diferentes no funcionarán en la misma página. Solo se realizará la primera llamada.

## Ha activado una actividad mediante la API de [!DNL Target], pero la actividad aparece con el estado [!UICONTROL Inactivo] en la IU de [!DNL Target].

Cuando se realizan determinadas acciones (por ejemplo, activar una actividad fuera de la interfaz de usuario empleando la API de Target), los cambios pueden tardar hasta 10 minutos en propagarse a la interfaz.
