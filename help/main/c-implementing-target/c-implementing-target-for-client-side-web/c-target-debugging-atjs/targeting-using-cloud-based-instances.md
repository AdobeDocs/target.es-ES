---
keywords: instancias en la nube;lista de sufijos públicos;sufijos públicos;cookie;cookie de origen;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
description: Explorar los problemas (con soluciones) a los que se enfrentan los clientes al usar instancias basadas en la nube para probar el Adobe [!DNL Target] o con fines de prueba de concepto.
title: ¿Puedo Usar [!DNL Target] con instancias basadas en la nube?
feature: at.js
role: Developer
exl-id: 220371a9-ba57-4e67-b82f-8fec6f9d2833
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 67%

---

# Uso de instancias basadas en la nube con Target

Información acerca de problemas que los clientes afrontan al usar instancias basadas en la nube para probar [!DNL Adobe Target].

Los clientes de [!DNL Target] utilizan en ocasiones instancias basadas en la nube para realizar pruebas o simplemente exponer conceptos. Estas instancias podrían incluir los siguientes dominios:

`azurewebsites.net`, `cloudapp.net`, `amazonaws.com`, `cloudfront.net`, `herokuapp.com` o `firebaseapp.com`.

Estos dominios, y muchos otros, son parte de la [Lista pública de sufijos](https://publicsuffix.org/list/public_suffix_list.dat).

**Problema:** los navegadores modernos no guardarán las cookies si utiliza estos dominios.

La variable [!DNL at.js] La biblioteca JavaScript usa cookies para rastrear usuarios y garantizar que [!DNL Target] siempre presenta una experiencia coherente. Si la variable [!DNL Target] La biblioteca JavaScript no puede guardar cookies, [!DNL Target] las solicitudes de están desactivadas.

**Solución:** Si piensa usar instancias basadas en la nube con dominios incluidos en la lista de sufijos públicos, es recomendable que se asegure de personalizar el ajuste `cookieDomain`. Para obtener más información, consulte [targetGlobalSettings()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/).
