---
keywords: Compositor de experiencias visuales;VEC;carrusel
description: Aprenda a crear un carrusel que se pueda editar en el Adobe [!DNL Target] Compositor de experiencias visuales (VEC).
title: ¿Cómo se crean carruseles en el Compositor de experiencias visuales?
feature: 'Compositor de experiencias visuales (VEC). '
exl-id: 50bc11d2-c9fc-4b53-8218-49842b59269a
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 71%

---

# Crear carruseles que funcionen en el Compositor de experiencias visuales

En este tema se muestra cómo crear un carrusel que se pueda editar en el [!DNL Adobe Target] [!UICONTROL Compositor de experiencias visuales] (VEC).

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
   >Actualmente, la opción [!UICONTROL Representar usando JavaScript] no se puede usar cuando existe código personalizado en el Compositor de experiencias visuales.

1. Actualice los classNames solo para ocultar otros y mostrar los siguientes con temporizador/animación.

   Nunca utilice JavaScript para actualizar la estructura del DOM.
