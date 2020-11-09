---
keywords: welcome kit;target welcome kit;intro;introduction;getting started
description: Kit de bienvenida de Adobe Target - Capítulo 4 - Sugerencias para el uso del Destinatario
title: Kit de bienvenida de Adobe Target - Capítulo 4 - Sugerencias para el uso del Destinatario
feature: intro
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '2880'
ht-degree: 0%

---


# Capítulo 4: Sugerencias para el uso de Destinatario

En base a nuestro trabajo con muchos [!DNL Target] usuarios, hemos observado maneras de obtener más valor de su [!DNL Target] solución. Hemos resumido estas sugerencias en las muchas sugerencias que hemos incluido en este capítulo. Aunque quizá no estés listo para usar todas estas ideas de inmediato, sigue con esta lista. Cuanta más experiencia tenga con la solución y cuanto más madure su programa, más podrá ver cómo estos consejos le ayudarán a conseguir más con [!DNL Target].

## Sugerencia 1: Profundizar la personalización aumentando el perfil de visitante con datos adicionales.

Puede personalizar las experiencias con [!DNL Target] los datos de inmediato. Pero personalice más profundamente agregando sus propios datos a la combinación. Puede aumentar el perfil con datos históricos [!DNL Adobe Analytics] y datos en tiempo real [!DNL Adobe Audience Manager]. También puede utilizar Atributos del cliente, una función del servicio principal Personas de [!DNL Adobe Experience Cloud], para introducir fácilmente datos de CRM, datos de socios de terceros y datos adquiridos por terceros en [!DNL Target].

Por ejemplo, puede asociar los datos de compra del sistema del punto de venta con un perfil de visitante. Para ello, solo tiene que crear un archivo CSV con un máximo de 200 variables sin conexión y cargarlo directamente en [!DNL Adobe Experience Cloud] un archivo mediante la carga o utilizar FTP para alojar y programar la actualización del archivo con regularidad. Una vez que los atributos del cliente se encuentren en [!DNL Adobe Experience Cloud], puede asignarlos a [!DNL Experience Cloud] soluciones como [!DNL Adobe Analytics] y [!DNL Target] dónde estarán disponibles para análisis, pruebas y personalización.

Consulte Atributos [](https://experienceleague.adobe.com/docs/target/using/audiences/visitor-profiles/working-with-customer-attributes.html) personalizados para obtener instrucciones paso a paso.

**Es bueno saber**: Dado que [!DNL Target] es una plataforma abierta y agnóstica que funciona bien con diferentes tecnologías, puede agregar CRM o datos adquiridos de muchas maneras diferentes. Esto significa que puede elegir un método que funcione mejor para su organización.

Consulte [Métodos para obtener datos en Destinatario](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md) para obtener más información.

## Sugerencia 2: Personalice más profundamente mezclando audiencias de Destinatario con otras audiencias de Adobe Experience Cloud.

La combinación de audiencias que viven en diferentes [!DNL Adobe Experience Cloud] soluciones puede proporcionarle una comprensión mucho más amplia de sus clientes, así como la capacidad de personalizar más profundamente. Por ejemplo, aunque [!DNL Target] proporciona datos de audiencia en tiempo real, [!DNL Adobe Analytics] proporciona datos de audiencia históricos. La combinación de ambos puede ayudarle a identificar cuándo el comportamiento de un cliente es coherente y cuándo puede haber una oportunidad para actuar en un nuevo comportamiento. Simplemente haga clic en el menú desplegable situado junto a &quot;Todos los Visitantes&quot; al crear una actividad. A continuación, marque las casillas de hasta veinte audiencias, haga clic en &quot;Combinar varias Audiencias&quot; y en &quot;Guardar&quot;.

Consulte [Combinación de varias audiencias](/help/c-target/combining-multiple-audiences.md) para obtener instrucciones paso a paso.

**Es bueno saber**: [!DNL Adobe Audience Manager] Las audiencias están disponibles en [!DNL Target] forma automática. Pero compartir [!DNL Adobe Analytics] audiencias requiere un poco de configuración manual. Simplemente marque la casilla rotulada &quot;Convertir esto en una audiencia Experience Cloud&quot; durante el proceso de creación de audiencias en [!DNL Analytics]. A continuación, en [!DNL Target], haga clic en &quot;Importar audiencias de Experience Cloud&quot;.

## Sugerencia 3: Exporte datos de Destinatario para utilizarlos con herramientas de terceros.

Con los tokens de respuesta, los administradores pueden extraer datos fácilmente de [!DNL Target] y en herramientas de terceros. Esto puede resultar útil cuando desee agregar los datos a los datos recopilados en una herramienta de encuesta. Por ejemplo, si una encuesta muestra una muestra de una población con una puntuación de &quot;9&quot; en una experiencia y otra con una puntuación de &quot;4&quot; en una experiencia, puede utilizar sus datos para ver quién vio la experiencia A y quién vio la experiencia B. También puede utilizar tokens de respuesta para exportar [!DNL Target] datos al almacén de datos interno. Haga clic en &quot;Administración&quot; y, a continuación, coloque el conmutador junto al testigo de respuesta deseado en la posición ON. A continuación, cree una actividad. Los datos están listos para transferirse al proveedor externo. Puede comprobar que [!DNL Target] está exportando los datos mediante las herramientas de depuración.

Consulte los tokens de [respuesta](/help/administrating-target/response-tokens.md) para obtener instrucciones paso a paso.

**Sugerencia**&#x200B;útil: Antes de que un administrador pueda activar un token de respuesta asociado a un tercero, un desarrollador debe establecer una asociación con esa compañía de terceros.

Consulte los tokens de [respuesta](/help/administrating-target/response-tokens.md) para obtener instrucciones paso a paso.

**Haga esto primero**: Asegúrese de que está utilizando la versión 1.1 o posterior de at.js. Si utiliza una versión anterior, verá los tokens de respuesta, pero at.js no podrá utilizarlos.

## Sugerencia 4: Cree audiencias a partir de estas variables clave para aumentar el valor de la actividad.

Al crear audiencias para objetivos o probar promociones y ofertas, considere primero estas variables:

* Comportamiento. Patrones de visitas al sitio y patrones de compra
* Referrer. Sitios y campañas de referencia
* Temporal. Horas del día, días de la semana y factores de temporada
* Sin conexión. Patrones de visitas y compras en tiendas físicas
* Entorno. País de origen, sistema operativo, tipo de explorador

## Sugerencia 5: Proporcione a los usuarios el nivel de acceso que necesitan para realizar su trabajo.

Facilite el trabajo con los datos de su organización y mantenerlos seguros. [!DNL Target Premium] permite a los administradores controlar el nivel de acceso dado a diferentes equipos internos y externos.

Consulte Permisos [de usuario de](/help/administrating-target/c-user-management/property-channel/property-channel.md) Enterprise para obtener más información.

**Sugerencia**&#x200B;útil: Al agregar usuarios, si el nombre de un miembro del equipo no se ha agregado previamente a su organización, como puede ser el caso de un empleado de una agencia de terceros, al introducir su dirección de correo electrónico y contraseña, se activará una invitación por correo electrónico para unirse al espacio de trabajo de un equipo.

¿Usar Target Standard? Todavía puede [asignar tres niveles de acceso](/help/administrating-target/c-user-management/c-user-management/user-management.md) para los usuarios con funciones de solo lectura, editor y aprobador.

## Sugerencia 6: Descubrir el rendimiento de una oferta a lo largo de un viaje del cliente probándola en cada página del viaje.

Ver el rendimiento de una oferta, como el envío gratuito, durante un viaje del cliente que tiene lugar en varias páginas del sitio web.

Consulte actividad [de](/help/c-experiences/c-visual-experience-composer/multipage-activity.md) varias páginas para obtener instrucciones paso a paso.

**Sugerencia**&#x200B;útil: Si cambia la dirección URL después de especificar un intervalo de páginas, se restablecerá la experiencia. Esto significa que las variaciones especificadas ya no aparecerán. Si necesita cambiar la dirección URL, recuerde redefinir la experiencia.

## Sugerencia 7: Pruebe una oferta con diferentes audiencias para descubrir si las audiencias tienen preferencias diferentes.

Con las versiones de experiencia, puede ejecutar una prueba con variaciones para tantas audiencias como desee. Por ejemplo, puede crear una publicidad tipo titular que ofrezca envío gratuito (con imágenes y variaciones de moneda para los clientes de EE.UU., Reino Unido y EE.UU.) sin tener que ejecutar pruebas para tres audiencias diferentes.

Consulte para ver las audiencias de [varias experiencias en una prueba](/help/c-activities/t-test-ab/t-test-create-ab/target-experience-to-multiple-audiences.md) A/B y las versiones de [experiencias en Adobe Target](https://helpx.adobe.com/target/how-to/experience-versions.html?playlist=/ccx/v1/collection/product/target/seg-%20ment/business-practitioners/explevel/beginner-adls/applaunch/how-to-2/collection.ccx.js?ref=helpx.adobe.com) para obtener instrucciones paso a paso.

## Sugerencia 8: Ahorre tiempo replicando experiencias de actividad en páginas similares.

Cree una variación en una página web, como un nuevo color de botón, y aplíquelo automáticamente a todas las páginas que compartan la misma plantilla. Puede especificar páginas o aplicar las variaciones a todas las páginas similares del sitio web.

Consulte [Incluir la misma experiencia en páginas](/help/c-experiences/c-visual-experience-composer/temtest.md) similares para obtener instrucciones paso a paso.

## Sugerencia 9: Reduzca el desorden en la biblioteca de Audiencias mediante la creación de audiencias únicas.

Si está dirigiendo un segmento que sabe que no volverá a tener destinatarios (por ejemplo, los clientes afectados por un evento meteorológico inesperado), la creación de una audiencia de un solo uso puede ayudarle a realizar el trabajo sin agregar más desorden a la biblioteca de Audiencias. Esto facilita la búsqueda de audiencias que se usan una y otra vez.

Consulte [Creación de una audiencia](/help/c-target/creating-activity-only-audience.md) de solo actividad para obtener instrucciones paso a paso.

**Capacidad** muy solicitada: Nuestros clientes nos pidieron que pudiéramos evitar que las audiencias de un solo uso se guardaran automáticamente en la Biblioteca de Audiencias. Ahora, ya no tienen que eliminar audiencias manualmente para mantener sus bibliotecas organizadas.

## Sugerencia 10: Ejecute pruebas simples más rápido, ya que no las coloca en el proceso de control de calidad estándar.

No hay nada peor que tener una actividad lista para ir y luego esperar semanas para que complete el proceso estándar de control de calidad. Puede realizar el control de calidad de la mayoría de las actividades simplemente pasando algunos vínculos de control de calidad a compañeros para probarlos en varios exploradores. Lo más probable es que quiera realizar más pruebas de control de calidad para los esfuerzos que cambian radicalmente la función del sitio, pero en realidad debería tener menos de esas actividades y muchas más de las actividades más básicas. Añadir mejores controles de derechos para que menos personas puedan impulsar las cosas en plena vida también añade límites significativos y le permite lograr lo que necesita sin sacrificar la velocidad y la eficiencia. Otra opción es contar con un recurso de TI designado para supervisar oportunamente el proceso de control de calidad.

Consulte Control de calidad de [Actividad](/help/c-activities/c-activity-qa/activity-qa.md) para obtener instrucciones paso a paso.

## Sugerencia 11: Ejecute pruebas en páginas de mucho tráfico para que alcancen más rápidamente la relevancia estadística.

Muchos especialistas en mercadotecnia inician programas de optimización para segmentación y segmentación de audiencias sin comprobar si los niveles de tráfico y las audiencias representadas proporcionarán resultados significativos dentro del intervalo de tiempo de prueba para sus objetivos de optimización y conversión. Para evitar este error común, responda a estas preguntas con antelación:

* ¿Cuántos visitantes únicos diarios tiene la página?
* ¿Cuál es la tasa de conversión de la página?
* ¿Cuánto tiempo espera que tenga que ejecutar la prueba antes de que pueda llamarla completa con confianza?

**Sugerencia**&#x200B;útil: Utilice la calculadora [de tamaño de la](https://docs.adobe.com/content/target-microsite/testcalculator.html) muestra de Destinatario para determinar el tamaño de la muestra necesario para una prueba correcta.

## Sugerencia 12: Diseñe pruebas más sencillas para asegurarse de que puede crearlas e implementarlas.

Después de considerar todos los aspectos de cómo diseñar una prueba, un plan puede resultar muy complejo. En función de dónde se encuentre su empresa con las pruebas y de la capacidad del grupo para diseñar, codificar, ejecutar y analizar los resultados, determine si la prueba parece demasiado ambiciosa. De ser así, estar preparados para reducir su alcance y complejidad. Es mejor realizar un inicio pequeño que no realizar la prueba en absoluto. No puede proporcionar un alza impactante si nunca inicia la prueba. Es importante equilibrar las aspiraciones del equipo con las realidades de sus recursos y capacidades.

## Sugerencia 13: Desglose pruebas complejas en actividades de prueba más pequeñas para hacerlas alcanzables.

En lugar de desarrollar una prueba grande con múltiples variables y desarrollo complejo, desarrolle una serie menos compleja de pruebas más pequeñas con variables mínimas. Esto permite una comprensión más profunda del rendimiento de las pruebas en función de variables específicas. También reduce los posibles problemas técnicos derivados del desarrollo de proyectos más grandes.

![Ilustración de pruebas complejas](/help/c-intro/assets/break-complex-tasks.png)

## Sugerencia 14: Maximice el impacto de la prueba probándola más cerca del final del canal de conversión.

Realizar pruebas tan cerca de la página en la que los visitantes hacen clic en Completar compra, Enviar solicitud o bien completar una conversión tiende a ofrecer los resultados más impactantes. Los visitantes que llegan al final del canal están más cualificados, han invertido más tiempo y están listos para comprar, por lo que probar las perspectivas sobre sus preferencias y acciones puede ayudarle a realizar cambios rentables. Dado que las páginas de la ruta de compra son críticas para las tasas de conversión, las pruebas que se realicen en esas páginas deben socializarse con los principales interesados antes de publicarlas.

![Ilustración del canal de conversión](/help/c-intro/assets/conversion-funnel.png)

## Sugerencia 15: Actualice constantemente las pruebas para realizar mejoras repetitivas.

Si su hipótesis no demostró ser cierta, piense en maneras de mejorar la prueba. Recuerde que, aunque ninguna de las experiencias probadas funcionara mejor, el experimento no era una pérdida de tiempo. Una prueba exitosa no siempre significa un aumento de ingresos o conversiones. Si la prueba realmente apoyó su hipótesis, entonces usted está en camino a desarrollar una teoría general. Pero incluso cuando tenga un claro resultado ganador, no se detenga ahí. Con demasiada frecuencia, los especialistas en mercadotecnia cometen el error de probar una vez y luego recurrir a esos resultados sin comprender realmente qué llevó al éxito. En cambio, planee repetir esos resultados para averiguar por qué el favorito estaba por delante. Esto le llevará a perspectivas más profundas que puede utilizar en campañas futuras.

## Sugerencia 16: Compare pruebas y actividades de personalización para obtener ideas a fin de mejorar la segmentación.

La comparación del rendimiento de conversión de diferentes audiencias dentro de diferentes pruebas en diferentes ubicaciones puede ayudar a enfocar y refinar la estrategia de optimización de una compañía. Utilice las comparaciones de prueba para identificar qué audiencias son más valiosas de probar, qué experiencias deben recibir experiencias objetivo y qué tipos de experiencias tienen más probabilidades de generar una respuesta.

Por ejemplo, un cliente de servicios financieros ejecutó una campaña promocional para una tarjeta de crédito que incluía incentivos profesionales de evento deportivo. Mediante pruebas multivariadas factoriales parciales de sus páginas de aterrizaje, el cliente pudo equilibrar de manera óptima los mensajes sobre los beneficios de las tarjetas de crédito con incentivos deportivos para el destinatario de audiencias distintas de su base de clientes. Este enfoque permitió a la compañía aprovechar al máximo la conversión durante una ventana en la que el tiempo depende de un evento deportivo importante.

## Sugerencia 17: Haga que las pruebas sean útiles solo al iniciarlas si sabe que puede actuar con los datos.

Una prueba no tiene sentido si no está claro cómo va a actuar con los datos. Esto incluye saber cuál es la métrica de éxito clave, qué debe suceder para impulsar al ganador, cómo seguirá los resultados de la prueba y qué hará con la información de audiencia. Para una prueba rápida y exitosa, es vital que todos los grupos involucrados en la prueba (desarrolladores, creativos, especialistas en pruebas y otros) conozcan su función antes del lanzamiento de la prueba.

## Sugerencia 18: Antes de lanzar una prueba, asegúrese de que la empresa admite la promoción del ganador.

Las organizaciones de optimización exitosas creen en el concepto de prueba y entienden que sus opiniones profesionales sobre qué experiencia ganará la prueba no siempre resultan verdaderas. Determinan el ganador en base a una sólida base de datos y están ansiosos y dispuestos a impulsar la experiencia ganadora en vivo después de que los resultados estén en curso, incluso aunque no esté en línea con sus expectativas o parezca contrario a la intuición.

Por ejemplo, un cliente de servicios de salud de Adobe demostró recientemente el valor de las pruebas mostrando cómo un titular héroe que el equipo había considerado que un fragmento de slam tenía un impacto negativo en la conversión. Si su organización aún no ha adoptado completamente las pruebas, es mejor realizar primero pruebas de ámbito más simples y más pequeñas para que los cambios de los resultados de las pruebas se puedan realizar de forma incremental.

## Sugerencia 19: Comunique a todos que ha lanzado una prueba para evitar preocuparse cuando el sitio cambie.

Una de las ventajas de configurar sus actividades para utilizar parámetros de control de calidad es que puede compartir esos vínculos con todos los integrantes de su equipo. Debe informar a más personas sobre la actividad y asegurarse de que no asumen que el sitio no funciona correctamente cuando se encuentra en una variante de prueba.

Una vez finalizadas las pruebas, la comunicación de los inicios de campaña, los resultados de las pruebas y, sobre todo, las lecciones aprendidas, le ayuda a crear conciencia de los resultados de las pruebas y a despertar interés en ellos. Compartir los resultados con todos los miembros de la organización también evita volver a probar una hipótesis, educa a todos sobre lo que funciona y los ayuda a desafiar fundamentalmente sus propias ideas sobre lo que funciona basándose en lo que se ha encontrado. Es aconsejable preparar una plantilla que se utilice cada vez para compartir sus conclusiones y las lecciones clave.
A continuación, considere la posibilidad de crear un libro que se pueda compartir o un paquete de Microsoft PowerPoint que capture de forma acumulativa estos conocimientos.

## Sugerencia 20: Aproveche la funcionalidad móvil para crear actividades móviles más innovadoras.

Las experiencias de los usuarios de tabletas y smartphones deben centrarse en los controles táctiles como la interacción principal del visitante en lugar de los clics del ratón y los controles del teclado. Aproveche los controles de visualización móviles, incluidos el barrido con los dedos, el tacto, el arrastre, la pellizco y el zoom. Utilice botones sencillos y grandes para designar las interacciones y la navegación, como un carro de compras grande o un botón de reproducción de vídeo. Si diseña para la venta al por menor móvil, incorpore una visualización de productos enriquecidos optimizada para el tipo de dispositivo. Siempre busque oportunidades para cambiar el enfoque de la experiencia del usuario a visores incrustados y grandes o zoom y recorrido interactivos a pantalla completa, giro de 360 grados y funcionalidad de vídeo mejorada.

## Sugerencia 21: Ayude a los visitantes móviles a encontrar lo que desean optimizando la búsqueda móvil.

Los usuarios móviles tienen una alta calidad. La mayoría de ellos utiliza la búsqueda antes de hacer cualquier otra cosa en los sitios de comercio electrónico, lo que hace que la optimización de la búsqueda de sitios móviles sea crucial. Para mejorar la optimización del motor de búsqueda (SEO) para dispositivos móviles, utilice indicaciones de navegación explícitas para facilitar la navegación. Además, implemente la sugerencia automática y la corrección automática en los cuadros de entrada de búsqueda para resolver la dificultad de escribir con dispositivos móviles. Proporcione resultados de búsqueda relevantes y convincentes optimizados para el tamaño y la ubicación de la pantalla.

## Sugerencia 22: Alcance mejor las audiencias móviles mediante la segmentación por hora del día para campañas SEM móviles.

Conozca cómo y cuándo llegar a su audiencia y cómo administrar mejor su gasto diario en publicidad &quot;partiendo el día&quot; de sus campañas móviles en diferentes segmentos a lo largo del día.

Muchos especialistas en marketing cometen el error de no asignar suficiente presupuesto para capturar esa parte de voz en las horas en que el uso de dispositivos particulares es más pesado, dejando así muchos ingresos y posibles clientes sobre la mesa.

Por ejemplo, el uso de tabletas suele aumentar en las horas de la noche y muchos usuarios navegan mientras ven la televisión. En cambio, los usuarios de smartphones suelen acceder al contenido sobre la marcha. Los tiempos de conversión pico también varían según la industria, por lo que es importante saber cuándo es más probable que actúen los clientes únicos.

## Recuerde

Considere las siguientes ideas antes de pasar al siguiente capítulo: &quot;Inspiración para pruebas y actividades de personalización&quot;.

### Cuando cree sus pruebas, no decore, sea intencional.

* Controle el flujo con las rutas oculares intencionales centradas en los puntos de conversión.
* Asegúrese de que utiliza sus bienes raíces en su beneficio.
* Aproveche el enfoque de imagen para asegurarse de que las imágenes no están decoradas, pero funcionan bien.
* Reduzca el desorden, la fricción y el desenfoque con Copia simplificada.
* Asegúrese de que tiene Llamadas a acción efectivas cuando necesite que el usuario actúe.
* Añada credibilidad a través de Contenido generado por el usuario siempre que sea posible.

### Simplifique el sitio web.

* No &quot;haga&quot; leer a los clientes. No lo harán.
* Facilite el escaneo.
* Utilice bloques de texto con viñetas.
* Asegúrese de que su copia sigue un proceso de pensamiento claro y secuencial.

### Utilizar llamadas a acción eficaces

* Pónganse en los zapatos del cliente.
* Utilice un lenguaje orientado a la acción.
* Considere la motivación para la conversión.
* Abordar el resultado de la conversión.
* ¡Asegúrate de que se vean los CTA!