---
keywords: Compositor de experiencias visuales;VEC;carrusel
description: Aprenda a crear un carrusel que se pueda editar en el Compositor de experiencias visuales (VEC) de Adobe [!DNL Target].
title: ¿Cómo se crean carruseles en el Compositor de experiencias visuales?
feature: Visual Experience Composer (VEC)
exl-id: 50bc11d2-c9fc-4b53-8218-49842b59269a
TQID: 'https://experienceleague.adobe.com/RN04MJgC49BI2-h2e-i-kgSRTejpLHzKACm-hOv2VCE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 2%
---
# Creando carruseles que funcionen en [!UICONTROL Compositor de experiencias visuales] {#vec-carousels}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a crear un carrusel que se pueda editar en el **[!UICONTROL Compositor de experiencias visuales]** (VEC).

>[!ENDSHADEBOX]

Un carrusel creado con la siguiente estructura se puede editar en el [!DNL Adobe Target] **[!UICONTROL Compositor de experiencias visuales]** (VEC). La estructura mantiene válido el selector de cada diapositiva, por lo que [!DNL Target] siempre identifica la diapositiva correcta, incluso cuando la diapositiva mostrada cambia unos segundos después de que la página se cargue en el VEC.

1. Cree las diapositivas como marcadores de posición estáticos de HTML, con una diapositiva visible y las otras diapositivas ocultas por clase.

   ```html
   <ul>
   <li class="show"> slide 1 </li>
   <li class="hidden"> slide 2 </li>
   <li class="hidden"> slide 3 </li>
   </ul>
   ```

1. Diseñe el aspecto solo con CSS. No use JavaScript para esto.

   >[!NOTE]
   >
   >La opción **[!UICONTROL Procesar usando JavaScript]** no se admite actualmente si se usa junto con código personalizado en **[!UICONTROL Compositor de experiencias visuales]**.

1. Mostrar la siguiente diapositiva actualizando sólo los nombres de clase: ocultar las otras diapositivas y mostrar la siguiente con un temporizador o una animación. Nunca actualice la estructura del DOM con JavaScript.
