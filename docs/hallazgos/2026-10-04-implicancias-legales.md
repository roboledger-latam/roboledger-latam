# Quién responde legalmente si el robot no cumple

- **Fecha:** 2026-10-04
- **Autor:** Facu
- **Estado:** abierto

> **Esto no es asesoramiento legal.** Sirve para entender el mapa de riesgos y anticipar preguntas del jurado. Antes de cualquier piloto con plata real, hay que consultarlo con un abogado.

## Qué encontré

### El robot no se puede demandar

Un robot o un agente no es una persona jurídica: no firma contratos, no tiene patrimonio y no responde ante un juez. Si clasifica mal un lote y la finca exporta tomates verdes, la demanda va contra alguien con nombre:

| Quién | Por qué podría responder |
|---|---|
| Dueño u operador del robot | Es quien ofrece el servicio y cobra. Primer candidato. |
| CalchAI como plataforma | Intermedia la contratación y cobra comisión. |
| CalchAI como evaluador | Firma "88 % de precisión". Asume un riesgo parecido al de un auditor que certifica balances. |
| Entrenador | Difícil, pero podría discutirse si sus ejemplos eran defectuosos. |

Esto agrava el [hallazgo sobre la autoridad del evaluador](2026-10-03-autoridad-del-evaluador.md): en el MVP, CalchAI es juez, parte y además el blanco más probable de una demanda.

### Un smart contract no reemplaza un contrato legal

La devolución automática cubre un caso: el cliente recupera lo que pagó si no hay entrega. No cubre el daño que puede causar un trabajo mal hecho (una exportación rechazada, una cosecha mal vendida), que puede valer mucho más que el precio del servicio.

Para eso hacen falta términos y condiciones que digan:
- **Qué se promete:** por ejemplo, "88 % de precisión medida con esta metodología, con un 12 % de error informado".
- **Qué no se promete:** perfección, ni resultados en condiciones fuera del alcance evaluado.
- **Hasta cuánto se responde:** un tope de responsabilidad.
- **Que las condiciones fijadas en el contrato onchain forman parte del acuerdo.**

### Regulación de activos virtuales

- En Argentina, quienes prestan servicios con activos virtuales tienen que inscribirse en el registro de PSAV de la CNV (creado en 2024). Una tesorería que recibe pagos y reparte a terceros podría encuadrar ahí.
- Las regalías que cobran los entrenadores son ingresos con implicancias impositivas.
- En otros países de la región las reglas cambian. Cada mercado requiere su análisis.

### Datos

Las imágenes de los clientes quedan en Supabase y en la cadena solo va su hash. Para tomates no hay problema. En industrias donde los datos son personales (documentos, rostros, salud), aplican las leyes de protección de datos de cada país, y un hash permanente en una cadena pública merece un análisis aparte.

## Fuente o evidencia

Análisis propio a partir del documento del proyecto. La referencia al registro de PSAV corresponde a la normativa argentina vigente desde 2024; hay que confirmar el encuadre con un abogado.

## Qué implica para el proyecto

- **Para el hackathon no hay exposición:** todo ocurre en testnet, sin plata real.
- **Para el pitch sí importa:** un jurado de inversores pregunta por esto porque es lo que frena a una startup en el mundo real.

## Qué propongo

1. **Respuesta para el jurado:** "El responsable legal es el operador del robot. La evaluación informa la tasa de error; no promete perfección. Para un piloto real definimos términos de servicio con topes de responsabilidad y hacemos el análisis regulatorio en cada país." Cargada en `docs/pitch/PITCH.md`.
2. **Decisión pendiente (Fede):** si CalchAI sigue como evaluador después del piloto o delega en evaluadores independientes, considerando también el riesgo legal de firmar evaluaciones.
3. **Antes de un piloto con plata real:** consulta legal sobre responsabilidad, registro de PSAV e impuestos.
