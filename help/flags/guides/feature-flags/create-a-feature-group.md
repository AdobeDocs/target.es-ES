---
title: Creación de un grupo de funciones
description: Obtenga información sobre cómo crear un grupo de funciones en Marcas para administrar varias marcas de funciones en todas las aplicaciones de su equipo como una sola unidad.
badge: label="Beta" type="Informative"
hide: true
exl-id: 58148df1-84ee-4a78-a4b4-71f74cd8ce0a
source-git-commit: 8fffd619232b2cae2f5dd0aa1e0a55183c4be698
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 0%

---

# Creación de un grupo de funciones {#create-feature-group}

## Requisitos previos {#prerequisites}

Antes de crear un grupo de funciones, complete lo siguiente:

* Tiene acceso a la consola Marcas; consulte [Iniciar sesión en la consola](../console/log-in-to-the-console.md)
* Su aplicación está integrada. Consulte [Incorporar su aplicación](../applications/onboard-your-application.md)
* Tiene el rol **Propietario de la versión del producto**
* Ha creado las marcas de características que desea agregar al grupo. Consulte [Crear su primera marca de características](create-your-first-feature-flag.md)

Para obtener una introducción a los grupos de características, vea [Grupos de características para controlar varias características](../../concepts/feature-groups-to-control-multiple-features.md).

## Paso 1: Crear el grupo de funciones {#create}

Abra la consola e inicie un nuevo grupo de funciones:

1. Inicie sesión en la consola **Banderas**, vaya al panel izquierdo y seleccione **Grupos de funciones**.
2. Seleccione **Nuevo grupo de características**.

## Paso 2: Detalles básicos {#basic-details}

Configure las opciones generales del grupo de funciones:

1. Proporcione un título, clave, descripción y, opcionalmente, una etiqueta.
2. Establezca un **despliegue porcentual** para el grupo de características.
3. Si desea ejecutar una prueba A/B, seleccione más de una variante. De lo contrario, déjelo en una variante. Consulte [Pruebas A/B con indicadores de características](a-b-testing.md) para obtener más información.

## Paso 3: Audiencia {#audience}

Defina quién recibirá las funciones de este grupo:

1. En la ficha **Audiencia**, agregue criterios de audiencia para definir qué usuarios recibirán la característica.
2. En **Aplicaciones**, agregue una o más aplicaciones de su equipo. Los grupos de funciones pueden abarcar varias aplicaciones, siempre que todas pertenezcan al mismo equipo.

## Paso 4: Funciones {#features}

Asigne los indicadores de funcionalidad que controlará este grupo:

1. En la ficha **Características**, verá un cuadro para cada aplicación seleccionada.
2. Agregue indicadores de características para cada aplicación.
3. Si ha seleccionado varias variantes (para pruebas A/B), verá las pestañas de cada variante. Agregue los indicadores de características adecuados a cada uno.

>[!IMPORTANT]
>
>Una marca de características solo se puede proporcionar mediante un método: directamente como marca de característica, a través de un grupo de características o a través de una versión. Al agregar una marca de característica a un grupo de características, se elimina cualquier despliegue de audiencia o porcentaje establecido en la marca. Los indicadores de características ya asignados a otra versión o grupo de características no aparecerán en la lista.

>[!IMPORTANT]
>
>Cuando **quita** una marca de características de un grupo de características, la marca vuelve a un estado **deshabilitado** y su audiencia está **no** restaurada, trátela como una marca nueva. Un marcador **disabled** dentro de un grupo siempre se evalúa como `false`. Al habilitar un grupo de características, **no** habilita sus marcas de miembro; habilita cada marca explícitamente.
>
>Los grupos de características son una **capa de administración**. En tiempo de ejecución, siempre realiza la evaluación en el nivel de **característica (indicador)**, nunca en el nivel de grupo; la respuesta incluye la variante en la que se encontró el usuario.

## Consulte también {#see-also}

* [Configuración de un grupo de funciones para su despliegue gradual](set-feature-group-gradual-rollout.md)
* [Pruebas A/B con indicadores de funcionalidades](a-b-testing.md)
* [Grupos de funciones para controlar varias funciones](../../concepts/feature-groups-to-control-multiple-features.md)

<!-- -->
