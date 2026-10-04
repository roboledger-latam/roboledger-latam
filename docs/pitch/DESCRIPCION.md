# Descripción del proyecto para la inscripción

Borrador. La página pública de Metropolis pide un perfil con demo, descripción corta y link al código. Los campos exactos del formulario los vemos cuando alguien entre a la plataforma; ahí ajustamos largos y formato.

Estado: borrador v0 · Responsable: Facu · Revisa: Fede

## Datos generales

| Campo | Valor |
|---|---|
| Nombre | ROBOLEDGER LATAM |
| Track | 04 · Trust, Identity & AI Infrastructure |
| Bounty a evaluar | Best Agent Wallet Plugin (ver [hallazgo](../hallazgos/2026-10-03-bases-metropolis.md)) |
| Código | https://github.com/roboledger-latam/roboledger-latam |
| Red | Monad testnet |
| Community (pedido por Fede) | Crecimiento |

## Descripción en una línea

**EN:** A marketplace to hire robots and AI agents with verifiable identity, evaluated skills and a work history, where each machine has its own treasury that pays the people who trained it.

**ES:** Un marketplace para contratar robots y agentes de IA con identidad verificable, habilidades evaluadas e historial de trabajo, donde cada máquina tiene su propia tesorería y le paga a quienes la entrenaron.

## Descripción corta

**EN:**

Hiring an autonomous agent today means trusting the seller's word. ROBOLEDGER LATAM gives each machine an onchain identity (ERC-8004), versioned skills that an independent evaluator tests on unseen cases, and a record of every job it completes.

Each robot has a treasury on Monad. When a client hires it, the payment is held in escrow until delivery is accepted. The treasury then covers authorized expenses and splits the rest between the owner, the robot's operating reserve, the people who trained the skill, and the platform. If the robot misses the deadline, the client gets a refund.

Our first robot is virtual: it classifies tomato ripeness from images, a real task with a direct path to agriculture in Latin America. The classification is real; the robot's body and battery are simulated and labeled as such.

**ES:**

Hoy, contratar un agente autónomo significa creerle al que lo vende. ROBOLEDGER LATAM le da a cada máquina una identidad onchain (ERC-8004), habilidades versionadas que un evaluador independiente prueba con casos que el agente nunca vio, y un registro de cada trabajo que completa.

Cada robot tiene una tesorería en Monad. Cuando un cliente lo contrata, el pago queda retenido hasta que acepta la entrega. Después, la tesorería cubre los gastos autorizados y reparte el resto entre el propietario, la reserva operativa del robot, las personas que entrenaron la habilidad y la plataforma. Si el robot no entrega a tiempo, el cliente recupera su dinero.

Nuestro primer robot es virtual: clasifica la maduración de tomates a partir de imágenes, una tarea real con aplicación directa en el agro de América Latina. La clasificación es real; el cuerpo y la batería del robot son simulados y están marcados como tales.

## Qué se puede verificar en la demo

1. La versión de la skill y quién contribuyó a desarrollarla.
2. La evaluación previa, con casos separados de los de enseñanza.
3. El depósito del cliente, la entrega, la aceptación y el reparto onchain.
4. Un gasto autorizado y el presupuesto que le queda al robot.
5. Una devolución por falta de entrega.
6. Que una liquidación repetida no genera un segundo pago.

## Preguntas abiertas

1. ¿La inscripción y el video van en inglés? El jurado es internacional, así que asumo que sí; falta confirmarlo con las reglas oficiales.
2. ¿Postulamos también al bounty Best Agent Wallet Plugin? Lo deciden Franco y Nico según cómo quede la tesorería.
