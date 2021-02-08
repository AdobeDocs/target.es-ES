---
keywords: Segmentación;categorías de objetivos;condiciones de segmentación;administrador de audiencias;parámetros de perfil personalizados;perfil de visitante;parámetros de usuario personalizados;reglas de segmentación
description: Aprenda a utilizar categorías (como Explorador, Geografía, Red, Sistema operativo, Perfil de Visitante) para destinatario de contenido.
title: ¿Cuáles son las Categorías para Audiencias?
feature: Audiences
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 92%

---


# Categorías para audiencias{#categories-for-audiences}

Se pueden tener varias categorías de objetivos. Cada una de ellas funciona como una ficha que le permite crear reglas de objetivos (o grupos) para cada categoría.

Cuando se selecciona una categoría en concreto, se puede aplicar una o más condiciones de segmentación. Por ejemplo, en la categoría Geo, defina una regla como Ciudad=San Francisco. Si se agregan varios valores, se crea una condición “O”. El visitante solo necesita cumplir uno de los valores para satisfacer la condición de segmentación. Para condiciones AND en el mismo parámetro, cree un objetivo de expresiones personalizado.

Después de crear una regla, haga clic en **[!UICONTROL Guardar]**. Se mostrará un resumen de la regla junto al vínculo de la segmentación para el nivel que esté segmentando.

Puede ajustar aún más la regla si agrega más condiciones o si crea reglas adicionales en otras categorías. Por ejemplo, para establecer como objetivo únicamente a los usuarios de Firefox de San Francisco que hayan accedido al sitio web desde Google, establezca que la categoría [!UICONTROL Geo] se dirija a los usuarios de San Francisco, que la categoría [!UICONTROL Comportamiento] de los visitantes se dirija a Firefox y [!UICONTROL Fuentes de tráfico] a Google. Todas las reglas creadas en las diferentes categorías se combinan con una condición “Y”. Para crear reglas de segmentación complejas que incluyan operaciones “O” de diferentes categorías, cree un objetivo de expresión.

También puede segmentar parámetros de perfil personalizados y parámetros de `user.`. Al agregar una audiencia, haga clic en **[!UICONTROL Perfil del visitante]** y, a continuación, elija el parámetro que quiera usar para segmentar la actividad. Si el parámetro que desea utilizar no está en la lista, significa que ningún mbox lo ha activado. Encontrará otros parámetros personalizados disponibles de mbox en la lista desplegable [!UICONTROL Parámetros personalizados].

Use el cuadro de búsqueda para buscar la lista [!UICONTROL Audiencias]. Puede buscar cualquier parte del nombre de una audiencia, o bien encerrar entre comillas una cadena específica.

Puede ordenar la lista de audiencias por nombre o por la fecha de la última modificación. Para ordenar por nombre o fecha, haga clic en el encabezado de columna y, a continuación, seleccione si quiere mostrar las audiencias en orden ascendente o descendente.

## Vídeo de capacitación: Creación de Audiencias ![distintivo de tutorial](/help/assets/tutorial.png)

Este vídeo contiene información sobre el uso de las categorías de audiencias.

* Crear audiencias
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)