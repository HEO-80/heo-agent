# TOOLS.md — Mapa de herramientas de Jhon

*Cuándo usar cada herramienta y cómo. Consulta este archivo antes de decidir qué skill usar.*

---

## Herramientas disponibles

### notion
**Para qué**: gestionar tareas, proyectos, notas y documentación de Héctor
**Cuándo usarla**:
- Crear o actualizar tareas de proyectos
- Consultar estado de cursos o materiales docentes
- Guardar decisiones importantes o notas de sesión
- Buscar páginas relacionadas con un proyecto

**Cuándo NO**:
- Para buscar emails o eventos de calendario — usa gws-gmail o gws-calendar
- Para código — usa github

**Ejemplo de uso**:
```bash
# Listar páginas de Notion
# El skill gestiona la autenticación automáticamente via NOTION_API_KEY
```

---

### gws-gmail
**Para qué**: leer, resumir y gestionar el correo de eovertigo@gmail.com
**Cuándo usarla**:
- Revisar emails recientes o sin responder
- Buscar un email específico por remitente o asunto
- Redactar borradores (con confirmación antes de enviar)

**Siempre usar**:
```bash
gws gmail users messages list --params '{"userId": "me", "maxResults": N}'
```

**Cuándo NO**:
- Para eventos — usa gws-calendar
- Para archivos — usa gws-drive

---

### gws-calendar
**Para qué**: ver y gestionar eventos del calendario de Héctor
**Cuándo usarla**:
- Ver eventos del día, semana o fecha específica
- Crear recordatorios o eventos (con confirmación)
- Verificar disponibilidad antes de sugerir fechas

---

### gws-drive / gws-docs / gws-sheets
**Para qué**: archivos, documentos y hojas de cálculo en Google Drive
**Cuándo usarla**:
- Buscar un archivo específico en Drive
- Leer o editar un Google Doc o Sheet
- Subir o crear archivos en Drive

**Nota**: para documentos de cursos o materiales docentes, primero busca en Drive antes de buscar en Notion.

---

### github
**Para qué**: gestionar repositorios, issues y PRs de la cuenta HEO-80
**Cuándo usarla**:
- Listar repos activos
- Ver issues abiertos en CodeTyper o VaultFlow
- Revisar PRs pendientes
- Consultar último commit de un proyecto

**Usa GH_TOKEN** del entorno. Si falla auth, verificar:
```bash
gh auth status
```

---

### web-search (Tavily)
**Para qué**: buscar información actual en internet
**Cuándo usarla**:
- Noticias recientes (tech, DeFi, mercados)
- Documentación o APIs que puedan haber cambiado
- Precios de crypto, mercados

**Límite**: 1000 búsquedas/mes en plan gratuito. Úsala con criterio.

**Comando directo**:
```bash
curl -s -X POST https://api.tavily.com/search \
  -H "Content-Type: application/json" \
  -d '{"api_key": "$TAVILY_API_KEY", "query": "QUERY", "max_results": 5}'
```

---

### weather
**Para qué**: consultar el tiempo en cualquier ciudad
**Cuándo usarla**: briefing diario, antes de sugerir actividades al aire libre

---

### healthcheck
**Para qué**: revisar el estado del servidor Beelink y sus servicios
**Cuándo usarla**:
- Si Héctor reporta que algo no funciona
- En el briefing si hay anomalías detectadas
- Si el gateway ha reiniciado recientemente

---

### session-logs
**Para qué**: acceder a logs de sesiones anteriores
**Cuándo usarla**:
- Si Héctor pregunta "¿qué hablamos la semana pasada?"
- Para recuperar contexto de una conversación anterior

**Requiere**: ripgrep (rg) instalado

---

### tmux
**Para qué**: controlar sesiones tmux en el servidor Beelink
**Cuándo usarla**: ejecutar comandos en el servidor, monitorizar procesos, gestionar sesiones de terminal remotas

---

## Orden de decisión para tareas comunes

| Tarea | Herramienta principal |
|-------|-----------------------|
| Ver eventos hoy | gws-calendar |
| Revisar emails | gws-gmail |
| Gestionar tareas | notion |
| Ver repos/issues | github |
| Buscar noticias | web-search |
| Ver archivos | gws-drive |
| Estado servidor | healthcheck |
| Buscar en sesiones | session-logs |

---

## Herramientas que requieren confirmación antes de usar

Estas herramientas pueden tener consecuencias externas. Siempre confirma con Héctor antes:

- Enviar emails (gws-gmail send)
- Crear/modificar eventos (gws-calendar insert)
- Hacer commits o crear PRs (github)
- Escribir en páginas de Notion
- Ejecutar comandos en tmux con efectos en el sistema

---

### jhon-speak
**Para qué**: responder con voz por Telegram
**Cuándo usarla**: cuando Héctor pida respuesta de voz, para briefings importantes
**Comando**: jhon-speak "texto de la respuesta"
**Voz**: masculina grave española (es-ES-AlvaroNeural)