# MEMORY.md — Contexto duradero

*Este archivo contiene decisiones, preferencias y contexto estable. No es un log de eventos diarios — eso va en memory/YYYY-MM-DD.md.*

---

## Stack del servidor HEO-AGENT

- **Hardware**: Beelink SER5 MAX (Ryzen 7 6800U, 24GB RAM, Ubuntu 24.04 LTS)
- **IP local**: 192.168.1.138
- **Acceso**: SSH desde PC Windows (Ryzen 7 7800X3D, 32GB, RX 9070 XT)
- **Gateway**: systemd user service en ~/.config/systemd/user/openclaw-gateway.service
- **Puerto**: ws://127.0.0.1:18789
- **Modelo activo**: google-gemini-cli/gemini-2.5-flash (OAuth gratuito ~1500 req/día)

---

## Skills activos y configuración

| Skill | Estado | Requiere |
|-------|--------|----------|
| notion | ✅ | NOTION_API_KEY en systemd |
| gws-gmail | ✅ | gws auth + GOOGLE_WORKSPACE_CLI_KEYRING_BACKEND=file |
| gws-calendar | ✅ | gws auth |
| gws-drive | ✅ | gws auth |
| gws-docs | ✅ | gws auth |
| gws-sheets | ✅ | gws auth |
| github | ✅ | GH_TOKEN en systemd |
| web-search | ✅ | TAVILY_API_KEY en systemd |
| weather | ✅ | nativo |
| healthcheck | ✅ | nativo |
| session-logs | ✅ | ripgrep instalado |
| tmux | ✅ | nativo |
| summarize | ❌ | sin soporte Linux oficial |

---

## Variables de entorno críticas (en systemd)

```
NOTION_API_KEY=ntn_...
GOOGLE_WORKSPACE_CLI_KEYRING_BACKEND=file
GH_TOKEN=ghp_...
TAVILY_API_KEY=tvly-dev-...
PATH=/home/heo/.nvm/versions/node/v22.22.0/bin:/usr/local/bin:/usr/bin:/bin
```

Si el Beelink se reinicia y algo falla, verificar con:
`systemctl --user show-environment | grep -E "NOTION|GOOGLE|GH_TOKEN|TAVILY"`

---

## Decisiones técnicas tomadas

- **Modelo gratuito elegido**: Gemini 2.5 Flash (OAuth, sin coste)
- **Búsqueda web**: Tavily (1000 req/mes gratis) en lugar de Brave (requiere tarjeta)
- **Auth Google Workspace**: keyring backend = file (para headless server)
- **GitHub**: Personal Access Token clásico (repo + read:user), sin expiración
- **n8n**: instalado en Docker, puerto 5678, accesible en http://192.168.1.138:5678
- **gws repo**: clonado en ~/gws-repo desde github.com/googleworkspace/cli
- **Node version**: v22.22.0 via nvm

---

## Estado actual de proyectos

### VaultFlow — PRIORIDAD MÁXIMA
- Dashboard UI construido, RainbowKit integrado
- Próximo paso: NextAuth.js + SIWE + Google OAuth
- Deadline: antes de final de verano 2026
- Repo: vaultflow-web en Vercel

### CodeTyper — EN PRODUCCIÓN
- Live en codetyper-eight.vercel.app
- ~5.000 personas alcanzadas via LinkedIn
- Próximo: refactor en componentes + nuevos lenguajes

### NETWATCH Terminal — COMPLETADO
- Build exe compilado y funcionando
- Documentación completa en repo
- No requiere trabajo inmediato

### VLBots — ACTIVO EN PRODUCCIÓN
- Bots MEV corriendo en BSC y Ethereum Mainnet
- Arquitectura: flash loans Aave V3, multi-DEX, sniper con GoPlus

---

## Preferencias permanentes

- Respuestas en español siempre
- Respuestas cortas por defecto, sin paja
- Para DeFi/Web3: nivel avanzado, sin explicar conceptos básicos
- LinkedIn: posts con ángulo técnico + personal, ~5.000 personas de alcance histórico
- Herramientas para guardar ideas/tareas: Notion
- Certificaciones en progreso: AZ-104 (activa), AZ-204 (abril 2026)

---

## Contexto docente

- Centro principal: Océano Atlántico (DAM/SMR)
- Big Data: Centro Salvador Allende
- Curso SEPE activo: Power BI / Power Query / Excel (hasta mayo 2026, IFCT153)
- Curso INAEM completado: frontend 300h (Astro, React, Next.js, React Native, GSAP)
- ~22-30 alumnos por clase en cursos FP, ~15 en INAEM
