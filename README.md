# Pre-entrega – Sistema de alerta automática de temperatura en Buenos Aires

Workflow en n8n que consulta la API Open-Meteo y envía alertas automáticas si la temperatura supera los 30°C.

---

## Trigger

El workflow se ejecuta automáticamente cada 30 minutos mediante un Schedule Trigger.

---

## Descripción de nodos

- **Schedule Trigger**  
Dispara automáticamente el workflow cada 30 minutos.

- **HTTP Request**  
Consulta la API pública Open-Meteo para obtener datos climáticos actuales de Buenos Aires.

- **Set (Manejo de datos)**  
Extrae y normaliza los datos relevantes (temperatura, humedad, fecha y zona horaria).

- **IF**  
Evalúa si la temperatura actual supera los 30°C.

- **Send Email / Telegram (rama TRUE)**  
Envía notificaciones automáticas si se detecta temperatura alta.

- **Set (Log registro – rama FALSE)**  
Genera un registro estructurado cuando la temperatura se encuentra dentro del rango normal.

---

## Lógica del Condicional

Se evalúa si la temperatura actual es mayor a 30°C para detectar calor extremo.

---

## Buenas prácticas aplicadas

- Uso de API pública sin autenticación.
- No se exponen credenciales en el repositorio.
- Uso del gestor de credenciales de n8n.
- Separación de nodos por función.
- Manejo explícito de datos con Set.
- Implementación de rama alternativa para registrar eventos no críticos.

---

## Tecnologías utilizadas

- n8n
- Open-Meteo API
- Gmail SMTP
- Telegram Bot API 
