# 🚗 VisionCar API (7º A - ITIID)

Bienvenidos al repositorio oficial de la API de VisionCar. Aquí encontrarán los endpoints necesarios para consumir los datos del carrito autónomo en tiempo real, así como los datos técnicos del hardware y los tiempos de reacción.

## 🔐 Autenticación (Headers)
Para que la API les permita leer los datos, deben enviar estos headers en **todas** sus peticiones HTTP:
- `apikey`: `sb_publishable_WKjH2KA6AaZTzxAKJjurPQ_3t5j7PZu`
- `Authorization`: `Bearer sb_publishable_WKjH2KA6AaZTzxAKJjurPQ_3t5j7PZu`

---

## 🔗 Endpoints Disponibles

### 1. Historial de Decisiones del Carrito (Eventos)
Devuelve todas las decisiones tomadas por la IA (señal detectada, acción y modo).
**URL:**
`https://iosqtfqxpigewzdpjmze.supabase.co/rest/v1/eventos?select=*&order=fecha.desc`

### 2. Componentes del Carrito
Devuelve la lista de hardware, voltajes y descripciones técnicas.
**URL:**
`https://iosqtfqxpigewzdpjmze.supabase.co/rest/v1/componentes?select=*`

### 3. Tiempos de Reacción
Devuelve los datos de latencia y tiempos mínimos/máximos de avance y frenado.
**URL:**
`https://iosqtfqxpigewzdpjmze.supabase.co/rest/v1/tiempos_reaccion?select=*`

---

## 📦 Ejemplo de Petición (JavaScript)
Así se vería el código para consultar los eventos desde su dashboard:

```javascript
const url = "https://iosqtfqxpigewzdpjmze.supabase.co/rest/v1/eventos?select=*&order=fecha.desc";
const headers = {
    "apikey": "sb_publishable_WKjH2KA6AaZTzxAKJjurPQ_3t5j7PZu",
    "Authorization": "Bearer sb_publishable_WKjH2KA6AaZTzxAKJjurPQ_3t5j7PZu"
};

fetch(url, { headers })
  .then(response => response.json())
  .then(data => console.log("Datos del carrito:", data))
  .catch(error => console.error("Error:", error));