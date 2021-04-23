---
keywords: implementar;implementación;configuración;configuración;atributos de perfil de secuencia
description: Obtenga datos en [!DNL Target] mediante atributos de perfil de secuencia de comandos.
title: ¿Cómo puedo obtener datos en  [!DNL Target] mediante atributos de perfil de secuencia de comandos?
feature: Implementación
role: Developer
exl-id: c323fb4c-f263-43d4-8523-9f42c2913542
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 83%

---

# Atributos de perfil en script

Los atributos de perfil de secuencia de comandos son pares de nombre-valor definidos en la solución [!DNL Adobe Target] . El valor se determina a partir de la ejecución de un fragmento JavaScript en el servidor de Target por llamada de servidor.

Los usuarios escriben pequeños fragmentos de código que se ejecutan mediante una llamada de mbox y antes de que el visitante se evalúe por audiencia y abono a la actividad.

## Formato

Los atributos de perfil en script se crean en la sección Audiencias de Target. Cualquier nombre de atributo es válido y el valor es el resultado de una función JavaScript escrita por el usuario de Target. Al nombre de atributo se le añade automáticamente el prefijo “user. &quot; en Target para distinguirlo de los atributos del perfil en página.

El fragmento de código se escribe en lenguaje Rhino JS y puede hacer referencia a tokens y a otros valores.

## Casos de uso de ejemplo

* **Abandono del carrito**: cuando el visitante llega hasta el carrito de compra, el script de perfil se establece en 1. Si el visitante hace una conversión, se restablece en 0. Si el valor es igual a 1, el visitante tiene un artículo en el carrito.
* **Recuento de visitas**: en cada nueva visita el recuento aumenta 1 punto para hacer el seguimiento de la frecuencia con la que un visitante regresa al sitio.

## Ventajas del método

No requiere actualizaciones de código.

Se ejecuta antes de la toma de decisiones de audiencia y abono a la actividad, por lo que estos atributos de script de perfil pueden afectar al abono en una sola llamada de servidor.

Puede ser muy potente. Se pueden ejecutar hasta 2000 instrucciones por script.

## Advertencias

Se requieren conocimientos de JavaScript.

La orden de ejecución de los scripts de perfil no está garantizada, por lo que no pueden depender los unos en los otros.

La depuración puede ser difícil.

## Ejemplos de código

Los scripts de perfil son bastante flexibles:

`user.purchase_recency: var dayInMillis = 3600 * 24 * 1000; if (mbox.name == 'orderThankyouPage') {  user.setLocal('lastPurchaseTime', new Date().getTime()); } var lastPurchaseTime = user.getLocal('lastPurchaseTime'); if (lastPurchaseTime) {  return ((new Date()).getTime()-lastPurchaseTime)/dayInMillis; }`

### Enlaces a información relevante

[Atributos de script de perfil](/help/c-target/c-visitor-profile/profile-parameters.md#concept_8C07AEAB0A144FECA8B4FEB091AED4D2)
