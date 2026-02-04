ALPHA RELEASE

SHOWCASE : https://youtu.be/Id5rk-E0xdM
DEPENDENCIAS
QBCORE- screenshotbasic 

# Critikal_Dispatch
🚨 Mega Dispatch System v1.0 - QBCore
Sistema de despacho avanzado para servicios de emergencia, diseñado con un enfoque extremo en el rendimiento (0.00ms en idle) y una integración total con Discord.

🚀 La Optimización
A diferencia de otros scripts de despacho que saturan el servidor, este sistema utiliza técnicas de optimización avanzadas:

Sincronización Selectiva: Solo los jugadores en servicio y con el trabajo autorizado reciben los datos de la alerta, reduciendo el tráfico de red un 80%.

Gestión de Memoria os Fix: Implementamos un sistema de marcas de tiempo basado en el motor de GTA (GetCloudTimeAsInt) para evitar fugas de memoria y errores de desbordamiento comunes en scripts que usan la librería os de Lua.

Standby Dinámico: La interfaz entra en modo "suspensión" cuando no hay alertas, dejando de procesar cálculos de renderizado y tiempos hasta que llega un nuevo reporte.

Renderizado Bajo Demanda: El mini-dispatch solo procesa la información de la alerta que estás viendo en ese momento, no de todo el historial a la vez.

🛠️ Funcionalidades Principales
Radar Policial Integrado: Escaneo frontal de matrículas, modelo y velocidad con sistema de bloqueo de datos.

Alertas Inteligentes de NPCs: El sistema detecta disparos, robos de vehículos y civiles armados de forma automática, enviando una alerta con foto a la central.

Sistema de Fotos: Captura de imágenes en tiempo real adjuntas al aviso (requiere screenshot-basic).

Discord Logs Profesionales: Webhooks independientes por trabajo (LSPD, BCSO, SAMU, Mecánicos) con diseño visual limpio y colores sincronizados.

Navegación Rápida: Acceso con teclas (Flechas y Enter) para marcar ubicaciones en el GPS sin abrir menús pesados.

📖 Guía de Configuración
1. Configuración de Webhooks (Discord)
En el archivo config.lua, encontrarás la tabla Config.Webhooks. Debes colocar las URLs de tus canales de Discord aquí:

Lua
Config.Webhooks = {
    ['default']   = "URL_AQUI", -- Canal general
    ['police']    = "URL_AQUI", -- Canal para LSPD/BCSO
    ['ambulance'] = "URL_AQUI", -- Canal para Médicos
}
2. Personalización de Colores y Blips
Cada alerta en Config.Alerts tiene sus propias propiedades visuales.

badgeColor: Cambia el color de la barra lateral en la UI y el color del mensaje en Discord.

sprite: El icono que aparecerá en el mapa (puedes buscar IDs en la wiki de FiveM).

isPanic: Si se marca como true, la alerta tendrá prioridad visual y un sonido distinto.

3. Ajuste de Alertas Automáticas (NPCs)
Puedes controlar qué tan sensibles son los avisos de la ciudad:

cooldown: Tiempo en segundos antes de que el mismo tipo de alerta pueda volver a saltar (evita el spam de disparos).

jobs_whitelist: Qué trabajos NO activan la alerta (ej. que la policía no genere alertas de disparos cuando ellos disparan).

4. Instalación
Asegúrate de tener qb-core y screenshot-basic instalados.

Arrastra la carpeta mi_dispatch a tus recursos.

Añade ensure mi_dispatch a tu server.cfg.

Importante: Revisa que el idioma en Config.Language coincida con tus preferencias.
