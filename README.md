# 🤖 Chatbot de Ventas por WhatsApp (Proyecto 2 - Express.js)

## 📋 Descripción general

Este proyecto implementa un **chatbot de ventas** para **WhatsApp**, desarrollado con **Node.js + Express.js**, e integrado con la **IA de DeepSeek** y una base de datos **SQL Server**.

Su objetivo es **automatizar la atención de clientes** y **asistir en la venta de productos**, simulando conversaciones naturales con inteligencia artificial.

> Este proyecto forma parte del estudio comparativo entre tecnologías, junto con otro chatbot desarrollado en **Python + LangChain** (Proyecto 1).  
> Ambos tienen el **mismo objetivo funcional**, pero están desarrollados **por separado**.

---

## 🧠 Tecnologías principales

| Componente | Tecnología |
|-------------|-------------|
| Lenguaje | JavaScript (Node.js) |
| Framework | Express.js |
| IA | DeepSeek API |
| Base de datos | SQL Server |
| Plataforma | WhatsApp |
| API de conexión | Twilio (para pruebas) / WhatsApp Cloud API (producción) |
| Protocolo | MCP |

---

## 🏗️ Estructura del proyecto

Chatbot-Js/
│
├── 📄 package.json
├── 📄 server.js
├── 📄 .env
├── 📄 .gitignore
│
├── 📁 src/
│   ├── 📁 config/
│   │   ├── db.js
│   │   └── deepseek.js
│   │
│   ├── 📁 routes/
│   │   └── whatsappRoutes.js
│   │
│   ├── 📁 controllers/
│   │   └── whatsappController.js
│   │
│   ├── 📁 services/
│   │   ├── twilioService.js
│   │   └── deepseekService.js
│   │
│   ├── 📁 models/
│   │   └── messageModel.js
│   │
│   ├── 📁 utils/
│   │   └── logger.js
│   │
│   └── 📁 middleware/
│       └── errorHandler.js
│
└── 📁 docs/
    └── arquitectura.md

## 📂 Explicación de carpetas
| Carpeta / Archivo  | Descripción                                                                                     |
| ------------------ | ----------------------------------------------------------------------------------------------- |
| `server.js`        | Punto de entrada del servidor Express. Aquí se cargan rutas, middlewares y la conexión inicial. |
| `.env`             | Variables de entorno: credenciales, claves API (DeepSeek, Twilio, SQL Server).                  |
| `.gitignore`       | Evita subir `node_modules`, `.env`, etc.                                                        |
| `package.json`     | Dependencias, scripts y metadatos del proyecto.                                                 |
| `src/config/`      | Configuraciones globales: conexión a base de datos y API de DeepSeek.                           |
| `src/routes/`      | Define las rutas del servidor, ej. `/webhook` para mensajes de WhatsApp.                        |
| `src/controllers/` | Lógica de cada endpoint: recibe mensajes, procesa, responde.                                    |
| `src/services/`    | Conexiones externas (Twilio API y DeepSeek API).                                                |
| `src/models/`      | Modelos o esquemas de datos (mensajes, usuarios, historial, etc.).                              |
| `src/utils/`       | Funciones de apoyo (logs, formateo de mensajes, validaciones).                                  |
| `src/middleware/`  | Middlewares para manejo de errores, autenticación, etc.                                         |
| `docs/`            | Documentación técnica del proyecto (guías, diagramas, API docs).                                |

## 3️⃣ Crear archivo .env (EJEMPLO)

El siguiente codigo, es una representacion grafica de como seria el archivo .env:

PORT=3000

# DeepSeek
DEEPSEEK_API_KEY=tu_clave_deepseek

# Twilio (WhatsApp API)
TWILIO_ACCOUNT_SID=tu_sid
TWILIO_AUTH_TOKEN=tu_token
TWILIO_WHATSAPP_NUMBER=whatsapp:+14155238886

# SQL Server
DB_USER=sa
DB_PASSWORD=12345
DB_SERVER=localhost
DB_NAME=chatbotDB
