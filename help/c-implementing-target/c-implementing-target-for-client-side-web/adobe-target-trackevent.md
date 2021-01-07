---
keywords: adobe.target.trackEvent;trackEvent;trackevent;track event;at.js;functions;function;preventDefault;preventdefault;prevent default
description: Información sobre la función adobe.target.trackEvent(options) para la biblioteca JavaScript at.js de Adobe Target.
title: adobe.target.trackEvent(options)
feature: at.js
translation-type: tm+mt
source-git-commit: 6bb75e3b818a71af323614d9150e50e3e9f611b7
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 78%

---


# adobe.target.trackEvent(options)

Esta función activa una solicitud para informar sobre las acciones de los usuarios, como clics y conversiones. No proporciona ninguna actividad en la respuesta.

Después, estas llamadas de mbox de seguimiento de eventos se pueden usar para definir métricas en las actividades. Para obtener más información, consulte [Métricas de éxito](/help/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) y [Conversiones de seguimiento](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053).

He aquí los detalles de API:

| Clave | Tipo | Requerido | Descripción |
|--- |--- |--- |--- |
| mbox | Cadena | Sí | Nombre de mbox <br>**Nota**: Si se activa una llamada a trackEvent() con un nombre de mbox que ya se ha activado en la página, el SDID de trackEvent() se restablece y será diferente a las llamadas de Destinatario en la página. Sin embargo, al activar una llamada a trackEvent() con un nombre de mbox diferente, el SDID de la llamada trackEvent() se mantiene coherente con las llamadas a Page Load Request/activateView() en la página. |
| selector | Cadena | No | Los selectores de CSS utilizados para encontrar los elementos HTML. Los detectores de eventos se adjuntarán a los elementos encontrados. |
| type | Cadena | No | Representa un tipo de evento registrado. Puede ser tanto eventos HTML conocidos como: click, mousedown, etc. como también eventos HTML personalizados. |
| preventDefault | Booleano | No | Indica si usar `event.preventDefault()` en la llamada de retorno de la escucha de eventos. Toma el valor predeterminado de falso.<br>**Nota:** Solo compatible con `form[submit] and `un[clic]. No se admiten otros escenarios debido a la complejidad y a la gran cantidad de escenarios por admitir. |
| params | Objeto | No | Parámetros de mbox. Un objeto de pares de clave-valor que tiene la siguiente estructura:<br>`{ "param1": "value1", "param2": "value2"}` |
| timeout | Número | No | Tiempo de espera en milisegundos.<br>Si no se especifica, se utiliza el valor predeterminado:<br>`...timeoutInSeconds: 0.15...}` |
| success | Función | No | Una función de llamada de retorno utilizada para indicar que se ha informado el evento. |
| error | Función | No | Una función de llamada de retorno utilizada para indicar que no se ha podido informar el evento. |

## Ejemplo

```javascript
<a href="https://asite.com">click me!</a> 
```

código javaScript plus para asignar `trackEvent`:

```javascript
<script> 
$('a').click(function(event){ 
  adobe.target.trackEvent({'mbox':'homePageHero'}) 
}); 
</script> 
```

O bien:

```javascript
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