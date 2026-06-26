<div align="center">

# 💸 PROMPTX

**Generador de Prompts de Monetización con IA — Gemini API + PayPal + Sistema Freemium**

[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178c6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Gemini](https://img.shields.io/badge/Gemini-API-4285F4?logo=google&logoColor=white)](https://ai.google.dev/)
[![PayPal](https://img.shields.io/badge/PayPal-SDK-003087?logo=paypal&logoColor=white)](https://developer.paypal.com/)
[![Vercel](https://img.shields.io/badge/Deploy-Vercel-black?logo=vercel)](https://vercel.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

</div>

---

## 🧠 ¿Qué es PROMPTX?

PROMPTX es una plataforma standalone para **generar y vender prompts optimizados** usando inteligencia artificial. Combina **Gemini API** para la generación de contenido con **PayPal** para pagos, y un modelo freemium que permite uso gratuito limitado con planes premium.

Migrado y mejorado desde MGX con arquitectura más limpia y mejor integración de pagos.

## ✨ Características

- 🤖 Generación de prompts con **Gemini Flash / Pro**
- 💳 Pagos integrados con **PayPal**
- 🎟️ Sistema **freemium**: créditos gratuitos + planes de pago
- 📂 Categorías de prompts: Marketing, SEO, Copywriting, Código, Arte
- 📄 Exportación y compartido de prompts
- 📊 Dashboard de uso y estadísticas
- 🚀 Deploy en un click con Vercel

## 🛠️ Stack Tecnológico

| Capa | Tecnología |
|------|------------|
| Framework | Next.js 15, TypeScript |
| Estilos | Tailwind CSS 4 |
| IA | Gemini API (Google AI Studio) |
| Pagos | PayPal SDK |
| Deploy | Vercel |

## 🚀 Inicio Rápido

### Prerequisitos

- Node.js 20+
- Cuenta [Google AI Studio](https://ai.google.dev/) → `GEMINI_API_KEY`
- Cuenta [PayPal Developer](https://developer.paypal.com/) → `PAYPAL_CLIENT_ID`

### Instalación

```bash
git clone https://github.com/jacxas/PROMPTX.git
cd PROMPTX
npm install
```

### Configuración

```bash
cp .env.example .env.local
```

```env
GEMINI_API_KEY=tu_clave_gemini
NEXT_PUBLIC_PAYPAL_CLIENT_ID=tu_client_id_paypal
PAYPAL_CLIENT_SECRET=tu_secret_paypal
NEXTAUTH_SECRET=un_secreto_random
```

### Ejecutar

```bash
npm run dev
# Abre http://localhost:3000
```

## 📦 Scripts

```bash
npm run dev      # Desarrollo local
npm run build    # Build de producción
npm run start    # Servidor de producción
npm run lint     # Linter
```

## 📁 Estructura del Proyecto

```
PROMPTX/
├── app/                  # App Router (Next.js)
│   ├── api/             # API Routes (Gemini, PayPal)
│   ├── components/      # Componentes React
│   ├── dashboard/       # Panel de usuario
│   └── page.tsx         # Landing principal
├── lib/                 # Helpers: Gemini, PayPal, auth
├── public/              # Assets estáticos
└── .env.local           # Variables de entorno
```

## 🌐 Deploy en Vercel

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/jacxas/PROMPTX)

## 🔗 Proyectos Relacionados

- **[CashPrompt-Generator](https://github.com/jacxas/CashPrompt-Generator)** — Frontend modular del ecosistema CashPrompt
- **[cashprompt-backend](https://github.com/jacxas/cashprompt-backend)** — API backend y agentes IA

## 📄 Licencia

MIT © [jacxas](https://github.com/jacxas)
