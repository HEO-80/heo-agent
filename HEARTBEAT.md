# HEARTBEAT.md — Checklist periódico de Jhon

*Este archivo define qué debe revisar Jhon en cada ciclo de heartbeat. Si no hay nada relevante en ningún punto, responde HEARTBEAT_OK sin enviar mensaje.*

---

## Revisión diaria (cada mañana)

Ejecuta estos checks en orden. Si algo requiere atención, agrúpalo en un único mensaje conciso:

1. **Calendario hoy** — ¿hay eventos importantes? ¿alguna reunión o deadline hoy?
2. **Emails sin responder** — ¿hay algo urgente en los últimos 3 emails? Mención solo si es importante.
3. **Tiempo en Zaragoza** — temperatura y condición en una línea.
4. **GitHub** — ¿hay issues nuevos o PRs sin revisar en CodeTyper o VaultFlow?
5. **Notion** — ¿hay tareas marcadas como urgentes o bloqueadas?

Formato del briefing diario:
```
📅 Hoy: [eventos del día]
📧 Emails: [solo si hay algo urgente]
🌤️ Zaragoza: [temperatura y condición]
💻 GitHub: [issues/PRs si los hay]
📝 Notion: [tareas urgentes si las hay]
```

Si no hay nada relevante en ningún punto: HEARTBEAT_OK (no enviar mensaje).

---

## Revisión semanal (lunes)

1. **Resumen de la semana anterior** — qué commits/PRs se hicieron en proyectos activos
2. **Prioridades de la semana** — basado en Notion y calendario
3. **VaultFlow deadline** — si queda menos de 4 semanas para final de verano, recordatorio
4. **LinkedIn** — recordatorio de publicar si no se publicó nada en 7+ días

---

## Alertas inmediatas (cualquier momento)

Detecta y avisa sin esperar al heartbeat si:

- Nuevo issue crítico en CodeTyper o VaultFlow
- PR sin revisar hace más de 3 días
- Email de alumno con asunto urgente
- Cualquier fallo del servidor Beelink detectado en healthcheck

---

## Configuración del heartbeat

Para activar el heartbeat automático en el Beelink:

```bash
openclaw cron add \
  --name "briefing-diario" \
  --cron "0 8 * * *" \
  --tz "Europe/Madrid" \
  --session isolated \
  --message "Ejecuta el briefing diario según HEARTBEAT.md. Revisa calendario, emails, tiempo en Zaragoza, GitHub y Notion. Agrupa todo en un mensaje conciso." \
  --announce \
  --channel telegram \
  --to "5377067623"
```
