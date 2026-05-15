# LenderHub — Prototipo Quirografarios V0

Prototipo HTML estático de la plataforma **LenderHub** (CXC) para monitoreo de portafolios de crédito quirografario y ABS.

## Pantallas

| Archivo | Descripción |
|---|---|
| [`home-lenderhub.html`](./home-lenderhub.html) | Portfolio Monitoring — Overview (Resumen, Capital & Risk, Pricing & WAL), Facilities |
| [`companies-lenderhub.html`](./companies-lenderhub.html) | Lista de Companies / Acreditados |
| [`company-detail-lenderhub.html`](./company-detail-lenderhub.html) | Detalle de Company + Wizard de creación/edición de Facilities (Quirografario / ABS) |
| [`data-studio-lenderhub.html`](./data-studio-lenderhub.html) | Data Studio (vista de exploración) |

## Cómo ejecutarlo en local

```bash
# Opción A: Python
python3 -m http.server 8080

# Opción B: Ruby
ruby -run -e httpd . --port=8080

# Luego abre: http://localhost:8080/home-lenderhub.html
```

## Stack

- HTML estático (sin build step)
- Design System CXC: Sofia Pro · Clear Sans · Phosphor Icons
- Colores: Slate-50 base · Magenta `#910057` brand · semáforo regulatorio (verde / amarillo / rojo)

## Estructura de datos

- **250 facilities quirografarias** simuladas con PRNG seeded — distribución de cartera sana (~85% ACTIVO, 84% IG)
- **5 facilities ABS** con Overcollateralization Ratio
- Single source of truth: `window.QUIRO_FACILITIES` + `window.ABS_FACILITIES`

## Audiencia target

BBVA IB&F Head — el prototipo cuenta la historia de:
- RAROC + RWA + ECL por rating
- Concentración (HHI sectorial + obligor)
- Vintage cohorts con MOB
- Stress waterfall (PD shock + LGD shock + cure rate)
- Muro de vencimientos segmentado por rating

## Demo & Deploy

Servible directo como sitio estático en cualquier hosting:
- GitHub Pages
- Vercel
- Netlify
- Cloudflare Pages
