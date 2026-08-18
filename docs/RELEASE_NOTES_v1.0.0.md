# Pi-hole + Tailscale Adblock v1.0.0 - Draft Release Notes

Primera version estable de la documentacion del laboratorio casero de bloqueo DNS con Raspberry Pi, Pi-hole y Tailscale.

## Alcance

- Instalacion paso a paso de Pi-hole.
- Integracion con Tailscale para usar el DNS fuera de la red local.
- Configuracion de DNS global y Override DNS.
- Verificacion con consultas DNS y logs de Pi-hole.
- Registro de errores reales encontrados y soluciones aplicadas.

## Puntos tecnicos para destacar

- Uso de Tailscale como transporte seguro para consultas DNS.
- Separacion clara entre red LAN y tailnet.
- Reglas regex para dominios dinamicos de publicidad y rastreo.
- Documentacion de problemas de Android, listening mode y DNS override.

## Antes de publicar

- Revisar screenshots para no exponer IPs privadas sensibles.
- Confirmar que los comandos siguen funcionando.
- Agregar diagrama Mermaid antes del release final si es posible.
