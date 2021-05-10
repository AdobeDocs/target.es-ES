---
keywords: Información general y referencia
description: Aprenda a utilizar Adobe [!DNL Target] con Adobe Campaign para optimizar el contenido del correo electrónico.
title: ¿Cómo se integra [!DNL Target] con Adobe Campaign?
feature: Integraciones
exl-id: 605b8fe4-e32f-43bc-9131-245008b655e1
translation-type: tm+mt
source-git-commit: f3a9ee9827d635d335cb9707d3d92d0de1bd0304
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 37%

---

# Integrar [!DNL Target] con Adobe Campaign

Utilice [!DNL Target] con [!DNL Adobe Campaign] para optimizar el contenido del correo electrónico.

Para optimizar el contenido del correo electrónico, puede crear una oferta de redireccionamiento en [!DNL Target] y luego utilizar [!DNL Adobe Campaign] para administrar las ofertas de correo electrónico. Por ejemplo, puede mostrar diferentes ofertas para destinatarios hombres y mujeres.

La integración tiene lugar cuando se abre el correo electrónico. Cuando el cliente abre el correo electrónico, llama a [!DNL Target] y aparece una versión dinámica del contenido. El contenido está formado por una imagen estática compatible con todos los navegadores. [!DNL Target] hace un seguimiento de la reacción ante la oferta en el nivel de audiencia o de sesión y pone esos datos a su disposición en los informes de [!DNL Target]

[!DNL Target] puede hacer un seguimiento de los datos siguientes:

* Agente de usuario
* Dirección IP
* Ubicación geográfica
* Segmento asociado con el ID del visitante en [!DNL Target] (sujeto a aprobación legal)
* Datos de Datamart [!DNL Campaign]

Existen varias limitaciones:

* Como solo se puede usar una imagen, el contenido no se puede personalizar.
* El seguimiento no está consolidado en [!DNL Adobe Campaign].
* No se puede unificar la experiencia de usuario.

Utilice [!DNL Target] y [!DNL Campaign] para configurar diferentes partes de la integración:

    * El cuadro sin procesar y la experiencia en [!DNL Target]
    
     >[!NOTE]
     > 
     > Al utilizar un rawbox y  [!DNL Target], see the important security notice under [Create allowlists that specify hosts that are authorized to send mbox calls to Target] (/help/administrating-target/hosts.md#lista de permitidos).
    
    * La entrega en [!DNL Campaign]

## Antes de empezar {#section_FF19BF1BCA064260930BF6C141313B0E}

Antes de utilizar [!DNL Adobe Campaign] para configurar las ofertas de correo electrónico de destino, configure lo siguiente en [!DNL Target]:

* Dos o más ofertas de redireccionamiento [!DNL Target]

   Consulte [Crear oferta de redireccionamiento](/help/c-experiences/c-manage-content/offer-redirect.md).

* Una actividad [!DNL Target] con una experiencia para cada oferta y la [métrica de éxito](/help/c-activities/r-success-metrics/success-metrics.md) deseada.

   Consulte [Redireccionar a una dirección URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md).

Inicie la actividad en [!DNL Target] antes de configurar la parte [!DNL Campaign] de la integración.

## Incluir una oferta [!DNL Target] en un [!DNL Adobe Campaign] correo electrónico {#section_B201BBE27A704E18AF0D553F35695837}

1. Cree un correo electrónico en [!DNL Adobe Campaign].
1. En las propiedades del correo electrónico, haga clic en **[!UICONTROL Incluir]** > **[!UICONTROL Imagen dinámica proporcionada por Adobe Target]**.
1. Seleccione la imagen predeterminada entre los recursos compartidos.
1. Especifique la ubicación (rawbox).
1. Agregue el resto de los parámetros de toma de decisiones, como puede ser el sexo del destinatario.
1. Seleccione por lo menos un destinatario para cada oferta (en este caso, un hombre y una mujer) y previsualice el correo electrónico.
1. En [!DNL Campaign], defina el servidor perimetral [!DNL Target] que está utilizando para controlar la actividad y el nombre del inquilino.
1. Especifique la cuenta externa utilizada para [!DNL Adobe Experience Cloud] para poder acceder a los recursos en [!DNL Experience Cloud].

Para obtener más información, consulte la documentación [!DNL Adobe Campaign] .

## Vídeo: Integrar [!DNL Target] con [!DNL Campaign]

>[!VIDEO](https://video.tv.adobe.com/v/35149)
