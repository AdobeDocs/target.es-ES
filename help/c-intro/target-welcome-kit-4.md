---
keywords: kit de bienvenida;kit de bienvenida de target;intro;introducción;introducción a
description: Lea sugerencias de nuestro panel de expertos acerca del uso de Adobe  [!DNL Target]  en sus tareas de prueba y personalización.
title: ¿Dónde puedo encontrar sugerencias y trucos sobre el uso de Target?
feature: Información general
exl-id: 86437ad1-83ea-4670-b503-6c3c1fff0c16
translation-type: ht
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: ht
source-wordcount: '2898'
ht-degree: 100%

---

# Capítulo 4: Sugerencias sobre el uso de Target

Basándonos en el trabajo realizado con numerosos usuarios de [!DNL Target], hemos identificado maneras de sacar mayor partido a su solución [!DNL Target]. Las distintas sugerencias que se incluyen en este capítulo ofrecen un resumen de estos recursos. Pese a que es posible que no esté listo para usar todas estas ideas de inmediato, manténgase al tanto de esta lista. Cuanto más experiencia adquiera con la solución y cuanto más madure su programa, más útiles le resultarán estas sugerencias para realizar más tareas con [!DNL Target].

## Sugerencia 1: Intensifique la personalización ofreciendo datos adicionales en el perfil del visitante.

Puede personalizar experiencias con datos de [!DNL Target] de inmediato. Sin embargo, puede mejorar la personalización agregando datos propios. De este modo, puede enriquecer su perfil con datos históricos de [!DNL Adobe Analytics] y datos en tiempo real de [!DNL Adobe Audience Manager]. También puede usar Atributos de cliente, una función del servicio principal Personas de [!DNL Adobe Experience Cloud], que permite incorporar fácilmente datos de CRM, datos de socios de segundo nivel y datos comprados de terceros a [!DNL Target].

Por ejemplo, puede asociar datos de compra de su sistema de puntos de venta a un perfil del visitante. Para ello, basta con crear un archivo CSV con hasta 200 variables sin conexión y cargarlo directamente en [!DNL Adobe Experience Cloud] mediante una operación de carga de archivo, o bien puede utilizar el FTP para alojar el archivo y programar su actualización periódica. Cuando los Atributos del cliente se encuentren en [!DNL Adobe Experience Cloud], podrá asignarlos a soluciones de [!DNL Experience Cloud], como [!DNL Adobe Analytics] y [!DNL Target], donde estarán disponibles para tareas de análisis, pruebas y personalización.

Consulte [Atributos personalizados](https://experienceleague.adobe.com/docs/target/using/audiences/visitor-profiles/working-with-customer-attributes.html?lang=es) para obtener instrucciones paso a paso.

**Datos útiles**: Como [!DNL Target] es una plataforma abierta y agnóstica que funciona con diferentes tecnologías, puede agregar datos de sistemas CRM o comprados de muchas maneras diferentes. Esto significa que puede elegir el método que mejor funcione para su organización.

Consulte [Métodos para obtener los datos en Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md) para obtener más información.

## Sugerencia 2: Intensifique la personalización mediante la fusión de audiencias de [!DNL Target] con otras audiencias de Adobe Experience Cloud.

La fusión de audiencias que residen en diferentes soluciones de [!DNL Adobe Experience Cloud] puede ofrecerle una perspectiva mucho más amplia de sus clientes, así como mayor capacidad de personalización. Por ejemplo, aunque [!DNL Target] proporciona datos de audiencia en tiempo real, [!DNL Adobe Analytics] ofrece datos de audiencia históricos. La combinación de ambos datos puede ayudarle a identificar cuándo el comportamiento de un cliente es coherente y cuándo puede haber una oportunidad para actuar ante un nuevo comportamiento. Simplemente haga clic en el menú desplegable situado junto a &quot;Todos los visitantes&quot; cuando cree una actividad. A continuación, active las casillas de hasta veinte audiencias, haga clic en &quot;Combinar varias audiencias&quot; y en &quot;Guardar&quot;.

Consulte [Combinación de varias audiencias](/help/c-target/combining-multiple-audiences.md) para obtener instrucciones paso a paso.

**Datos útiles**: Las audiencias de [!DNL Adobe Audience Manager] están disponibles en [!DNL Target] automáticamente. Sin embargo, el uso compartido de audiencias de [!DNL Adobe Analytics] requiere un poco de configuración manual. Simplemente active la casilla &quot;Convertir esto en audiencia Experience Cloud&quot; durante el proceso de creación de audiencias en [!DNL Analytics]. A continuación, en [!DNL Target], haga clic en &quot;Importar audiencias de Experience Cloud&quot;.

## Sugerencia 3: Exporte datos de [!DNL Target] para usarlos con herramientas de terceros.

Con los tokens de respuesta, los administradores pueden obtener fácilmente datos de [!DNL Target] y usarlos en herramientas de terceros. Esto puede resultar útil cuando desea agregar los datos a los datos recopilados en una herramienta de encuesta. Por ejemplo, si un estudio muestra un segmento de población que obtuvo una puntuación de experiencia de &quot;9&quot; y otro que obtuvo una puntuación de experiencia de &quot;4&quot;, puede utilizar los datos para ver quién vio la experiencia A y quién la experiencia B. También puede utilizar tokens de respuesta para exportar datos de [!DNL Target] al almacén de datos interno. Simplemente haga clic en &quot;Administración&quot; y, a continuación, active el conmutador situado junto al token de respuesta deseado en la posición ON. A continuación, cree una actividad. Los datos están listos para transferirlos al proveedor de terceros. Puede verificar que [!DNL Target] está exportando los datos con las herramientas de depuración.

Consulte [Tokens de respuesta](/help/administrating-target/response-tokens.md) para obtener instrucciones paso a paso.

**Sugerencia útil**: Para que un administrador pueda activar un token de respuesta asociado a un tercero, un desarrollador debe configurar una asociación con dicha compañía de terceros.

Consulte [Tokens de respuesta](/help/administrating-target/response-tokens.md) para obtener instrucciones paso a paso.

**Haga esto primero**: asegúrese de que está utilizando la versión 1.1 o posterior de at.js. Si utiliza una versión anterior, verá los tokens de respuesta, pero at.js no podrá utilizarlos.

## Sugerencia 4: Cree audiencias a partir de estas variables clave para aumentar el valor de la actividad.

Cuando cree audiencias para dirigir o probar promociones y ofertas, tenga primero en cuenta las variables siguientes:

* Comportamiento. Patrones de visita al sitio y patrones de compra.
* Referrer. Sitios de referencia y campañas.
* Temporal. Horas del día, días de la semana y factores de temporada.
* Sin conexión. Patrones de visita y compra en tiendas físicas.
* Entorno. País de origen, sistema operativo, tipo de navegador.

## Sugerencia 5: Proporcione a los usuarios el nivel de acceso que necesitan para realizar su trabajo.

Facilite el trabajo con los datos de su organización a la vez que mantiene la seguridad. [!DNL Target Premium] permite a los administradores controlar el nivel de acceso que se concede a los distintos equipos internos y externos.

Consulte [Permisos de usuarios empresariales](/help/administrating-target/c-user-management/property-channel/property-channel.md) para obtener más información.

**Sugerencia útil**: Cuando agregue usuarios, si el nombre de un miembro del equipo no se ha agregado previamente a su organización (como puede ser el caso de un empleado de una agencia de terceros), al introducir su dirección de correo electrónico y contraseña, se enviará una invitación por correo electrónico para unirse al espacio de trabajo de un equipo.

¿Es usuario de Target Standard? Puede [asignar tres niveles de acceso](/help/administrating-target/c-user-management/c-user-management/user-management.md) a los usuarios con funciones de solo lectura, editor y aprobador.

## Sugerencia 6: Descubra el rendimiento de una oferta en un recorrido de cliente probándola en todas las páginas del recorrido.

Puede ver el rendimiento de una oferta, como, por ejemplo, el envío gratuito, durante el recorrido del cliente en varias páginas del sitio web.

Consulte [Actividad multipágina](/help/c-experiences/c-visual-experience-composer/multipage-activity.md) para obtener instrucciones paso a paso.

**Sugerencia útil**: Si cambia la dirección URL después de especificar un intervalo de páginas, la experiencia se restablecerá. Esto significa que las variaciones especificadas dejarán de mostrarse. Si necesita cambiar la dirección URL, recuerde que debe redefinir la experiencia.

## Sugerencia 7: Pruebe una oferta con distintas audiencias para descubrir si las audiencias tienen preferencias diferentes.

Con las versiones de Experience, puede ejecutar una prueba con variaciones para tantas audiencias como desee. Por ejemplo, puede crear una publicidad tipo titular que ofrezca envío gratuito (con imágenes y variaciones de moneda para clientes de EE.UU., Reino Unido y EE.AA.UU.) sin tener que ejecutar pruebas para tres audiencias diferentes.

Consulte [Audiencias de experiencias múltiples en pruebas A/B](/help/c-activities/t-test-ab/t-test-create-ab/target-experience-to-multiple-audiences.md) y [Versiones de Experience en Adobe Target](https://helpx.adobe.com/es/target/how-to/experience-versions.html?playlist=/ccx/v1/collection/product/target/seg-%20ment/business-practitioners/explevel/beginner-adls/applaunch/how-to-2/collection.ccx.js?ref=helpx.adobe.com) para obtener instrucciones paso a paso.

## Sugerencia 8: Ahorre tiempo con la replicación de experiencias de actividad en páginas similares.

Cree una variación en una página web, como, por ejemplo, un nuevo color de botón, y aplíquela automáticamente a todas las páginas que compartan la misma plantilla. Puede especificar páginas o aplicar las variaciones a todas las páginas similares del sitio web.

Consulte [Incluir la misma experiencia en páginas similares](/help/c-experiences/c-visual-experience-composer/temtest.md) para obtener instrucciones paso a paso.

## Sugerencia 9: Reduzca el desorden en la biblioteca de audiencias creando audiencias únicas.

Si va a direccionar un segmento que sabe que no volverá a direccionar (por ejemplo, clientes afectados por un evento meteorológico inesperado), la creación de una audiencia de un solo uso puede ayudarle a realizar el trabajo sin necesidad de agregar desorden a la biblioteca de audiencias. Esto facilita la búsqueda de audiencias que utiliza una y otra vez.

Consulte [Creación de audiencias solo de actividad](/help/c-target/creating-activity-only-audience.md) para obtener instrucciones paso a paso.

**Capacidad muy solicitada**: Nuestros clientes nos pidieron que fuese posible evitar que las audiencias de un solo uso se guardaran automáticamente en la Biblioteca de audiencias. Ahora, ya no es necesario eliminar audiencias manualmente para mantener las bibliotecas organizadas.

## Sugerencia 10: Ejecute pruebas sencillas más rápido al no someterlas al proceso de control de calidad estándar.

No hay nada peor que tener una actividad lista y tener que esperar semanas para que complete el proceso estándar de control de calidad. Puede realizar el control de calidad de la mayoría de las actividades simplemente pasando unos cuantos vínculos de control de calidad a compañeros para probarlos en varios navegadores. Es probable que quiera realizar más pruebas de control de calidad en actividades que cambian drásticamente el funcionamiento del sitio; sin embargo, en realidad debería tener menos actividades de ese tipo y muchas más actividades básicas. Agregar mejores controles de derechos para que menos personas puedan publicar cosas también agrega límites significativos y le permite hacer lo que debe hacer, pero sin sacrificar velocidad ni eficacia. Otra opción es contar con un recurso de TI designado que supervise cuando corresponda el proceso de control de calidad.

Consulte [Control de calidad de actividades](/help/c-activities/c-activity-qa/activity-qa.md) para obtener instrucciones paso a paso.

## Sugerencia 11: Ejecute pruebas en páginas de tráfico intenso para que alcancen la relevancia estadística con mayor rapidez.

Muchos especialistas en marketing inician programas de optimización de segmentación de audiencia y direccionamiento sin comprobar si los niveles de tráfico y las audiencias representadas proporcionarán resultados significativos dentro del marco temporal de prueba para sus objetivos de optimización y conversión. Para evitar este error común, responda antes a las preguntas siguientes:

* ¿Cuántos visitantes únicos diarios tiene la página?
* ¿Cuál es la tasa de conversión de la página?
* ¿Cuánto tiempo espera que se ejecute la prueba antes de que pueda darla por completa con seguridad?

**Sugerencia útil**: Utilice la [calculadora de tamaño de muestra](https://docs.adobe.com/content/target-microsite/testcalculator.html) de Target para determinar el tamaño de muestra necesario para que la prueba se realice correctamente.

## Sugerencia 12: Diseñe pruebas más sencillas para asegurarse de que puede crearlas e implementarlas.

Tras considerar todos los aspectos relacionados con el diseño de pruebas, el plan puede llegar a ser muy complejo. Determine si la prueba es demasiado ambiciosa en función de dónde se encuentre su negocio con las pruebas y de la capacidad de su grupo para diseñar, codificar, ejecutar y analizar los resultados. En caso de que sí lo sea, deberá reducir su alcance y su complejidad. Es mejor comenzar con una prueba pequeña que no realizar ninguna prueba. Tenga en cuenta que no logrará un alza impactante si no inicia nunca la prueba. Es importante encontrar el equilibrio entre las aspiraciones del equipo y la realidad de cuáles son sus recursos y sus capacidades.

## Sugerencia 13: Divida las pruebas complejas en actividades de prueba más pequeñas para que sean alcanzables.

En lugar de desarrollar una prueba de gran tamaño con múltiples variables y desarrollo complejo, desarrolle una serie de pruebas menos complejas y más pequeñas con mínimas variables. Esto permite le permitirá obtener una perspectiva más detallada del rendimiento de las pruebas en función de variables específicas. También reduce los posibles problemas técnicos que conlleva el desarrollo de proyectos de mayor envergadura.

![Ilustración de la división de pruebas complejas](/help/c-intro/assets/break-complex-tasks.png)

## Sugerencia 14: Maximice el impacto de la prueba realizando pruebas más cerca del final del canal de conversión.

Realizar las pruebas lo más cerca posible de la página en la que los visitantes hagan clic para completar su compra, enviar su solicitud o completar la conversión tiende a ofrecer los resultados más impactantes. Los visitantes que llegan al final del canal están más cualificados, han invertido más tiempo y están preparados para realizar compras, por lo que la prueba de perspectivas sobre sus preferencias y sus acciones puede ayudarle a realizar cambios rentables. Dado que las páginas en la ruta de compra son críticas para las tasas de conversión, las pruebas que se realicen en esas páginas deben socializarse con las partes interesadas clave antes de su implementación.

![Ilustración sobre el canal de conversión](/help/c-intro/assets/conversion-funnel.png)

## Sugerencia 15: Actualice constantemente las pruebas para realizar mejoras de manera iterativa.

Si su hipótesis resultó no ser cierta, piense en formas de mejorar la prueba. Recuerde que aunque ninguna de las experiencias que probó funcionara mejor, su actividad no ha sido una pérdida de tiempo. El hecho de que una prueba se realice correctamente no siempre significa un aumento de ingresos o conversiones. Si la prueba realmente confirmó su hipótesis, entonces estará en camino de desarrollar una teoría general. Pero incluso cuando tenga un claro resultado ganador, no se detenga allí. Con frecuencia, los especialistas en marketing cometen el error de realizar la prueba una vez y confiar en los resultados obtenidos sin comprender realmente qué factor fue el que llevó al éxito. En cambio, planee repetir esos resultados para determinar las razones por las que la opción favorita destacaba entre las demás. Esto le proporcionará perspectivas más detalladas que podrá usar en futuras campañas.

## Sugerencia 16: Compare pruebas y actividades de personalización para obtener ideas y mejorar la segmentación.

La comparación del rendimiento de conversión de distintas audiencias de distintas pruebas en diferentes ubicaciones puede ayudarle a enfocar y refinar la estrategia de optimización de una empresa. Utilice comparaciones de prueba para identificar qué audiencias merecen más la pena probar, cuáles deben recibir experiencias segmentadas y qué tipos de experiencias tienen más probabilidades de generar respuestas.

Por ejemplo, un cliente de servicios financieros dirigió una campaña promocional para una tarjeta de crédito que incluía incentivos de eventos deportivos profesionales. Mediante pruebas multivariadas factoriales parciales de sus páginas de aterrizaje, el cliente pudo encontrar el equilibrio óptimo en el envío de mensajes sobre los beneficios de las tarjetas de crédito con incentivos deportivos para dirigirse a distintas audiencias de su base de clientes. Este método permitió a la compañía aprovechar y maximizar la conversión en un periodo clave durante un importante evento deportivo.

## Sugerencia 17: Haga que las pruebas sean útiles al iniciarlas únicamente si sabe que podrá tomar acciones en base a los datos.

No tiene sentido realizar una prueba si no tiene claro qué acciones podrá realizar con los datos. Esto incluye saber cuál es la métrica de éxito clave, qué debe suceder para impulsar a un ganador, cómo seguirá los resultados de las pruebas y qué hará con la información de la audiencia. Para que la prueba se realice de manera rápida y con éxito, es vital que todos los grupos involucrados en la prueba (desarrolladores, creativos, especialistas en pruebas y otros) conozcan su papel antes de comenzar.

## Sugerencia 18: Antes de iniciar una prueba, asegúrese de que la empresa impulse al ganador.

Las organizaciones de optimización de éxito creen en el concepto de las pruebas y saben que sus opiniones profesionales sobre cuál será la experiencia ganadora de la prueba no siempre son ciertas. Estas organizaciones determinan la experiencia ganadora en función de los datos y suelen publicar la experiencia tras la obtención de los resultados, aunque no esté alineada con las expectativas o parezca ilógica.

Por ejemplo, un cliente de servicios de atención médica de Adobe demostró recientemente el valor que tienen las pruebas mostrando cómo un banner que el equipo había considerado como un éxito asegurado afectó negativamente a la conversión. Si su organización aún no ha adoptado completamente los procesos de pruebas, es preferible realizar primero pruebas de ámbito más simple y más pequeñas para que los cambios de los resultados de las pruebas se puedan implementar de manera gradual.

## Sugerencia 19: Comunique a todos que ha iniciado una prueba para evitar problemas cuando cambie el sitio.

Una de las ventajas de configurar las actividades para que utilicen parámetros de control de calidad es que puede compartir esos vínculos con todos los miembros de su equipo. De este modo, se asegurará de que más personas estén al tanto de la actividad y de que no supongan que el sitio no funciona correctamente cuando se topen con una variante de prueba.

Una vez finalizadas las pruebas, la comunicación de los lanzamientos de las campañas, los resultados de las pruebas y, en especial, las lecciones aprendidas, le ayudará a sensibilizar a los demás de los resultados de las pruebas y a despertar su interés. Compartir los resultados con todos los miembros de la organización también evita volver a probar hipótesis. Asimismo, muestra a los demás qué es lo que funciona y les ayuda a cuestionar sus propias ideas sobre lo que funciona a partir de lo que haya averiguado. Es aconsejable preparar una plantilla para utilizarla cada vez que desee compartir conclusiones y aprendizajes clave.
A continuación, considere la posibilidad de crear un libro que se pueda compartir o una presentación de Microsoft PowerPoint que capture todo este conocimiento de manera incremental.

## Sugerencia 20: Aproveche la funcionalidad móvil para crear actividades móviles más innovadoras.

Las experiencias de los usuarios de dispositivos de tableta y smartphones deben centrarse en los controles táctiles como elemento de interacción principal del visitante en lugar de los clics de ratón o los controles de teclado. Aproveche los controles de las pantallas de dispositivos móviles, como, por ejemplo, deslizamientos de dedo, toques, arrastres, pellizcos de pantalla y zoom. Utilice botones grandes y sencillos para designar las interacciones y la navegación, como, por ejemplo, un carrito de la compra o un botón de reproducción de vídeo de gran tamaño. Si diseña contenido para la distribución minorista a través de dispositivos móviles, incluya una visualización de producto enriquecida que esté optimizada para estos dispositivos. Busque siempre oportunidades para cambiar el enfoque de la experiencia del usuario a visores integrados, de gran tamaño, con características interactivas de zoom y vista panorámica o de 360 grados, así como a funciones de vídeo mejoradas.

## Sugerencia 21: Ayude a los visitantes móviles a encontrar lo que desean optimizando la búsqueda móvil.

Los usuarios de móviles tienen una intención alta. La mayoría de ellos utilizan las funciones de búsqueda antes de hacer cualquier otra cosa en los sitios de comercio electrónico, lo que hace que la optimización de la búsqueda en sitios móviles sea crucial. Para mejorar la optimización de los motores de búsqueda (SEO) para móviles, utilice indicaciones de navegación explícitas que faciliten la exploración del contenido. Además, implemente funciones de sugerencias y correcciones automáticas en los cuadros de búsqueda para resolver la dificultad que plantea la escritura los en dispositivos móviles. Ofrezca resultados de búsqueda relevantes y convincentes optimizados según el tamaño y la ubicación de la pantalla.

## Sugerencia 22: Llegue mejor a las audiencias móviles gracias al direccionamiento según la hora del día para las campañas móviles de marketing en buscadores.

Sepa cómo y cuándo llegar a su audiencia, y cómo administrar mejor su gasto en publicidad diaria dividiendo sus campañas móviles en distintos segmentos a lo largo del día.

Muchos especialistas en marketing cometen el error de no asignar suficiente presupuesto para capturar esa cuota de información en las horas de mayor utilización de dispositivos particulares, dejando escapar cuantiosos ingresos y posibles clientes.

Por ejemplo, el uso de dispositivos de tableta suele aumentar en el horario nocturno y hay muchos usuarios que navegan mientras ven la televisión. Por el contrario, los usuarios de smartphones suelen acceder al contenido en sus desplazamientos. Los tiempos de picos de conversión también varían según el sector, por lo que es importante comprender cuándo es más probable que actúen sus clientes específicos.

## Recuerde

Considere las siguientes ideas antes de pasar al siguiente capítulo: &quot;Inspiración para pruebas y actividades de personalización&quot;.

### Cuando cree las pruebas, no las decore, actúe de manera intencionada.

* Controle el flujo con rutas oculares intencionadas centradas en los puntos de conversión.
* Asegúrese de usar sus bienes en su propio beneficio.
* Aproveche el enfoque de la imagen para asegurarse de que las imágenes no sean decorativas, sino que funcionen para usted.
* Reduzca el desorden, la fricción y la confusión con contenido sencillo.
* Asegúrese de que dispone de llamadas a la acción efectivas cuando necesite que el usuario tome medidas.
* Agregue credibilidad utilizando contenido generado por el usuario siempre que sea posible.

### Simplifique su sitio web.

* No &quot;obligue&quot; a los clientes a leer. No lo harán.
* Facilite la lectura rápida.
* Utilice bloques de contenido con viñetas.
* Asegúrese de que su contenido siga un proceso lógico claro y ordenado.

### Utilice llamadas a la acción (CTA) efectivas.

* Póngase en el lugar del cliente.
* Utilice un lenguaje orientado a la acción.
* Tenga en cuenta la motivación de la conversión.
* Aborde el resultado de la conversión.
* Asegúrese de que las CTA tengan visibilidad.
