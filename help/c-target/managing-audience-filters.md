---
keywords: Segmentación;filtro de audiencia;audiencias;filtro
description: Aprenda a usar filtros de audiencia en [!DNL Adobe Target] para ver datos de visitantes que comparten características.
title: ¿Puedo usar filtros de audiencia para los informes?
feature: Audiencias
exl-id: af8dae97-4b10-4edb-a0e6-0d8daf2f0d22
source-git-commit: 20a5201b5c05b1f083252ac73b3b4bbc91e97aaa
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 74%

---

# Filtros de audiencia para la creación de informes

Los filtros de audiencia (o audiencias) en [!DNL Adobe Target] son grupos de visitantes que comparten una característica o conjunto de características específicos.

Utilice los filtros de audiencia para especificar las audiencias utilizadas en los informes. Puede seleccionar una audiencia y comparar su rendimiento con el tráfico global. Tal vez quiera saber si los ganadores de las múltiples fuentes de tráfico eran diferentes cuando se comparan con el tráfico general. Los filtros de audiencia le ayudan a descubrir audiencias a las que se debería destinar potencialmente a distintos contenidos. En muchos casos, un ganador no se ajusta a todo el tráfico.

Por ejemplo, una audiencia puede ser la de los visitantes que llegan a la página desde un motor de búsqueda determinado. Otras audiencias pueden estar basadas en el sexo, la edad, la ubicación, el estado de registro, el historial de compras o en cualquier otro dato que se pueda recabar sobre los visitantes. Utilice filtros de audiencia para dividir el tráfico de los visitantes y comparar el rendimiento de las experiencias en cada segmento de tráfico.

Cuando vaya a utilizar filtros de audiencia en una actividad, tenga en cuenta las pautas siguientes:

* **Los visitantes pueden estar en varias audiencias.** Si hay dos audiencias configuradas (por ejemplo, &quot;nuevos visitantes&quot; y &quot;visitantes de Google&quot;) y una persona cumple ambos criterios, este visitante se cuenta y se rastrea en ambas audiencias. Por lo tanto, la suma de los visitantes de las audiencias no coincide con el número de visitantes de una actividad.
* **Configure las audiencias antes de iniciar la actividad.** Los datos de audiencia no se pueden recuperar de manera retroactiva. Si no configura los filtros de audiencia antes de iniciar la actividad y luego decide usarlos cuando esta ya lleva un tiempo en marcha, no recabará los datos correspondientes al tiempo que ya ha pasado.
* **Empiece con un número de audiencias de entre dos y cuatro.** Céntrese en la información básica, como la fuente del tráfico.
* **Cambie el nombre de las audiencias cuando sea necesario.** Puede cambiarles el nombre sin que ello afecte a los datos con el fin de que el nombre de la audiencia represente mejor los resultados que se están recopilando aunque la actividad esté activa.
* **Introduzca valores precisos.** Los valores de los filtros de audiencia distinguen entre mayúsculas y minúsculas. Por ejemplo, si usa un audiencia que filtra por ciudad, debe usar una condición “O” para que se incluyan variantes de escritura y mayúsculas/minúsculas, como “Vienna”, “Viena”, “viena”, “wien” y “Wien”.
* **[!UICONTROL Las audiencias creadas a partir de la lista de audiencias se pueden reutilizar.]** Las audiencias creadas dentro de una actividad no se pueden reutilizar.

Las secciones siguientes contienen más información sobre la configuración y la creación de informes sobre audiencias:

| Tarea | Tema |
|--- |--- |
| Crear la actividad o prueba apropiadas. | [Actividades y pruebas](/help/c-intro/target-key-concepts.md) |
| Crear audiencias en caso necesario. | [Crear una audiencia](/help/c-target/c-audiences/create-audience.md) |
| Combinar varias audiencias en caso necesario. | [Combinación de varias audiencias](/help/c-target/combining-multiple-audiences.md) |
| Aplicar audiencias en la página Objetivos y configuración de la actividad. | Prueba A/B: [Objetivos y configuración](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)<br>Automated Personalization:  [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md)<br>Segmentación de experiencias: [Objetivos y configuración](/help/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md)<br>Prueba multivariable:  [Objetivos y configuración](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md)<br>Recommendations: [Configuración de actividades de Recommendations](/help/c-recommendations/t-create-recs-activity/recs-activity-settings.md)<br>Configuración de actividades: [Configuración de actividades](/help/c-activities/activity-settings.md) |
| Ver informes con datos sobre los filtros de audiencia. | [Configuración de informes](/help/c-reports/c-report-settings/report-settings.md) |
