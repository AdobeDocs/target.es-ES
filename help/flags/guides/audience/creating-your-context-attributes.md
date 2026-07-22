---
title: Creación de atributos de contexto
description: Aprenda a crear y organizar atributos de contexto y grupos de contexto en Banderas para que pueda utilizarlos en criterios de audiencia.
badge: label="Beta" type="Informative"
hide: true
source-git-commit: 8fffd619232b2cae2f5dd0aa1e0a55183c4be698
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 5%

---

# Creación de atributos de contexto {#creating-your-context-attributes}

Los atributos de contexto son campos de datos personalizados que describen el contexto de usuario, sesión o aplicación (por ejemplo, nivel de suscripción, versión de aplicación o región). Utilice los atributos de contexto para definir los criterios de audiencia para los indicadores de características.

Los grupos de contexto organizan los atributos de contexto relacionados en una jerarquía lógica. Utilice grupos de contexto para facilitar la búsqueda y administración de atributos durante la configuración de funciones.

| Término | Descripción | Utilizado en |
| --- | --- | --- |
| **Atributo de contexto** | Campo con nombre con un tipo de datos y valores predefinidos opcionales. | Criterios de audiencia, configuración de funciones |
| **Grupo de contexto** | Categoría que organiza los atributos de contexto relacionados. | Selección de contexto al crear una función |
| **Etiqueta de interfaz de usuario** | El nombre para mostrar aparece en la interfaz de usuario. | Criterios de audiencia y páginas de administración |
| **ID** | Un identificador técnico único. | Solicitudes de aplicación |
| **Valores predefinidos** | Una lista opcional de valores permitidos con etiquetas de visualización. | Listas desplegables y creadores de reglas de audiencia |

## Requisitos previos {#prerequisites}

Antes de administrar atributos de contexto y grupos de contexto, complete lo siguiente:

* Tiene acceso a la **consola Indicadores** en la zona protegida correcta.
* Tiene el rol **Admin** necesario para crear y administrar atributos de contexto y grupos de contexto.

## Navegar a Atributos de contexto {#navigate}

1. Inicie sesión en la **consola Indicadores**.
1. En el panel de navegación izquierdo, en **Paneles**, seleccione **Atributos de contexto**.

Ahora se encuentra en la página **Atributos de contexto**. Utilice esta página para crear grupos de contextos y atributos de contexto.

## Creación de un grupo de contexto {#create-group}

Cada atributo de contexto debe pertenecer a un grupo.

1. En el panel de navegación izquierdo, en **Paneles**, seleccione **Atributos de contexto**.
1. En la ficha **Mis atributos de contexto**, seleccione **Agregar grupo**.
1. Complete los campos obligatorios.
1. Seleccione **Crear**.

### Agrupar campos {#group-fields}

| Campo | Descripción |
| --- | --- |
| **Nombre de grupo** | Introduzca un nombre único para el grupo. |
| **Crear un subgrupo de** | Seleccione un grupo principal para organizar la jerarquía. También puede crear un grupo al crear un atributo. |

## Crear un atributo de contexto {#create-attribute}

1. En la ficha **Mis atributos de contexto**, seleccione **Nuevo atributo de contexto**.
1. Complete los campos obligatorios.
1. Seleccione **Enviar**.

### Campos de atributo {#attribute-fields}

| Campo | Descripción |
| --- | --- |
| **Etiqueta de interfaz de usuario** | Introduzca el nombre para mostrar utilizado en los criterios de audiencia. |
| **ID** | Introduzca un identificador técnico único utilizado en las solicitudes de aplicaciones. |
| **Grupo de contexto** | Seleccione un grupo o cree un nuevo grupo en línea. |
| **Tipo de datos** | Seleccione el tipo que coincida con los datos que envía su aplicación. |

| Tipo de datos | Ejemplo |
| --- | --- |
| CADENA | `gold` |
| ENTERO | `42` |
| BOOLEANO | `true` |
| DECIMAL | `9.99` |
| FECHA | `2026-07-17` |
| VERSIÓN | `1.2.0` |

### Valores predefinidos (opcional) {#predefined-values}

Utilice valores predefinidos para limitar un atributo a un conjunto fijo de valores. Seleccione **Agregar valores predefinidos**.

| Campo | Descripción |
| --- | --- |
| **Etiqueta de interfaz de usuario** | Introduzca el nombre para mostrar. |
| **Valor** | Introduzca el valor técnico enviado por la aplicación. |

Seleccione **Guardar** para aplicar los cambios.

## Resolución de problemas {#troubleshooting}

| Problema | Resolución |
| --- | --- |
| **Crear** está deshabilitado | Complete **Nombre de grupo** y **Cree un subgrupo de**. |
| No se puede enviar un atributo | Complete **ID** y **grupo de contexto**. |
| Grupo no visible en la lista desplegable | Actualice la página o cree el grupo en línea desde el formulario de atributos. |
| Valores predefinidos no guardados | Seleccione **Guardar** en el modal antes de enviar el atributo. |

## Consulte también {#see-also}

* [Creación y uso de conjuntos de reglas](creating-and-using-rule-sets.md)
* [Uso del contexto en las reglas de audiencia](using-context-in-audience-rules.md)
* [Audiencia en indicadores y grupos de características](audience-in-feature-flags-and-feature-groups.md)

<!-- -->
