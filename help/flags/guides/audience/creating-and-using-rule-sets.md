---
title: Creación y uso de conjuntos de reglas
description: Obtenga información sobre cómo crear un conjunto de reglas reutilizables de criterios de contexto de audiencia en Marcas e importarlas en indicadores de características y grupos de características.
hide: true
source-git-commit: 9c6f2b72f964b06da51e1f3655545147d7240a93
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 1%

---

# Creación y uso de conjuntos de reglas {#creating-and-using-rule-sets}

Un conjunto de reglas es una colección reutilizable de criterios de contexto de audiencia. Cree un conjunto de reglas cuando varios indicadores de características o grupos de características necesiten la misma audiencia. A continuación, puede importar el conjunto de reglas en lugar de volver a crear los criterios de audiencia para cada función.

## Requisitos del conjunto de reglas {#requirements}

| Etiqueta de IU | Utilice | Requerido |
| --- | --- | --- |
| **Introducir conjunto de reglas** | Introduzca un nombre para el conjunto de reglas. | Sí |
| **Descripción del conjunto de reglas** | Describa el propósito del conjunto de reglas. | No |
| **Contexto** | Defina al menos un criterio de audiencia. Los atributos de contexto son campos con nombre, como nivel de suscripción, versión de aplicación o región. | Sí |

## Crear un conjunto de reglas {#create-rule-set}

### Paso 1: Iniciar un nuevo conjunto de reglas {#step-1-start}

En Marcas, seleccione **Conjunto de reglas** en el panel de navegación izquierdo y, a continuación, seleccione **Nuevo conjunto de reglas**.

La ficha **Mi conjunto de reglas** muestra los conjuntos de reglas que ha creado. La ficha **Conjunto de reglas de equipo** muestra los conjuntos de reglas disponibles para su equipo.

![Lista de conjuntos de reglas sin conjuntos de reglas creados todavía](assets/rule-set-list-empty.png)

### Paso 2: Añadir los detalles y criterios del conjunto de reglas {#step-2-details}

1. Introduzca un nombre para el conjunto de reglas.
1. Si lo desea, introduzca una descripción.
1. En **Contexto**, defina los criterios de audiencia que desee reutilizar.
1. Use **And** o **Or** para combinar varios criterios.
1. Para crear una expresión más compleja, seleccione **Habilitar lógica anidada**.

![Formulario de creación de conjunto de reglas con criterios de contexto de ejemplo](assets/rule-set-create-context.png)

### Paso 3: Guardar el conjunto de reglas {#step-3-save}

Seleccione **Guardar configuración**. El conjunto de reglas guardado aparece en **Mi conjunto de reglas**.

![Lista de conjuntos de reglas que muestra un conjunto de reglas recién guardado](assets/rule-set-list-created.png)

## Usar un conjunto de reglas en un indicador o grupo de características {#use-rule-set}

### Paso 1: Abrir y habilitar la configuración de audiencia {#step-1-open}

Abra la marca de características o el grupo de características en el que desee usar el conjunto de reglas, seleccione la ficha **Audiencia** y, a continuación, active **Regla de audiencia** para habilitar los criterios de audiencia.

### Paso 2: Selección del conjunto de reglas {#step-2-select}

Abra la lista desplegable **Seleccionar conjunto de reglas**. Elija el conjunto de reglas de **Mi conjunto de reglas** o **Mi conjunto de reglas de equipo**.

![Abrir el menú desplegable Seleccionar conjunto de reglas en la pestaña Audiencia](assets/rule-set-select-in-audience.png)

### Paso 3: Revisar los criterios importados {#step-3-review}

Los criterios de contexto del conjunto de reglas seleccionado se importan en la audiencia. Revise los criterios y, a continuación, guarde la marca de características o el grupo de características.

![Pestaña de audiencia de indicador de características que muestra los criterios importados del conjunto de reglas](assets/rule-set-imported-audience.png)

Puede utilizar el mismo conjunto de reglas en varios indicadores de características y grupos de características que requieran la misma audiencia.

### Paso 4: guardar el indicador o el grupo de características {#step-4-save}

Después de revisar los criterios de audiencia importados, seleccione **Guardar configuración**.

>[!NOTE]
>
>Al importar un conjunto de reglas, se copian sus criterios de audiencia en el indicador o grupo de características. Si es necesario actualizar más adelante los criterios de audiencia, actualícelos por separado en todos los indicadores y grupos de características en los que se importó el conjunto de reglas. La actualización del conjunto de reglas original no actualiza automáticamente las audiencias importadas anteriormente.

## Crear un conjunto de reglas a partir de un indicador o grupo de características {#create-from-feature}

También puede crear un conjunto de reglas directamente desde la pantalla Audiencia de un indicador o grupo de características:

1. Abra la marca de características o el grupo de características y, a continuación, seleccione la ficha **Audiencia**.
1. Activar **regla de audiencia**.
1. Defina los criterios de contexto que desee reutilizar.
1. Seleccione el botón **+** en la esquina superior derecha, junto al menú desplegable **Seleccionar conjunto de reglas**.
1. En el cuadro de diálogo **Guardar conjunto de reglas**, escriba un nombre para el conjunto de reglas.
1. Seleccione **Guardar conjunto de reglas**.

## Consulte también {#see-also}

* [Creación de atributos de contexto](creating-your-context-attributes.md)
* [Uso del contexto en las reglas de audiencia](using-context-in-audience-rules.md)
* [Audiencia en indicadores y grupos de características](audience-in-feature-flags-and-feature-groups.md)

<!-- -->
