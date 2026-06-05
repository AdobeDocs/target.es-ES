---
keywords: Segmentación;categorías de objetivos;condiciones de segmentación;administrador de audiencias;parámetros de perfil personalizados;perfil de visitante;parámetros de usuario personalizados;reglas de segmentación
description: Aprenda a utilizar categorías (como Explorador, Geografía, Red, Sistema operativo, Perfil del visitante) para segmentar contenido.
title: ¿Cuáles son las categorías de las audiencias?
feature: Audiences
exl-id: 37d6435d-4139-47c5-a871-6595e089d052
TQID: https://experienceleague.adobe.com/gdwPSImsbXfvaX2Z4bL9-hGyLwo0b0q-At0fokUfYN8
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 385
ht-degree: 50%

---

# Categorías para públicos

Puede segmentar cualquiera de los distintos atributos de categoría mediante [!DNL Adobe Target]. Para crear reglas de segmentación (o grupos) para cada atributo, arrastre y suelte los atributos deseados en el panel Generador de audiencias.

![Atributos para audiencias](/help/main/c-target/c-audiences/assets/attributes.png)

Cuando se selecciona una categoría en concreto, se puede aplicar una o más condiciones de segmentación. Por ejemplo, en la categoría Geo, defina una regla como Ciudad=San Francisco. Si se agregan varios valores, se crea una condición “O”. El visitante solo necesita cumplir uno de los valores para satisfacer la condición de segmentación. Para condiciones AND en el mismo parámetro, cree un objetivo de expresiones personalizado.

Después de crear una regla, haga clic en **[!UICONTROL Finalizado]**. Se mostrará un resumen de la regla junto al vínculo de la segmentación para el nivel que esté segmentando.

Puede ajustar aún más la regla si agrega más condiciones o si crea reglas adicionales en otras categorías. Por ejemplo, solo puede segmentar usuarios de Firefox de San Francisco que accedan al sitio desde Google. Defina la categoría [!UICONTROL Geo] para segmentar usuarios de San Francisco, la categoría [!UICONTROL Browser] para segmentar usuarios que usen Firefox y la categoría [!UICONTROL Traffic Sources] para segmentar usuarios que vienen de [!UICONTROL Desde Google]. Las reglas creadas en las distintas categorías se combinan con el operador AND.

Para crear reglas de segmentación complejas que incluyan operaciones O entre categorías, cree un objetivo de expresión.

También puede segmentar parámetros de perfil personalizados y parámetros de `user.`. Al agregar una audiencia, arrastra y suelta **[!UICONTROL Perfil del visitante]** y, a continuación, elige el parámetro que quieras usar para segmentar la actividad. Si el parámetro deseado no se muestra, un mbox no ha activado el parámetro.

Use el cuadro de búsqueda para buscar la lista [!UICONTROL Audiencias]. Puede buscar cualquier parte del nombre de una audiencia, o bien encerrar entre comillas una cadena específica.

Puede ordenar la lista [!UICONTROL Audiencia] por nombre de audiencia o por la fecha de la última modificación. Para ordenar por nombre o fecha, haga clic en el encabezado de columna y, a continuación, seleccione si quiere mostrar los públicos en orden ascendente o descendente.

## Vídeo de formación: Creación de audiencias ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo contiene información sobre el uso de las categorías de audiencias.

* Crear públicos
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)
