# La autoridad del evaluador es el punto más débil del proyecto, y el criterio humano no se puede eliminar

- **Fecha:** 2026-10-03
- **Autor:** Facu
- **Estado:** abierto · **⚠ prioridad alta para el pitch**

## Qué encontré

Todo ROBOLEDGER se apoya en que las habilidades del robot son "verificables". Pero en el MVP, quien evalúa y quien resuelve disputas es CalchAI, que además cobra una comisión por cada trabajo. El evaluador es juez y parte: le conviene aprobar robots.

La blockchain no resuelve esto. Garantiza que la firma de la evaluación es auténtica y que nadie la modificó, pero no que el juicio sea correcto. Es como un escribano: certifica que firmaste vos, no que el contrato sea bueno.

## Mecanismos posibles para darle autoridad al evaluador

| Mecanismo | Equivalente en evaluación de personas | Qué resuelve | Dónde queda el criterio humano |
|---|---|---|---|
| Evaluación reproducible: metodología y set de prueba publicados con hash, para que cualquiera pueda volver a correrla | Test estandarizado con baremo público | Se puede auditar sin confiar en el evaluador | En quién etiquetó las imágenes de prueba y en quién definió los criterios |
| Reputación del evaluador (registro de validación de ERC-8004) | Assessor con trayectoria comprobable | Los evaluadores que aprueban mal quedan expuestos | En quién decide que una evaluación pasada estuvo mal |
| Evaluador con plata en garantía, que la pierde si aprobó mal | Responsabilidad profesional | Hace caro mentir | En quién decide que se equivocó y debe perder la garantía |
| Varios evaluadores independientes | Panel de entrevistadores, confiabilidad entre evaluadores | Un solo evaluador no decide | En cada evaluador, aunque el error individual pesa menos |
| Entidades acreditadas por industria | Certificaciones oficiales | Autoridad externa reconocida | En la entidad acreditadora |

## El punto central: ningún mecanismo elimina el criterio humano

La última columna de la tabla es el hallazgo. Cada mecanismo traslada la decisión humana a otro lugar, pero no la hace desaparecer:

- La evaluación reproducible es la más fuerte para una tarea como clasificar tomates, pero la "respuesta correcta" de cada imagen la decidió una persona al etiquetarla.
- Poner plata en riesgo **obliga** a tener un árbitro. Para quitarle la garantía a un evaluador alguien tiene que decidir que se equivocó, y esa decisión es humana. Cuanto más dinero hay en juego, más importa quién arbitra y con qué reglas.

## Qué implica para el proyecto

1. **Riesgo de pitch.** Si el discurso es débil en este punto, se cae la premisa de "verificable" y con ella todo lo demás: la identidad, el historial y el reparto pasan a registrar con prolijidad algo que nadie comprobó. Es la pregunta que más probablemente haga un jurado con experiencia en cripto.
2. **No podemos prometer "sin intermediarios" ni "trustless".** Sería falso y el jurado lo desarma en una pregunta.
3. **La respuesta honesta también es la más fuerte:** no eliminamos el criterio humano, lo hacemos visible, atribuible y con responsabilidad. Cada evaluación registra qué metodología se usó, quién etiquetó, quién evaluó y con qué resultado. Es coherente con la idea central del proyecto, que es atribuir la contribución humana.
4. **El árbitro de disputas tiene que estar definido** antes de cualquier mecanismo con garantía. En el MVP es CalchAI, y hay que decirlo así.

## Qué propongo

1. **Para la demo:** evaluación reproducible. Publicamos la metodología, el hash del set de prueba y el origen de las etiquetas (dataset Laboro Tomato, ver [hallazgo del dataset](2026-10-03-dataset-laboro-tomato.md)), y mostramos que cualquiera puede volver a correrla.
2. **En el pitch:** responder la pregunta de frente con la frase del punto 3. Está desarrollado en el bloque de riesgo de `docs/pitch/PITCH.md`.
3. **Para el roadmap:** varios evaluadores con reputación y garantía, con reglas de arbitraje públicas.
4. **Decisión pendiente (Fede):** quién arbitra las disputas después del piloto y con qué reglas.
