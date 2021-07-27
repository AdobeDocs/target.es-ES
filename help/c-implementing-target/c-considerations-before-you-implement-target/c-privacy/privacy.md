---
keywords: privacidad;dirección ip;segmentación geográfica;exclusión;exclusión;exclusión;privacidad de datos;regulaciones gubernamentales;regulaciones;rgpd;ccpa
description: Descubra cómo Adobe [!DNL Target] cumple las leyes aplicables sobre privacidad de datos, incluida la recopilación y administración de direcciones IP, y las instrucciones de exclusión.
title: ¿Cómo gestiona  [!DNL Target] los problemas de privacidad?
feature: Privacidad y seguridad
role: Developer
exl-id: fb632923-fa36-4553-88a6-f27860472eb6
source-git-commit: 2403f63a6b993818fdc845d17f1a0dde72be664d
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 58%

---

# Privacidad

[!DNL Adobe Target] ha habilitado procesos y configuraciones que permiten utilizar en cumplimiento con las leyes aplicables sobre privacidad de datos.[!DNL Target]

## Recopilación de direcciones IP {#section_91BDB8105EBF4B85B7B8B8A14675AC85}

La dirección IP de un visitante del sitio web se transmite a un centro de procesamiento de datos (DPC) de Adobe. Dependiendo de la configuración de red del visitante, la dirección IP no representa necesariamente la dirección IP del equipo del visitante. Por ejemplo, la dirección IP puede ser una dirección IP externa de un cortafuegos de traducción de direcciones de red (NAT), un proxy HTTP o una puerta de enlace de Internet. Target no almacena ninguna dirección IP del usuario ni ningún tipo de información personal de identificación (PII). Target solo utiliza las direcciones IP durante la sesión (en memoria, nunca persistió).

## Sustitución del último octeto de direcciones IP {#section_AE84EB0D7CE04E93B279B77732ADD61E}

Adobe ha desarrollado una nueva configuración de “privacidad mediante diseño” que Adobe ClientCare puede habilitar para Adobe Target. Cuando se habilita esta configuración, el último octeto (la última parte) de la dirección IP se oculta inmediatamente cuando Adobe recopila la dirección IP. Esta anonimización se realiza antes de cualquier procesamiento de la dirección IP, incluso antes de una búsqueda geográfica opcional de la dirección IP.

Cuando se habilita esta función, la dirección IP se convierte en lo suficientemente anónima para que ya no pueda identificarse como información personal. Por ello, Adobe Target puede utilizarse en cumplimiento con las leyes de privacidad de datos en países en los que no se permite la recopilación de información personal. Es muy probable que la obtención de información por nivel de ciudad vea significativamente afectada por la confusión de la dirección IP. La obtención de información por nivel de región y país solo debería verse ligeramente afectada.

Las configuraciones disponibles son las siguientes:

* Sin confusión: Target no oculta ninguna parte de la dirección IP.
* Último octeto: Target oculta el último octeto de la dirección IP.
* IP completa: Target oculta toda la dirección IP.

Target recibe la dirección IP completa y la confunde (si se configura en Último octeto o IP completa) según se ha especificado. A continuación, Target guarda la dirección IP ofuscada en la memoria durante la sesión.

>[!NOTE]
>
>[Póngase en contacto con el ](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) servicio de atención al cliente de Adobe para determinar qué configuración está utilizando o para habilitar la función de confusión de IP.

## Segmentación geográfica {#section_BB69F96559BD44BDA4177537C4A5345A}

Si habilita la sustitución del último octeto de la dirección IP, los valores restantes de la dirección IP pueden analizarse mediante los informes de Adobe Target. Si el último octeto de la dirección IP no se ha disimulado, entonces se podrá analizar toda la dirección IP en Adobe Target. Puede usar la característica Segmentación geográfica para determinar la ubicación del visitante por zona geográfica. Los datos de segmentación geográfica se detallan solamente hasta el nivel de ciudad o de código postal, y no a nivel individual.

Si las direcciones IP se ocultan por completo, la segmentación geográfica y el direccionamiento geográfico no estarán disponibles.

## Vínculo de no participación {#section_E7A62B7B99C94B3A806CB262D16E27FC}

Puede añadir un vínculo de no participación a sus sitios para permitir que los visitantes renuncien a los recuentos y la publicación de contenido.

1. Añada el vínculo siguiente a su sitio:

   `<a href="https://clientcode.tt.omtrdc.net/optout"> Your Opt Out Language Here</a>`

1. (Condicional) Si utiliza CNAME, el vínculo debe contener el parámetro &quot;client=`clientcode`, por ejemplo:
https://my.cname.domain/optout?client=clientcode.

1. Reemplace `clientcode` por su código de cliente y añada el texto o la imagen que se vinculará a la dirección URL de exclusión.

Los visitantes que hagan clic en este vínculo no se incluirán en ninguna petición de mbox llamada desde sus sesiones de navegación hasta que eliminen sus cookies o hasta pasados dos años, lo que ocurra primero. Esto funciona estableciendo una cookie para el visitante llamada `disableClient` en el dominio `clientcode.tt.omtrdc.net`.

Aunque utilice una implementación de cookies de origen, la posibilidad de exclusión proporcionada se establece mediante una cookie de terceros. Si el cliente solo utiliza una cookie de origen, Target comprueba si se ha establecido una cookie de exclusión.

## Recopilación de datos sobre el uso de las funciones {#feature-usage}

Los datos del uso de las funcionalidades individuales se recopilan con fines internos [!DNL Adobe] para identificar si las características [!DNL Target] están funcionando según lo previsto o para identificar las características que se están infrautilizando. Se recopilan varias mediciones de latencia para ayudar a resolver los problemas de rendimiento. Los datos personales no se recopilan.

Puede excluirse de los datos de uso de informes estableciendo `telemetryEnabled` en el archivo de configuración en `false`.

## Reglamentos de protección de datos y privacidad

Consulte [Privacidad y regulaciones de protección de datos](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) para obtener información sobre el Reglamento General de Protección de Datos (RGPD) de la Unión Europea, la Ley de Privacidad del Consumidor de California (CCPA) y otros requisitos de privacidad internacionales, y cómo estas regulaciones afectan a su organización y a Adobe Target.
