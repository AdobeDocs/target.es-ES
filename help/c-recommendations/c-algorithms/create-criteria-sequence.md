---
keywords: criteria sequence;multiple criteria;algorithms;criteria;recommendations criteria;sequence;
description: Utilice secuencias de hasta cinco criterios para ejercer el bueno control de los elementos que aparecen en las actividades de Adobe Target Recommendations.
title: Crear secuencias de criterios
feature: criteria
uuid: 9a5ca86b-fc79-4c24-b86f-e333b0c63088
translation-type: tm+mt
source-git-commit: b85237ba7526701dee76810af1b719be00fb4fc3
workflow-type: tm+mt
source-wordcount: '840'
ht-degree: 57%

---


# ![PREMIUM](/help/assets/premium.png) Creación de secuencias de criterios

Utilice secuencias de hasta cinco criterios para ejercer un mayor control sobre los elementos que aparecen en las actividades de [!UICONTROL Recomendaciones].

>[!NOTE]
>
>Las secuencias de criterios no se pueden usar con las actividades de [!UICONTROL Recommendations] creadas antes de la versión de octubre de 2016 de [!DNL Target Premium].

Para crear una secuencia de criterios, debe crear primero los criterios que desea incluir en la secuencia. Consulte [Crear criterios](/help/c-recommendations/c-algorithms/create-new-algorithm.md) para obtener más información.

Si utiliza una secuencia de criterios, puede ofrecer recomendaciones personalizadas adicionales, en lugar de utilizar más recomendaciones secundarias genéricas, cuando un criterio no obtenga suficientes resultados para llenar el diseño. Normalmente, una secuencia de criterios pasa de un objetivo más específico, que puede devolver menos resultados, a un objetivo más general, que generalmente devuelve más resultados.

Las secuencias de criterios pueden variar según el tipo de página, como se muestra en los siguientes ejemplos:

| Tipo de página | Posible orden de secuencia |
| --- | --- |
| Página de productos | <ol><li>Basado en el elemento actual, para la misma marca</li><li>Basado en el elemento actual, para todas las marcas</li><li>Basado en similitudes de contenido</li><li>Basado en los productos más vendidos</li><li>Basado en los elementos más visitados en todo el sitio</li></ol> |
| Página de inicio | <ol><li>Basado en la última compra del visitante </li><li>Basado en el elemento favorito del visitante</li><li>Basado en la categoría favorita del visitante</li><li>Basado en los productos más vendidos</li><li>Basado en lo más visitado en todo el sitio</li></ol> |

## Acceso a la pantalla Crear secuencia de criterios

Existen varias maneras de llegar a la pantalla [!UICONTROL Crear secuencia de criterios]. Algunas opciones de pantalla dependen de cómo llega a la pantalla.

* En la pantalla de la biblioteca **[!UICONTROL Recomendaciones]** > **[!UICONTROL Criterios]**, haga clic en **[!UICONTROL Crear criterio]** > **[!UICONTROL Crear secuencia de criterios]**. Los criterios que crea aquí quedan disponibles automáticamente para todas las actividades de [!UICONTROL Recommendations].
* Cuando esté creando una actividad de [!UICONTROL Recommendations] , en la pantalla Seleccionar criterios, haga clic en **[!UICONTROL Crear nuevo]** > **[!UICONTROL Crear secuencia]** de criterios. Tendrá la opción de guardar la nueva secuencia de criterios para usarla con otras actividades de [!UICONTROL Recommendations].
* When you are editing a [!UICONTROL Recommendations] activity, click in a [!UICONTROL Recommendations Location] box on your page, then select **[!UICONTROL Change Criteria]**. En la pantalla [!UICONTROL Seleccionar criterios], haga clic en **[!UICONTROL Crear nuevo]** > **[!UICONTROL Crear secuencia de criterios]**. Tendrá la opción de guardar los nuevos criterios para usarlos con otras actividades de [!UICONTROL Recommendations].

En los pasos siguientes se asume que accede a la pantalla [!UICONTROL Crear secuencia] de criterios mediante el primer método: la pantalla de la biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Criterios]** .

1. Haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Criterios]**.

1. Haga clic en **[!UICONTROL Crear criterios]** > **[!UICONTROL Crear secuencia]** de criterios.

   ![](assets/CreateCriteriaSequence.png)

## Complete la sección Información

1. Introduzca un **[!UICONTROL Nombre]** para la secuencia.

   Es el nombre “interno” que se usa para describir la secuencia de criterios. Los visitantes de su sitio web no verán este nombre.

   ![Sección Crear información de secuencia de criterios](/help/c-recommendations/c-algorithms/assets/criteria-sequence-info.png)

1. Escriba un **[!UICONTROL Título genérico]** de orientación pública que se mostrará en la página si se utilizan varios criterios de la secuencia para llenar el diseño de [!UICONTROL Recommendations].

   Por ejemplo, es posible que quiera reemplazar “Los clientes que han consultado esto, también han consultado...” por “Recomendado para ti” si el diseño incluye elementos basados en más de una clave de [!UICONTROL Recommendations].

1. Escriba una breve **[!UICONTROL Descripción]** de la secuencia de criterios.

   La descripción debería ayudarle a identificar la secuencia de criterios y podría incluir información sobre su propósito.

1. Seleccione un **[!UICONTROL Segmento de mercado vertical]**.

   Your default [industry vertical](/help/c-recommendations/c-algorithms/algorithms.md#section_936BCFCF234C49A2BEC1C38AAC2D71AF) appears automatically.

1. Seleccione un **[!UICONTROL Tipo de página]**.

   Puede seleccionar varios tipos de página.

   En conjunto, el sector y los tipos de página se usan para categorizar la secuencia de criterios guardada, lo que facilita su reutilización para otras actividades de [!UICONTROL Recommendations].

## Crear secuencias de criterios

El orden de secuencia define el orden en que se rellena un diseño. Si el criterio 1 no tiene suficientes recomendaciones para completar el diseño, las ranuras restantes se rellenarán con el criterio 2, etc.

1. En la sección Secuencia **[!UICONTROL de]** criterios, haga clic en **[!UICONTROL Añadir criterios]**.

   ![Añadir criterios](/help/c-recommendations/c-algorithms/assets/add-criteria.png)

1. On the [!UICONTROL Select Criteria] screen, select a criteria.

   ![Seleccionar criterios](/help/c-recommendations/c-algorithms/assets/select-criteria.png)

1. Haga clic en **[!UICONTROL Agregar]**.

1. Continúe agregando criterios a la secuencia. Puede agregar hasta cinco criterios en una secuencia.

## Especificar contenido de copia de seguridad

Elija qué contenido se devuelve cuando no hay suficientes recomendaciones disponibles para rellenar la plantilla de diseño.

Cuando crea una secuencia de criterios, se ignora la configuración de representación de diseño parcial y recomendaciones secundarias para los criterios individuales que forman la secuencia. Para utilizar una representación de diseño parcial y recomendaciones secundarias, debe habilitarlas para la secuencia. Seleccione las conmutaciones adecuadas. Si decide admitir las recomendaciones secundarias, también puede decidir si desea aplicar las reglas de inclusión a dichas recomendaciones.

![Configuración del contenido de copia de seguridad](/help/c-recommendations/c-algorithms/assets/backup-content-settings.png)

1. (Opcional) Deslice el conmutador Representación **[!UICONTROL de diseño]** parcial a la posición &quot;activado&quot;.

   Se rellenarán tantas ranuras como sea posible, pero la plantilla de diseño puede incluir espacio en blanco para las ranuras restantes.

1. (Opcional) Reduzca el conmutador **[!UICONTROL Backup Recommendations]** a la posición &quot;activado&quot;.

   Llene los espacios vacíos restantes del diseño con una selección aleatoria de los productos más vistos de todo el sitio.

   Para obtener más información, consulte [Uso de una recomendación](/help/c-recommendations/c-algorithms/backup-recs.md)de copia de seguridad.

1. (Condicional) Si seleccionó **[!UICONTROL Copia de seguridad de Recommendations]** en el paso anterior, puede seleccionar **[!UICONTROL Aplicar reglas de inclusión a las recomendaciones]** de copia de seguridad.

   For more information see [Use dynamic and static inclusion rules](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

1. Haga clic en **[!UICONTROL Guardar]**.

   La secuencia de criterios se mostrará en la lista de criterios.

   ![](assets/CriteriaSequenceCard.png)

   Para obtener más información sobre opciones de lógica de recomendación, consulte [Criterios](../../c-recommendations/c-algorithms/algorithms.md#concept_4BD01DC437F543C0A13621C93A302750).

## Vídeo de formación: Crear criterios en Recommendations (12:33) ![Insignia de tutorial](/help/assets/tutorial.png)

Este vídeo contiene la información siguiente:

* Crear criterios
* Crear secuencias de criterios
* Cargar criterios personalizados

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
