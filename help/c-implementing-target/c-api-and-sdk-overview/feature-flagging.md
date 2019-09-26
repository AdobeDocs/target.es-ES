---
description: Los equipos de productos de tecnología contemporánea están adoptando principios de entrega continua para lanzamientos de productos. Target ayuda a los desarrolladores y a los equipos de productos a desarrollar nuevas capacidades de productos de forma rápida y eficaz.
keywords: implementación;despliegue;entrega continua;lanzamiento del producto;implementación gradual
seo-description: Los equipos de productos de tecnología contemporánea están adoptando principios de entrega continua para lanzamientos de productos. Adobe Target ayuda a los desarrolladores y a los equipos de productos a desarrollar nuevas funciones de producto de forma rápida y eficaz en una implementación gradual.
seo-title: Los equipos de productos de tecnología contemporánea están adoptando principios de entrega continua para lanzamientos de productos. Adobe Target ayuda a los desarrolladores y a los equipos de productos a desarrollar nuevas funciones de producto de forma rápida y eficaz.
solution: Target
title: Indicador de funciones
topic: Standard
translation-type: tm+mt
source-git-commit: 08debab3ec3d2f6e6bfd3c42476dc1a021185ab7

---


# Indicador de funciones

Los equipos de productos de tecnología contemporánea están adoptando principios de entrega continua para lanzamientos de productos. Adobe Target ayuda a los desarrolladores y a los equipos de productos a desarrollar nuevas funciones de producto de forma rápida y eficaz en una implementación gradual.

Los siguientes vínculos proporcionan información sobre los conceptos clave que necesita comprender para permitir la entrega continua:

* [Actividades de prueba A/B](/help/c-activities/t-test-ab/test-ab.md)
* [JSON offers](/help/c-experiences/c-manage-content/create-json-offer.md)
* [Mejoras de audiencia](/help/c-target/c-audiences/creating-a-profile-attribute-comparison-audience.md)

## Continuous delivery

1. By default, turn the feature "off" on release.

   Use una variable en la aplicación o en el lado del servidor para controlar esto.

1. Cree una oferta JSON de Target que establezca esta variable en "on".

1. Cree una actividad de prueba A/B en el Compositor [de experiencias](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) visuales (VEC) con dos experiencias y utilice la oferta JSON creada en el paso anterior en una experiencia.

   O

   Cree una actividad de prueba A/B en el Compositor [de experiencias basadas en](/help/c-experiences/form-experience-composer.md) formularios con una sola experiencia y utilice la oferta JSON creada en el paso anterior.

   >[!NOTE]
   >
   >The Form-based Experience Composer allows you to create an A/B Test activity with a single experience. You cannot create the activity with a single experience using the VEC.

1. Specify your desired traffic allocation for the activity.

   If you want to start by rolling this feature out to 5% of your visitors, specify 5 in the Targeting step of the three-part guided workflow and send 100% of the qualifying visitors to the experience with the JSON offer (Experience A).

   La siguiente ilustración muestra el VEC con dos experiencias.

   ![Asignación de tráfico para el marcado de funciones en el VEC](/help/c-implementing-target/c-api-and-sdk-overview/assets/feature-flagging.png)

   La siguiente ilustración muestra el Compositor de experiencias basadas en formularios con una sola experiencia.

   ![Traffic allocation for feature flagging in the Form-based Experience Composer](/help/c-implementing-target/c-api-and-sdk-overview/assets/feature-flagging-form.png)

1. Puede aumentar la asignación de tráfico a esta actividad aumentando gradualmente el 5 % a través de la interfaz de usuario de Target o mediante la API hasta que alcance la asignación de tráfico del 100 %.

   >[!NOTE]
   >
   >An A/B Test activity is sticky for a visitor through the session. If you decrease the traffic allocation, visitors who started seeing this feature continue to view it until their sessions are reset.

## Características de la prueba A/B

Si está utilizando A/B/..En Características de la prueba, utilice el método descrito anteriormente con las siguientes mejoras:

* Cada variante de función debe representarse mediante una oferta JSON adecuada que realice una experiencia de Target.
* Puede administrar la asignación de tráfico para esta prueba de la manera descrita anteriormente.

## Implementaciones parametrizadas

El método descrito anteriormente le ayuda a administrar una implementación controlada.

Puede desplegar una función solo para los participantes de la versión beta y, posteriormente, implementarla para todos los demás clientes. Esto se puede lograr fácilmente aprovechando los parámetros [de ubicación de](/help/c-target/c-audiences/c-target-rules/custom-parameters.md) destino (mbox) o los parámetros [](/help/c-target/c-audiences/c-target-rules/visitor-profile.md)de perfil. Estos parámetros se pueden utilizar junto con la asignación de tráfico por fases.

## Server-side vs. client-side

Feature rollouts and testing can be delivered via Target APIs (and server-side SDKs) as well as the client side SDKs (JS, Mobile SDK). [](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md) Depending on how your website, mobile app, or kiosk is architected, you can leverage Target's different integration options.
