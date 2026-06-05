---
keywords: lista de permitidos;oferta remota;administración;patrones de URL;validación;actividades;ofertas;comodín;regex
description: Obtenga información sobre cómo ver, buscar, agregar y eliminar direcciones URL incluidas en la lista de permitidos para ofertas remotas en la sección Administración de Adobe Target, incluido el comportamiento de validación y el ámbito de toda la cuenta.
title: Administración de direcciones URL de ofertas remotas incluidas en la lista de permitidos
feature: Administration & Configuration
topic: Implementation
role: Admin
level: Intermediate
solution: Target
product: Target
source-git-commit: 882c91244e5dae0977c8a6a1e5878525f497a720
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---

# URL INCLUIDAS EN LA LISTA DE PERMITIDOS

Las direcciones URL incluidas en la lista de permitidos definen patrones de direcciones URL de confianza en los que su organización puede crear y ejecutar experiencias de [!DNL Adobe Target], incluso cuando utiliza ofertas remotas o de redireccionamiento. La lista funciona junto con [administración de hosts](/help/main/administrating-target/hosts.md) y [entornos](/help/main/administrating-target/environments.md), pero se aplica específicamente a los patrones de URL de ofertas remotas permitidas y a las validaciones relacionadas.

Para administrar las direcciones URL incluidas en la lista de permitidos, haga clic en **[!UICONTROL Administración]** > **[!UICONTROL URL Incluidas en la lista de permitidos]**.

![Página de direcciones URL Incluidas en la lista de permitidos que muestra la lista de direcciones URL, el campo de búsqueda y Agregar control de URL](../administrating-target/assets/allowlist-1.png)

## Administración de direcciones URL incluidas en la lista de permitidos {#add-url}

La tabla principal enumera cada patrón incluido en la lista de permitidos en una sola columna. Las entradas compatibles pueden incluir direcciones URL exactas, rutas comodín o formatos de patrón que su organización acepta para experiencias remotas.

1. Haga clic en **[!UICONTROL Agregar URL]**.

   ![](../administrating-target/assets/allowlist-2.png)

1. En el cuadro de diálogo, introduzca la dirección URL o el patrón que debe permitir su organización.

   ![](../administrating-target/assets/allowlist-3.png)

1. Guarde los cambios.

   Una vez incluido en la lista de permitidos el patrón, los usuarios pueden crear o ejecutar actividades y ofertas que dependan de esa dirección URL, según las demás reglas de [!DNL Target].

1. Utilice el campo **[!UICONTROL Buscar direcciones URL]** para filtrar la tabla.

1. Para eliminar una dirección URL, busca la fila del patrón que ya no necesitas y haz clic en el icono ![Eliminar](../administrating-target/assets/do-not-localize/Smock_Delete_18_N.svg).

   ![](../administrating-target/assets/allowlist-4.png)


