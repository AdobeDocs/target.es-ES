---
keywords: implementar;implementación;configuración;configuración;atributos del cliente
description: Obtenga datos en Target mediante atributos del cliente.
title: ¿Cómo puedo obtener datos en Target mediante Atributos del cliente?
feature: Implementation
role: Developer
exl-id: b6c4a286-7994-492d-bde9-346af7aa314f
translation-type: tm+mt
source-git-commit: 20daf4510e754d77cd16be64770105932178fec5
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 56%

---

# Atributos del cliente

Los atributos del cliente le permiten cargar datos de perfil del visitante a través del FTP a [!DNL Adobe Experience Cloud]. Una vez cargados, utilice los datos en [!DNL Adobe Analytics] y [!DNL Adobe Target].

Los clientes de Target Standard pueden aplicar cinco atributos; los clientes de Target Premium pueden aplicar 200 atributos.

## Formato

Se carga un archivo .csv con Experience Cloud IDs (ECID) y pares de atributos nombre-valor a través de FTP o manualmente en la IU de Experience Cloud.

## Casos de uso de ejemplo

Su CRM u otros sistemas internos almacenan información valiosa que le interesa compartir con Adobe Experience Cloud, incluidos Target y Analytics.

## Ventajas del método

Al cargar datos del cliente se crea una entrada de perfil para cada visitante en Target, aunque Target todavía no haya visto el visitante.

Los mismos datos están disponibles automáticamente en Target y Analytics.

FTP puede ser un método de implementación más sencillo que la API.

## Advertencias

Los clientes de Target Standard pueden aplicar cinco atributos; los clientes de Target Premium pueden aplicar 200 atributos

Los valores solo se pueden actualizar a través de Atributos del cliente, no en la página.

Se requiere la implementación del Experience Cloud ID (ECID).

## Ejemplos de código

Puede encontrar más información en [Crear un origen de atributos del cliente y cargar el archivo de datos](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).

### Enlaces a información relevante

[Creación de un origen de atributos del cliente y carga del archivo de datos](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).
