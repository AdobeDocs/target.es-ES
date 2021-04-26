---
keywords: implementación;biblioteca javascript;js;atjs;toma de decisiones en el dispositivo;en la toma de decisiones del dispositivo;at.js;en el dispositivo;en el dispositivo;solución de problemas;solución de problemas
description: Obtenga información sobre cómo solucionar problemas de decisiones en el dispositivo con la biblioteca at.js.
title: ¿Cómo puedo solucionar problemas de la toma de decisiones en el dispositivo con la biblioteca JavaScript at.js?
feature: 'at.js '
role: Developer
translation-type: tm+mt
source-git-commit: 85a17944c7d5924edb1bbabb7531274249ceaaa8
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 0%

---

# Resolución de problemas de la toma de decisiones en el dispositivo para at.js

Complete los siguientes pasos para solucionar los problemas de la toma de decisiones en el dispositivo en [!DNL Adobe Target] con la biblioteca JavaScript at.js:

## Paso 1: Habilitar el registro de la consola para at.js

Añadir el parámetro de URL `mboxDebug=1` permite que at.js imprima mensajes en la consola del explorador.

Todos los mensajes contienen el prefijo &quot;AT:&quot; para una descripción general práctica. Para asegurarse de que un artefacto se ha cargado correctamente, el registro de la consola debe contener mensajes similares a los siguientes:

```
AT: LD.ArtifactProvider fetching artifact - https://assets.adobetarget.com/your-client-cide/production/v1/rules.json
AT: LD.ArtifactProvider artifact received - status=200
```

La siguiente ilustración muestra estos mensajes en el registro de la consola:

![Registro de consola con mensajes de artefactos](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/browser-console.png)

## Paso 2: Verifique la descarga de artefactos de reglas en la pestaña Red del explorador

Abra la pestaña Red del explorador.

Por ejemplo, para abrir DevTools en Google Chrome:

1. Pulse Control+Mayús+J (Windows) o Comando+Opción+J (Mac).
1. Vaya a la pestaña Red (Network).
1. Filtre sus llamadas por palabra clave &quot;rules.json&quot; para asegurarse de que solo se muestre el archivo de reglas de artefactos.

   Además, puede filtrar por &quot;/delivery|rules.json/&quot; para mostrar todas las llamadas [!DNL Target] y artifact rules.json.

   ![Pestaña Red en Google Chrome](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/rule-json.png)

## Paso 3: Verifique la descarga de artefactos de reglas mediante eventos personalizados de at.js

La biblioteca at.js envía dos nuevos eventos personalizados para admitir la toma de decisiones en el dispositivo.

* `adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED`
* `adobe.target.event.ARTIFACT_DOWNLOAD_FAILED`

Puede suscribirse para escuchar estos eventos personalizados en la aplicación a la acción si la descarga del archivo de reglas de artefactos se ha realizado correctamente o no se ha realizado correctamente.

El siguiente ejemplo muestra una muestra de código que escucha los eventos de éxito y error de descarga de artefactos:

```javascript
document.addEventListener(adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED, function(e) { 
  console.log("Artifact successfully downloaded", e.detail);
}, false);

document.addEventListener(adobe.target.event.ARTIFACT_DOWNLOAD_FAILED, function(e) { 
  console.log("Artifact failed to download", e.detail);
}, false);
```
