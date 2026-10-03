# Cómo trabajamos en este repo

Reglas cortas para no pisarnos y no romper lo que vamos a entregar. Si algo no está claro, preguntá en el chat del equipo antes de adivinar.

## Quién decide qué

| Tema | Decide |
|---|---|
| Código, arquitectura, contratos, web3 | Franco y Nico |
| Producto y qué entra en la demo | Fede |
| Evaluación de skills, pitch, reglas del repo y proceso | Facu |
| Empate o duda | Fede, y se anota en [docs/DECISIONES.md](docs/DECISIONES.md) |

## Flujo de trabajo

1. Creá una rama desde `main` con un nombre que diga qué hace: `feat/rental-manager`, `fix/hash-evaluacion`, `docs/pitch`.
2. Trabajá y commiteá en tu rama.
3. Abrí un Pull Request contra `main` y completá la plantilla.
4. Otra persona lo revisa y lo aprueba. Nadie aprueba su propio PR.
5. Resolvé todos los comentarios del PR.
6. Merge con **squash** (cada PR entra como un solo commit). La rama se borra sola.

## Reglas de `main`

GitHub las aplica solo; están acá para que sepas por qué te frena.

- Nadie pushea directo a `main`. Todo entra por PR.
- Cada PR necesita 1 aprobación de otra persona.
- Si cambiás código después de una aprobación, la aprobación se cae y hay que pedirla de nuevo.
- Sin force-push y sin borrar `main`.
- Cada carpeta tiene revisores obligatorios (ver `.github/CODEOWNERS`):
  - `contracts/`, `app/`, `worker/`: Franco y Nico, que se revisan entre ellos.
  - `docs/`, `evaluation/`: Facu.
  - `.github/`: Fede y Facu.

## Secretos y wallets

Lo más importante de esta lista. Un error acá no se arregla con un revert.

- **Nunca** subas claves privadas, seed phrases, tokens ni archivos `.env`. El `.gitignore` los excluye, pero no confíes solo en eso.
- Las variables necesarias van en `.env.example` con el nombre y sin el valor.
- GitHub bloquea el push si detecta una clave (secret scanning con push protection). Si te bloquea, sacá la clave; no fuerces el push.
- **Solo testnet.** Las wallets del proyecto son nuevas y exclusivas para la hackatón. Nunca uses una wallet personal que tenga fondos reales, tampoco para deployar.
- La service-role key de Supabase va solo en el servidor. Nunca en el frontend.
- Si una clave se filtra: avisá en el chat y rotala en ese momento. Borrarla del repo no alcanza, porque la historia de git la conserva.

## Agentes de IA (Devin, OpenCode y similares)

- Trabajan como cualquier colaborador: en su rama y con PR.
- Sus PRs los revisa y aprueba una persona.
- No tienen permisos de administrador ni acceso a claves privadas.

## Fechas de cierre

| Fecha | Qué pasa |
|---|---|
| 12-oct, 12:00 | Congelamiento de código: solo entran arreglos de bugs de la demo |
| 13-oct | Entrega. La versión entregada se marca con el tag `v1.0-entrega` |

## Hallazgos

Si descubrís algo que el resto tiene que saber (un límite de una herramienta, un riesgo, un problema de diseño), documentalo en [docs/hallazgos/](docs/hallazgos/). Si además requiere trabajo, abrí un Issue y linkealo.

## Decisiones

Toda decisión que cambie el alcance, la arquitectura o estas reglas se anota en [docs/DECISIONES.md](docs/DECISIONES.md): qué se decidió, quién y por qué.
