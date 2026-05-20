# 🚀 Roy / Sales Order Assistant

AI-powered multimodal sales assistant (Gemini API, Make, and Telegram) for real-time order automation.

---

## 📝 Descripción del Proyecto
Este proyecto implementa una solución de arquitectura Cloud-Native y Multimodal diseñada para optimizar la toma de pedidos en el sector de consumo masivo. A través de un bot de Telegram, los preventistas en la calle pueden dictar un pedido por nota de voz; el sistema procesa el audio de forma asincrónica en la nube y extrae variables estructuradas directamente hacia un sistema de reportes analíticos.

## ⚙️ Functional Design

### Phase 1 — Multimodal Data Engine

**Input**
* Telegram Voice Message (Unstructured Audio / .ogg)
* System Instruction Prompt (P&G Sales Context)

**Processing**
* Cloud Staging via Google File API
* LLM Semantic Inference (Gemini 1.5 Flash)
* Schema-based Data Extraction

**Output**
* Structured Sales Data:
    * `vendedor`: Seller Identification
    * `cliente`: Client Business Inference
    * `ubicacion`: Geo-spatial Location
    * `producto`: Product Catalog Mapping
    * `cantidad`: Units / Numeric Quantities
* Data Persistence: Automated Google Sheets Logging

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
