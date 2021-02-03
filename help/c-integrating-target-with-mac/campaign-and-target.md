---
keywords: Información general y referencia
description: Utilice Target con Adobe Campaign para optimizar el contenido del correo electrónico.
title: Integración de con Adobe Campaign
feature: Integrations
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 51%

---


# Integración de Target con Adobe Campaign{#integrate-target-with-adobe-campaign}

Utilice [!DNL Target] con [!DNL Adobe Campaign] para optimizar el contenido del correo electrónico.

Para optimizar el contenido del correo electrónico (por ejemplo, para mostrar diferentes ofertas para destinatarios hombres y mujeres), puede crear una oferta de redireccionamiento en [!DNL Target] y luego utilizar [!DNL Adobe Campaign] para administrar las ofertas de correo electrónico.

La integración tiene lugar cuando se abre el correo electrónico. Cuando el cliente abre el correo electrónico, se realiza una llamada a [!DNL Target] y aparece una versión dinámica del contenido. El contenido está formado por una imagen estática compatible con todos los navegadores. [!DNL Target] hace un seguimiento de la reacción ante la oferta en el nivel de audiencia o de sesión y pone esos datos a su disposición en los informes de [!DNL Target]

Target puede hacer un seguimiento de los datos siguientes:

* Agente de usuario
* Dirección IP
* Ubicación geográfica
* Segmento asociado con el ID del visitante en Target (si recibe aprobación legal)
* Datos de Datamart [!DNL Campaign]

Existen varias limitaciones:

* Como solo se puede usar una imagen, el contenido no se puede personalizar.
* El seguimiento no está consolidado en [!DNL Adobe Campaign].
* No se puede unificar la experiencia de usuario.

   Debe utilizar [!DNL Target] y [!DNL Campaign] para configurar diferentes partes de la integración:

   * El rawbox y la experiencia en [!DNL Target]
   >[!NOTE]
   >
   >Cuando utilice un rawbox y [!DNL Target], consulte el aviso de seguridad importante en [Crear listas de permitidos que especifiquen hosts autorizados para enviar llamadas de mbox a Destinatario](/help/administrating-target/hosts.md#allowlist).

   * El envío en [!DNL Campaign]



## Antes de empezar    {#section_FF19BF1BCA064260930BF6C141313B0E}

Antes de utilizar [!DNL Adobe Campaign] para configurar las ofertas de correo electrónico objetivo, configure lo siguiente en [!DNL Target]:

* Dos o más ofertas de redireccionamiento [!DNL Target]

   Consulte [Crear oferta de redireccionamiento](/help/c-experiences/c-manage-content/offer-redirect.md).
* Una actividad de Target con una experiencia para cada oferta y la [métrica de éxito](/help/c-activities/r-success-metrics/success-metrics.md) deseada.

   Consulte [Redireccionar a una dirección URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md).

Inicio la actividad en [!DNL Target] antes de configurar la porción [!DNL Campaign] de la integración.

## Incluir una oferta de Target en un correo electrónico de Adobe Campaign    {#section_B201BBE27A704E18AF0D553F35695837}

1. Cree un correo electrónico en [!DNL Adobe Campaign].
1. En las propiedades del correo electrónico, haga clic en **[!UICONTROL Incluir]** > **[!UICONTROL Imagen dinámica proporcionada por Adobe Target]**.
1. Seleccione la imagen predeterminada entre los recursos compartidos.
1. Especifique la ubicación (rawbox).
1. Agregue el resto de los parámetros de toma de decisiones, como puede ser el sexo del destinatario.
1. Seleccione por lo menos un destinatario para cada oferta (en este caso, un hombre y una mujer) y previsualice el correo electrónico.
1. En [!DNL Campaign], defina el [!DNL Target] servidor Edge que está utilizando para controlar la actividad y el nombre del inquilino.
1. Especifique la cuenta externa utilizada para [!DNL Adobe Experience Cloud] para poder acceder a los recursos en [!DNL Experience Cloud].

Para obtener más información, consulte la documentación de [!DNL Adobe Campaign].
