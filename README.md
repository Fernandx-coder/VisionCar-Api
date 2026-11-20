# 🚗 VisionCar API (7º A - ITIID)

Bienvenidos al repositorio oficial de la API de VisionCar. Aquí encontrarán los endpoints necesarios para consumir los datos del carrito autónomo en tiempo real.

## 🔗 Endpoint Base
La URL para consultar los datos es:
`https://iosqtfqxpigewzdpjmze.supabase.co/rest/v1/eventos?select=*&order=fecha.desc`

## 🔐 Autenticación (Headers)
Para que la API les permita leer los datos, deben enviar estos headers en su petición HTTP:
- `apikey`: `sb_publishable_WKjH2KA6AaZTzxAKJjurPQ_3t5j7PZu`
- `Authorization`: `Bearer sb_publishable_WKjH2KA6AaZTzxAKJjurPQ_3t5j7PZu`

## 📦 Ejemplo de Petición (JavaScript)
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