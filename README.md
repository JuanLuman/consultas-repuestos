# Consultas de Repuestos

Sistema web para gestionar las consultas de precio de repuestos entre Ventas y Compras, con seguimiento de estado en tiempo real.

## El problema

Cuando un vendedor no tiene un repuesto en stock, tiene que pedirle el precio a Compras. Hoy esto se hace por correo electrónico: el vendedor escribe un mail preguntando por un número de pieza, y espera. Estas consultas son variables, pero no son un caso raro: hay días con 5 o más.

El problema es que los hilos de correo se mezclan. Como varias consultas terminan referenciando el mismo número de pieza, es fácil perder el hilo correcto, reenviar la pregunta equivocada o responder sobre una pieza distinta a la que se está pidiendo. Nadie tiene una bandeja única con todas las consultas pendientes: cada uno revisa su propio correo, así que no hay forma de saber, a simple vista, si una consulta ya está siendo gestionada por otra persona de Compras o si sigue sin respuesta. Tampoco hay forma de saber cuánto tiempo lleva esperando cada consulta.

El resultado es que el cliente, que está esperando en el mostrador o por teléfono, termina esperando: en general, la demora es de 24 horas en adelante para obtener una respuesta, mientras la consulta se pierde entre decenas de correos sin ningún indicador de urgencia ni de estado.

## La solución

Una aplicación web donde cada consulta de precio tiene un estado explícito (pendiente, en gestión, respondida, cerrada) y queda visible para todo el equipo, no solo para quien la recibió.

- **Consultas con estado**: cada pedido de precio se registra como una consulta individual, con su propio historial, en lugar de perderse en un hilo de correo.
- **Bandeja única para Compras**: todo el equipo de Compras ve las mismas consultas pendientes en un solo lugar, evitando que dos personas gestionen lo mismo o que ninguna lo haga.
- **Respuestas de varios proveedores por consulta**: una misma consulta puede recibir cotizaciones de distintos proveedores, y quedan todas asociadas a esa consulta para comparar.
- **Semáforo de tiempo**: cada consulta muestra visualmente (verde/amarillo/rojo) cuánto tiempo lleva esperando respuesta, para priorizar las que están por vencer.

## Stack

- PHP
- MySQL
- Bootstrap
- WAMP
- Git

## Estado

En desarrollo.
