---
keywords: Segmentación;categorías de objetivos;condiciones de segmentación;administrador de audiencias;parámetros de perfil personalizados;perfil de visitante;parámetros de usuario personalizados;reglas de segmentación
description: Aprenda a utilizar categorías (como Explorador, Geografía, Red, Sistema operativo, Perfil del visitante) para el contenido objetivo.
title: ¿Cuáles son las categorías de las audiencias?
feature: Audiences
exl-id: 37d6435d-4139-47c5-a871-6595e089d052
source-git-commit: b74cccdc43c34367819ed8a908a304b567d7ecbb
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 50%

---

# Categorías para audiencias

Puede segmentar en cualquiera de los atributos de categoría utilizando [!DNL Adobe Target]. Para crear reglas de segmentación (o grupos) para cada atributo, arrastre y suelte los atributos que desee en el panel del Generador de audiencias .

![Atributos para audiencias](/help/c-target/c-audiences/assets/attributes.png)

Cuando se selecciona una categoría en concreto, se puede aplicar una o más condiciones de segmentación. Por ejemplo, en la categoría Geo, defina una regla como Ciudad=San Francisco. Si se agregan varios valores, se crea una condición “O”. El visitante solo necesita cumplir uno de los valores para satisfacer la condición de segmentación. Para condiciones AND en el mismo parámetro, cree un objetivo de expresiones personalizado.

Después de crear una regla, haga clic en **[!UICONTROL Finalizado]**. Se mostrará un resumen de la regla junto al vínculo de la segmentación para el nivel que esté segmentando.

Puede ajustar aún más la regla si agrega más condiciones o si crea reglas adicionales en otras categorías. Por ejemplo, puede segmentar solo los usuarios de Firefox de San Francisco que accedan al sitio desde Google. Defina la categoría [!UICONTROL Geografía] para dirigirse a los usuarios de San Francisco, la categoría [!UICONTROL Explorador] para dirigirse a los usuarios que utilicen Firefox y la categoría [!UICONTROL Fuentes de tráfico] para dirigirse a los usuarios que provengan de [!UICONTROL Desde Google]. Las reglas creadas entre categorías se combinan con el operador AND.

Para crear reglas de segmentación complejas que incluyan operaciones OR en todas las categorías, cree un objetivo de expresión.

También puede segmentar parámetros de perfil personalizados y parámetros de `user.`. Al agregar una audiencia, arrastre y suelte **[!UICONTROL Perfil del visitante]** y, a continuación, elija el parámetro que desea usar para segmentar la actividad. Si el parámetro deseado no se muestra, un mbox no lo ha activado.

Use el cuadro de búsqueda para buscar la lista [!UICONTROL Audiencias]. Puede buscar cualquier parte del nombre de una audiencia, o bien encerrar entre comillas una cadena específica.

Puede ordenar la lista [!UICONTROL Audiencia] por nombre de audiencia o por la fecha de la última modificación. Para ordenar por nombre o fecha, haga clic en el encabezado de columna y, a continuación, seleccione si quiere mostrar las audiencias en orden ascendente o descendente.

## Vídeo de formación: Creación de audiencias ![Distintivo del tutorial](/help/assets/tutorial.png)

Este vídeo contiene información sobre el uso de las categorías de audiencias.

* Crear audiencias
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)
