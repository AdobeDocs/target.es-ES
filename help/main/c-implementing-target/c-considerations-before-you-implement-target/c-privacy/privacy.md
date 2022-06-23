---
keywords: privacidad;dirección ip;segmentación geográfica;exclusión;exclusión;exclusión;privacidad de datos;regulaciones gubernamentales;regulaciones;rgpd;ccpa
description: Descubra cómo Adobe  [!DNL Target]  cumple con las leyes de privacidad de datos aplicables, incluida la recopilación y administración de direcciones IP, así como las instrucciones de exclusión.
title: ¿Cómo soluciona  [!DNL Target]  los problemas de privacidad?
feature: Privacy & Security
role: Developer
exl-id: fb632923-fa36-4553-88a6-f27860472eb6
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '752'
ht-degree: 98%

---

# Privacidad

[!DNL Adobe Target] ha habilitado procesos y configuraciones que permiten [!DNL Target] utilizar en cumplimiento con las leyes aplicables sobre privacidad de datos.

## Recopilación de datos sobre el uso de las funciones

Los datos de uso de funciones individuales se recopilan para los objetivos internos de [!DNL Adobe] para averiguar si las funciones de [!DNL Target] están funcionando según lo previsto o para identificar las características que se están infrautilizando. Se recopilan varias mediciones de latencia para ayudar a resolver los problemas de rendimiento. Los datos personales no se recopilan.

Puede excluirse de los datos de uso de informes en nuestros SDK configurando `telemetryEnabled` como false en las opciones de inicialización del cliente. Para obtener más información, consulte [telemetryEnabled en targetGlobalSettings](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/).

## Recopilación de direcciones IP {#section_91BDB8105EBF4B85B7B8B8A14675AC85}

La dirección IP de un visitante del sitio web se transmite a un centro de procesamiento de datos (DPC) de Adobe. Dependiendo de la configuración de red del visitante, la dirección IP no representa necesariamente la dirección IP del equipo del visitante. Por ejemplo, la dirección IP puede ser una dirección IP externa de un cortafuegos de traducción de direcciones de red (NAT), un proxy HTTP o una puerta de enlace de Internet. Target no almacena ninguna dirección IP del usuario ni ningún tipo de información personal de identificación (PII). Target utiliza las direcciones IP solo mientras dura la sesión (y lo hace en memoria, nunca de forma persistente).

## Sustitución del último octeto de direcciones IP {#section_AE84EB0D7CE04E93B279B77732ADD61E}

Adobe ha desarrollado una nueva configuración de “privacidad mediante diseño” que Adobe Client Care puede habilitar para Adobe Target. Cuando se habilita esta configuración, el último octeto (la última parte) de la dirección IP se oculta inmediatamente cuando Adobe recopila la dirección IP. Esta anonimización se realiza antes de cualquier procesamiento de la dirección IP, incluso antes de una consulta geográfica opcional de la dirección IP.

Cuando se habilita esta función, la dirección IP se convierte en lo suficientemente anónima para que ya no pueda identificarse como información personal. Por ello, Adobe Target puede utilizarse en cumplimiento con las leyes de privacidad de datos en países en los que no se permite la recopilación de información personal. Es muy probable que la obtención de información por nivel de ciudad vea significativamente afectada por la confusión de la dirección IP. La obtención de información por nivel de región y país solo debería verse ligeramente afectada.

Las configuraciones disponibles son las siguientes:

* Sin ocultación: Target no oculta ninguna parte de la dirección IP.
* Último octeto: Target oculta el último octeto de la dirección IP.
* IP completa: Target oculta toda la dirección IP.

Target recibe la dirección IP completa y la oculta (si se configura en Último octeto o IP completa) según se ha especificado. A continuación, Target guarda la dirección IP ocultada en la memoria durante la sesión.

>[!NOTE]
>
>[Póngase en contacto con Atención al cliente de Adobe](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para determinar qué configuración está utilizando o para habilitar la función de ocultación de IP.

## Segmentación geográfica {#section_BB69F96559BD44BDA4177537C4A5345A}

Si habilita la sustitución del último octeto de la dirección IP, los valores restantes de la dirección IP pueden analizarse mediante los informes de Adobe Target. Si el último octeto de la dirección IP no se ha disimulado, entonces se podrá analizar toda la dirección IP en Adobe Target. Puede usar la característica Segmentación geográfica para determinar la ubicación del visitante por zona geográfica. Los datos de segmentación geográfica se detallan solamente hasta el nivel de ciudad o de código postal, y no a nivel individual.

Si las direcciones IP se ocultan por completo, la segmentación geográfica y el direccionamiento geográfico no estarán disponibles.

## Vínculo de no participación {#section_E7A62B7B99C94B3A806CB262D16E27FC}

Puede añadir un vínculo de no participación a sus sitios para permitir que los visitantes renuncien a los recuentos y la publicación de contenido.

1. Añada el vínculo siguiente a su sitio:

   `<a href="https://clientcode.tt.omtrdc.net/optout"> Your Opt Out Language Here</a>`

1. (Condicional) Si utiliza CNAME, el vínculo debe contener el parámetro “client=`clientcode`”, por ejemplo: https://my.cname.domain/optout?client=clientcode.

1. Reemplace `clientcode` por su código de cliente de y añada el texto o la imagen que se vinculará a la dirección URL de no participación.

Los visitantes que hagan clic en este vínculo no se incluirán en ninguna petición de mbox llamada desde sus sesiones de navegación hasta que eliminen sus cookies o hasta pasados dos años, lo que ocurra primero. Esto funciona estableciendo una cookie para el visitante llamada `disableClient` en el dominio `clientcode.tt.omtrdc.net`.

Aunque utilice una implementación de cookies de origen, la posibilidad de exclusión proporcionada se establece mediante una cookie de terceros. Si el cliente solo utiliza una cookie de origen, Target comprueba si se ha establecido una cookie de exclusión.

## Reglamentos de protección de datos y privacidad

Consulte [Reglamentos de protección de datos y privacidad](https://developer.adobe.com/target/before-implement/privacy/cmp-privacy-and-general-data-protection-regulation/) para obtener Información sobre el Reglamento General de Protección de Datos (RGPD) de la Unión Europea, la Ley de privacidad del consumidor de California (CCPA) y otros requisitos de privacidad internacionales, y cómo estos reglamentos afectan a su organización y a Adobe Target.
