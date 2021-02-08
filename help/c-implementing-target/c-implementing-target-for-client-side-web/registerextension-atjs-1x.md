---
keywords: registerExtension;registerextension;registrar extensión;at.js;funciones;función;clientCode;serverDomain;globalMboxName;globalMboxAutoCreate;timeout
description: Utilice la función registerExtension() de la biblioteca JavaScript at.js de Adobe Target para registrar una extensión específica. (at.js 1.x)
title: ¿Cómo se usa la función registerExtension()?
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 90%

---


# registerExtension(): at.js 1.x

Ofrece una forma estándar de registrar una extensión determinada.

>[!NOTE]
>
>Esta función está disponible para las versiones 1 de at.js.Solamente *x*. Esta función quedó obsoleta con el lanzamiento de at.js 2.x. Esta función devuelve el contenido predeterminado si se utiliza con at.js 2.x.

El parámetro de opciones es obligatorio y tiene la siguiente estructura:

| Clave | Tipo | Requerido | Descripción |
|--- |--- |--- |--- |
| name | Cadena | Sí | Nombre de la extensión. |
| módulos | Matriz[Cadena] | Sí | Una matriz de cadenas que representan los nombres de los módulos solicitados. |
| registrarse | Función | Sí | Una función que se usa para inicializar y compilar la extensión. Esta función recibe argumentos basados en la matriz de módulos. |

Notas:

* Si no se proporciona uno de los parámetros, se genera una excepción.
* Si la matriz de módulos está vacía, se genera una excepción.

Para obtener más información y ejemplos sobre el uso de `registerExtension`, consulte la página [Extensiones atjs de Target de Adobe Experience Cloud](https://github.com/Adobe-Marketing-Cloud/target-atjs-extensions) en GitHub.

## Métodos del módulo de configuración {#section_8501CDD4B0624FA2B10532C98C5F4328}

| Clave | Tipo | Descripción |
|--- |--- |--- |
| clientCode | Cadena | Código de cliente |
| serverDomain | Cadena | Dominio de servidor Edge |
| globalMboxName | Cadena | Nombre de mbox global de Target |
| globalMboxAutoCreate | Booleano | Indica si la creación automática está habilitada o no |
| timeout | Número | Tiempo de espera de la solicitud |

## Métodos del módulo del registrador    {#section_10AF62B49AEF48F981E950D26E176138}

| Clave | Tipo | Descripción |
|--- |--- |--- |
| log | Función | Registra la lista variable de argumentos en la consola del navegador (si existe). Solo se activa cuando `mboxDebug=true` se pasa a la dirección URL. |
| error | Función | Registra la lista variable de argumentos en la consola del navegador. Solo se activa cuando hay errores graves, como tiempo de espera de la red, nodos HTML que no se encuentran, etc. |
