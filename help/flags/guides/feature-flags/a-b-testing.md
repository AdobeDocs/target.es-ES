---
title: Pruebas A/B con indicadores de funcionalidades
description: Obtenga información sobre cómo ejecutar pruebas A/B mediante grupos de características en Marcas configurando varias variantes para un conjunto de indicadores de características.
badge: label="Beta" type="Informative"
hide: true
exl-id: bb849049-229c-40ff-bbfe-7996f868bcc3
source-git-commit: 8fffd619232b2cae2f5dd0aa1e0a55183c4be698
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 1%

---

# Pruebas A/B con indicadores de funcionalidades {#a-b-testing}

Las pruebas A/B en los indicadores se realizan con **grupos de características**. Al configurar más de una variante en un grupo de funciones, puede ofrecer distintas versiones de una función a diferentes subconjuntos de la audiencia y comparar los resultados.

## Requisitos previos {#prerequisites}

* Tiene acceso a la consola; consulte [Iniciar sesión en la consola](../console/log-in-to-the-console.md)
* Pertenece a un equipo y la aplicación está integrada
* Tiene el rol **Propietario de la versión del producto**
* Ha creado los indicadores de características que desea probar. Consulte [Crear su primer indicador de características](create-your-first-feature-flag.md)

## Paso 1: Crear un grupo de funciones con varias variantes {#create}

1. Vaya a **Prueba de características > Grupos de características** y seleccione **Nuevo grupo de características**.
1. En **Detalles básicos**, proporcione un título, clave y descripción.
1. Establezca un **despliegue porcentual** para definir qué parte de su audiencia participa en la prueba.
1. Establezca **Variants** en un valor mayor que uno (por ejemplo, dos variantes para una prueba A/B clásica). Puede definir hasta **3 variantes más un grupo de control**.
1. Ver [Configurar un grupo de características para que se implemente gradualmente](set-feature-group-gradual-rollout.md) para comprender cómo se distribuye el porcentaje de exposición entre las variantes.

>[!NOTE]
>
>La exposición se divide **equitativamente** entre variantes; por ejemplo, 50/50 para dos variantes. No se admiten divisiones personalizadas como 60/40. Se puede agregar una sola marca de característica a **más de una variante**. La audiencia se establece **una vez por grupo de características**, no por variante.

## Paso 2: Configuración de la audiencia {#audience}

En la ficha **Audiencia**, agregue criterios de audiencia y seleccione las aplicaciones que desea incluir. Los grupos de funciones pueden abarcar varias aplicaciones dentro del mismo equipo.

## Paso 3: Añadir funciones por variante {#features}

En la ficha **Características**, cada variante tiene su propia ficha. Agregue los indicadores de características adecuados a cada variante para definir las diferentes experiencias que desee comparar.

>[!IMPORTANT]
>
>Una marca de características solo se puede mostrar mediante un método a la vez: marca de características, grupo de características o versión. Al agregar una marca a un grupo de funciones, se elimina cualquier audiencia o porcentaje de despliegue establecido directamente en la marca.

## Paso 4: Guardar y activar {#save}

Guarde la configuración del grupo de funciones. Cuando esté listo para iniciar la prueba, establezca el grupo de características en el estado activo.

## Consulte también {#see-also}

* [Creación de un grupo de funciones](create-a-feature-group.md)
* [Configuración de un grupo de funciones para su despliegue gradual](set-feature-group-gradual-rollout.md)
* [Informes](reporting.md)

<!-- -->
