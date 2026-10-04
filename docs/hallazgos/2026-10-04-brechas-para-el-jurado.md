# Cinco brechas que puede explotar el jurado, y qué peso real tiene el hash

- **Fecha:** 2026-10-04
- **Autor:** Facu
- **Estado:** abierto · **⚠ prioridad alta para el pitch**

## Qué encontré

Además de la autoridad del evaluador (ver [hallazgo anterior](2026-10-03-autoridad-del-evaluador.md)), hay cinco brechas que un jurado técnico o con experiencia en cripto puede detectar. Están ordenadas por gravedad.

### 1. Nada prueba que el robot usó la versión evaluada

El contrato fija "tomato-ripeness v1, aprobada con 88 %". El worker ejecuta y entrega, pero nada garantiza que corrió la v1 y no una versión más barata, otro modelo o una respuesta inventada. El hash prueba qué se entregó, no qué lo produjo. Es como certificar a un cirujano y que después opere otra persona.

- **Solución técnica posible:** ejecución en entornos certificados (TEE) que firman qué código corrió. No está en el MVP.
- **Respuesta para el pitch:** reconocerlo como límite del MVP y ponerlo en el roadmap. No negarlo.

### 2. Reputación inflada con contrataciones falsas

Un dueño puede crear varias wallets, contratar a su propio robot, aceptar todas las entregas y fabricar un historial de "50 trabajos exitosos" pagando solo las comisiones. En cripto esto se conoce como *wash trading*. El historial es una de las cuatro patas del proyecto y hoy se puede falsificar.

- **Mitigaciones posibles:** ponderar la reputación por cliente distinto y verificado, mostrar cuántos clientes únicos tiene el robot y no solo cuántos trabajos, y que la comisión de plataforma haga caro el autoabastecimiento.

### 3. La demo contradice la premisa de atribución

El proyecto promete que quien entrena cobra regalías. Pero los ejemplos de enseñanza de la demo salen del dataset Laboro Tomato, etiquetado por personas de Laboro.AI que no cobran nada. Si un miembro del equipo carga esas fotos como entrenador y recibe el 10 %, estamos cobrando regalías por el trabajo de otros, sobre un dataset con licencia no comercial.

- **Es la única brecha que hay que resolver antes de grabar la demo.** Ver Issue abierto.

### 4. El modelo de IA puede cambiar sin aviso

Si el agente usa un modelo de un proveedor externo, el proveedor puede actualizarlo sin avisar: la versión evaluada pasa a correr sobre un modelo distinto. Además, estos modelos no siempre responden igual ante la misma entrada, lo que debilita el argumento de evaluación reproducible.

- **Mitigaciones posibles:** fijar la versión exacta del modelo en la configuración de la skill, registrarla en la evaluación y re-evaluar si el proveedor la cambia. Medir la variación corriendo la evaluación más de una vez.

### 5. El cliente puede rechazar trabajos bien hechos para no pagar

Si el cliente rechaza, los fondos quedan bloqueados hasta resolver la disputa, y la disputa la resuelve CalchAI. Vuelve el problema del árbitro centralizado.

- **Mitigaciones posibles:** aceptación automática si el cliente no responde en un plazo, y reputación también para clientes (cuántas disputas abre y cuántas pierde).

### Otras de menor peso

- **Pagos en un token volátil:** ningún cliente real va a querer pagar en MON. Para un piloto real hacen falta stablecoins.
- **Tiempo y estándar:** el proyecto cambió de idea el 3 de octubre, con 10 días por delante, y ERC-8004 está en borrador y puede cambiar.

## Qué resuelve blockchain y qué no

El documento del proyecto no pone todo en blockchain: imágenes y resultados quedan fuera de la cadena. El riesgo está en el relato, si el pitch vende "verificable gracias a blockchain".

| Qué | Lo resuelve blockchain | Lo resuelve otra cosa |
|---|---|---|
| Que nadie toque la plata retenida | ✅ | |
| Reparto automático e inalterable | ✅ | |
| Que un registro no se modifique después | ✅ | |
| Que la skill funcione | | Evaluación (criterio humano) |
| Que el trabajo esté bien hecho | | Aceptación del cliente y disputas |
| Que corrió la versión correcta | | Nada, por ahora (brecha 1) |
| Quién responde si sale mal | | La ley y los contratos (ver [hallazgo legal](2026-10-04-implicancias-legales.md)) |

## Qué peso tiene el hash y qué peso tiene la ejecución

El hash funciona como el precinto de una caja: prueba que nadie cambió el contenido desde que se cerró, y cuándo se cerró. No dice nada sobre si el contenido sirve.

| | Hash en blockchain | Ejecución del robot |
|---|---|---|
| Qué prueba | Que el resultado entregado es este y no otro, y en qué momento | Nada por sí sola: hay que evaluarla |
| Para qué sirve | Evidencia en una disputa, trazabilidad | Es lo que el cliente paga |
| Qué no prueba | Calidad, ni qué versión lo produjo | — |
| Peso en el valor del producto | Bajo: es un respaldo | Alto: es el producto |

## Qué implica para el proyecto

- Si el pitch pone el hash en el centro, muestra el precinto en lugar de lo que hay adentro.
- El valor está en la ejecución, que es justamente la parte que hoy no se puede verificar (brecha 1).

## Qué propongo

1. **Antes de grabar:** resolver la brecha 3 (Issue abierto).
2. **En el pitch:** usar el relato "blockchain para que nadie toque la plata ni reescriba la historia; personas con nombre y responsabilidad para juzgar la calidad". Preguntas y respuestas cargadas en `docs/pitch/PITCH.md`.
3. **Si hay tiempo (Franco y Nico deciden):** fijar la versión del modelo en la skill (brecha 4) y mostrar clientes únicos en el perfil del robot (brecha 2). Son cambios chicos que cierran dos preguntas.
4. **Roadmap:** ejecución certificada (brecha 1), reputación de clientes y aceptación automática (brecha 5), stablecoins.
