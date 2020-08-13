---
keywords: adobe.target.trackEvent;trackEvent;trackevent;track event;at.js;functions;function;preventDefault;preventdefault;prevent default
description: Información sobre la función adobe.target.trackEvent(options) para la biblioteca JavaScript at.js de Adobe Target.
title: Información sobre la función adobe.target.trackEvent(options) para la biblioteca JavaScript at.js de Adobe Target.
feature: client-side
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 100%

---


# adobe.target.trackEvent(options)

Esta función activa una solicitud para informar sobre las acciones de los usuarios, como clics y conversiones. No proporciona ninguna actividad en la respuesta.

Después, estas llamadas de mbox de seguimiento de eventos se pueden usar para definir métricas en las actividades. Para obtener más información, consulte [Métricas de éxito](../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) y [Conversiones de seguimiento](../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053).

He aquí los detalles de API:

| Clave | Tipo | Requerido | Descripción |
|--- |--- |--- |--- |
| mbox | Cadena | Sí | Nombre de mbox |
| selector | Cadena | No | Los selectores de CSS utilizados para encontrar los elementos HTML. Los detectores de eventos se adjuntarán a los elementos encontrados. |
| type | Cadena | No | Representa un tipo de evento registrado. Puede ser tanto eventos HTML conocidos como: click, mousedown, etc. como también eventos HTML personalizados. |
| preventDefault | Booleano | No | Indica si usar `event.preventDefault()` en la llamada de retorno de la escucha de eventos. Toma el valor predeterminado de falso.<br>**Nota:** Solo compatible con `form[submit] and `un[clic]. No se admiten otros escenarios debido a la complejidad y a la gran cantidad de escenarios por admitir. |
| params | Objeto | No | Parámetros de mbox. Un objeto de pares de clave-valor que tiene la siguiente estructura:<br>`{ "param1": "value1", "param2": "value2"}` |
| timeout | Número | No | Tiempo de espera en milisegundos.<br>Si no se especifica, se utiliza el valor predeterminado:<br>`...timeoutInSeconds: 0.15...}` |
| success | Función | No | Una función de llamada de retorno utilizada para indicar que se ha informado el evento. |
| error | Función | No | Una función de llamada de retorno utilizada para indicar que no se ha podido informar el evento. |

## Ejemplo

```
<a href="https://asite.com">click me!</a> 
```

código javaScript plus para asignar `trackEvent`:

```
<script> 
$('a').click(function(event){ 
  adobe.target.trackEvent({'mbox':'homePageHero'}) 
}); 
</script> 
```

O bien:

```
adobe.target.trackEvent({ 
    "mbox": "clicked-cta", 
    "params": { 
        "param1": "value1" 
    } 
});
```

>[!NOTE]
>
>En caso de que no se establezcan los campos obligatorios, no se ejecutará la solicitud y se generará un error.