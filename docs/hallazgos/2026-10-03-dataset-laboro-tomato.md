# El dataset Laboro Tomato sirve para la demo, con tres condiciones

- **Fecha:** 2026-10-03
- **Autor:** Facu
- **Estado:** abierto

## Qué encontré

**Licencia:** CC BY-NC-SA 4.0.
- Permite usarlo gratis en el hackathon, citando la fuente.
- No permite uso comercial. Para eso hay que contactar a Laboro.AI.
- Si publicamos un derivado (por ejemplo, recortes de las imágenes), tiene que salir con la misma licencia.

**Contenido:**
- 804 imágenes de tomates en planta (643 de entrenamiento, 161 de prueba), en alta resolución.
- Cada imagen tiene **varios tomates**, marcados con recuadros. Son 10.610 tomates etiquetados en total. Está pensado para detección de objetos, no para clasificar una foto con un solo tomate.
- 6 clases: 3 estados de maduración por 2 tamaños (normal y cherry).

**Cómo define la maduración:**

| Clase del dataset | Superficie roja | Nuestra clase |
|---|---|---|
| `green` | 0 % a 30 % | Verde |
| `half_ripened` | 30 % a 89 % | Pintón |
| `fully_ripened` | 90 % o más | Maduro |

El propio dataset aclara que los porcentajes son aproximados.

## Fuente o evidencia

- https://github.com/laboroai/LaboroTomato (consultado el 2026-10-03)

## Qué implica para el proyecto

1. **Los cortes de nuestra metodología no coinciden con los del dataset.** En `docs/EVALUACION.md` puse 10 % y 60 %; el dataset usa 30 % y 90 %. Si evaluamos con nuestros cortes sobre etiquetas del dataset, vamos a contar como errores cosas que no lo son.
2. **Hay que recortar cada tomate de la imagen** usando los recuadros, para que el agente reciba un tomate por imagen. Es trabajo de preparación de datos que nadie tenía previsto.
3. **No sirve para cobrar a clientes reales.** Para la demo con pagos en testnet alcanza; para un piloto comercial hay que conseguir otra fuente o un permiso de Laboro.AI.

## Qué propongo

1. Adoptar los cortes del dataset (30 % y 90 %) en la metodología. Lo actualizo en `docs/EVALUACION.md` si el equipo está de acuerdo.
2. Definir quién arma el script de recorte de tomates y abrir un Issue para eso.
3. Citar el dataset y su licencia en el README y en el pitch.
4. Usar el set de prueba original del dataset (161 imágenes) como base del set de evaluación, para que quede separado del de enseñanza desde el origen.
