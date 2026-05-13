---
keywords: Segmentación;filtro de audiencia;audiencias;filtro
description: Aprenda a utilizar los filtros de audiencia en  [!DNL Adobe Target]  para ver los datos de los visitantes que comparten características.
title: ¿Puedo usar filtros de audiencia para informes?
feature: Audiences
exl-id: af8dae97-4b10-4edb-a0e6-0d8daf2f0d22
TQID: https://experienceleague.adobe.com/7h16ay64Y1IVu2CbkEJny-rnGms80q8X7G6gOM1P900
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eebid: f69bc5f1-ebdb-4306-a281-f2e77daf734c
subfeature_v2: id: b6f5758b-84f7-4943-8b05-1297a046943cid: e73b329c-f712-4a22-abe7-bfbf3be6d0f9id: ed58f4a1-16eb-4c8c-b505-be9da766a9ecid: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 477
ht-degree: 59%

---

# Filtros de público para la creación de informes

Los filtros de audiencia (o audiencias) de [!DNL Adobe Target] son grupos de visitantes que comparten una característica o un conjunto de características específicos.

Utilice los filtros de audiencia para especificar las audiencias utilizadas en los informes. Puede seleccionar una audiencia y comparar su rendimiento con el tráfico global. Tal vez quiera saber si los ganadores de las múltiples fuentes de tráfico eran diferentes cuando se comparan con el tráfico general. Los filtros de audiencia le ayudan a descubrir audiencias que deberían estar potencialmente dirigidas a contenido diferente. En muchos casos, un ganador no se ajusta a todo el tráfico.

Por ejemplo, una audiencia puede ser la de los visitantes que llegan a la página desde un motor de búsqueda determinado. Otras audiencias pueden estar basadas en el sexo, la edad, la ubicación, el estado de registro, el historial de compras o en cualquier otro dato que se pueda recabar sobre los visitantes. Utilice filtros de audiencia para dividir el tráfico de los visitantes y comparar el rendimiento de las experiencias en cada segmento de tráfico.

Cuando vaya a utilizar filtros de audiencia en una actividad, tenga en cuenta las pautas siguientes:

* **Los visitantes pueden estar en varias audiencias.** Si hay dos audiencias configuradas (por ejemplo, &quot;nuevos visitantes&quot; y &quot;visitantes de Google&quot;) y una persona cumple ambos criterios, este visitante se cuenta y se rastrea en ambas audiencias. Por lo tanto, la suma de los visitantes de las audiencias no coincide con el número de visitantes de una actividad.
* **Configurar audiencias antes de iniciar la actividad.** Los datos de audiencia no se pueden recuperar de forma retroactiva. Si no configura los filtros de público antes de iniciar la actividad y luego decide usarlos cuando esta ya lleva un tiempo en marcha, no recabará los datos correspondientes al tiempo que ya ha pasado.
* **Empiece con dos o cuatro audiencias.** Céntrese en la información básica, como la fuente del tráfico.
* **Cambie el nombre de las audiencias según sea necesario.** Puede cambiar el nombre de una audiencia sin que los datos se vean afectados, de modo que el nombre de la audiencia represente mejor los resultados que se están recopilando aunque la actividad esté activa.
* **Introduzca valores precisos.** Los valores de los filtros de audiencia distinguen entre mayúsculas y minúsculas. Por ejemplo, si usa un público que filtra por ciudad, debe usar una condición “O” para que se incluyan variantes de escritura y mayúsculas/minúsculas, como “Vienna”, “Viena”, “viena”, “wien” y “Wien”.
* **Las audiencias creadas a partir de la lista [!UICONTROL Audiences] se pueden reutilizar.** Las audiencias creadas dentro de una actividad no se pueden reutilizar.

Las secciones siguientes contienen más información sobre la configuración y la creación de informes sobre audiencias:

| Tarea | Tema |
|--- |--- |
| Crear la actividad o prueba apropiadas. | [Actividades y pruebas](/help/main/c-intro/target-key-concepts.md) |
| Crear audiencias en caso necesario. | [Crear un público](/help/main/c-target/c-audiences/create-audience.md) |
| Combinar varios públicos en caso necesario. | [Combinación de varios públicos](/help/main/c-target/combining-multiple-audiences.md) |
| Aplicar públicos en la página Objetivos y configuración de la actividad. | Prueba A/B: [Objetivos y configuración](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)<br>Automated Personalization: [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<br>Segmentación de experiencias: [Objetivos y configuración](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md)<br>Prueba multivariable: [Objetivos y configuración](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md)<br>Recommendations: [Configuración de actividades de Recommendations](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md)<br>Configuración de actividades: [Configuración de actividades](/help/main/c-activities/activity-settings.md) |
| Ver informes con datos sobre los filtros de público. | [Configuración de informes](/help/main/c-reports/c-report-settings/report-settings.md) |
