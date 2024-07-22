---
keywords: Segmentación;categorías de objetivos;condiciones de segmentación;administrador de audiencias;parámetros de perfil personalizados;perfil de visitante;parámetros de usuario personalizados;reglas de segmentación
description: Aprenda a utilizar categorías (como Explorador, Geografía, Red, Sistema operativo, Perfil del visitante) para segmentar contenido.
title: ¿Cuáles son las categorías de las audiencias?
feature: Audiences
exl-id: 37d6435d-4139-47c5-a871-6595e089d052
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 47%

---

# Categorías para audiencias

Puede segmentar cualquiera de los distintos atributos de categoría mediante [!DNL Adobe Target]. Para crear reglas de segmentación (o grupos) para cada atributo, arrastre y suelte los atributos deseados en el panel Generador de audiencias.

![Atributos para audiencias](/help/main/c-target/c-audiences/assets/attributes.png)

Cuando se selecciona una categoría en concreto, se puede aplicar una o más condiciones de segmentación. Por ejemplo, en la categoría Geo, defina una regla como Ciudad=San Francisco. Si se agregan varios valores, se crea una condición “O”. El visitante solo necesita cumplir uno de los valores para satisfacer la condición de segmentación. Para condiciones AND en el mismo parámetro, cree un objetivo de expresiones personalizado.

Después de crear una regla, haga clic en **[!UICONTROL Done]**. Se mostrará un resumen de la regla junto al vínculo de la segmentación para el nivel que esté segmentando.

Puede ajustar aún más la regla si agrega más condiciones o si crea reglas adicionales en otras categorías. Por ejemplo, solo puede segmentar usuarios de Firefox de San Francisco que accedan al sitio desde Google. Establezca la categoría [!UICONTROL Geo] para segmentar usuarios de San Francisco, la categoría [!UICONTROL Browser] para segmentar usuarios mediante Firefox y la categoría [!UICONTROL Traffic Sources] para segmentar usuarios provenientes de [!UICONTROL From Google]. Las reglas creadas en las distintas categorías se combinan con el operador AND.

Para crear reglas de segmentación complejas que incluyan operaciones O entre categorías, cree un objetivo de expresión.

También puede segmentar parámetros de perfil personalizados y parámetros de `user.`. Al agregar una audiencia, arrastre y suelte **[!UICONTROL Visitor Profile]** y, a continuación, elija el parámetro que quiera usar para segmentar la actividad. Si el parámetro deseado no se muestra, un mbox no ha activado el parámetro.

Utilice el cuadro de búsqueda para buscar en la lista [!UICONTROL Audiences]. Puede buscar cualquier parte del nombre de una audiencia, o bien encerrar entre comillas una cadena específica.

Puede ordenar la lista [!UICONTROL Audience] por nombre de audiencia o por la fecha de la última modificación. Para ordenar por nombre o fecha, haga clic en el encabezado de columna y, a continuación, seleccione si quiere mostrar las audiencias en orden ascendente o descendente.

## Vídeo de formación: Creación de audiencias ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo contiene información sobre el uso de las categorías de audiencias.

* Crear audiencias
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)
