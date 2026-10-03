# ROBOLEDGER — Rol: evaluación de skills y pitch

Responsable: Facu Villanueva
Estado: propuesta, pendiente de OK del equipo
Fecha: 2026-10-03 · Entrega del hackathon: 2026-10-13

## Qué me propongo hacer

Me hago cargo de dos piezas:

1. **La evaluación de la skill.** Cómo comprobamos que el agente clasifica bien los tomates antes de habilitarlo para trabajos pagos. Incluye criterios, set de prueba, umbral de aprobación y el registro firmado que queda vinculado a la versión de la skill.
2. **El pitch y el guion de la demo.** Cómo contamos el proyecto en 3 minutos a un jurado que viene mayormente del mundo inversor.

No toco contratos, tesorería, ERC-8004 ni el worker. Si necesito un dato de esas piezas, lo pido.

## Por qué esta pieza importa

Todo el proyecto se apoya en una frase: "habilidades evaluadas". Si la evaluación es floja, el resto (identidad, historial, reparto) registra con mucha prolijidad algo que no sabemos si funciona. El jurado lo va a preguntar.

## Metodología v0 (para discutir)

### Categorías

Tres clases, para que sea simple de etiquetar y de explicar:

| Clase | Criterio visual | Caso borde |
|---|---|---|
| Verde | Superficie verde o verde claro, sin rojo visible | Verde con una mancha amarilla mínima → sigue siendo verde |
| Pintón | Entre 10 % y 60 % de la superficie con rojo, rosa o naranja | Duda entre pintón y maduro → se decide por la superficie más visible |
| Maduro | Más de 60 % de la superficie roja | Rojo con zonas oscuras o daño → queda fuera del alcance (ver abajo) |

Fuera del alcance del MVP: tomates dañados, podridos, cortados o con varias unidades superpuestas. Si aparecen, el agente debe responder "no clasificable" en lugar de inventar una clase.

### Datos

- **Set de enseñanza:** imágenes etiquetadas que aporta el entrenador. Es lo que el agente usa como ejemplos.
- **Set de evaluación:** imágenes distintas, que el agente nunca vio. Propongo 60 (20 por clase) más 6 casos "no clasificable".
- Los dos sets no comparten ninguna imagen. Publicamos el hash de cada set para que se pueda comprobar que no se mezclaron.
- Fuente candidata: el dataset público Laboro Tomato (tiene clases de maduración). Hay que verificar la licencia antes de usarlo.

### Cómo se mide

- **Precisión general:** porcentaje de imágenes bien clasificadas.
- **Matriz de confusión:** muestra en qué clases se equivoca. Confundir verde con maduro es más grave que confundir pintón con maduro.
- **Umbral para habilitar la skill (propuesta):** 85 % de precisión general y ningún verde clasificado como maduro.
- Si la skill cambia (nuevos ejemplos, otro modelo, otras instrucciones), es una versión nueva y se vuelve a evaluar.

### Qué queda registrado en cada evaluación

| Campo | Ejemplo |
|---|---|
| Skill y versión | `tomato-ripeness v1` |
| Configuración del agente | modelo, instrucciones, hash del paquete de enseñanza |
| Hash del set de evaluación | `0x…` |
| Metodología | este documento, versión v0 |
| Resultado | 88 % de precisión, matriz de confusión adjunta |
| Decisión | habilitada / no habilitada |
| Evaluador | identidad y firma |
| Fecha | 2026-10-09 |

El detalle (imágenes, matriz completa) queda en Supabase. En Monad va el hash del registro y la decisión. Esto lo tengo que confirmar con quien arme `SkillRegistry`.

## Entregas y fechas

| Fecha | Entrega |
|---|---|
| 05-oct | Metodología cerrada con el equipo (este documento, versión v1) |
| 07-oct | Set de evaluación armado y etiquetado, con su hash |
| 09-oct | Primera evaluación corrida contra el agente real, con resultados |
| 11-oct | Guion del pitch y de la demo |
| 12-oct | Video grabado, con un día de margen |

## Qué necesito del equipo

- Quién arma el agente clasificador, para correr la evaluación contra él.
- Quién arma `SkillRegistry`, para acordar qué campos van on-chain.
- Las bases del hackathon (criterios de evaluación y formato de entrega), para armar el pitch en función de lo que puntúa.

## Preguntas abiertas

1. ¿Tres clases alcanzan o el equipo quiere más detalle?
2. ¿El umbral de 85 % les parece razonable para la demo?
3. ¿Quién firma la evaluación en la demo: CALCHAI como plataforma o un evaluador separado?
