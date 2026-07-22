---
title: Creación de la primera marca de funcionalidad
description: Obtenga información sobre cómo crear un indicador de funciones en Banderas, establecer una audiencia y probarla antes de distribuirla a los usuarios.
badge: label="Beta" type="Informative"
hide: true
exl-id: ae115120-8da9-465e-a556-c17591ea7054
source-git-commit: 8fffd619232b2cae2f5dd0aa1e0a55183c4be698
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 2%

---

# Creación de la primera marca de funcionalidad {#create-feature-flag}

## Requisitos previos {#prerequisites}

Antes de crear un indicador de funcionalidad, complete lo siguiente:

* Tiene acceso a la consola Marcas; consulte [Iniciar sesión en la consola](../console/log-in-to-the-console.md)
* Su aplicación está integrada. Consulte [Incorporar su aplicación](../applications/onboard-your-application.md)
* Tiene el rol **Propietario de la versión del producto**

## Paso 1: Crear el indicador de funcionalidad {#create}

Para crear un nuevo indicador de funcionalidad, siga estos pasos en la consola:

1. Inicie sesión en la consola **Banderas**, vaya al panel izquierdo y seleccione **Marcas de características**.
1. Seleccione su aplicación en la lista desplegable **Aplicación**.
1. Seleccione **Nuevos indicadores de características**.
1. Rellene los campos del formulario:

   | Campo | Descripción |
   | --- | --- |
   | **Nombre** | Una etiqueta de visualización para el indicador de funcionalidad. No se utiliza en el código. |
   | **Clave** * | El identificador utilizado en el código para evaluar el indicador. No se puede cambiar después de la creación. |
   | **Descripción** | Descripción opcional para fines de documentación. |
   | **Metadatos** | Opcional. Hasta 1.024 caracteres. Utilice este campo para cualquier metadato adicional que se asocie al indicador. |
   | **Etiquetas** | Etiquetas opcionales para fines de documentación. |
   | **Identidad** * | La identidad con la que se evalúa el indicador (por ejemplo, ECID). Identidad que se pasa en la solicitud de funcionalidad. |
   | **Despliegue de porcentaje** | El porcentaje de la audiencia definida que sirve esta función. El valor predeterminado es 100%. Ver [Establecer una característica para implementarla gradualmente](set-feature-gradual-rollout.md). |

   Los campos marcados con * son obligatorios.

>[!IMPORTANT]
>
>La clave **Key** es el identificador usado en tu código y no se puede cambiar después de crearla. Las claves **no pueden contener espacios** y distinguen entre mayúsculas y minúsculas **.****Name** es una etiqueta de presentación solamente y no se usa en el código; los dos son independientes (el nombre no se convierte en la clave). Al escribir un espacio en el campo Clave se produce el error: _&quot;Valor no válido para la clave de característica.&quot;_

1. Si lo desea, puede añadir un criterio de audiencia (consulte el paso 2).
1. Guarde la configuración de las marcas de características.

## Paso 2: Añadir un criterio de audiencia {#audience}

Los criterios de audiencia controlan qué usuarios ven la función. Puede segmentar usuarios con **atributos de contexto**: valores que su sitio web o aplicación envía en la solicitud de características (por ejemplo, `locale` o `platform`). Combínelos con **AND**, **OR** y **NOT**. Ver [Usar contexto en reglas de audiencia](../audience/using-context-in-audience-rules.md).

Para agregar criterios de audiencia, vaya a la pestaña **Audiencia** al crear o editar una marca de característica.

## Consulte también {#see-also}

* [Configurar una función para que se implemente gradualmente](set-feature-gradual-rollout.md)
* [Creación de un grupo de funciones](create-a-feature-group.md)

<!-- -->
