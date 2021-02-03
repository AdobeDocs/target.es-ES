---
keywords: Compositor de experiencias visuales;VEC;carrusel
description: En este tema se muestra cómo crear un carrusel que se puede editar en el Compositor de experiencias visuales (VEC) de Adobe Target.
title: Creación de carruseles que funcionan en el Compositor de experiencias visuales
feature: Visual Experience Composer (VEC)
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 69%

---


# Crear carruseles que funcionen en el Compositor de experiencias visuales

Este tema muestra cómo crear un carrusel que se puede editar en el [!DNL Adobe Target] [!UICONTROL Compositor de experiencias visuales] (VEC).

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