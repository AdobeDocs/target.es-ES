---
keywords: solucionar problemas de target;resolución de problemas de target;contenido predeterminado;prueba no activa;actividad no activa;segmentación no funciona;pantallas de experiencias anteriores;no se pueden crear actividades;no se pueden crear actividades;crear actividades;cambió la estructura de la página;se modificó la estructura de la página;mensaje de error;error al eliminar script de perfil;ajax no funciona
description: Encontrará sugerencias para la resolución de problemas en caso de que la actividad de Adobe [!DNL Target] no aparezca en el sitio.
title: ¿Cómo puedo solucionar problemas de actividades?
feature: Activities
exl-id: 6aa0486a-9ca3-4545-ae06-9b02e586d777
TQID: 'https://experienceleague.adobe.com/L-011t7q6c3aICs0ZrM01m9pZByH86FKGiLG1A7Rl2s'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 9621044454d3e1b47c06cac2ad5d08cba8e482c0
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 7%
---
# Introducción a las actividades de resolución de problemas {#troubleshooting-activities}

>[!BEGINSHADEBOX]

**En esta página:** Encuentre soluciones a problemas comunes cuando una actividad de [!DNL Adobe Target] no aparezca en su sitio o no se comporte como se espera.

>[!ENDSHADEBOX]

Varias causas pueden impedir que aparezca una actividad [!DNL Adobe Target] en el sitio. Utilice los siguientes problemas y soluciones sugeridas para identificar la causa y aplicar la corrección.

>[!NOTE]
>
>Además de la siguiente información de solución de problemas, vea [Solucionar problemas de Target](/help/main/r-troubleshooting-target/troubleshooting-target.md) para obtener vínculos a temas de solución de problemas adicionales, preguntas frecuentes y otra información útil acerca de la solución de problemas y otras características en [!DNL Adobe Target].

## La actividad no se muestra según lo esperado {#not-displayed}

+++ Está viendo el contenido predeterminado

Asegúrese de que la actividad se haya completado y activado.

+++

</br>

+++ La actividad no está activa

**Validar:** En la ficha **[!UICONTROL Información general]**, compruebe si la actividad está marcada como inactiva o borrador.

**Opciones:**

* Activar la actividad.
* Utilice los vínculos de vista previa para mostrar la actividad inactiva.

+++

</br>

+++ No cumple los requisitos para las condiciones de segmentación de audiencia

**Validar:** Revise las condiciones de segmentación en la página **[!UICONTROL Información general]**.

**Opciones:**

* Apto para la audiencia e inténtelo de nuevo.
* Utilice los vínculos de vista previa para omitir las condiciones de segmentación.

+++

</br>

+++ La página no cumple los requisitos para las condiciones de segmentación de páginas

**Validar:** En la página **[!UICONTROL Información general]**, determine si la página no cumple las condiciones de segmentación.

**Opciones:**

* Vaya a **[!UICONTROL Compositor de experiencias visuales]** y, a continuación, haga clic en URL > Avanzadas > página actual.

+++

</br>

+++ Se muestra una experiencia anterior en lugar de la nueva

**Validar:** Pruebe una de las siguientes opciones e intente ver de nuevo la experiencia.

**Opciones:**

* Borre la caché y las cookies e inténtelo de nuevo.
* Pruebe con un navegador diferente.
* Utilice el modo privado o de incógnito.

+++

</br>

+++ La estructura de la página cambió desde que se configuró la actividad

**Validar:** Vaya a **[!UICONTROL Compositor de experiencias visuales]** para la actividad existente y busque un mensaje de advertencia que indique que los selectores (o la estructura) han cambiado.

**Opciones:**

* Recompile la actividad.

Para obtener más información acerca de cómo las modificaciones en la página afectan la capacidad de [!DNL Target] para mostrar contenido, vea [Escenarios de modificación de página](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md).

+++

</br>

+++ La estructura de la página se modifica durante la carga de la página (en tiempo de ejecución)

**Validar:** Pregunte a su desarrollador.

**Nota:** Para que [!DNL Target] reconozca dónde se deben aplicar los cambios de la actividad, evite insertar dinámicamente un elemento con la misma clase o modificar dinámicamente la clase de cualquier elemento del mismo nivel.

**Opciones:**

* Actualice el código de página para que identifique de forma exclusiva cada elemento que se pruebe mediante un ID.
* Deje de modificar dinámicamente la clase o los elementos del mismo nivel como se describe más arriba.

Para obtener más información acerca de cómo las modificaciones en la página afectan la capacidad de [!DNL Target] para mostrar contenido, vea [Escenarios de modificación de página](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md).

+++

</br>

+++ Otras actividades se ejecutan en la misma página

**Validar:** Utilice la ficha **[!UICONTROL Conflictos]** para ver si se están ejecutando otras actividades.

**Nota:** La ficha **[!UICONTROL Conflictos]** no funciona con el módulo Prueba de plantilla.

**Opciones:**

* Aumente la prioridad de esta actividad.
* Disminuir la prioridad de las demás actividades.
* Desactive las demás actividades.

+++

## Usuarios, API y la IU de {#users-api-ui}

+++ He creado una actividad con la interfaz de usuario [!DNL Target] y no puedo actualizarla mediante API

Las actividades creadas con la interfaz de usuario [!DNL Target] deben actualizarse mediante la interfaz de usuario [!DNL Target]. Las actividades creadas mediante API deben actualizarse mediante esta. Por ejemplo, si crea una actividad mediante la API, pero posteriormente edita la actividad mediante la interfaz de usuario de [!DNL Target], no se actualizarán todos los cambios. Todos los cambios se almacenan en el servidor y se pueden actualizar realizando otra llamada de API.

Como práctica recomendada, actualice la actividad utilizando el mismo método (IU o API) que se utilizó para crearla.

+++

</br>

+++ Hace poco se le agregó a [!DNL Target], pero no puede crear actividades

**Validar:** Haga Clic En **[!UICONTROL Crear Actividad]**. Si la opción no está disponible, lo más probable es que no tenga los derechos suficientes para crear una actividad.

**Opciones:**

Una vez que se le agregue como usuario en [!DNL Target], necesitará la función **[!UICONTROL Aprobador]** para crear actividades.

* Solicite al administrador de su cuenta que le convierta en aprobador.
* Si usted es el administrador, asígnese usted mismo la función **[!UICONTROL Aprobador]** de **[!UICONTROL Administración]** > **[!UICONTROL Usuarios]** en [!DNL Target]. Consulte [Asignarse a sí mismo la función de aprobador](/help/main/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7).

+++

</br>

+++ Ha activado una actividad mediante la API [!DNL Target], pero la actividad muestra el estado [!UICONTROL Inactivo] en la interfaz de usuario de [!DNL Target]

Cuando se realizan determinadas acciones (por ejemplo, activar una actividad fuera de la interfaz de usuario empleando la API [!DNL Target]), los cambios pueden tardar hasta 10 minutos en propagarse a la interfaz.

+++

</br>

+++ Aparece un mensaje de error al eliminar un script de perfil

**Validar:** Al eliminar un script de perfil de [!DNL Target], se muestra el mensaje de error &quot;No se pudo eliminar el script de perfil&quot;.

**Opciones:**

Realice uno de los siguientes pasos:

* Vuelva a eliminar el script de perfil. Aparece el mensaje de proceso realizado correctamente.
* Espere unos 10 minutos para que se ejecute el importador de [!DNL Target]. El programa de importación actualiza la lista de scripts de perfil.

+++

## Llamadas y conversión {#calls-and-conversion}

+++ Algunas llamadas de ajax [!DNL Target] no funcionan

**Nota:** Varias llamadas ajax [!DNL Target] con el mismo nombre pero parámetros diferentes no funcionan en la misma página. Solo se realiza la primera llamada.

+++

</br>

+++ Después de la conversión de la actividad, el visitante no está en ninguna experiencia

En casos excepcionales, si la métrica de conversión de la actividad que clasifica a un visitante para una experiencia se envía en la misma solicitud que la calificación de la actividad, es posible que el visitante no esté en ninguna experiencia una vez enviada la solicitud. En este caso, el visitante ve contenido predeterminado y el ID de experiencia capturado mediante tokens es -1. [!DNL Adobe] no recomienda enviar la calificación y conversión de la actividad en la misma solicitud [!DNL Target].

Si desea enviar ambas métricas en la misma solicitud, puede usar **[!UICONTROL Configuración avanzada]** para especificar que el visitante permanezca en la misma experiencia después de la conversión.

+++
