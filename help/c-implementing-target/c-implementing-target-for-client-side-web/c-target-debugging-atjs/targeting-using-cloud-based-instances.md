---
keywords: instancias en la nube;lista de sufijos públicos;sufijos públicos;cookie;cookie de origen;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
description: Información acerca de problemas que los clientes afrontan al usar instancias basadas en la nube para probar Adobe Target.
title: Usar instancias basadas en la nube
feature: at.js
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 94%

---


# Uso de instancias basadas en la nube con Target{#use-cloud-based-instances-with-target}

Información acerca de problemas que los clientes afrontan al usar instancias basadas en la nube para probar [!DNL Adobe Target].

Los clientes de [!DNL Target] utilizan en ocasiones instancias basadas en la nube para realizar pruebas o simplemente exponer conceptos. Estas instancias podrían incluir los siguientes dominios:

`azurewebsites.net`, `cloudapp.net`, `amazonaws.com`, `cloudfront.net`, `herokuapp.com` o `firebaseapp.com`.

Estos dominios, y muchos otros, son parte de la [Lista pública de sufijos](https://publicsuffix.org/list/public_suffix_list.dat).

**Problema:** los navegadores modernos no guardarán las cookies si utiliza estos dominios.

Las bibliotecas JavaScript [!DNL at.js] y [!DNL mbox.js] utilizan cookies para realizar un seguimiento de los usuarios y asegurar que [!DNL Target] ofrezca siempre una experiencia coherente. Si las bibliotecas JavaScript de [!DNL Target] no pueden guardar las cookies, las solicitudes de [!DNL Target] se desactivan.

**Solución:** Si piensa usar instancias basadas en la nube con dominios incluidos en la lista de sufijos públicos, es recomendable que se asegure de personalizar el ajuste `cookieDomain`. Para obtener más información, consulte [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).
