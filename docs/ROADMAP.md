# Pi-hole + Tailscale Roadmap

Este roadmap convierte el laboratorio de DNS/VPN en una documentacion mas mantenible y facil de revisar.

## Prioridad 1: arquitectura visual

- Agregar diagrama Mermaid del flujo DNS.
- Mostrar dispositivos cliente, tailnet, Raspberry Pi, Pi-hole y upstream DNS.
- Explicar diferencia entre IP LAN y IP Tailscale.

## Prioridad 2: reglas verificables

- Separar reglas regex utiles en un archivo documentado.
- Explicar que dominios dinamicos cubre cada regla.
- Agregar comandos `dig` o `nslookup` para verificar bloqueo.

## Prioridad 3: release inicial

- Preparar tag `v1.0.0` cuando la documentacion este revisada.
- Publicar notas sobre alcance, arquitectura, errores encontrados y soluciones.
- Confirmar que las capturas y metricas incluidas no expongan datos privados.

## Issues relacionados

- #1 Preparar release v1.0.0 de la documentacion
- #2 Agregar diagrama de arquitectura de red en Mermaid
- #3 Documentar reglas regex usadas para anuncios dinamicos
