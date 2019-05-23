---
description: Este tema explica cómo crear un carrusel que se pueda editar en el Compositor de experiencias visuales (VEC).
keywords: Compositor de experiencias visuales;VEC;carrusel
seo-description: Este tema explica cómo crear un carrusel que se pueda editar en el Compositor de experiencias visuales (VEC).
seo-title: Crear carruseles que funcionen en el Compositor de experiencias visuales
solution: Target
subtopic: Prueba multivariable
title: Crear carruseles que funcionen en el Compositor de experiencias visuales
topic: Standard
uuid: 19538f6e-445c-49ca-9f0d-b49fc330b721
translation-type: tm+mt
source-git-commit: fda7c96a67d310e9b94e50e167cfaaaa937ada35

---


# Crear carruseles que funcionen en el Compositor de experiencias visuales{#creating-carousels-that-work-in-the-visual-experience-composer}

Este tema explica cómo crear un carrusel que se pueda editar en el Compositor de experiencias visuales (VEC).

Cuando se siguen los pasos descritos a continuación, [!DNL Target] siempre sabe que la diapositiva seleccionada tendrá el “selector” de la diapositiva correcta aunque, pasados unos segundos, se cambie en el Compositor de experiencias visuales.

1. Cree marcadores de posición de HTML estáticos.

   ```
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