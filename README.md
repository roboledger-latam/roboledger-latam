# ROBOLEDGER LATAM

Plataforma de CALCHAI para contratar robots y agentes autónomos con identidad verificable, habilidades evaluadas e historial de trabajo. Cada máquina tiene una tesorería que recibe ingresos, cubre gastos autorizados y reparte resultados entre su propietario y las personas que contribuyeron a desarrollar sus capacidades.

Proyecto para Monad Metropolis, Track 04: Trust, Identity & AI Infrastructure. Entrega: 13 de octubre de 2026.

## Primer caso de uso

Un robot virtual clasifica la maduración de tomates a partir de imágenes. Un colaborador aporta ejemplos y criterios, el agente se evalúa con imágenes separadas y después un cliente contrata la clasificación de un lote nuevo. Pagos y repartos en Monad testnet.

## Estructura

| Carpeta | Contenido |
|---|---|
| `app/` | Portal y API (Next.js, React, TypeScript) |
| `worker/` | Agente ejecutor y adaptador del robot virtual |
| `contracts/` | `SkillRegistry`, `RentalManager`, `RobotTreasury` e identidad ERC-8004 |
| `evaluation/` | Servicio de evaluación, sets de prueba y resultados |
| `docs/` | Metodología de evaluación, decisiones y documentación del proyecto |

## Cómo correrlo

Pendiente: lo completan los devs cuando el stack esté armado.

## Cómo contribuir

Leé [CONTRIBUTING.md](CONTRIBUTING.md) antes de tu primer PR.

## Equipo

| Persona | Responsabilidad |
|---|---|
| Fede Juarez | Dueño del proyecto, producto y alcance de la demo |
| Franco | Desarrollo y build |
| Nico | Desarrollo y build |
| Facu Villanueva | Evaluación de skills, pitch y reglas del repo |
