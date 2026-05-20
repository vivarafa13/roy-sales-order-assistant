# 🚀 Roy / Sales Order Assistant

AI-powered multimodal sales assistant (Gemini API, Make, and Telegram) for real-time order automation.

---

## 📝 Descripción del Proyecto
Este proyecto implementa una solución de arquitectura Cloud-Native y Multimodal diseñada para optimizar la toma de pedidos en el sector de consumo masivo (P&G). A través de un bot de Telegram, los preventistas en la calle pueden dictar un pedido por nota de voz; el sistema procesa el audio de forma asincrónica en la nube y extrae variables estructuradas directamente hacia un sistema de reportes analíticos.

## 🏗️ Arquitectura del Sistema
El flujo de datos opera de forma 100% asincrónica en la nube, optimizando el uso de hardware local (Cómputo Local Cero):

1. **Captura (Ingestion):** Telegram Bot intercepta el archivo de audio (.ogg).
2. **Staging:** Módulo de descarga e interfaz con la API de Google File.
3. **Procesamiento (Cerebro):** Google Gemini AI (`Extract structured data`) aplica ingeniería de prompts y valida el esquema de datos.
4. **Persistencia:** Google Sheets almacena de forma normalizada las variables de negocio.

## 📊 Esquema de Datos Normalizado
El "Response Schema" configurado en la IA garantiza que los datos se almacenen de forma atómica:
* `vendedor`: Identificador del preventista.
* `cliente`: Nombre del comercio o local comercial.
* `ubicacion`: Dirección física validada.
* `producto`: Nombre y marca comercial extraída.
* `cantidad`: Unidades numéricas correspondientes.

## ⏱️ Impacto de Negocio
* **Eficiencia operativa:** Reducción del tiempo de carga de 15 minutos a 2.2 minutos por pedido (85% de ahorro de tiempo).
* **Mitigación de errores:** Eliminación del error humano en la transcripción de pedidos complejos mediante el uso del comando de control "próximo ítem".
