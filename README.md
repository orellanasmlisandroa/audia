# Audia · VoiceBridge

> Dictate. Don't type. — Dicta tu voz y envíala directo a Claude, ChatGPT, Gemini, Perplexity o Grok.

Aplicación 100% estática (un solo HTML). Sin backend, sin build, sin dependencias.

## 🌐 Demo

Una vez desplegada en Vercel: `https://audia-tuusuario.vercel.app`

---

## 🚀 Despliegue rápido

### Opción 1 · Vercel (1-click)

1. Haz un fork de este repo en GitHub.
2. Entra a [vercel.com/new](https://vercel.com/new).
3. Importa el repo.
4. **Framework Preset**: selecciona **"Other"**.
5. Deja todo lo demás vacío y pulsa **Deploy**.

Vercel detectará automáticamente que es un sitio estático, leerá `vercel.json`, y te dará una URL `https://...vercel.app` lista para usar el micrófono.

### Opción 2 · Vercel CLI

```bash
npm i -g vercel
cd audia-deploy
vercel
```

Sigue los prompts y al final tendrás tu URL.

---

## 📦 Estructura

```
audia-deploy/
├── index.html        # La app completa (HTML + CSS + JS inline)
├── vercel.json       # Cabeceras HTTP (permite micrófono)
├── .gitignore
└── README.md
```

## 🔐 Por qué `vercel.json` importa

La cabecera `Permissions-Policy: microphone=(self)` autoriza explícitamente el uso del micrófono en tu dominio. Sin ella, algunos navegadores (especialmente en iframes) bloquean el acceso aunque el usuario haya concedido permiso.

## 🧪 Probar en local

```bash
npx serve .
# o
python3 -m http.server 8000
```

Abre `http://localhost:8000` y prueba.

## 🛠️ Stack

- HTML5 + CSS3 (sin frameworks)
- Web Speech API (transcripción nativa del navegador)
- Web Audio API (visualizador de niveles)
- Permissions API (detección de permisos en vivo)

## 📱 Compatibilidad

| Navegador | Soporte |
|-----------|---------|
| Chrome / Edge / Brave (escritorio) | ✅ Completo |
| Safari (macOS / iOS) | ⚠️ Web Speech API limitada |
| Firefox | ⚠️ No soporta Web Speech API |
| Chrome Android | ✅ Completo |

## 📜 Licencia

MIT
