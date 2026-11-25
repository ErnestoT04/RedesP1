# RedesP1 · Laboratorio de redes

Práctica académica de direccionamiento IPv4, enrutamiento y diagnóstico de conectividad con Cisco Packet Tracer. El objetivo es relacionar lo planificado en las tablas con la configuración de los dispositivos y explicar qué revisar cuando dos equipos no se comunican.

## Qué incluye

- Un escenario de Packet Tracer (`.pkt`).
- Una hoja de cálculo y documentos de asignación y enrutamiento.

Los archivos originales corresponden a la entrega académica. Esta guía no reproduce datos de esos adjuntos.

## Cómo revisar la práctica

1. Abre una copia local del archivo `.pkt` en Cisco Packet Tracer para conservar el escenario original.
2. Selecciona un equipo origen y anota su IP, prefijo y puerta de enlace. Compáralos con la tabla de asignación.
3. Comprueba primero la conectividad con la puerta de enlace desde el equipo origen (`ping`). Si falla, revisa enlace, estado de la interfaz, direccionamiento y máscara antes de buscar errores de enrutamiento.
4. Comprueba la conectividad con un equipo de otra subred. Si el primer paso funciona y este no, revisa la tabla de rutas en los routers IOS simulados (`show ip route`), el siguiente salto y la ruta de retorno. Puedes seguir los paquetes en el modo Simulation.
5. Registra origen, destino, resultado esperado, resultado observado y causa probable. Repite el intento después de corregir un solo factor para saber qué cambió.

## Ejemplo ilustrativo

Este esquema es ficticio y no representa la topología entregada:

```text
PC-A ── LAN A ── [router simulado] ── LAN B ── PC-B
        192.0.2.0/24                  198.51.100.0/24
```

Si PC-A alcanza su puerta de enlace pero no PC-B, la conexión local de PC-A funciona; aún falta verificar la red de destino, su puerta de enlace y el camino de retorno. Las direcciones del esquema son rangos de documentación, no direcciones de la práctica.

## Estado de la evidencia

Se confirmó la presencia del escenario y de las tablas en el repositorio. Esta revisión no abrió el simulador ni ejecutó las comprobaciones; los pasos anteriores son un procedimiento propuesto, no resultados registrados. Antes de añadir capturas al portafolio, usa una simulación ficticia o revisa que no contengan nombres, identificadores ni configuraciones reales.
