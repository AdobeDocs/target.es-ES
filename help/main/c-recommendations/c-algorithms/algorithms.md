---
keywords: recomendaciones;actividad de recomendaciones;criterios;algoritmo;clave de recomendación;clave personalizada;sector comercial;minorista;comercio electrónico;generación de posibles clientes;b2b;servicios financieros;medios;publicación
description: Aprenda a utilizar los criterios en Adobe [!DNL Target] [!DNL Recommendations].
title: ¿Cómo utilizo los criterios en [!DNL Target] Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
TQID: 'https://experienceleague.adobe.com/Wo7I3piBQ7zwYF7kqRphDeWjcBCpyvIvTkwKK0t0f9U'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
    internal-label: Integrations
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 5%
---
# Introducción a [!UICONTROL Criterios] {#get-started-criteria}

>[!BEGINSHADEBOX]

**En esta página:** Descubra cómo funcionan los criterios en [!DNL Adobe Target Recommendations] y qué sector, tipo de algoritmo y opciones de clave de recomendación están disponibles.

>[!ENDSHADEBOX]

Los **[!UICONTROL criterios]** de [!DNL Adobe Target] [!DNL Recommendations] son reglas que determinan qué productos o contenido se recomiendan en función de un conjunto predeterminado de comportamientos del visitante. Los criterios se pueden basar en tendencias populares, los comportamientos actuales y pasados de un visitante o productos y contenido similares. Se pueden agregar varios criterios a una actividad para probar varios tipos de recomendaciones entre sí.

El sector vertical y el tipo de algoritmo seleccionado determinan las opciones disponibles cuando se crean los criterios.

## Sector {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

Cuando se crean criterios, se selecciona un sector vertical en función de los objetivos de la actividad de recomendaciones.

| Sector | Objetivo |
|--- |--- |
| **[!UICONTROL Venta minorista/Comercio electrónico]** | Conversión que termina en compra |
| **[!UICONTROL Generación de clientes potenciales/B2B/Servicios financieros]** | Conversión sin compra |
| **[!UICONTROL Medios/Publicación]** | Participación |

Otras opciones de criterios cambian según el sector seleccionado. El sector predeterminado se puede establecer en la página **[!UICONTROL Administración]** > **[!UICONTROL Recomendaciones]**, o el sector se puede especificar para cada criterio.

## Tipo de algoritmo {#section_885B3BB1B43048A88A8926F6B76FC482}

El tipo de algoritmo seleccionado determina los algoritmos disponibles. En la tabla siguiente se explican los tipos de algoritmos y los algoritmos que los acompañan.

| Tipo de algoritmo | Cuándo usar | Algoritmos disponibles |
| --- | --- | --- |
| **[!UICONTROL Basado en el carro de compras]** | Haga recomendaciones basadas en el contenido del carro de compras del usuario. | <ul><li>**[!UICONTROL Las Personas Que Vieron Esto, También Vieron]**</li><li>**[!UICONTROL Otras Personas Que Vieron Esto, También Compraron]**</li><li>**[!UICONTROL Otras Personas Que Compraron Esto, También Compraron]**</li></ul>Para obtener más información, consulte [Basado en el carro de compras](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based) en *Basar la recomendación en una clave de recomendación*. |
| **[!UICONTROL Basado en popularidad]** | Haga recomendaciones basadas en la popularidad general de un elemento en todo el sitio o en la popularidad de elementos dentro de la categoría, marca, género, etc. favoritas o más vistas del usuario. | <ul><li>**[!UICONTROL Más visitados en todo el sitio]**</li><li>**[!UICONTROL Más visitados por categoría]**</li><li>**[!UICONTROL Más visitados por atributo de artículo]**</li><li>**[!UICONTROL Más visitados por atributo de perfil]**</li><li>**[!UICONTROL Principales vendedores en todo el sitio]**</li><li>**[!UICONTROL Principales vendedores por categoría]**</li><li>**[!UICONTROL Principales vendedores por atributo de artículo]**</li><li>**[!UICONTROL Principales vendedores por atributo de perfil]**</li><li>**[!UICONTROL Métrica superior por Analytics]**</li></ul> |
| **[!UICONTROL Basado en elementos]** | Haga recomendaciones basadas en artículos que sean similares a un artículo que el usuario esté viendo en este momento o que haya visto recientemente. | <ul><li>**[!UICONTROL Las Personas Que Vieron Esto, Vieron Aquello]**</li><li>**[!UICONTROL Otras Personas Que Vieron Esto, Compraron Aquello]**</li><li>**[!UICONTROL Otras Personas Que Compraron Esto, Compraron Aquello]**</li><li>**[!UICONTROL Elementos con atributos similares]**</li></ul> |
| **[!UICONTROL Basado en usuario]** | Haga recomendaciones basadas en el comportamiento del usuario. | <ul><li>**[!UICONTROL Artículos vistos recientemente]**</li><li>**[!UICONTROL Recomendado para usted]**</li></ul> |
| **[!UICONTROL Criterios personalizados]** | Haga recomendaciones basadas en un archivo personalizado cargado. | <ul><li>Algoritmo personalizado</li></ul> |

Para obtener más información acerca de cada algoritmo, vea [Basar la recomendación en una clave de recomendación](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

## Usar una clave de recomendación personalizada {#custom-key}

Las recomendaciones también se pueden basar en el valor de un atributo de perfil personalizado. Por ejemplo, las películas recomendadas se pueden mostrar en función de la película que agregó un usuario recientemente a la cola.

1. Haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Criterios]**.

1. Haga clic en **[!UICONTROL Crear criterios]** > **[!UICONTROL Crear criterios]**.

   ![Página de criterios con el menú Crear criterios abierto, que muestra Crear criterio y Crear secuencia de criterios](../assets/criteria_1.png)

1. Rellene la información de la [sección Información básica](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. En la sección [Algoritmo recomendado](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#rec-algo), seleccione **[!UICONTROL Basado en elementos]** de la lista **[!UICONTROL Tipo de algoritmo]**.

1. Seleccione **[!UICONTROL Las personas que vieron esto, vieron aquello]** de la lista **[!UICONTROL Algoritmo]**.

1. Seleccione el atributo de perfil personalizado de la lista **[!UICONTROL Clave de recomendación]** (por ejemplo, **[!UICONTROL Última visualización agregada a la lista de observación]**).

   >[!NOTE]
   >
   >Los parámetros de perfil personalizados se pueden pasar a [!DNL Target] mediante JavaScript, API o integraciones. Para obtener más información sobre los atributos de perfil personalizados, consulte [Perfiles de visitantes](/help/main/c-target/c-visitor-profile/visitor-profile.md).

   ![Cuadro de diálogo Crear criterios que muestra la sección Algoritmo de recomendaciones con las listas Tipo de algoritmo, Algoritmo y Clave de recomendación](../assets/criteria_2.png)

## Ver información de criterios {#section_7162DE58E4594FD688A4D7FDB829FD8B}

Los detalles de criterios muestran cómo se configura un criterio y qué actividades lo utilizan.

1. Haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Criterios]** para mostrar la lista de criterios.

1. Haga clic en los criterios deseados en la columna **[!UICONTROL Nombre]**.

1. Vea información general sobre los criterios seleccionados en las secciones **[!UICONTROL Atributos]** y Detalles, incluidos su **[!UICONTROL Nombre]**, **[!UICONTROL Descripción]**, **[!UICONTROL Sector vertical]**, **[!UICONTROL Tipos de página]**, **[!UICONTROL Clave de recomendación]**, **[!UICONTROL Lógica de recomendación]**, **[!UICONTROL ID de algoritmo]** e información de la última modificación (fecha y quién modificó el algoritmo).

1. Vea la lista de actividades que hacen referencia a los criterios seleccionados en la sección **[!UICONTROL Uso]**.

   >[!NOTE]
   >
   >Actualmente, la característica **[!UICONTROL Uso del algoritmo]** solo es compatible con [!DNL Recommendations] actividades. Esta característica no se admite actualmente para las actividades de **[!UICONTROL Prueba A/B]**, **[!UICONTROL Asignación automática]**, **[!UICONTROL Segmentación automática]** y **[!UICONTROL Segmentación de experiencias]** (XT) que incluyen [recomendaciones como oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).

   ![Detalles de criterios con las secciones Atributos y Detalles y la sección Uso resaltada](../assets/criteria_3.png)
