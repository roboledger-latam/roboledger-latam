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

## Pendientes antes de grabar

- [ ] Confirmar si el video va en inglés
- [ ] Confirmar el largo máximo del video en las reglas oficiales
- [ ] Dato de mercado con fuente
- [ ] Revisión técnica de Franco y Nico
- [ ] Guion final palabra por palabra
- [ ] Ensayo con cronómetro
