---
keywords: instancias en la nube;lista de sufijos públicos;sufijos públicos;cookie;cookie de origen;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
description: Explore los problemas (con soluciones) que los clientes afrontan al usar instancias basadas en la nube para probar el Adobe [!DNL Target] o con fines de prueba de concepto.
title: ¿Puedo usar [!DNL Target] con instancias basadas en la nube?
feature: at.js
role: Developer
exl-id: 220371a9-ba57-4e67-b82f-8fec6f9d2833
source-git-commit: 3c79b2ce70e456275ddf6774a35ae5c36f0ae99d
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 67%

---

# Uso de instancias basadas en la nube con Target

Información acerca de problemas que los clientes afrontan al usar instancias basadas en la nube para probar [!DNL Adobe Target].

Los clientes de [!DNL Target] utilizan en ocasiones instancias basadas en la nube para realizar pruebas o simplemente exponer conceptos. Estas instancias podrían incluir los siguientes dominios:

`azurewebsites.net`, `cloudapp.net`, `amazonaws.com`, `cloudfront.net`, `herokuapp.com` o `firebaseapp.com`.

Estos dominios, y muchos otros, son parte de la [Lista pública de sufijos](https://publicsuffix.org/list/public_suffix_list.dat).

**Problema:** los navegadores modernos no guardarán las cookies si utiliza estos dominios.

La biblioteca JavaScript [!DNL at.js] usa cookies para rastrear usuarios y asegurar que [!DNL Target] siempre ofrezca una experiencia coherente. Si la biblioteca JavaScript [!DNL Target] no puede guardar cookies, las solicitudes [!DNL Target] se desactivan.

**Solución:** Si piensa usar instancias basadas en la nube con dominios incluidos en la lista de sufijos públicos, es recomendable que se asegure de personalizar el ajuste `cookieDomain`. Para obtener más información, consulte [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).
