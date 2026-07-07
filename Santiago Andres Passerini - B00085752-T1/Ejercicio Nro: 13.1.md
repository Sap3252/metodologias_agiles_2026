# Ejercicio Nro: 13

## Enunciado
1. ¿Qué es Extreme Programming (XP) y cuál es su objetivo principal dentro de las metodologías ágiles?
2. ¿Cuáles son los cinco valores principales de XP? Explicá brevemente cada uno.
3. ¿Por qué XP considera que las pruebas son un elemento fundamental del desarrollo de software?
4. ¿Qué es Test Driven Development (TDD) y cómo se relaciona con XP?
5. ¿En qué consiste la práctica de Pair Programming? Mencioná dos ventajas y una posible dificultad.
6. ¿Qué son las historias de usuario en XP y por qué se prefieren frente a una especificación extensa de requisitos?
7. ¿Qué significa Continuous Integration en XP y qué beneficios aporta al equipo de desarrollo?
8. ¿Cómo se aplica el concept de Weekly Cycle en un proyecto desarrollado con XP?
9. En XP se plantea que se fija el tiempo, el costo y la calidad, y se negocia el alcance. ¿Qué significa esta idea? Explicalo con un ejemplo.
10. Elegí tres prácticas de XP y explicá cómo podrían aplicarse en un proyecto real de desarrollo de software.

## Resolución

1. ¿Qué es Extreme Programming (XP) y cuál es su objetivo principal dentro de las metodologías ágiles?

Extreme Programming (XP) es un marco de trabajo ágil orientado al desarrollo de software, estructurado especialmente para escenarios donde los requisitos son difusos, mutables o conllevan un nivel de incertidumbre elevado. Se fundamenta en pilares como la flexibilidad ante el cambio, el perfeccionamiento técnico continuo y la sinergia del factor humano en el equipo.
El propósito central de XP es elevar al máximo la calidad del producto final y reaccionar con agilidad ante las prioridades del cliente. Esto se logra amortiguando el impacto económico que suelen tener las modificaciones en el código con el paso del tiempo. Para alcanzarlo, adopta las metodologías convencionales de ingeniería y las lleva a una ejecución radical (por ejemplo, si inspeccionar el código es beneficioso, se vuelve una actividad permanente mediante el desarrollo de a dos).

2. ¿Cuáles son los cinco valores principales de XP? Explicá brevemente cada uno.
Las directrices esenciales que conducen las interacciones y elecciones en un entorno XP son:

Comunicación: El éxito de cualquier iniciativa radica en la fluidez del intercambio de información. XP fomenta el diálogo directo cara a cara, el empleo de tarjetas físicas para plasmar las tareas y la distribución de oficinas abiertas que mitiguen los malentendidos entre los técnicos y el usuario.

Simplicidad: Radica en programar la alternativa más directa y funcional para el día de hoy, evitando adelantarse a supuestos requerimientos del mañana. Concentrarse en lo estrictamente útil minimiza el mantenimiento futuro y agiliza los despliegues.

Retroalimentación (Feedback): Se busca evaluar el rumbo del proyecto de manera constante. El equipo obtiene devoluciones inmediatas: mediante pruebas de software que corren en segundos, herramientas de unificación de código en minutos, iteraciones con el cliente en días y entregas de versiones operativas en meses.

Respeto: Los integrantes del proyecto valoran las capacidades y funciones de sus pares. Los ingenieros atienden las necesidades del negocio, el cliente confía en los tiempos estimados por el equipo técnico, y todos se comprometen con la limpieza del software y el clima laboral.

Coraje (Valor): Es la determinación para asumir posturas complejas en beneficio del producto. Implica ser transparentes frente a desvíos en el cronograma, descartar código redundante o ineficiente (hacer reestructuraciones) y mitigar los contratiempos de inmediato en lugar de evadirlos.

3. ¿Por qué XP considera que las pruebas son un elemento fundamental del desarrollo de software?
En este marco metodológico, los tests son el motor que guía la programación cotidiana y se consideran indispensables por factores clave:

Resguardo ante fallos (Regresiones): Modificar la estructura del código de forma habitual exige la certeza de que las funcionalidades previas sigan operando correctamente. Los tests automatizados aportan este respaldo en instantes.

Especificación dinámica: Una prueba bien diseñada actúa como la guía técnica más fidedigna sobre el comportamiento de un módulo, superando la utilidad de cualquier manual tradicional que queda desactualizado de inmediato.

Optimización de costos de corrección: Localizar una falla inmediatamente después de escribir las líneas de código es sustancialmente más económico y ágil que detectarlo semanas más tarde en los entornos de producción o mediante revisiones manuales tardías.

4. ¿Qué es Test Driven Development (TDD) y cómo se relaciona con XP?

Test Driven Development (TDD) es una metodología de ingeniería en la que el programador diseña los escenarios de prueba automatizados con anterioridad a la creación del código funcional. Este enfoque se rige por una secuencia cíclica y rigurosa denominada Rojo-Verde-Refactor:

Rojo (Red): Crear un test automatizado para una función inexistente, verificando que, lógicamente, falle en primera instancia.

Verde (Green): Implementar el código mínimo y necesario para lograr que dicha prueba se ejecute de manera exitosa.

Refactorizar (Refactor): Limpiar, estructurar y pulir el diseño del código generado, eliminando redundancias pero garantizando que las pruebas continúen dando luz verde.

TDD representa una de las prácticas de ingeniería nucleares de XP. Se alinea de forma directa con los valores de Simplicidad y Retroalimentación, asegurando piezas de software limpias, modulares y fáciles de testear desde su origen.

5. ¿En qué consiste la práctica de Pair Programming? Mencioná dos ventajas y una posible dificultad.
Esta dinámica consiste en que dos profesionales de desarrollo unan esfuerzos frente a una única estación de trabajo para resolver un mismo requerimiento. Para ello, se alternan dinámicamente dos roles:

El Conductor (Driver): Se encarga de la interacción con el teclado y el mouse, concentrado en la lógica inmediata y en la escritura minuciosa de las líneas de código.

El Navegador (Navigator): Supervisa la marcha en tiempo real, adoptando una visión macro (analiza la arquitectura, previene fallos perimetrales y evalúa casos atípicos) mientras planifica la ruta a seguir.

Ventajas:

Incremento en la calidad y reducción de fallos: La validación cruzada por dos personas previene errores de lógica y desvíos de diseño en el momento exacto en que se está programando.

Diseminación del conocimiento: Facilita el aprendizaje mutuo de destrezas técnicas y reglas de negocio, evitando que la información quede retenida en una sola persona (silos).

Desventaja latente:

Este nivel de colaboración estrecha demanda un alto desgaste de atención y una gran madurez interpersonal. En ausencia de afinidad, ante conflictos de personalidad, o si se omiten las pausas necesarias, se puede caer en el desgaste mental y en roces internos.

6. ¿Qué son las historias de usuario en XP y por qué se prefieren frente a una especificación extensa de requisitos?

Las Historias de Usuario son enunciados concisos y comprensibles redactados desde la perspectiva del cliente, orientados a reflejar una funcionalidad que aporta utilidad práctica al negocio. En el esquema tradicional de XP, se plasmaban en fichas o notas autoadhesivas estructurándose así: "Como [perfil], requiero [acción] para obtener [valor]".

Se eligen prioritariamente por encima de los extensos pliegos de especificaciones debido a:

Privilegian el diálogo sobre los procesos rígidos: En XP, los requisitos no se congelan en un texto estático, sino que se conversan de forma continua. La historia sirve como un recordatorio físico para un intercambio verbal posterior entre las partes.

Ductilidad ante los cambios: Un dossier formal de cientos de páginas pierde vigencia rápidamente y su modificación es compleja. Las tarjetas de historias permiten ser jerarquizadas, reconfiguradas o divididas ágilmente según el rumbo del negocio.

Lenguaje universal: Al prescindir de tecnicismos complejos, operan como un canal de entendimiento fluido entre el equipo técnico y los decisores del negocio.

7. ¿Qué significa Continuous Integration en XP y qué beneficios aporta al equipo de desarrollo?

La Integración Continua (CI) es la disciplina mediante la cual los programadores unifican sus modificaciones en la rama de código principal con alta regularidad (múltiples veces en una jornada). Cada actualización es validada autónomamente por un sistema que compila el código y ejecuta las pruebas necesarias para alertar sobre desajustes al instante.

Los beneficios clave que confiere al equipo son:

Evita las integraciones caóticas: Se eliminan los dolores de cabeza derivados de acoplar ramas de código aisladas durante largos períodos, tareas que suelen consumir jornadas enteras resolviendo colisiones de archivos.

Detección temprana de anomalías: Si una modificación altera el ecosistema general, el sistema de CI da aviso en pocos minutos, posibilitando una solución inmediata cuando el desarrollador aún tiene el diseño fresco en su mente. Mantener la base de código estable eleva la predictibilidad del proyecto.

8. ¿Cómo se aplica el concept de Weekly Cycle en un proyecto desarrollado con XP?

El Ciclo Semanal marca la cadencia temporal a corto plazo en la metodología. Se ejecuta al comenzar la semana de trabajo mediante una planificación conjunta donde intervienen el cliente y los técnicos, articulándose bajo los siguientes pasos:

Balance del periodo anterior: El cliente inspecciona el software terminado en los días previos para validar el cumplimiento de sus expectativas.

Planificación de entregas: El cliente determina cuáles historias de usuario se programarán en los siguientes días, basándose en la prioridad del negocio y el rendimiento histórico (velocidad) del equipo.

Apertura de subtareas: Los desarrolladores fragmentan los requerimientos seleccionados en actividades técnicas más acotadas (que demanden pocas horas) y las asumen de forma autónoma.

Ejecución enfocada: Durante las jornadas restantes, los profesionales se abocan de lleno a codificar, probar y consolidar dichas tareas, apuntando a entregar un incremento de software utilizable al concluir la semana.

9. En XP se plantea que se fija el tiempo, el costo y la calidad, y se negocia el alcance. ¿Qué significa esta idea? Explicalo con un ejemplo.

En la gestión tradicional en Cascada, se suele fijar el alcance global y se calculan de forma variable los plazos y la inversión, lo que suele decantar en demoras o en desmedro de los testeos. XP redefine este enfoque manejando las cuatro restricciones de un proyecto (Tiempo, Inversión, Calidad y Alcance):

El Tiempo y el Costo se vuelven constantes (la fecha de entrega y el número de integrantes del equipo no varían). La Calidad tampoco es prescindible, dado que saltearse revisiones ralentiza la productividad futura; por ende, se sostiene bajo altos estándares de ingeniería. Así, el Alcance es el único elemento flexible: si los plazos aprietan, se reduce el volumen de características funcionales destinadas a esa entrega.

Ejemplo: Pensemos en un equipo que desarrolla una plataforma de reservas hoteleras para la temporada alta de verano (Tiempo fijo), operando con un staff de 5 ingenieros (Costo fijo) y garantizando un procesamiento seguro de las transacciones bancarias (Calidad fija).

A una semana del lanzamiento, advierten que el tiempo es insuficiente para programar el "motor de sugerencias por preferencias de usuario" y el "módulo de canje de puntos de fidelidad". Bajo el enfoque XP, se coordina con el negocio para ajustar el alcance: se pospone el recomendador para una etapa posterior y se crea una versión manual muy básica para el sistema de puntos. El producto se estrena a término, bajo el presupuesto pautado y operando de forma robusta en sus servicios centrales (búsqueda y pasarela de pago).

10. Elegí tres prácticas de XP y explicá cómo podrían aplicarse en un proyecto real de desarrollo de software.

Para ejemplificarlo en un escenario real, supongamos el desarrollo de una Plataforma Web para la Gestión de Envíos de una Empresa de Logística:

Cliente en el Sitio (On-Site Customer):

Implementación: Ubicar físicamente (o en comunicación virtual permanente) a un supervisor de operaciones de la compañía de logística junto al área de desarrollo.

Caso práctico: Si el equipo técnico tiene dudas sobre las prioridades de despacho cuando un camión excede su peso límite, no se redacta un pliego formal de consulta. Se le pregunta directamente al supervisor presente en la mesa, resolviendo la regla de negocio en cuestión de minutos.

Refactorización (Refactoring):

Implementación: Modificar de forma continua la arquitectura del código interno sin variar las funciones externas del sistema, garantizando un software limpio.

Caso práctico: Al principio, la fórmula para calcular las tarifas de envío según la distancia y el volumen se programó de urgencia dentro del formulario web de despacho. En la siguiente iteración, notando que el fragmento de código es confuso, la pareja de desarrollo reestructura el sistema extrayendo la lógica a un componente aislado llamado CalculadorTarifas. Esto optimiza el orden arquitectónico y deja el código listo para futuros módulos de facturación, confirmando que las pruebas automáticas sigan funcionando.

Ritmo Sostenible (Sustainable Pace):

Implementación: Desterrar la cultura de las jornadas extendidas crónicas y las horas extra sin planificación, cuidando el rendimiento integral de las personas.

Caso práctico: Al aproximarse el fin de la iteración semanal, surgen tareas técnicas remanentes. En lugar de presionar al equipo para que extienda su horario nocturno, se aplica la norma de XP: se conversa con el cliente para postergar una funcionalidad secundaria y el equipo finaliza su labor en la hora habitual. Al día siguiente, regresan descansados y lúcidos, minimizando la introducción de fallos por fatiga en la base de código.
