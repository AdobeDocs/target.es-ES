---
keywords: Recommendations;configuración;preferencias;sector;filtro de criterios incompatibles;grupo de hosts predeterminado;URL de base en miniatura;token de api de recomendaciones
description: 'Obtenga información sobre cómo implementar actividades de Recommendations en Adobe Target. '
title: ¿Cómo Implemento Las Actividades De Recommendations?
feature: Recommendations
exl-id: b6edb504-a8b6-4379-99c1-6907e71601f9
source-git-commit: 802ed4cc03973ee61ff3e40930b137422868835b
workflow-type: tm+mt
source-wordcount: '1544'
ht-degree: 30%

---

# ![PREMIUM](/help/assets/premium.png) Planificar e implementar [!DNL Recommendations]

Antes de configurar la primera [!DNL Recommendations] actividad en [!DNL Adobe Target], complete los siguientes pasos:

1. [Implementación [!DNL Target]](#implement-target) en la web y en la aplicación móvil que desea utilizar para capturar el comportamiento del usuario y enviar recomendaciones.
1. [Configure su [!DNL Recommendations] catálogo](#rec-catalog) de productos o contenido que desea recomendar a sus usuarios.
1. [Pasar información de comportamiento y contexto](#pass-behavioral) a [!DNL Target Recommendations] para permitir que envíe recomendaciones personalizadas.
1. [Configuración de exclusiones globales](#exclusions).
1. [Configurar [!DNL Recommendations] configuración](#concept_C1E1E2351413468692D6C21145EF0B84).

## Implementación [!DNL Target] {#implement-target}

[!DNL Target Recommendations] requiere que implemente el [!DNL Adobe Experience Platform Web SDK] o at.js 0.9.2 (o posterior). Consulte [Implementación [!DNL Target]](/help/c-implementing-target/implementing-target.md) para obtener más información.

## Configurar el catálogo de Recommendations {#rec-catalog}

Para ofrecer recomendaciones de alta calidad, [!DNL Target] debe conocer los productos o el contenido que desea recomendar. El catálogo debería incluir tres tipos de información sobre los artículos que desea recomendar. Supongamos que está recomendando películas. Incluya lo siguiente:

1. Datos que desea mostrar al usuario que recibe la recomendación. Por ejemplo, puede mostrar el nombre de la película y una dirección URL para una imagen en miniatura del póster de la película.
1. Datos que son útiles para aplicar controles de marketing y comercialización. Por ejemplo, puede mostrar la clasificación de la película, de modo que no recomiende las películas NC-17.
1. Datos que son útiles para determinar la similitud de elementos a otros elementos. Por ejemplo, puede mostrar el género de la película y el director de la película.

[!DNL Target] ofrece varias opciones de integración para rellenar el catálogo. Estas opciones se pueden usar en combinación para actualizar diferentes artículos del catálogo o para actualizar diferentes atributos de artículos en distintas frecuencias.

| Método | Qué es | Cuándo utilizarla | Información adicional |
| --- | --- | --- | --- |
| Fuente del catálogo | Programar una fuente (CSV, Google Product XML o [!DNL Analytics Product Classifications]) que se cargarán e incorporarán diariamente. | Para enviar información sobre varios elementos a la vez. Para enviar información que cambia con poca frecuencia. | Consulte [Fuentes](/help/c-recommendations/c-products/feeds.md). |
| API de entidades | Llame a una API para enviar actualizaciones de última hora para un solo elemento. | Para enviar actualizaciones a medida que ocurren de un elemento a la vez. Para enviar información que cambia con frecuencia (por ejemplo, precio, inventario/nivel de existencias). | Consulte la [Documentación para desarrolladores de la API de entidades](https://developers.adobetarget.com/api/recommendations/#tag/Entities). |
| Pasar actualizaciones en la página | Envíe actualizaciones minuto a minuto para un solo elemento usando JavaScript en la página o usando la API de envío. | Para enviar actualizaciones a medida que ocurren de un elemento a la vez. Para enviar información que cambia con frecuencia (por ejemplo, precio, inventario/nivel de existencias). | Consulte [Vistas de elementos/páginas de productos](#items-product-pages) más abajo. |

La mayoría de los clientes deben implementar al menos una fuente. A continuación, puede elegir complementar la fuente con actualizaciones para los atributos o elementos modificados con frecuencia mediante la API Entidades o el método en la página.

## Pasar información de comportamiento y contexto {#pass-behavioral}

La información de comportamiento y el contexto al que debe pasar [!DNL Target] depende de la acción que realice el visitante, que a menudo está asociada con el tipo de página con la que esté interactuando el visitante.

### Vistas de elementos/páginas de productos {#items-product-pages}

En las páginas donde un visitante está viendo un solo elemento, como una página de detalles de un producto, debe pasar la identidad del elemento que el visitante está viendo. También debe pasar la categoría más granular del elemento que el visitante esté viendo, para permitir el filtrado de recomendaciones a la categoría actual.

También puede pasar ciertos atributos que cambian rápidamente en la propia página del producto. Por ejemplo, puede pasar el precio (`value`) y nivel de inventario/stock.

```
<script type="text/javascript">
function targetPageParams() { 
   return { 
      "entity": { 
         "id": "32323", 
         "categoryId": "running-shoes", 
         "value": 119.99, 
         "inventory": 329 
      } 
   } 
}
</script>
```

### Vistas de categoría/páginas de categoría

En una página de categoría, es probable que quiera restringir las recomendaciones a productos o contenido dentro de esa categoría. Para ello, asegúrese de pasar la identidad de la categoría visualizada actualmente.

```
function targetPageParams() { 
   return { 
      "entity": { 
         "categoryId": "running-shoes" 
      } 
   } 
}
```

### Adiciones al carro de compras/vistas del carro de compras/páginas de cierre de compra {#cart}

En una página del carro de compras, puede recomendar artículos según el contenido del carro de compras actual del visitante. Para ello, pase los ID de todos los elementos del carro de compras actual del visitante utilizando el parámetro especial `cartIds`.

```
function targetPageParams() {
   return {
      "cartIds": ["352", "223", "23432", "432", "553"]
      }
}
```

La lógica de recomendación basada en el carro de compras es similar a la &quot;[!UICONTROL Recomendado]&quot; algoritmo basado en el usuario y a &quot;[!UICONTROL Los usuarios que vieron esto, compraron aquéllos]&quot; y &quot;[!UICONTROL Las personas que compraron estos, compraron esos]&quot; algoritmos basados en elementos.

[!DNL Target] utiliza técnicas de filtrado colaborativas para determinar las similitudes de cada elemento del carro de compras del visitante y, a continuación, combina estas similitudes de comportamiento en cada elemento para obtener una lista combinada.

[!DNL Target] también ofrece a los especialistas en marketing la opción de observar el comportamiento de los visitantes en una sola sesión o en varias sesiones:

* **Dentro de una sola sesión**: En función de lo que otros visitantes hicieron dentro de una sola sesión.

   Mirar el comportamiento dentro de una sola sesión puede tener sentido cuando existe la sensación de que los productos se &quot;unen&quot; estrechamente en función de un uso, ocasión o evento. Por ejemplo, un visitante está comprando una impresora y también puede necesitar tinta y papel. O, un visitante está comprando mantequilla de maní y también podría necesitar pan y gelatina.

* **En varias sesiones**: En función de lo que otros visitantes hicieron en varias sesiones.

   Ver el comportamiento en varias sesiones puede tener sentido cuando existe la sensación de que los productos &quot;van con&quot; fuerza unos con otros según la preferencia o el gusto del visitante. Por ejemplo, a un visitante le gusta Star Wars y también puede gustarle Indiana Jones, aunque no necesariamente quiera ver ambas películas en la misma sesión. O, a un visitante le gusta el juego de tablero &quot;Codenames&quot; y también el juego de tablero &quot;Avalon&quot;, aunque el visitante no pueda jugar ambos juegos simultáneamente. 

Independientemente de si observa el comportamiento de los visitantes en una sola sesión o en varias sesiones, [!DNL Target] realiza recomendaciones para cada visitante en función de los artículos del carro de compras actual.

### Excluir elementos que ya están en el carro de compras del visitante

En las páginas de todo el sitio, puede excluir algunos artículos de las recomendaciones. Por ejemplo, es posible que no desee recomendar artículos que ya estén en el carro de compras actual del visitante. Para ello, pase los ID de todos los elementos que desee excluir mediante el parámetro especial `excludedIds`.

```
function targetPageParams() {
   return {
      "excludedIds": ["352", "223", "23432", "432", "553"]
      }
}
```

### Páginas de confirmación de compra/pedido

Cuando se produce un evento de compra, pase la identidad del artículo o artículos comprados. Consulte [Seguimiento de conversiones](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053) en *Implementación [!DNL Target] sin un administrador de etiquetas*.

## Configuración de exclusiones globales {#exclusions}

Excluya cualquier elemento de nivel global que no desee recomendar a un visitante. Consulte [Exclusiones](/help/c-recommendations/c-products/exclusions.md).

## Configurar [!DNL Recommendations] configuración {#concept_C1E1E2351413468692D6C21145EF0B84}

Utilice la configuración para administrar la implementación de [!DNL Recommendations].

Para acceder a la [!UICONTROL Configuración de Recommendations] opciones, abrir [!DNL Target] en el [!DNL Adobe Experience Cloud]y haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Configuración]**.

![](assets/recs_settings.png)

Las opciones disponibles son las siguientes:

| Configuración | Descripción |
|--- |--- |
| Mbox global personalizado | (Opcional) Especifique el mbox global personalizado que se usa para aprovisionar actividades de [!DNL Target]. De forma predeterminada, el mbox global utilizado por [!DNL Target] se usa para [!DNL Recommendations].<br>Nota: Esta opción se establece en la variable [!DNL Target] [!UICONTROL Administración] página. Apertura [!DNL Target]y haga clic en [!UICONTROL Administración] > [!UICONTROL Compositor de experiencias visuales]. |
| Sector | El sector se usa para ayudarle a categorizar los criterios de recomendaciones. Esta información ayuda a los miembros de su equipo a encontrar criterios que tengan sentido para una página en particular, como los criterios que son mejores para la página del carro de compras o para una página de medios. |
| Criterios incompatibles de filtro | Habilite esta opción para mostrar únicamente aquellos criterios donde la página seleccionada pasa los datos necesarios. No todos los criterios se ejecutan correctamente en cada página. La página o el mbox deben pasar `entity.id` o `entity.categoryId` para que las recomendaciones de la categoría actual o el elemento actual sean compatibles. En general, se recomienda mostrar solamente criterios compatibles. Sin embargo, si desea que haya disponibles criterios incompatibles para la actividad, desactive esta opción.<br>Se recomienda deshabilitar esta opción si se usa una solución de administración de etiquetas.<br>Para obtener más información sobre esta opción, consulte [Preguntas frecuentes de Recommendations](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md). |
| Grupo de hosts predeterminado | Seleccione su grupo de hosts predeterminado.<br>El grupo de hosts puede utilizarse para separar los elementos disponibles en el catálogo para usos diferentes. Por ejemplo, puede utilizar grupos de hosts para entornos de desarrollo y producción, marcas diferentes o regiones geográficas diferentes. De forma predeterminada, la vista previa de los resultados en Búsqueda de catálogo, Colecciones y Exclusiones se basa en el grupo de hosts predeterminado. (También puede seleccionar otro grupo de hosts para obtener una vista previa de los resultados mediante el filtro Entorno). De forma predeterminada, los elementos recién añadidos están disponibles en todos los grupos de hosts a menos que se especifique un ID de entorno al crear o actualizar el elemento. Las recomendaciones enviadas dependen del grupo de hosts especificado en la solicitud.<br>Si no ve sus productos, asegúrese de que esté usando el grupo de hosts correcto. Por ejemplo, si configura que la recomendación use un entorno de ensayo y establece el grupo de hosts en Ensayo, puede que tenga que volver a crear las colecciones en el entorno de ensayo para que se puedan mostrar los productos. Para ver qué productos están disponibles en cada entorno, use Búsqueda en catálogo con cada entorno. También puede obtener una vista previa del contenido de las colecciones y exclusiones de Recommendations para un entorno seleccionado (grupo de hosts).<br>**Nota:** Después de cambiar el entorno seleccionado, debe hacer clic en Buscar para actualizar los resultados devueltos.<br>El filtro [!UICONTROL Entorno] está disponible en los siguientes lugares de la interfaz de usuario de [!DNL Target]:<ul><li>Búsqueda en el catálogo (Recommendations > Buscar en el catálogo)</li><li>Cuadro de diálogo Crear colección ([!UICONTROL Recommendations > Colecciones > Crear nuevo])</li><li>Cuadro de diálogo Actualizar colección ([!UICONTROL Recommendations > Colecciones > Editar])</li><li>Cuadro de diálogo Crear exclusión ([!UICONTROL Recommendations > Exclusiones > Crear nuevo])</li><li>Cuadro de diálogo Actualizar exclusión ([!UICONTROL Recommendations > Exclusiones > Editar])</li></ul>Para obtener más información, consulte [Hosts](/help/administrating-target/hosts.md). |
| Dirección URL de base en miniatura | Al establecer una dirección URL de base para su catálogo de productos, es posible usar direcciones URL relativas al especificar vistas en miniatura de sus productos al pasar su dirección URL de vista en miniatura.<br>Por ejemplo:<br>`"entity.thumbnailURL=/Images/Homepage/product1.jpg"`<br> establece una dirección URL relativa para la dirección URL de base de vista en miniatura. |
| Token de API de Recommendations | Use este token en las llamadas de la API de Recommendations como, por ejemplo, la API de Descargar. |
