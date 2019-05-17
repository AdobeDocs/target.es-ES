---
description: Lista de funciones mbox.js que se deben usar al implementar con mbox.js.
keywords: Funciones mbox
seo-description: Lista de funciones mbox.js que se deben usar al implementar con mbox.js.
seo-title: Funciones mbox.js
solution: Target
title: Funciones mbox.js
uuid: f503bc44-a664-4d09-82dc-80a1198ad9d0
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Funciones mbox.js{#mbox-js-functions}

Lista de funciones mbox.js que se deben usar al implementar con mbox.js.

>[!NOTE]
>
>Si está usando [!DNL at.js], no se aplican estos métodos.

| Método | Notas |
|--- |--- |
| `mbox.getName()` |
| `mbox.getURL()` |
| `mbox.getDiv()` | Devuelve el div asociado al mbox (con el contenido u oferta predeterminados) |
| `mbox.getParameters()` | Matriz de parámetros con dos campos, nombre y valor |
| `mbox.setOnError()` | Ejemplo:<br>`mbox.setOnError(function() { alert(this.getName() +" had error"});` |
| `mbox.setMessage(message)` | Puede ver un mensaje en la ventana de depuración. |
| `mboxCurrent.activate()` |
| `mboxCurrent.cancelTimeout()` |
| `mboxCurrent.finalize()` |
| `mboxCurrent.getDefaultDiv()` |
| `mboxCurrent.getDiv()` | Devuelve el div asociado al mbox (con el contenido u oferta predeterminados) |
| `mboxCurrent.getEventTimes()` |
| `mboxCurrent.getFetcher()` |
| `mboxCurrent.getId()` |
| `mboxCurrent.getImportName()` |
| `mboxCurrent.getName()` |
| `mboxCurrent.getOffer()` |
| `mboxCurrent.getParameters()` | Matriz de parámetros con dos campos, nombre y valor. |
| `mboxCurrent.getURL()` |
| `mboxCurrent.getURLBuilder()` |
| `mboxCurrent.hide()` |
| `mboxCurrent.isActivated`() |
| `mboxCurrent.load()` |
| `mboxCurrent.loaded()` |
| `mboxCurrent.setEventTime()` |
| `mboxCurrent.setFetcher()` |
| `mboxCurrent.setMessage()` |
| `mboxCurrent.setMessage(message)` | Ver mensaje en ventana de depuración. |
| `mboxCurrent.setOffer()` |
| `mboxCurrent.setOnError()` | Ejemplo:<br>`mboxCurrent.setOnError(function(){ alert(this.getName() +" had error"});` |
| `mboxCurrent.setOnLoad()` | Ejemplo:<br>`mboxCurrent.setOnLoad(function(){alert(this.getName()+" loaded")});` |
| `mboxCurrent.show()` |
| `mboxCurrent.showContent()` |
| `mboxFactoryDefault.addOnLoad(action)` | Se llama a una acción cuando se carga la página. |
| `mboxFactoryDefault.getMboxes().each()` | Ejemplo:<br>`mboxFactoryDefault.getMboxes().each(function() { alert(mbox.getName()) };` |
| `mboxFactoryDefault.getMboxes().length()` |
| `mboxFactoryDefault.getPageId()` |
| `mboxFactoryDefault.getPCId().getId()` |
| `mboxFactoryDefault.getSessionId().getId()` |
| `mboxFactories.get('default').getSessionId()​.forceId("1276011116668");` |
| `mboxFactories.get('default').getPCId()​.forceId("1276011116668");` |
| `mboxFactoryDefault.create()` |
| `mboxFactoryDefault.disable()` |
| `mboxFactoryDefault.enable()` |
| `mboxFactoryDefault.get()` |
| `mboxFactoryDefault.getCookieManager()` |
| `mboxFactoryDefault.getDisableReason()` |
| `mboxFactoryDefault.getEllapsedTime()` |
| `mboxFactoryDefault.getEllapsedTimeUntil()` |
| `mboxFactoryDefault.getMboxes()` | Devuelve un `mboxList`. |
| `mboxFactoryDefault.getSignaler()` |
| `mboxFactoryDefault.getURLBuilder()` |
| `mboxFactoryDefault.isAdmin()` |
| `mboxFactoryDefault.isDomLoaded()` |
| `mboxFactoryDefault.isEnabled()` |
| `mboxFactoryDefault.isSupported()` |
| `mboxFactoryDefault.limitTraffic()` |
| `mboxFactoryDefault.update()` |
| `mboxFactoryDefault.getCookieManager()​.getCookie("name")//!= null) {` |
| `mboxFactoryDefault.getCookieManager()​.setCookie(_name,_value, _duration);` |