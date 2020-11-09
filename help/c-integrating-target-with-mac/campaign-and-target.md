---
keywords: Overview and Reference
description: Utilice Target con Adobe Campaign para optimizar el contenido del correo electrónico.
title: Integración de Target con Adobe Campaign
feature: campaign
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 51%

---


# Integración de Target con Adobe Campaign{#integrate-target-with-adobe-campaign}

Use [!DNL Target] with [!DNL Adobe Campaign] to optimize email content.

To optimize your email content--for example, to display different offers for male and female recipients--you can create a redirect offer in [!DNL Target], then use [!DNL Adobe Campaign] to manage the email offers.

La integración tiene lugar cuando se abre el correo electrónico. When the customer opens the email, a call is made to [!DNL Target] and a dynamic version of the content appears. El contenido está formado por una imagen estática compatible con todos los navegadores. [!DNL Target] hace un seguimiento de la reacción ante la oferta en el nivel de audiencia o de sesión y pone esos datos a su disposición en los informes de [!DNL Target]

Target puede hacer un seguimiento de los datos siguientes:

* Agente de usuario
* Dirección IP
* Ubicación geográfica
* Segmento asociado con el ID del visitante en Target (si recibe aprobación legal)
* Data from [!DNL Campaign] Datamart

Existen varias limitaciones:

* Como solo se puede usar una imagen, el contenido no se puede personalizar.
* Tracking is not consolidated in [!DNL Adobe Campaign].
* No se puede unificar la experiencia de usuario.

   You must use both [!DNL Target] and [!DNL Campaign] to set up different parts of the integration:

   * El rawbox y la experiencia en [!DNL Target]
   >[!NOTE]
   >
   >Al utilizar un rawbox y [!DNL Target], consulte el aviso de seguridad importante en [Crear listas de permitidos que especifique los hosts autorizados para enviar llamadas de mbox a Destinatario](/help/administrating-target/hosts.md#allowlist).

   * The delivery in [!DNL Campaign]



## Antes de empezar   {#section_FF19BF1BCA064260930BF6C141313B0E}

Before you use [!DNL Adobe Campaign] to set up your targeted email offers, set up the following in [!DNL Target]:

* Two or more [!DNL Target] redirect offers

   See [Create redirect offer](/help/c-experiences/c-manage-content/offer-redirect.md).
* Una actividad de Target con una experiencia para cada oferta y la [métrica de éxito](/help/c-activities/r-success-metrics/success-metrics.md) deseada.

   Consulte [Redireccionar a una dirección URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md).

Start the activity in [!DNL Target] before setting up the [!DNL Campaign] portion of the integration.

## Incluir una oferta de Target en un correo electrónico de Adobe Campaign   {#section_B201BBE27A704E18AF0D553F35695837}

1. Create an email in [!DNL Adobe Campaign].
1. En las propiedades del correo electrónico, haga clic en **[!UICONTROL Incluir]** > **[!UICONTROL Imagen dinámica proporcionada por Adobe Target]**.
1. Seleccione la imagen predeterminada entre los recursos compartidos.
1. Especifique la ubicación (rawbox).
1. Agregue el resto de los parámetros de toma de decisiones, como puede ser el sexo del destinatario.
1. Seleccione por lo menos un destinatario para cada oferta (en este caso, un hombre y una mujer) y previsualice el correo electrónico.
1. In [!DNL Campaign], define the [!DNL Target] Edge server you are using to control the activity and the name of the tenant.
1. Specify the external account used for the [!DNL Adobe Experience Cloud] so you can access the resources in the [!DNL Experience Cloud].

For more information, refer to the [!DNL Adobe Campaign] documentation.
