---
keywords: Compositor de experiencias visuales;VEC;carrusel
description: Aprenda a crear un carrusel que se pueda editar en el Adobe  [!DNL Target] Compositor de experiencias visuales (VEC).
title: ¿Cómo se crean carruseles en el Compositor de experiencias visuales?
feature: Visual Experience Composer (VEC)
exl-id: 50bc11d2-c9fc-4b53-8218-49842b59269a
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 58%

---

# Crear carruseles que funcionen en el Compositor de experiencias visuales

Este tema muestra cómo crear un carrusel que se pueda editar en el [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC).

Cuando se siguen los pasos descritos a continuación, [!DNL Target] siempre sabe que la diapositiva seleccionada tendrá el “selector” de la diapositiva correcta aunque, pasados unos segundos, se cambie en el Compositor de experiencias visuales.

1. Cree marcadores de posición de HTML estáticos.

   ```html
   <ul>
   <li class="show"> slide 1 </li>
   <li class="hidden"> slide 2 </li>
   <li class="hidden"> slide 3 </li>
   </ul>
   ```

1. Añada CSS para diseñar el aspecto.

   No utilice JavaScript aquí.

   >[!NOTE]
   >
   >Actualmente, la opción [!UICONTROL Render Using JavaScript] no se admite si se usa junto con código personalizado en el Compositor de experiencias visuales.

1. Actualice los classNames solo para ocultar otros y mostrar los siguientes con temporizador/animación.

   Nunca utilice JavaScript para actualizar la estructura del DOM.
