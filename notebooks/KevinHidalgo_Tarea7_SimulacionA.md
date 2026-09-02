<link
  rel="stylesheet"
  href="https://cdn.jsdelivr.net/gh/dracula/markdown-css/dracula-markdown.css"
/>
<!-- <link rel="stylesheet" href="dracula-markdown.css" /> -->
<hr style="border:2px solid #CC00FF"> </hr>
<a><img src="https://www.vhv.rs/dpng/d/313-3134285_logo-de-la-universidad-nacional-de-colombia-png.png" width="100" align="center"></a>
<a><img src="https://minaslap.net/pluginfile.php/1/core_admin/logo/0x200/1770226238/Logo%20MinasLAP-3%20%281%29.png" width="100" align="center"></a>
<h1><center>Simulación Avanzada</center></h1>
<h2><center>Tarea 7</center></h2>
<h3><center>Cuestionario sobre teoría de colas (Flexsim)</center></h3>

<a name="conte"></a>
<hr style="border:2px solid #CC00FF"> </hr>


**Elaborado por:** _Kevin Ferney Hidalgo Higuita_

**Correos:** _kfhidalgoh@unal.edu.co_

**Fecha de elaboración:** _2026 Marzo 28_

**Fecha última modificación:** _2026 Marzo 28_

---

<h2><center>Tabla de contenido</center></h2>

- [Objetivo](#objetivo)
- [Preguntas](#preguntas)
  - [1. ¿Con qué otro nombre se le conoce a una cola (fila de espera)?](#1-con-qué-otro-nombre-se-le-conoce-a-una-cola-fila-de-espera)
  - [2. ¿Cuáles son los tres elementos principales de los sistemas de colas? Identifique algunas características de cada uno.](#2-cuáles-son-los-tres-elementos-principales-de-los-sistemas-de-colas-identifique-algunas-características-de-cada-uno)
  - [3. ¿Por qué los sistemas de colas son dinámicos?](#3-por-qué-los-sistemas-de-colas-son-dinámicos)
  - [4. ¿Cuáles son los dos componentes del tiempo de entrega (lead time)?](#4-cuáles-son-los-dos-componentes-del-tiempo-de-entrega-lead-time)
  - [5. En la teoría de colas básica y en los modelos de simulación, ¿cuál es el orden asumido en el que un servidor atiende a los clientes?](#5-en-la-teoría-de-colas-básica-y-en-los-modelos-de-simulación-cuál-es-el-orden-asumido-en-el-que-un-servidor-atiende-a-los-clientes)
  - [6. ¿Qué significa un proceso de llegada estacionario?](#6-qué-significa-un-proceso-de-llegada-estacionario)
  - [7. ¿Cuál es la diferencia entre las acciones de balking (rechazo/no entrar a la fila) y reneging (abandonar la fila)?](#7-cuál-es-la-diferencia-entre-las-acciones-de-balking-rechazono-entrar-a-la-fila-y-reneging-abandonar-la-fila)
  - [8. Explique qué sucede cuando un cliente hace jockeying (“jockeys”cambio de fila).](#8-explique-qué-sucede-cuando-un-cliente-hace-jockeying-jockeyscambio-de-fila)
  - [9. Identifique las razones por las cuales un servidor podría no estar disponible el 100% del tiempo.](#9-identifique-las-razones-por-las-cuales-un-servidor-podría-no-estar-disponible-el-100-del-tiempo)
  - [10. Describa los dos comportamientos diferentes que ocurren entre un servidor y una cola cuando se utiliza un recurso compartido para transportar elementos entre ambos.](#10-describa-los-dos-comportamientos-diferentes-que-ocurren-entre-un-servidor-y-una-cola-cuando-se-utiliza-un-recurso-compartido-para-transportar-elementos-entre-ambos)
  - [11. Describa los sistemas que están definidos por las siguientes notaciones:](#11-describa-los-sistemas-que-están-definidos-por-las-siguientes-notaciones)
  - [12. Defina la Ley de Little.](#12-defina-la-ley-de-little)
  - [13. Explique la relación entre el inventario en proceso (work-in-process), la tasa de salida (throughput) y el tiempo de ciclo (cycle time).](#13-explique-la-relación-entre-el-inventario-en-proceso-work-in-process-la-tasa-de-salida-throughput-y-el-tiempo-de-ciclo-cycle-time)
  - [14. Defina el dilema o compensación básica (tradeoff) que típicamente se considera en el análisis de los sistemas de colas.](#14-defina-el-dilema-o-compensación-básica-tradeoff-que-típicamente-se-considera-en-el-análisis-de-los-sistemas-de-colas)
  - [15. Describa cómo afecta la variabilidad al rendimiento de un sistema de colas. Por ejemplo, si se incrementa la variabilidad en los tiempos de procesamiento, ¿cómo se ven afectados los tiempos de espera del sistema, el número de clientes en espera, etc.?](#15-describa-cómo-afecta-la-variabilidad-al-rendimiento-de-un-sistema-de-colas-por-ejemplo-si-se-incrementa-la-variabilidad-en-los-tiempos-de-procesamiento-cómo-se-ven-afectados-los-tiempos-de-espera-del-sistema-el-número-de-clientes-en-espera-etc)
  - [16. Explique en qué se diferencia el estudio de los sistemas de colas desde el enfoque de la teoría de colas frente al enfoque de la simulación de eventos discretos.](#16-explique-en-qué-se-diferencia-el-estudio-de-los-sistemas-de-colas-desde-el-enfoque-de-la-teoría-de-colas-frente-al-enfoque-de-la-simulación-de-eventos-discretos)
  - [17. Explique la diferencia entre un promedio observacional y un promedio ponderado en el tiempo.](#17-explique-la-diferencia-entre-un-promedio-observacional-y-un-promedio-ponderado-en-el-tiempo)
  - [18. Identifique algunos de los estados posibles en un sistema de colas.](#18-identifique-algunos-de-los-estados-posibles-en-un-sistema-de-colas)
  - [19. Describa a qué se refiere un sistema de eventos discretos.](#19-describa-a-qué-se-refiere-un-sistema-de-eventos-discretos)
  - [20. ¿Qué es una réplica (en simulación)?](#20-qué-es-una-réplica-en-simulación)
  - [21. Proporcione ejemplos de sistemas de colas y defina para cada uno:](#21-proporcione-ejemplos-de-sistemas-de-colas-y-defina-para-cada-uno)
  - [22. Si el tiempo promedio entre llegadas es de 12 minutos, ¿cuál es la tasa promedio de llegadas por hora?](#22-si-el-tiempo-promedio-entre-llegadas-es-de-12-minutos-cuál-es-la-tasa-promedio-de-llegadas-por-hora)
  - [23. ¿Cuál es la distribución asumida para los tiempos de servicio en los modelos básicos de la teoría de colas?](#23-cuál-es-la-distribución-asumida-para-los-tiempos-de-servicio-en-los-modelos-básicos-de-la-teoría-de-colas)
  - [24. Si las tasas de llegada y de servicio para un sistema de colas M/M/1 son de 18 y 20 por hora, respectivamente, ¿qué porcentaje del tiempo se espera que el servidor esté ocupado?](#24-si-las-tasas-de-llegada-y-de-servicio-para-un-sistema-de-colas-mm1-son-de-18-y-20-por-hora-respectivamente-qué-porcentaje-del-tiempo-se-espera-que-el-servidor-esté-ocupado)
  - [25. Si las tasas de llegada a un sistema siguen una distribución de Poisson, ¿cómo se distribuye el tiempo entre llegadas?](#25-si-las-tasas-de-llegada-a-un-sistema-siguen-una-distribución-de-poisson-cómo-se-distribuye-el-tiempo-entre-llegadas)
  - [26. Un único equipo de mantenimiento se encarga de todas las reparaciones en la gran granja de servidores de Bully, la cual opera de forma continua. La tasa promedio de fallos de los servidores es de 1 por hora, en promedio toma 50 minutos reparar un servidor. Utilice la teoría de colas básica para responder a las siguientes preguntas:](#26-un-único-equipo-de-mantenimiento-se-encarga-de-todas-las-reparaciones-en-la-gran-granja-de-servidores-de-bully-la-cual-opera-de-forma-continua-la-tasa-promedio-de-fallos-de-los-servidores-es-de-1-por-hora-en-promedio-toma-50-minutos-reparar-un-servidor-utilice-la-teoría-de-colas-básica-para-responder-a-las-siguientes-preguntas)
  - [27. Las llamadas entran a un único centro de atención (help desk) a una tasa promedio de 5 por hora. En promedio, el operador pasa 10 minutos con cada usuario. Utilice la teoría de colas básica para responder las siguientes preguntas:](#27-las-llamadas-entran-a-un-único-centro-de-atención-help-desk-a-una-tasa-promedio-de-5-por-hora-en-promedio-el-operador-pasa-10-minutos-con-cada-usuario-utilice-la-teoría-de-colas-básica-para-responder-las-siguientes-preguntas)
  - [28. Los trabajadores de mantenimiento llegan a un centro de repuestos operado por Bob a una tasa promedio de 15 por hora. Bob requiere, en promedio, 3 minutos para procesar la solicitud de cada trabajador.](#28-los-trabajadores-de-mantenimiento-llegan-a-un-centro-de-repuestos-operado-por-bob-a-una-tasa-promedio-de-15-por-hora-bob-requiere-en-promedio-3-minutos-para-procesar-la-solicitud-de-cada-trabajador)
  - [29.	Considere un sistema de colas con un solo servidor y disciplina PEPS (Primero en Entrar, Primero en Salir / FIFO), donde el tiempo entre llegadas está distribuido exponencialmente con una media de 10 minutos. En promedio, el 40% de las llegadas son artículos Rojos y el resto son Azules. Los tiempos de procesamiento para los artículos Rojos y Azules están distribuidos exponencialmente con medias de 12 y 6 minutos, respectivamente.](#29considere-un-sistema-de-colas-con-un-solo-servidor-y-disciplina-peps-primero-en-entrar-primero-en-salir--fifo-donde-el-tiempo-entre-llegadas-está-distribuido-exponencialmente-con-una-media-de-10-minutos-en-promedio-el-40-de-las-llegadas-son-artículos-rojos-y-el-resto-son-azules-los-tiempos-de-procesamiento-para-los-artículos-rojos-y-azules-están-distribuidos-exponencialmente-con-medias-de-12-y-6-minutos-respectivamente)
  - [30. Considere las siguientes operaciones de una clínica para responder a las preguntas planteadas a continuación: El tiempo entre llegadas de los pacientes a la sala de imágenes (por ejemplo, rayos X) está distribuido exponencialmente con una media de 30 minutos, y el tiempo para procesar a un paciente está distribuido exponencialmente con una media de 25 minutos.](#30-considere-las-siguientes-operaciones-de-una-clínica-para-responder-a-las-preguntas-planteadas-a-continuación-el-tiempo-entre-llegadas-de-los-pacientes-a-la-sala-de-imágenes-por-ejemplo-rayos-x-está-distribuido-exponencialmente-con-una-media-de-30-minutos-y-el-tiempo-para-procesar-a-un-paciente-está-distribuido-exponencialmente-con-una-media-de-25-minutos)
  - [31. Si λ=5/ hora y μ=6/ hora, ¿cuál es el efecto de lo siguiente sobre el tiempo promedio de espera? Asuma tiempos exponenciales entre llegadas (media de 12 minutos), tiempos de servicio exponenciales (media de 10 minutos) y una disciplina de cola PEPS (FIFO), a menos que se indique lo contrario.](#31-si-λ5-hora-y-μ6-hora-cuál-es-el-efecto-de-lo-siguiente-sobre-el-tiempo-promedio-de-espera-asuma-tiempos-exponenciales-entre-llegadas-media-de-12-minutos-tiempos-de-servicio-exponenciales-media-de-10-minutos-y-una-disciplina-de-cola-peps-fifo-a-menos-que-se-indique-lo-contrario)
  - [32. Vuelva a considerar la Pregunta #30. Responda todas las preguntas asumiendo que hay dos salas de imágenes idénticas disponibles para los pacientes.](#32-vuelva-a-considerar-la-pregunta-30-responda-todas-las-preguntas-asumiendo-que-hay-dos-salas-de-imágenes-idénticas-disponibles-para-los-pacientes)
  - [33. Vuelva a considerar la Pregunta #30. Responda todas las preguntas asumiendo que la desviación estándar de los tiempos de procesamiento es la mitad de la media (y no igual a la media, como ocurre en la distribución exponencial).](#33-vuelva-a-considerar-la-pregunta-30-responda-todas-las-preguntas-asumiendo-que-la-desviación-estándar-de-los-tiempos-de-procesamiento-es-la-mitad-de-la-media-y-no-igual-a-la-media-como-ocurre-en-la-distribución-exponencial)
  - [34. Vuelva a considerar la Pregunta #30. Responda todas las preguntas asumiendo que el tiempo de procesamiento es constante e igual a 25 minutos.](#34-vuelva-a-considerar-la-pregunta-30-responda-todas-las-preguntas-asumiendo-que-el-tiempo-de-procesamiento-es-constante-e-igual-a-25-minutos)
  - [35. Compare el rendimiento de los sistemas de las preguntas 30, 32, 33 y 34.](#35-compare-el-rendimiento-de-los-sistemas-de-las-preguntas-30-32-33-y-34)

---

## Objetivo

Cuestionario de FlexSim realtivo al capítulo del texto “Applied Simulation Modeling and Analysis
using FlexSim” 5ta Ed. 2017 (Modelado y análisis de simulación aplicada mediante FlexSim):
El cuestionario considera 35 preguntas acerca de los sistemas de colas de espera, tema que sea aborda
en el capítulo 2 del texto que titula “Introduction to Modeling and Analysis of Queueing Systems”
(Introducción al modelado y análisis de sistemas de colas).
Se recomienda usar como material de estudio la clase del 06 de mayo de 2026, el documento de 15
páginas el profesor lo compartió a sus correos. Está abierta la posibilidad de consultar en otros
medios.

## Preguntas

### 1. ¿Con qué otro nombre se le conoce a una cola (fila de espera)?

**Otro nombre para una cola:** Línea de espera (waiting line).

### 2. ¿Cuáles son los tres elementos principales de los sistemas de colas? Identifique algunas características de cada uno.

**Tres elementos principales y sus características:**
* **Clientes:** Tienen un proceso de llegada (frecuencia, tipo), comportamiento (balking,
reneging, jockeying) y una población de origen.
* **Servidores:** Se definen por su tiempo de proceso, número de servidores disponibles y
confiabilidad (tiempos de inactividad).
* **Colas:** Tienen una capacidad (finita o infinita) y una disciplina de ordenamiento
(ej. FIFO).

### 3. ¿Por qué los sistemas de colas son dinámicos?

**Naturaleza dinámica:** Las colas son dinámicas porque **cambian con el tiempo** y presentan un
**alto grado de variabilidad** en las llegadas y en los tiempos de servicio.

### 4. ¿Cuáles son los dos componentes del tiempo de entrega (lead time)?

**Componentes del Lead Time:** El tiempo de proceso (o servicio) y los tiempos de espera en cada
paso.

### 5. En la teoría de colas básica y en los modelos de simulación, ¿cuál es el orden asumido en el que un servidor atiende a los clientes?

**Orden de procesamiento asumido:** Generalmente se asume **FIFO** (First-In, First-Out), es
decir, el primero en llegar es el primero en ser atendido.

### 6. ¿Qué significa un proceso de llegada estacionario?

**Proceso de llegada estacionario:** Es aquel donde los parámetros estadísticos (como la tasa de
llegada) **no cambian con el paso del tiempo**.

### 7. ¿Cuál es la diferencia entre las acciones de balking (rechazo/no entrar a la fila) y reneging (abandonar la fila)?

**Balking vs. Reneging:** **Balking** ocurre cuando un cliente decide no entrar a la cola al
verla muy larga. **Reneging** es cuando el cliente entra a la cola pero se retira antes de ser
atendido.

### 8. Explique qué sucede cuando un cliente hace jockeying (“jockeys”cambio de fila).

**Jockeying:** Ocurre cuando un cliente **se mueve de una cola a otra** en sistemas con
múltiples servidores y colas paralelas.

### 9. Identifique las razones por las cuales un servidor podría no estar disponible el 100% del tiempo.

**Indisponibilidad del servidor:** Puede deberse a variabilidad en el tiempo de proceso, pasos
adicionales, o **tiempos de inactividad (downtime)** tanto planeados (mantenimiento) como no
planeados (fallos).

### 10. Describa los dos comportamientos diferentes que ocurren entre un servidor y una cola cuando se utiliza un recurso compartido para transportar elementos entre ambos.

**Push vs. Pull:** En sistemas con recursos compartidos de transporte:
*   **Push:** El servidor envía el producto a la cola terminada.
*   **Pull:** El servidor "jala" el producto de la cola anterior cuando está disponible.

### 11. Describa los sistemas que están definidos por las siguientes notaciones:

a. M/E/2/10//SPT
b. D/G/1
c. M/G/3

**Notación de Kendall:**
* **M/E/2/10//SPT:** Llegadas Markovianas (exponenciales), Servicio Erlang, 2 servidores,
capacidad del sistema de 10, disciplina Shortest Processing Time.
* **D/G/1:** Llegadas Determinísticas (constantes), Servicio General, 1 servidor.
* **M/G/3:** Llegadas Markovianas, Servicio General, 3 servidores.

### 12. Defina la Ley de Little.

**Ley de Little:** Establece que el Inventario en Proceso (WIP) es igual a la Tasa de Salida
(Throughput) multiplicada por el Tiempo de Ciclo ($L = \lambda W$).

### 13. Explique la relación entre el inventario en proceso (work-in-process), la tasa de salida (throughput) y el tiempo de ciclo (cycle time).

**Relación WIP, Throughput y Ciclo:** El inventario aumenta si el tiempo de ciclo crece (más
espera) o si la tasa de entrada es mayor a la capacidad de procesamiento.

### 14. Defina el dilema o compensación básica (tradeoff) que típicamente se considera en el análisis de los sistemas de colas.

**Tradeoff básico:** Es el equilibrio entre el **costo de que los clientes esperen** y el
**costo de proporcionar el servicio** (mantener servidores activos o inactivos).

### 15. Describa cómo afecta la variabilidad al rendimiento de un sistema de colas. Por ejemplo, si se incrementa la variabilidad en los tiempos de procesamiento, ¿cómo se ven afectados los tiempos de espera del sistema, el número de clientes en espera, etc.?

**Efecto de la variabilidad:** El aumento de la variabilidad (en llegadas o servicio)
**incrementa drásticamente los tiempos de espera** y el número de clientes en cola, incluso si la
utilización promedio del servidor no cambia.

### 16. Explique en qué se diferencia el estudio de los sistemas de colas desde el enfoque de la teoría de colas frente al enfoque de la simulación de eventos discretos.

**Teoría de Colas vs. Simulación:** La teoría usa **fórmulas analíticas** basadas en supuestos
simplificadores. La simulación es **basada en lógica**, permitiendo mayor detalle y complejidad sin
depender de fórmulas rígidas.

### 17. Explique la diferencia entre un promedio observacional y un promedio ponderado en el tiempo.

**Promedio observacional vs. ponderado en el tiempo:** El observacional es el promedio de datos
individuales (ej. espera media de 10 clientes). El ponderado considera cuánto tiempo el sistema
estuvo en un estado (ej. promedio de clientes en cola durante 8 horas).

### 18. Identifique algunos de los estados posibles en un sistema de colas.

**Estados posibles:** Libre (Idle), Ocupado (Busy), En falla (Downtime), Bloqueado (Blocked).

### 19. Describa a qué se refiere un sistema de eventos discretos.

**Sistema de eventos discretos:** Sistema donde los estados cambian solo en
**puntos específicos y discretos del tiempo**.

### 20. ¿Qué es una réplica (en simulación)?

**Replicación:** Es una ejecución individual de un modelo de simulación con un conjunto único de
números aleatorios para obtener una muestra de resultados.

### 21. Proporcione ejemplos de sistemas de colas y defina para cada uno:

* Los clientes en términos de sus tipos y su comportamiento en la cola.
* El servidor o servidores y su disponibilidad.
* Los problemas que necesitan ser resueltos en esos sistemas.
* Las medidas clave de rendimiento del sistema.

---

**Ejemplo 1: Sistema de colas en un banco**

* **a. Clientes y su comportamiento:** Los clientes son **personas** que llegan para realizar
retiros, consignaciones, pagos, asesorías. Su llegada puede ser programada (aplicaciones con
asignación de turno) o seguir intervalos de tiempo aleatorios. Su comportamiento de cola puede
incluir el ***jockeying*** (cambiarse de una fila a otra buscando la más rápida) o incluso el
***balking*** si ven una fila excesivamente larga y deciden usar otra sucursal bancaria. También se
puede ocurrir filas con prioridad (adultos mayores, clientes preferenciales)
* **b. Servidores y su disponibilidad:** Los servidores son
**cajeros humanos, asesores financieros, cajeros automáticos**. Su disponibilidad suele estar
planificada por horarios laborales, número limitado de cajas abiertas, pero puede verse afectada por
periodos de inactividad no planificados (fallas en el sistema informático).
* **c. Problemas a resolver:** Reducir tiempos de espera, determinar cuántos cajeros abrir,
balancear filas, evitar congestión en horas pico.
* **d. Medidas de desempeño:** El tiempo de espera de los clientes (*waiting time*), tasa de
abandono de clientes, utilización de cajeros, longitud promedio de la fila.

---

**Ejemplo 2: Sistema de colas en un hospital o urgencias**

* **a. Clientes y su comportamiento:** Los clientes son los **pacientes con diferentes niveles de
gravedad**. llegadas aleatorias, prioridad según el triaje, algunos requieren múltiples servicios
(consulta, exámenes, hospitalización).
* **b. Servidores y su disponibilidad:** Los servidores son los **médicos, enfermeros, equipos
médicos, camas hospitalarias**. Su disponibilidad se ve limitada por turnos y capacidad física.
* **c. Problemas a resolver:** Minimizar tiempos de atención crítica, asignar recursos médicos
eficientemente, manejar saturación en emergencias, priorizar pacientes graves.
* **d. Medidas de desempeño:** tiempo de espera por prioridad, ocupación de camas, número de
pacientes atendidos por hora, tiempo promedio de atención, nivel de saturación del sistema..

---

**Ejemplo 3: Reclamos de seguros esperando ser procesados**

*   **a. Clientes y su comportamiento:** Los clientes son las **solicitudes o expedientes de reclamos**. Su flujo de llegada suele ser estocástico (aleatorio). Al ser objetos inanimados en un flujo de trabajo, su comportamiento de cola es pasivo (no abandonan la fila por aburrimiento), pero pueden ser "re-priorizados" por el servidor.
*   **b. Servidores y su disponibilidad:** Los servidores son los **ajustadores o analistas de casos**. El proceso puede involucrar múltiples pasos y servidores compartidos (transporte de archivos entre departamentos).
*   **c. Problemas a resolver:** ¿Cómo asignar los casos a los analistas para reducir el tiempo total que el reclamo permanece en el sistema?.
*   **d. Medidas de desempeño:** El **tiempo de ciclo** (*cycle time*), que es fundamental para la satisfacción del cliente final que espera su indemnización.

**Resumen del enfoque técnico**
Independientemente del ejemplo, todos estos sistemas de colas involucran un **intercambio fundamental** (*tradeoff*) entre el costo de que el cliente espere y el costo de proporcionar el servicio (mantener servidores ocupados o inactivos). Como se observa en la **Figura 1.4**, el objetivo de analizar estos ejemplos es encontrar el punto de utilización óptimo (generalmente entre el 70% y 90%) para minimizar el costo total del sistema.

### 22. Si el tiempo promedio entre llegadas es de 12 minutos, ¿cuál es la tasa promedio de llegadas por hora?

**Tasa de llegada ($\lambda$):** Si el tiempo promedio entre llegadas es de 12 minutos, la tasa
horaria se calcula dividiendo los 60 minutos de una hora por dicho intervalo:
* **$\lambda = 60 / 12 = 5$ clientes por hora**.

### 23. ¿Cuál es la distribución asumida para los tiempos de servicio en los modelos básicos de la teoría de colas?

**Distribución de servicio:** Generalmente se asume la **distribución Exponencial** en modelos
básicos.

### 24. Si las tasas de llegada y de servicio para un sistema de colas M/M/1 son de 18 y 20 por hora, respectivamente, ¿qué porcentaje del tiempo se espera que el servidor esté ocupado?

**Utilización del servidor ($\rho$):** Para un sistema $M/M/1$ con una tasa de llegada de 18 y
una tasa de servicio de 20 por hora:
* **$\rho = \lambda / \mu = 18 / 20 = 0.90$**. El servidor estará ocupado el **90% del tiempo**.

### 25. Si las tasas de llegada a un sistema siguen una distribución de Poisson, ¿cómo se distribuye el tiempo entre llegadas?

**Tiempo entre llegadas:** En los procesos de Poisson, donde las llegadas ocurren de forma
aleatoria e independiente, el tiempo que transcurre entre un evento y otro sigue siempre una
**distribución exponencial**.

### 26. Un único equipo de mantenimiento se encarga de todas las reparaciones en la gran granja de servidores de Bully, la cual opera de forma continua. La tasa promedio de fallos de los servidores es de 1 por hora, en promedio toma 50 minutos reparar un servidor. Utilice la teoría de colas básica para responder a las siguientes preguntas:

* ¿Cuál es la distribución asumida para el tiempo entre fallos?
* ¿Cuál es el tiempo promedio entre fallos, en minutos?
* ¿Qué porcentaje del tiempo está ocupado el equipo de mantenimiento?
* En promedio, ¿cuántos servidores están esperando a ser reparados?
* ¿Cuál es el costo anual por tiempo de inactividad si Bully pierde $50 por cada hora que un
servidor está caído?

---

**Granja de servidores de Bully ($\lambda=1$ falla/h, Servicio=50 min):**
* **Tasa de servicio ($\mu$):** $60 / 50 = 1.2$ reparaciones por hora.
* **Utilización ($\rho$):** $1 / 1.2 = 83.33\%$.
* **Servidores esperando reparación ($L_q$):** Utilizando la fórmula de cola para $M/M/1$:
    * $L_q = \frac{\lambda^2}{\mu(\mu - \lambda)} = \frac{1^2}{1.2(1.2 - 1)} = \frac{1}{0.24} \approx \mathbf{4.17 \text{ servidores}}$.

Este es un sistema clásico de colas tipo **M/M/1** (llegadas de Poisson, tiempos de servicio
exponenciales y un solo servidor), donde la eficiencia del equipo de mantenimiento es crítica para
los costos operativos.

**Datos Base del Problema**
* **Tasa de fallas ($\lambda$):** 1 servidor por hora.
* **Tiempo de reparación promedio ($1/\mu$):** 50 minutos.
* **Costo de tiempo de inactividad:** $50 por hora por cada servidor fuera de servicio.
* **Operación:** Continua (24 horas al día, 365 días al año).

---

**a. Distribución del tiempo entre fallas**
Cuando se indica una tasa de llegada promedio (como 1 falla por hora) en un proceso aleatorio e
independiente, se asume que las llegadas siguen una distribución de Poisson. Por lo tanto, el tiempo
transcurrido entre una falla y la siguiente sigue una **distribución exponencial**.

**b. Tiempo promedio entre fallas**
Dado que la tasa de llegada ($\lambda$) es de 1 falla por hora, el tiempo promedio es simplemente el
inverso de la tasa:
* $1 / 1 \text{ hora} = 1 \text{ hora} = \mathbf{60 \text{ minutos}}$.

**c. Porcentaje de tiempo que el equipo está ocupado ($\rho$)**
La utilización del servidor ($\rho$) se calcula dividiendo la tasa de llegada por la tasa de servicio.
1. **Tasa de servicio ($\mu$):** Si se reparan en promedio en 50 minutos, la tasa por hora es $60 / 50 = \mathbf{1.2 \text{ reparaciones/hora}}$.
2. **Utilización:** $\rho = \lambda / \mu = 1 / 1.2 \approx \mathbf{0.8333}$ o **83.33%**.
3. **Análisis:** El equipo de mantenimiento está trabajando el 83.33% del tiempo, lo que deja poco
margen para absorber variaciones repentinas en las fallas.

**d. Servidores esperando reparación en promedio ($L_q$)**
Este cálculo representa la longitud de la cola (servidores que han fallado pero aún no están siendo
atendidos). Usamos la fórmula para sistemas $M/M/1$:
* $L_q = \frac{\rho^2}{1 - \rho} = \frac{0.8333^2}{1 - 0.8333} = \frac{0.6944}{0.1667} \approx \mathbf{4.17 \text{ servidores}}$.
* **Nota:** Si sumamos el servidor que está siendo reparado en ese momento, el número total de
servidores fuera de servicio ($L$) es de **5 servidores** en promedio ($L = L_q + \rho$).

**e. Costo anual del tiempo de inactividad**
Para calcular este costo, debemos considerar que **todos** los servidores en el sistema (esperando o en reparación) están generando pérdidas de $50/hora.
1. **Servidores inactivos promedio ($L$):** 5 servidores.
2. **Costo por hora del sistema:** $5 \text{ servidores} \times \$50/\text{h} = \$250/\text{hora}$.
3. **Costo anual:** $\$250/\text{h} \times 24 \text{ h/día} \times 365 \text{ días/año} = \mathbf{\$2,190,000}$.

El alto costo anual se debe a que la utilización del 83.33% sitúa al sistema en la zona de
crecimiento exponencial de la cola. Una pequeña mejora en la tasa de reparación ($\mu$) reduciría
drásticamente tanto el número de servidores en espera como el millonario costo de inactividad.

### 27. Las llamadas entran a un único centro de atención (help desk) a una tasa promedio de 5 por hora. En promedio, el operador pasa 10 minutos con cada usuario. Utilice la teoría de colas básica para responder las siguientes preguntas:

* ¿Cuál es la distribución asumida para el tiempo entre llamadas?
* ¿Cuál es el tiempo promedio entre llamadas, en minutos?
* ¿Qué porcentaje del tiempo está ocupado el operador?
* En promedio, ¿cuántos usuarios están esperando a ser atendidos?
* En promedio, ¿cuánto tiempo pasan los usuarios en la línea?

**Centro de atención telefónica ($\lambda=5$ llamadas/h, Servicio=10 min):**
* **Tasa de servicio ($\mu$):** $60 / 10 = 6$ llamadas por hora.
* **Utilización:** $5 / 6 = 83.33\%$.
* **Tiempo total en la línea ($W$):** Incluye la espera y el servicio:
    * $W = \frac{1}{\mu - \lambda} = \frac{1}{6 - 5} = \mathbf{1 \text{ hora (60 minutos)}}$.

Sistema de atención telefónica (*help desk*) utilizando las fórmulas fundamentales de la teoría de
colas para un modelo **M/M/1** (un solo servidor con llegadas y servicios aleatorios).

**Datos del Problema**
* **Tasa de llegada ($\lambda$):** 5 llamadas por hora.
* **Tiempo de servicio promedio ($1/\mu$):** 10 minutos por llamada.
* **Tasa de servicio ($\mu$):** Al procesar una llamada cada 10 minutos, el operador puede atender $\mathbf{6}$ **llamadas por hora** ($60 / 10$).

---

**a. Distribución del tiempo entre llamadas**
En la teoría básica de colas, cuando se proporciona una tasa promedio de llegada (como 5
llamadas/hora), se asume que las llegadas siguen un proceso de Poisson. Bajo este supuesto, el
tiempo que transcurre entre una llamada y la siguiente (tiempo de inter-llegada) sigue una
**distribución exponencial**.

**b. Tiempo promedio entre llamadas**
Como se menciona en las fuentes, las tasas y los tiempos son inversos. Si llegan 5 llamadas en una
hora (60 minutos):
* **Cálculo:** $60 \text{ minutos} / 5 \text{ llamadas} = \mathbf{12 \text{ minutos por llamada}}$.
* **Interpretación:** En promedio, el teléfono suena cada 12 minutos.

**c. Porcentaje de tiempo que el operador está ocupado ($\rho$)**
La utilización del servidor ($\rho$) representa la fracción de tiempo que el operador no está
inactivo (*idle*).
* **Cálculo:** $\rho = \lambda / \mu = 5 / 6 \approx \mathbf{0.8333}$ o **83.33%**.
* **Análisis:** Una utilización del 83.33% es considerablemente alta. Según la **Figura 1.9**,
cuando la utilización supera el 80%, el sistema entra en una fase donde los tiempos de espera crecen
de forma **exponencial** ante cualquier mínima variación en el flujo de llamadas.

**d. Número promedio de personas esperando ser atendidas ($L_q$)**
Este cálculo nos dice cuántas llamadas están en cola (sin contar la que está siendo procesada en ese
momento). Usamos la fórmula para sistemas $M/M/1$:
* $L_q = \frac{\lambda^2}{\mu(\mu - \lambda)} = \frac{5^2}{6(6 - 5)} = \frac{25}{6} \approx \mathbf{4.17 \text{ llamadas}}$.
* **Significado:** En promedio, siempre habrá poco más de 4 personas esperando en la línea antes de
que el operador pueda contestarles.

**e. Tiempo promedio que los clientes pasan en la línea ($W$)**
Este valor representa el **tiempo de entrega total** (*customer lead time*), que suma el tiempo de
espera en la cola más el tiempo de la conversación con el operador.
* **Cálculo:** $W = \frac{1}{\mu - \lambda} = \frac{1}{6 - 5} = \mathbf{1 \text{ hora (60 minutos)}}$.
* **Desglose:** De esa hora completa, el cliente pasa **50 minutos esperando** en silencio o con
música de espera ($W_q = W - 1/\mu$) y solo **10 minutos hablando** con el operador.

El sistema está operando muy cerca de su límite. Aunque el operador "puede" con la carga (6
llamadas/h de capacidad vs 5 de demanda), la variabilidad de las llamadas genera esperas de casi una
hora, lo que indica que el diseño actual es ineficiente para la satisfacción del cliente.

### 28. Los trabajadores de mantenimiento llegan a un centro de repuestos operado por Bob a una tasa promedio de 15 por hora. Bob requiere, en promedio, 3 minutos para procesar la solicitud de cada trabajador.

* En promedio ¿qué porcentaje del tiempo está ocupado Bob?
* En promedio ¿cuántos trabajadores de mantenimiento están en la fila esperando a ver a Bob?
* En promedio ¿cuánto tiempo tienen que esperar los trabajadores en la fila para ver a Bob y
cuánto tiempo pasan en total dentro del sistema?
* ¿Debería implementarse una mejora propuesta si esta reduce el tiempo promedio de
procesamiento de Bob en 0.25 minutos? Asuma que la mejora cuesta $10000 al año y que el tiempo
de inactividad de las máquinas (las cuales atienden los trabajadores de mantenimiento) cuesta
$100 por hora en ganancias perdidas. Considere que el centro de repuestos opera 2000 horas al año.

sistema de gestión de partes de Bob, utilizando las fórmulas de la teoría de colas para un modelo
**M/M/1** (un solo servidor, llegadas de Poisson y tiempos de servicio exponenciales), tal como se
sugiere en los principios del texto.

**Datos del Problema**
* **Tasa de llegada ($\lambda$):** 15 trabajadores de mantenimiento por hora.
* **Tiempo de servicio promedio ($1/\mu$):** 3 minutos por solicitud.
* **Tasa de servicio ($\mu$):** Al procesar una solicitud cada 3 minutos, Bob puede atender **20 trabajadores por hora** ($60 / 3$).

---

**Análisis del Desempeño Actual**

* **a. Utilización de Bob ($\rho$):**
    Representa el porcentaje de tiempo que Bob está ocupado atendiendo solicitudes.
    *   $\rho = \lambda / \mu = 15 / 20 = \mathbf{0.75 \text{ (o 75\% de su tiempo)}}$.

* **b. Trabajadores esperando en fila ($L_q$):**
    Calculamos cuántos trabajadores están en la cola (sin contar al que está siendo atendido):
    *   $L_q = \frac{\rho^2}{1 - \rho} = \frac{0.75^2}{1 - 0.75} = \frac{0.5625}{0.25} = \mathbf{2.25 \text{ trabajadores}}$.

* **c. Tiempos de espera ($W_q$) y tiempo total en el sistema ($W$):**
    Utilizando la **Ley de Little** ($L = \lambda W$) y las relaciones de tiempo:
    * **Tiempo en fila ($W_q$):** $L_q / \lambda = 2.25 / 15 = 0.15 \text{ horas} = \mathbf{9 \text{ minutos}}$.
    * **Tiempo total en el sistema ($W$):** Incluye la espera y el trámite: $9 \text{ min} + 3 \text{ min} = \mathbf{12 \text{ minutos (0.2 horas)}}$.

---

**Evaluación de la Mejora Propuesta d.**

La propuesta es reducir el tiempo de proceso en **0.25 minutos**, quedando en **2.75 minutos**.

* **Nueva capacidad de servicio ($\mu_{nuevo}$):** $60 / 2.75 \approx \mathbf{21.818 \text{ trabajadores/hora}}$.
* **Nueva utilización ($\rho_{nuevo}$):** $15 / 21.818 \approx \mathbf{0.6875}$ (68.75%).
* **Nuevo inventario en proceso ($L_{nuevo}$):** Trabajadores totales en el sistema (en espera o siendo atendidos):
  * $L = \frac{\lambda}{\mu - \lambda} = \frac{15}{21.818 - 15} = \frac{15}{6.818} \approx \mathbf{2.2 \text{ trabajadores (máquinas inactivas)}}$.

**Análisis Económico Comparativo:**
1. **Reducción de máquinas inactivas:** Antes había 3 máquinas en el sistema ($L = L_q + \rho = 2.25 + 0.75$). Con la mejora, baja a 2.2. Se "liberan" **0.8 máquinas** en promedio.
2. **Ahorro por tiempo de inactividad:** 0.8 máquinas x \$100/hora x 2,000 horas operativas al año = **\$160,000 anuales**.
3. **Costo de la mejora:** \$10,000 anuales.
4. **Beneficio Neto:** \$160,000 - \$10,000 = **\$150,000 anuales**.

Se recomienda **implementar la mejora de inmediato**. Como se observa en la **Figura 1.9**, pequeñas
reducciones en el tiempo de proceso cuando la utilización es alta (en este caso bajando del 75% al
68.75%) tienen un impacto desproporcionadamente positivo en la reducción de las colas y los costos
asociados. El ahorro de \$150,000 supera por mucho la inversión requerida.

### 29.	Considere un sistema de colas con un solo servidor y disciplina PEPS (Primero en Entrar, Primero en Salir / FIFO), donde el tiempo entre llegadas está distribuido exponencialmente con una media de 10 minutos. En promedio, el 40% de las llegadas son artículos Rojos y el resto son Azules. Los tiempos de procesamiento para los artículos Rojos y Azules están distribuidos exponencialmente con medias de 12 y 6 minutos, respectivamente.

* ¿Cuál es la tasa promedio de servicio por hora para los artículos Rojos?
* Si el sistema se simula durante 40 horas, ¿cuántos artículos Rojos se esperaría que lleguen?

**Datos del problema**
* **Tiempo entre llegadas:** Promedio de 10 minutos (distribución exponencial).
* **Composición de las llegadas:** 40% son artículos **Rojos** y 60% son artículos **Azules**.
* **Tiempo de servicio (Rojos):** Promedio de 12 minutos (exponencial).
* **Tiempo de servicio (Azules):** Promedio de 6 minutos (exponencial).

**a. Tasa promedio de servicio por hora para artículos Rojos**
La tasa de servicio ($\mu$) es la inversa del tiempo de servicio. Para calcular cuántos artículos
rojos puede procesar el servidor en una hora si solo se dedicara a ellos:
  1. **Tiempo de servicio:** 12 minutos por artículo.
  2. **Cálculo de la tasa:** $60 \text{ minutos} / 12 \text{ minutos por artículo} = \mathbf{5 \text{ artículos/hora}}$.

La capacidad teórica de procesamiento para el flujo de artículos rojos es de 5 unidades por hora.

**b. Llegadas esperadas de artículos Rojos en 40 horas**
Para conocer el volumen esperado, primero debemos determinar la tasa de llegada total del sistema y luego aplicar la proporción correspondiente a los artículos rojos:
  1. **Tasa de llegada total ($\lambda$):** Si llega un artículo cada 10 minutos, la tasa es de **6 artículos/hora** ($60/10$).
  2. **Tasa de llegada de artículos Rojos ($\lambda_{rojos}$):** Dado que representan el 40% del total:
      *   $6 \text{ artículos/hora} \times 0.40 = \mathbf{2.4 \text{ artículos rojos/hora}}$.
  3. **Total en 40 horas:**
      *   $2.4 \text{ artículos/hora} \times 40 \text{ horas} = \mathbf{96 \text{ artículos rojos}}$.

**Análisis Adicional: El Comportamiento del Sistema**
Para ofrecer una visión más completa, podemos calcular la **utilización del servidor ($\rho$)**, un concepto clave en la gestión de colas:

 * **Tiempo de servicio promedio ponderado ($\bar{P}_t$):** Como el servidor atiende ambos tipos, el tiempo medio real de servicio es la mezcla de ambos:
  *   $(0.40 \times 12 \text{ min}) + (0.60 \times 6 \text{ min}) = 4.8 + 3.6 = \mathbf{8.4 \text{ minutos por artículo}}$.
 * **Tasa de servicio promedio del sistema:** $60 / 8.4 \approx \mathbf{7.14 \text{ artículos/hora}}$.
 * **Utilización ($\rho$):** $\rho = \text{Tasa de llegada} / \text{Tasa de servicio} = 6 / 7.14 \approx \mathbf{84\%}$.

Según las gráficas de la fuente, una utilización del **84%** sitúa al sistema en una zona donde los tiempos de espera comienzan a crecer de forma **exponencial**. Cualquier incremento en la variabilidad o un pequeño aumento en la tasa de llegada (por ejemplo, si el porcentaje de artículos rojos, que son más lentos, aumentara) podría causar que el tiempo de espera se dispare drásticamente.

### 30. Considere las siguientes operaciones de una clínica para responder a las preguntas planteadas a continuación: El tiempo entre llegadas de los pacientes a la sala de imágenes (por ejemplo, rayos X) está distribuido exponencialmente con una media de 30 minutos, y el tiempo para procesar a un paciente está distribuido exponencialmente con una media de 25 minutos.

* En promedio ¿cuántos pacientes esperaría la clínica en 8 horas?
* En promedio ¿cuántos minutos tienen que esperar los pacientes desde que llegan hasta que
comienzan su proceso en la sala de imágenes?
* En promedio ¿cuántos pacientes están esperando para el proceso de imágenes?
* En promedio ¿qué porcentaje del tiempo se utiliza la sala de imágenes?

**Operaciones de Clínica ($\lambda=2$ pacientes/h, Servicio=25 min):**
* **Tasa de servicio ($\mu$):** $60 / 25 = 2.4$ pacientes por hora.
* **Tiempo de espera antes de iniciar ($W_q$):**
    * $W_q = \frac{\lambda}{\mu(\mu - \lambda)} = \frac{2}{2.4(0.4)} = \frac{2}{0.96} = 2.08 \text{ h} \approx \mathbf{125 \text{ minutos}}$.

Analizaremos paso a paso el desempeño de la clínica utilizando las fórmulas de la teoría de colas
para un sistema **M/M/1** (llegadas y servicios exponenciales con un solo servidor) y el contexto
teórico de las fuentes sobre la saturación de los sistemas.

**Datos Base del Problema**
* **Tiempo entre llegadas (Mean interarrival time):** 30 minutos.
    * **Tasa de llegada ($\lambda$):** $60 \text{ min} / 30 \text{ min} = \mathbf{2 \text{ pacientes/hora}}$.
* **Tiempo de proceso (Mean service time):** 25 minutos.
    * **Tasa de servicio ($\mu$):** $60 \text{ min} / 25 \text{ min} = \mathbf{2.4 \text{ pacientes/hora}}$.

---

**a. Pacientes esperados en 8 horas**
Este cálculo se basa en la tasa de llegada promedio:
* $2 \text{ pacientes/hora} \times 8 \text{ horas} = \mathbf{16 \text{ pacientes}}$.
* **Contexto:** Independientemente de la eficiencia del servidor, la clínica debe estar preparada para recibir este volumen de demanda en una jornada estándar.

**b. Tiempo de espera promedio antes del proceso ($W_q$)**
Utilizamos la fórmula para el tiempo de espera en la cola de un sistema $M/M/1$:
* $W_q = \frac{\lambda}{\mu(\mu - \lambda)}$
* $W_q = \frac{2}{2.4(2.4 - 2)} = \frac{2}{2.4(0.4)} = \frac{2}{0.96} = \mathbf{2.0833 \text{ horas}}$.
* **Conversión:** $2.0833 \times 60 \approx \mathbf{125 \text{ minutos}}$.
* **Análisis:** Es alarmante que para un procedimiento de solo 25 minutos, el paciente deba esperar más de **2 horas** en la sala. Según la **Figura 1.9**, esto ocurre porque la utilización es alta y la variabilidad inherente de los procesos exponenciales genera "olas" de acumulación.

**c. Número promedio de pacientes esperando ($L_q$)**
Aplicamos la **Ley de Little** ($L_q = \lambda \times W_q$), que relaciona el inventario en proceso con el tiempo de ciclo:
* $L_q = 2 \text{ pacientes/hora} \times 2.0833 \text{ horas} \approx \mathbf{4.17 \text{ pacientes}}$.
* **Análisis:** En cualquier momento aleatorio que entres a la clínica, encontrarás en promedio a 4
personas sentadas esperando su turno para el examen de imágenes.

**d. Utilización de la instalación ($\rho$)**
La utilización es la proporción de tiempo que el equipo está siendo operado:
* $\rho = \lambda / \mu = 2 / 2.4 \approx \mathbf{0.8333}$ o **83.33%**.
* **Análisis Crítico:** Aunque el 83.33% de utilización puede parecer un buen indicador de
"productividad", las fuentes advierten que cuando la utilización supera el **70-80%**, los tiempos
de espera aumentan de forma **exponencial**. En este caso, el equipo está tan ocupado que no tiene
margen para absorber la variabilidad de las llegadas de los pacientes, lo que resulta en las largas
esperas calculadas en el punto b.

**Conclusión del Desempeño**
La clínica opera en una zona de **alto riesgo de congestión**. Al tener una utilización del 83.33%,
se encuentra en la parte empinada de la curva de tiempo de espera (Figura 1.3). Para mejorar este
sistema, se debería considerar reducir la variabilidad del proceso (hacerlo más constante) o añadir
capacidad, ya que pequeñas reducciones en el tiempo de proceso tendrían un impacto masivo en la
reducción de la cola.

### 31. Si λ=5/ hora y μ=6/ hora, ¿cuál es el efecto de lo siguiente sobre el tiempo promedio de espera? Asuma tiempos exponenciales entre llegadas (media de 12 minutos), tiempos de servicio exponenciales (media de 10 minutos) y una disciplina de cola PEPS (FIFO), a menos que se indique lo contrario.

* Un solo servidor.
* Dos servidores en paralelo.
* Tiempos de servicio constantes de 10 minutos.

**Efectos en el tiempo de espera ($W_q$) con $\lambda=5, \mu=6$:**
* **a. Servidor único ($M/M/1$):** La espera es de **50 minutos**.
* **b. Dos servidores paralelos (M/M/2):** 2.1 min.
* **c. Tiempo constante ($M/D/1$):** Al eliminar la variabilidad del servicio ($cv=0$), la espera se reduce exactamente a la mitad: **25 minutos**.

Se realiza un análisis comparativo de cómo el tiempo de espera promedio ($W_q$ o $\bar{W}_t$) se ve
afectado por la configuración del sistema, la capacidad y la variabilidad, utilizando los parámetros
$\lambda = 5$ clientes/hora y $\mu = 6$ clientes/hora.

**Parámetros del Sistema**
* **Tasa de llegada ($\lambda$):** 5 clientes/hora (1 cada 12 minutos).
* **Tasa de servicio ($\mu$):** 6 clientes/hora (1 cada 10 minutos).
* **Tiempo promedio de proceso ($\bar{P}_t$):** 10 minutos.

---

**a. Servidor Único (Modelo M/M/1)**
En este escenario, tanto las llegadas como los servicios son aleatorios (exponenciales).
* **Cálculo de Utilización ($\rho$):** $\rho = 5 / 6 \approx \mathbf{0.8333}$ (83.33%).
* **Coeficiente de Variación ($c_v$):** Para una distribución exponencial, $c_v = 1$.
* **Tiempo de espera ($\bar{W}_t$):** Aplicando la ecuación de Pollaczek-Khintchine presente en las fuentes:
    $$\bar{W}_t = 0.5(1 + c_v) \left( \frac{\rho}{1 - \rho} \right) (\bar{P}_t)$$
    $$\bar{W}_t = 0.5(1 + 1) \left( \frac{0.8333}{0.1667} \right) (10) = 1 \times 5 \times 10 = \mathbf{50 \text{ minutos}}$$
* **Análisis:** Con una utilización superior al 80%, el sistema se encuentra en la "zona de peligro"
de la curva exponencial, donde la variabilidad causa largas colas. El cliente espera 5 veces más de
lo que dura su servicio.

---

**b. Dos Servidores Paralelos (Modelo M/M/2)**
Al añadir un segundo servidor idéntico, la capacidad total del sistema se duplica, lo que impacta
drásticamente la utilización.
* **Nueva Utilización ($\rho$):** $\lambda / (s \times \mu) = 5 / (2 \times 6) \approx \mathbf{0.4167}$ (41.67%).
* **Tiempo de espera ($\bar{W}_t$):** Al reducir la utilización a menos de la mitad, el sistema se
desplaza hacia la "parte plana" de la curva de espera.
  * El tiempo de espera cae drásticamente a aproximadamente **2.1 minutos**.
* **Análisis:** Esta es la mejora más potente. Como indican las fuentes, añadir capacidad es a
menudo la única forma de reducir significativamente las colas en sistemas con alta variabilidad.

---

**c. Tiempos de Servicio Constantes de 10 min (Modelo M/D/1)**
Aquí mantenemos un solo servidor, pero eliminamos la variabilidad del proceso (el servicio siempre
dura exactamente 10 minutos).
* **Utilización ($\rho$):** Sigue siendo **83.33%**.
* **Coeficiente de Variación ($c_v$):** Un patrón constante tiene un coeficiente de variación de **cero**.
* **Tiempo de espera ($\bar{W}_t$):**
    $$\bar{W}_t = 0.5(1 + 0) \left( \frac{0.8333}{0.1667} \right) (10) = 0.5 \times 5 \times 10 = \mathbf{25 \text{ minutos}}$$
* **Análisis:** Al eliminar la variabilidad del servidor, el tiempo de espera se reduce exactamente
a la **mitad** (de 50 a 25 min). Esto demuestra que la variabilidad es "la mitad del problema" en la
formación de colas.

**Comparación y Conclusión**
Según el texto, existen tres formas de reducir el tiempo de espera: reducir la utilización, añadir
máquinas o reducir la variabilidad.
1. **La variabilidad importa:** Pasar de servicio aleatorio (M/M/1) a constante (M/D/1) reduce la
espera un 50%.
2. **La capacidad manda:** Añadir un servidor (M/M/2) es casi **12 veces más efectivo** que eliminar
la variabilidad en este caso, reduciendo la espera en un 95%.
3. **Relación Exponencial:** Como se observa en la **Figura 1.9**, pequeñas reducciones en la
utilización o la varianza cuando el sistema está cerca del 90% producen beneficios masivos en el
tiempo de ciclo.

### 32. Vuelva a considerar la Pregunta #30. Responda todas las preguntas asumiendo que hay dos salas de imágenes idénticas disponibles para los pacientes.

Es necesario analizar cómo cambia el desempeño del sistema de la clínica al pasar de un único
servidor (M/M/1) a un sistema con **dos instalaciones de imágenes idénticas** (M/M/2). Esta
modificación altera drásticamente la dinámica de las colas, especialmente porque reduce la
saturación de los servidores.

Los parámetros base derivados de la pregunta 30 son:
* **Tasa de llegada ($\lambda$):** 1 paciente cada 30 min = **2 pacientes/hora**.
* **Tasa de servicio ($\mu$):** 1 paciente cada 25 min = **2.4 pacientes/hora** por cada instalación.
* **Número de servidores ($s$):** **2**.

**a. Pacientes esperados en 8 horas**
Esta cifra depende únicamente de la tasa de llegada, por lo que no cambia al añadir servidores:
*   $2 \text{ pacientes/hora} \times 8 \text{ horas} = \mathbf{16 \text{ pacientes}}$.

**b. Utilización de las instalaciones (Parte d)**
En un sistema multiservidor, la utilización ($\rho$) se distribuye entre la capacidad total disponible:
* $\rho = \lambda / (s \times \mu) = 2 / (2 \times 2.4) = 2 / 4.8 \approx \mathbf{41.67\%}$.
* **Comparativa:** En la pregunta 30, con un solo servidor, la utilización era del **83.33%**. Al
duplicar la capacidad, el uso de las máquinas cae a la mitad, alejándose de la zona crítica de
saturación.

**c. Tiempo de espera promedio ($W_q$)**
El impacto más notable se observa aquí. Mientras que en el sistema de un solo servidor el tiempo de
espera era de **125 minutos**, con dos servidores baja a aproximadamente **5.25 minutos**.

**¿Por qué esta reducción tan drástica?**
* **La curva exponencial:** Según las fuentes, el tiempo de espera crece de forma exponencial a
medida que la utilización se acerca al 100%. Al reducir la utilización del 83.3% al 41.7%, el
sistema se mueve de la "parte empinada" de la curva (Figura 1.9) a la "parte plana", donde la
variabilidad tiene un impacto mínimo.
* **Flexibilidad:** Con dos servidores, el sistema puede procesar a dos pacientes simultáneamente,
lo que reduce la probabilidad de que una llegada encuentre a todos los servidores ocupados.

**d. Pacientes esperando en promedio ($L_q$)**
Utilizando la **Ley de Little** ($L_q = \lambda \times W_q$), que relaciona el inventario en proceso
con el tiempo de ciclo:
* $L_q = 2 \text{ pacientes/hora} \times 0.0875 \text{ horas} \approx \mathbf{0.175 \text{ pacientes}}$.
* **Análisis:** En promedio, habrá menos de un paciente esperando (específicamente, solo el 17.5%
del tiempo habrá alguien en cola). Esto es una mejora inmensa frente a los **4.17 pacientes** que
esperaban en el sistema original.

**Conclusión:** La adición de una segunda instalación es la forma más efectiva de eliminar colas
persistentes, ya que atacar la utilización mediante el **aumento de capacidad** tiene un efecto
mucho mayor que simplemente intentar reducir la variabilidad del proceso.

### 33. Vuelva a considerar la Pregunta #30. Responda todas las preguntas asumiendo que la desviación estándar de los tiempos de procesamiento es la mitad de la media (y no igual a la media, como ocurre en la distribución exponencial).

Se analiza el impacto de la reducción de la variabilidad en el sistema de la clínica. En este
escenario, dejamos de tener una distribución exponencial pura en el servicio (donde la desviación
estándar es igual a la media, $c_v = 1$) para pasar a una situación donde la variabilidad es menor
($c_v = 0.5$).

Este es un modelo **M/G/1** (llegadas de Poisson y servicio de distribución general), lo que
requiere el uso de la **Ecuación de Pollaczek-Khintchine** para determinar el tiempo de espera,.

**Datos del Problema**
* **Tasa de llegada ($\lambda$):** 2 pacientes/hora (según pregunta 30).
* **Tiempo medio de servicio ($\bar{P}_t$):** 25 minutos.
* **Tasa de servicio ($\mu$):** 2.4 pacientes/hora.
* **Desviación estándar ($\sigma$):** 12.5 minutos (la mitad de la media, 25 min).
* **Coeficiente de variación ($c_v$):** $\sigma / \text{media} = 12.5 / 25 = \mathbf{0.5}$.

---

**a. Pacientes esperados en 8 horas**
Dado que el patrón de llegada no ha cambiado respecto a la pregunta original, la cifra se mantiene
igual:
*   $2 \text{ pacientes/hora} \times 8 \text{ horas} = \mathbf{16 \text{ pacientes}}$.

**b. Tiempo de espera promedio antes de iniciar ($W_q$ o $\bar{W}_t$)**
Aplicamos la fórmula que relaciona utilización ($\rho$) y variabilidad ($c_v$):
1. **Utilización ($\rho$):** $\lambda / \mu = 2 / 2.4 \approx \mathbf{0.8333}$ (83.33%).
2. **Cálculo:**
    $$\bar{W}_t = 0.5(1 + c_v^2) \left( \frac{\rho}{1 - \rho} \right) (\bar{P}_t)$$
    $$\bar{W}_t = 0.5(1 + 0.5^2) \left( \frac{0.8333}{0.1667} \right) (25)$$
    $$\bar{W}_t = 0.5(1.25) \times (5) \times (25)$$
    $$\bar{W}_t = 0.625 \times 125 = \mathbf{78.125 \text{ minutos}}$$

3. **Comparativa:** En el sistema original (pregunta 30) la espera era de **125 minutos**. Al
reducir la desviación estándar a la mitad, el tiempo de espera bajó un **37.5%**, pasando a 78
minutos.

**c. Número promedio de pacientes esperando ($L_q$)**
Usamos la **Ley de Little** ($L_q = \lambda \times W_q$):
* $L_q = 2 \text{ pacientes/hora} \times (78.125 / 60) \text{ horas} \approx \mathbf{2.60 \text{ pacientes}}$.
* **Análisis:** En el sistema original había **4.17 pacientes** esperando en promedio. La reducción
de la varianza en el proceso permitió "limpiar" la sala de espera en casi 1.5 personas de forma permanente.

**d. Utilización de la instalación ($\rho$)**
La utilización depende de las tasas medias, no de la varianza, por lo que se mantiene igual:
* $\rho = 2 / 2.4 \approx \mathbf{83.33\%}$.

---

**Análisis del Impacto de la Variabilidad**
Este ejercicio demuestra una de las lecciones fundamentales de las fuentes: **"La variabilidad es la
raíz de las colas"**,.

* **La "Magia" de la Consistencia:** Aunque el equipo de la clínica sigue tardando los mismos 25
minutos en promedio por paciente y la máquina está ocupada el mismo 83% del tiempo, el simple hecho
de que los tiempos de proceso sean más consistentes (menos dispersos) reduce drásticamente la
formación de filas.
* **Relación con la Curva de Espera:** Como se observa en la **Figura 1.3**, un sistema con alta
utilización ($\rho > 0.80$) es extremadamente sensible a la variabilidad. Al bajar el coeficiente de
variación de 1.0 a 0.5, "empujamos" el desempeño del sistema hacia abajo en la curva de tiempo de
espera, evitando los picos de congestión extrema que ocurren cuando se juntan varios servicios
largos seguidos,.

### 34. Vuelva a considerar la Pregunta #30. Responda todas las preguntas asumiendo que el tiempo de procesamiento es constante e igual a 25 minutos.

**Tiempo de servicio constante (25 min):**
* Al ser constante, $c_v = 0$. La espera es $\bar{W}_t = 0.5(1 + 0)(5)(25) = \mathbf{62.5 \text{ minutos}}$.

Se realiza un análisis técnico del desempeño de la clínica bajo un escenario de **tiempos de
servicio constantes**. En este caso, el sistema se comporta como un modelo **M/D/1** (llegadas de
Poisson y servicio determinístico o constante).

Este cambio es fundamental porque elimina por completo la variabilidad del servidor (el examen
siempre dura exactamente 25 minutos), lo que reduce el coeficiente de variación del servicio ($c_v$)
a **cero**.

**Datos del Problema (Reconsiderando la pregunta 30)**
* **Tasa de llegada ($\lambda$):** 2 pacientes/hora (1 cada 30 min).
* **Tiempo de servicio ($\bar{P}_t$):** 25 minutos constantes.
* **Tasa de servicio ($\mu$):** 2.4 pacientes/hora.
* **Coeficiente de variación del servicio ($c_v$):** **0** (por ser constante).

---

**a. Pacientes esperados en 8 horas**
Dado que la frecuencia de llegada de los pacientes no se ve afectada por el tipo de equipo o
proceso, la cifra se mantiene igual a los cálculos anteriores:
* $2 \text{ pacientes/hora} \times 8 \text{ horas} = \mathbf{16 \text{ pacientes}}$.

**b. Tiempo de espera promedio antes de iniciar ($W_q$ o $\bar{W}_t$)**
Para calcular la espera cuando el servicio es constante, aplicamos la ecuación de
Pollaczek-Khintchine con $c_v = 0$,:
1. **Utilización ($\rho$):** $\lambda / \mu = 2 / 2.4 \approx \mathbf{0.8333}$ (83.33%).
2. **Cálculo:**
    $$\bar{W}_t = 0.5(1 + 0) \left( \frac{0.8333}{1 - 0.8333} \right) (25)$$
    $$\bar{W}_t = 0.5 \times (5) \times (25) = \mathbf{62.5 \text{ minutos}}$$
3. **Comparativa:** En el sistema original con servicio aleatorio (pregunta 30), la espera era de
**125 minutos**. Al hacer que el tiempo de proceso sea constante, la espera se reduce exactamente a
la **mitad**, a pesar de que la máquina sigue trabajando el mismo 83% del tiempo,.

**c. Número promedio de pacientes esperando ($L_q$)**
Usamos la **Ley de Little** ($L_q = \lambda \times W_q$):
* $L_q = 2 \text{ pacientes/hora} \times (62.5 / 60) \text{ horas} \approx \mathbf{2.08 \text{ pacientes}}$.
* **Análisis:** Al eliminar la varianza del servidor, el número de personas en la sala de espera
baja de **4.17** (en el modelo M/M/1) a solo **2.08**,.

**d. Utilización de la instalación ($\rho$)**
La utilización es una medida de la carga de trabajo media y no depende de la varianza:
*   $\rho = \lambda / \mu = 2 / 2.4 \approx \mathbf{83.33\%}$.

---

**Importancia de la Respuesta: El Impacto de la Estandarización**

Este ejercicio ilustra un concepto crítico de la simulación aplicada: **la variabilidad "crea" la
mitad de la fila**,.

1. **Mitigación del Caos:** En un sistema M/M/1 (pregunta 30), las colas crecen porque a veces
llegan muchos pacientes juntos y, casualmente, el servicio de esos pacientes también tarda más de lo
normal. Al fijar el tiempo de servicio en 25 minutos exactos, eliminamos la mitad de esa incertidumbre.
2. **Límite Teórico:** Como se observa en la **Figura 1.3**, para una utilización fija (en este caso
83%), el tiempo de espera mínimo posible se alcanza cuando el coeficiente de variación es cero. No
se puede reducir más la fila sin añadir capacidad o reducir la tasa de llegada.
3. **Decisión de Gestión:** Si la clínica no puede comprar otra máquina (como en la pregunta 32), su
mejor opción es **estandarizar el proceso** para que sea lo más constante posible. Esto reduce la
espera de los pacientes de 125 a 62.5 minutos sin gastar en nuevo equipamiento, solo mediante la
mejora del método de trabajo,.

### 35. Compare el rendimiento de los sistemas de las preguntas 30, 32, 33 y 34.

**Conclusión:** Al comparar los resultados, se evidencia que
**añadir una segunda instalación (ejercicio 32)** reduce la espera de 125 a solo 5.25 minutos,
siendo mucho más efectivo que solo reducir la variabilidad o el tiempo de proceso.
