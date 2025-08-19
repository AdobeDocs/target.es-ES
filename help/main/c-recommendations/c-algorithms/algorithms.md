---
keywords: recomendaciones;actividad de recomendaciones;criterios;algoritmo;clave de recomendación;clave personalizada;sector comercial;minorista;comercio electrónico;generación de posibles clientes;b2b;servicios financieros;medios;publicación
description: Aprenda a utilizar criterios en Adobe [!DNL Target] [!DNL Recommendations].
title: ¿Cómo se usan los criterios en  [!DNL Target] Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 6%

---

# [!UICONTROL Criteria]

[!UICONTROL Criteria] en [!DNL Adobe Target] [!DNL Recommendations] son reglas que determinan qué productos o contenido se recomiendan en función de un conjunto predeterminado de comportamientos del visitante. Los criterios pueden basarse en tendencias populares, en los comportamientos actuales y pasados de un visitante o en productos y contenido similares. Puede probar distintos tipos de recomendaciones entre sí si se agregan varios criterios.

En las secciones siguientes se explica más información sobre las claves de criterios y la lógica de recomendación que puede utilizar para cada clave. Haga clic en los vínculos para obtener información más detallada.

## Sector {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

Al crear un criterio, puede seleccionar un sector vertical en función de los objetivos de su actividad de recomendaciones.

| Sector | Objetivo |
|--- |--- |
| [!UICONTROL Retail/Ecommerce] | Conversión que termina en compra |
| [!UICONTROL Lead Generation/B2B/Financial Services] | Conversión sin compra |
| [!UICONTROL Media/Publishing] | Participación |

Otras opciones de criterios cambian según el sector que seleccione. Puede establecer el sector predeterminado en vertical en la página **[!UICONTROL Administration]>[!UICONTROL Recommendations]** o especificar el sector vertical para cada criterio.

## Tipo de algoritmo {#section_885B3BB1B43048A88A8926F6B76FC482}

El tipo de algoritmo que seleccione determina los algoritmos disponibles.

En la tabla siguiente se explican los distintos tipos de algoritmos y los algoritmos que los acompañan.

| Tipo de algoritmo | Cuándo usar | Algoritmos disponibles |
| --- | --- | --- |
| [!UICONTROL Cart-Based] | Haga recomendaciones basadas en el contenido del carro de compras del usuario. | <ul><li>[!UICONTROL People Who Viewed These, Also Viewed]</li><li>[!UICONTROL People Who Viewed These, Also Bought]</li><li>[!UICONTROL People Who Bought These, Also Bought]</li></ul>Para obtener más información, consulte [Basado en el carro de compras](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based) en *Basar la recomendación en una clave de recomendación*. |
| [!UICONTROL Popularity-Based] | Haga recomendaciones basadas en la popularidad general de un elemento en el sitio o en la popularidad de elementos dentro de la categoría, marca, género, etc. favoritos o más vistos de un usuario. | <ul><li>[!UICONTROL Most Viewed Across the Site]</li><li>[!UICONTROL Most Viewed by Category]</li><li>[!UICONTROL Most Viewed by Item Attribute]</li><li>[!UICONTROL Top Sellers Across the Site]</li><li>[!UICONTROL Top Sellers by Category]</li><li>[!UICONTROL Top Sellers by Item Attribute]</li><li>[!UICONTROL Top by Analytics Metric]</li></ul> |
| [!UICONTROL Item-Based] | Haga recomendaciones basadas en la búsqueda de artículos similares a los que el usuario está viendo en este momento o ha visto recientemente. | <ul><li>[!UICONTROL People Who Viewed This, Viewed That]</li><li>[!UICONTROL People Who Viewed This, Bought That]</li><li>[!UICONTROL People Who Bought This, Bought That]</li><li>[!UICONTROL Items with Similar Attributes]</li></ul> |
| [!UICONTROL User-Based] | Haga recomendaciones basadas en el comportamiento del usuario. | <ul><li>[!UICONTROL Recently Viewed Items]</li><li>[!UICONTROL Recommended for You]</li></ul> |
| [!UICONTROL Custom Criteria] | Cree recomendaciones basadas en un archivo personalizado que haya cargado. | <ul><li>Algoritmo personalizado</li></ul> |

Para obtener más información acerca de cada algoritmo, vea [Basar la recomendación en una clave de recomendación](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

## Uso de una clave de recomendación personalizada {#custom-key}

También puede basar las recomendaciones en el valor de un atributo de perfil personalizado.

>[!NOTE]
>
>Los parámetros de perfil personalizados se pueden pasar a [!DNL Target] mediante JavaScript, API o integraciones. Para obtener más información sobre los atributos de perfil personalizados, consulte [Perfiles de visitantes](/help/main/c-target/c-visitor-profile/visitor-profile.md).

Por ejemplo, supongamos que desea mostrar películas recomendadas basadas en la película que agregó un usuario recientemente a la cola.

1. Haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Haga clic en **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**.

1. Rellene la información de la [sección Información básica](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. En la sección [Algoritmo recomendado](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#rec-algo), seleccione **[!UICONTROL Item Based]** de la lista **[!UICONTROL Algorithm Type]**.

1. Seleccione **[!UICONTROL People Who Viewed This, Viewed That]** de la lista **[!UICONTROL Algorithm]**.

1. Seleccione su atributo de perfil personalizado de la lista **[!UICONTROL Recommendation Key]** (por ejemplo, [!UICONTROL Last Show Added to Watchlist]).

## Visualización de información de criterios {#section_7162DE58E4594FD688A4D7FDB829FD8B}

Para ver los detalles de los criterios, haga clic en los criterios deseados en la columna [!UICONTROL Name].

Las secciones **[!UICONTROL Attributes]** y Detalles le permiten ver información general sobre los criterios seleccionados, incluidos sus datos de [!UICONTROL Name], [!UICONTROL Description], [!UICONTROL Industry Vertical], [!UICONTROL Page Types], [!UICONTROL Recommendation Key], [!UICONTROL Recommendation Logic], [!UICONTROL Algorithm ID] y la información de la última modificación (fecha y quién modificó el algoritmo).

La sección **[!UICONTROL Usage]** le permite ver una lista de actividades que hacen referencia a los criterios seleccionados.

>[!NOTE]
>
>Actualmente, la característica [!UICONTROL Algorithm Usage] solo es compatible con las actividades [!DNL Recommendations]. Esta característica no se admite actualmente para las actividades [!UICONTROL A/B Test], [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target] y [!UICONTROL Experience Targeting] (XT) que incluyen [recomendaciones como oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).
