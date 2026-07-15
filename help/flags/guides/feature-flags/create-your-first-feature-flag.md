---
title: Creación de la primera marca de funcionalidad
description: Obtenga información sobre cómo crear un indicador de funciones en Banderas, establecer una audiencia y probarla antes de distribuirla a los usuarios.
hide: true
exl-id: ae115120-8da9-465e-a556-c17591ea7054
source-git-commit: 045bd3321fd4041fe7f723ce300a400102ed7274
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 1%

---

# Creación de la primera marca de funcionalidad {#create-feature-flag}

## Requisitos previos {#prerequisites}

Antes de crear un indicador de funcionalidad, complete lo siguiente:

* Tiene acceso a la consola Marcas; consulte [Iniciar sesión en la consola](../console/log-in-to-the-console.md)
* Su aplicación está integrada. Consulte [Incorporar su aplicación](../applications/onboard-your-application.md)
* Tiene la función **Desarrollador** o **Propietario de la versión del producto**

## Paso 1: Crear el indicador de funcionalidad {#create}

Para crear un nuevo indicador de funcionalidad, siga estos pasos en la consola:

1. Inicie sesión en la consola Indicadores y vaya a **Características y versiones > Indicadores de características**.
1. Seleccione su aplicación en la lista desplegable **Aplicación**.
1. Seleccione **Nueva característica**.
1. Rellene los campos del formulario:

   | Campo | Descripción |
   | --- | --- |
   | **Nombre** | Una etiqueta de visualización para el indicador de funcionalidad. No se utiliza en el código. |
   | **Clave** * | El identificador utilizado en el código para evaluar el indicador. No se puede cambiar después de la creación. |
   | **Descripción** | Descripción opcional para fines de documentación. |
   | **Metadatos** | Opcional. Hasta 1.024 caracteres. Utilice este campo para cualquier metadato adicional que se asocie al indicador. |
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

>[!NOTE]
>
>El rol **Desarrollador** se encuentra en una zona protegida. Los desarrolladores solo pueden exponer una característica a sí mismos agregando su propio ID de usuario en **Audiencia > Perfil > ID de usuario**. Para exponer una característica a usuarios externos, necesita el rol **Propietario de la versión del producto**.

## Paso 3: Calcular el tamaño de la audiencia {#audience-size}

Después de agregar los criterios de audiencia, selecciona **Calcular** en la barra inferior para obtener un recuento estimado de los usuarios que califican para la función. Esto ayuda a validar el direccionamiento antes de lanzarse.

## Paso 4: Programar (opcional) {#schedule}

Puede programar una marca de características para que se active en una fecha y hora futuras mediante la opción **Programar** en la configuración de la marca de características.

## Preguntas frecuentes: No puedo agregar un indicador de funcionalidad como desarrollador {#faq}

El rol **Desarrollador** se encuentra en una zona protegida. Los desarrolladores pueden probar las funciones de forma privada añadiendo su ID de usuario a la audiencia. No pueden exponer las funciones a usuarios externos. Utilice el rol **Propietario de la versión del producto** para publicar características para usuarios externos. Póngase en contacto con el administrador para actualizar su función.

## Consulte también {#see-also}

* [Configurar una función para que se implemente gradualmente](set-feature-gradual-rollout.md)
* [Creación de un grupo de funciones](create-a-feature-group.md)

<!-- -->
