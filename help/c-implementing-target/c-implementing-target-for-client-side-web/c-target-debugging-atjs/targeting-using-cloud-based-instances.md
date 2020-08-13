---
keywords: cloud instances;public suffix list;public suffix;cookie;first-party cookie;1st-party cookie;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
description: Información acerca de problemas que los clientes afrontan al usar instancias basadas en la nube para probar Adobe Target.
title: Uso de instancias basadas en la nube con Target
feature: client-side
uuid: dcaba49e-7567-4970-bb9a-19377aff7d38
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 95%

---


# Uso de instancias basadas en la nube con Target{#use-cloud-based-instances-with-target}

Información acerca de problemas que los clientes afrontan al usar instancias basadas en la nube para probar [!DNL Adobe Target].

Los clientes de [!DNL Target] utilizan en ocasiones instancias basadas en la nube para realizar pruebas o simplemente exponer conceptos. Estas instancias podrían incluir los siguientes dominios:

`azurewebsites.net`, `cloudapp.net`, `amazonaws.com`, `cloudfront.net`, `herokuapp.com` o `firebaseapp.com`.

Estos dominios, y muchos otros, son parte de la [Lista pública de sufijos](https://publicsuffix.org/list/public_suffix_list.dat).

**Problema:** los navegadores modernos no guardarán las cookies si utiliza estos dominios.

Las bibliotecas JavaScript [!DNL at.js] y [!DNL mbox.js] utilizan cookies para realizar un seguimiento de los usuarios y asegurar que [!DNL Target] ofrezca siempre una experiencia coherente. Si las bibliotecas JavaScript de [!DNL Target] no pueden guardar las cookies, las solicitudes de [!DNL Target] se desactivan.

**Solución:** Si piensa usar instancias basadas en la nube con dominios incluidos en la lista de sufijos públicos, es recomendable que se asegure de personalizar el ajuste `cookieDomain`. Para obtener más información, consulte [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).
