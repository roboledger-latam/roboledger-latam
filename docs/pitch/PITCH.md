# Esqueleto del pitch

Borrador. Pensado para un video de alrededor de 3 minutos y un jurado mayormente de inversores (ver [hallazgo de bases](../hallazgos/2026-10-03-bases-metropolis.md)). Un inversor se pregunta tres cosas: si el problema es real, si el equipo lo puede resolver y si puede ser un negocio grande. El pitch responde esas tres, en ese orden.

Estado: esqueleto v0 · Responsable: Facu · Revisan: Fede (producto), Franco y Nico (que lo técnico sea correcto)

## Estructura y tiempos

| # | Bloque | Tiempo | Qué tiene que quedar claro |
|---|---|---|---|
| 1 | Problema | 0:00 a 0:25 | Contratar una máquina hoy es un acto de fe |
| 2 | Qué hicimos | 0:25 a 0:45 | Identidad, evaluación, contratación y reparto verificables |
| 3 | Demo | 0:45 a 2:15 | Funciona de punta a punta, con plata real de testnet |
| 4 | Por qué ahora y por qué Monad | 2:15 a 2:30 | Hay miles de agentes y ninguna forma estándar de confiar en ellos |
| 5 | Negocio | 2:30 a 2:50 | Suscripción por robot más comisión por trabajo liquidado |
| 6 | Cierre | 2:50 a 3:00 | Qué sigue y quiénes somos |

La demo se lleva la mitad del tiempo a propósito: el jurado tiene que ver el producto andando, no slides que hablan de él.

## 1. Problema (25 s)

Idea central: un cliente que quiere contratar un agente o un robot no tiene cómo saber si sabe hacer lo que dice, quién lo entrenó ni qué hizo antes. Y la persona que le enseñó una habilidad no cobra nada cuando esa habilidad genera ingresos.

Guion tentativo:
> Hay miles de agentes de IA ofreciendo trabajo, y pronto robots físicos. Para contratar uno, hoy le tenés que creer al que lo vende. No sabés si sabe hacer lo que promete, quién lo entrenó ni qué hizo antes. Y la persona que le enseñó no ve un peso cuando esa habilidad empieza a facturar.

## 2. Qué hicimos (20 s)

Cuatro piezas, una frase cada una:
- **Identidad:** cada robot tiene un registro onchain con ERC-8004.
- **Evaluación:** cada habilidad se prueba con casos que el robot nunca vio, y el evaluador firma el resultado.
- **Contratación:** el pago queda retenido hasta que el cliente acepta la entrega.
- **Reparto:** la tesorería del robot cubre sus gastos y le paga al propietario y a quienes lo entrenaron.

## 3. Demo (90 s)

Un solo recorrido, sin cortes, siguiendo al robot clasificador de tomates:

| Paso | Qué se ve en pantalla | Segundos |
|---|---|---|
| a | Perfil del robot: identidad, skill `tomato-ripeness v1`, quién la entrenó | 10 |
| b | Evaluación: resultado sobre imágenes separadas, firma del evaluador | 15 |
| c | Un cliente contrata la clasificación de un lote y deposita el pago | 15 |
| d | El robot clasifica el lote y entrega los resultados | 15 |
| e | El cliente acepta y se ejecuta el reparto, que se ve en el explorador de Monad | 20 |
| f | Historial del robot actualizado: trabajo, skill usada, movimientos | 10 |
| g | Caso de error: contratación sin entrega y devolución automática | 5 |

Reglas para la demo:
- Lo simulado se dice en voz alta: el cuerpo del robot y su batería son simulados; la clasificación y los pagos son reales (en testnet).
- Mostrar transacciones en el explorador de Monad, no solo en nuestra interfaz. Es lo que vuelve creíble la palabra "verificable".
- Grabar con un plan B: si algo falla en vivo, usamos la grabación.

## 4. Por qué ahora y por qué Monad (15 s)

- ERC-8004 está naciendo como estándar de identidad para agentes. Construir sobre él ahora nos pone del lado del estándar.
- Cada trabajo genera varias transacciones (depósito, entrega, aceptación, reparto). Monad las hace rápidas y baratas, y eso permite cobrar trabajos chicos.

Pendiente: que Franco y Nico confirmen o corrijan este argumento técnico.

## 5. Negocio (20 s)

- **Suscripción** para los propietarios que administran robots en la plataforma.
- **Comisión** sobre cada trabajo liquidado (en el ejemplo, 5 % del saldo distribuible).
- **Primer mercado:** agro en América Latina. Clasificar la maduración es una tarea repetitiva, medible y con demanda en cada cosecha.

Pendiente: un dato concreto de mercado (por ejemplo, producción de tomate o de hortalizas en la región) con fuente verificable. No inventar cifras.

## 6. Cierre (10 s)

- Qué sigue: más habilidades, varios entrenadores por habilidad, adaptadores para robots físicos.
- Equipo: nombres y una línea por persona.
- Frase final: lo que pidamos al jurado o la visión, en una oración simple.

## Preguntas que el jurado probablemente haga

Conviene tener la respuesta preparada aunque no entre en el video.

| Pregunta | Respuesta corta |
|---|---|
| ¿Qué impide que el robot mienta sobre su trabajo? | El hash prueba integridad, no calidad. La calidad la comprueban la evaluación previa y la aceptación del cliente. |
| ¿Qué pasa si el entrenador copia su aporte a otra plataforma? | No lo podemos detectar. Pagamos por los trabajos que se ejecutan dentro de la plataforma con la versión atribuida. |
| ¿Por qué blockchain y no una base de datos? | Fondos retenidos y repartos que ninguna de las partes puede alterar, incluida la plataforma. |
| ¿Cómo se pasa de virtual a físico? | Cada robot físico necesita verificar el vínculo con el dispositivo y una evaluación en condiciones reales. La arquitectura ya separa al agente del adaptador del robot. |
| ¿Quién paga la evaluación? | Pendiente de definir con Fede. |
| ¿Es para el agro o para cualquier industria? | La plataforma sirve para cualquier tarea evaluable. Arrancamos por el agro porque clasificar maduración es fácil de medir y tiene demanda en cada cosecha. |
| ¿Por qué blockchain y no Mercado Pago más una base de datos? | Por cuatro cosas que un sistema tradicional no resuelve bien: la plataforma no puede tocar la plata ni cambiar el reparto, el robot tiene fondos propios con límites de gasto, se puede pagar a entrenadores en cualquier país aunque el monto sea chico, y el historial del robot no queda atado a CalchAI (ERC-8004 es un estándar abierto). |
| ¿Son robots físicos o agentes en la nube? | Hoy, agentes en la nube auditados: el robot virtual es un agente de IA que hace una tarea real. Los robots físicos son el siguiente paso y requieren verificar el vínculo con el dispositivo y evaluarlo en condiciones reales. |
| ¿Cuál es el diferencial, si cada pieza ya existe? | La combinación, y sobre todo dos piezas: skills versionadas que hay que re-certificar cuando cambian, y regalías automáticas para quien entrena. *Pendiente: relevamiento de competencia para confirmarlo.* |
| ¿Quién le da autoridad al evaluador? | Ver el bloque de riesgo de abajo. Es la pregunta más importante del pitch. |

## ⚠ Riesgo de pitch: la autoridad del evaluador

**Esta es la pregunta que puede tirar abajo el proyecto entero frente al jurado.** Todo ROBOLEDGER se apoya en la palabra "verificable". Si cuando preguntan quién certifica que el robot hizo bien el trabajo la respuesta es débil o evasiva, el jurado concluye que la verificación es de mentira y que todo lo demás (identidad, historial, reparto) registra con mucha prolijidad algo que nadie comprobó.

**La trampa:** responder que la blockchain lo garantiza. La blockchain garantiza que la firma es auténtica, no que el juicio sea correcto.

**La segunda trampa:** creer que se resuelve sacando a las personas del medio. Cualquier mecanismo que propongamos termina en una decisión humana:
- Una evaluación reproducible depende de quién etiquetó las imágenes de prueba y de quién escribió los criterios.
- Un evaluador que pone plata en garantía solo la pierde si alguien decide que se equivocó. Esa decisión la toma una persona o un grupo de personas.
- Varios evaluadores reducen el error de uno solo, pero siguen siendo personas aplicando un criterio.

**Lo que decimos:** no eliminamos el criterio humano, lo hacemos visible, atribuible y con responsabilidad. Cada evaluación dice qué metodología se usó, quién etiquetó, quién evaluó y con qué resultado, y cualquiera puede volver a correrla. Es coherente con el resto del proyecto, que justamente se basa en atribuir la contribución humana.

**Lo que no decimos nunca:** "sin intermediarios", "trustless", "sin necesidad de confiar en nadie". Un inversor con experiencia en cripto lo desarma en una pregunta.

Detalle completo en el [hallazgo sobre la autoridad del evaluador](../hallazgos/2026-10-03-autoridad-del-evaluador.md).

## Pendientes antes de grabar

- [ ] Confirmar si el video va en inglés
- [ ] Confirmar el largo máximo del video en las reglas oficiales
- [ ] Dato de mercado con fuente
- [ ] Revisión técnica de Franco y Nico
- [ ] Guion final palabra por palabra
- [ ] Ensayo con cronómetro
