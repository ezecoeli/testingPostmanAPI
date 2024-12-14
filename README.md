# **Resumen del Proyecto**

Este proyecto tiene como objetivo demostrar el uso de Postman para realizar pruebas automatizadas sobre la API de [The Dog API](https://thedogapi.com/). A continuación, se describen los pasos realizados, las configuraciones implementadas y las pruebas creadas para validar diferentes aspectos de la API.

---

## **Configuraciones Realizadas**

### **1. Variables de Entorno**
- Configuramos variables de entorno para gestionar dinámicamente valores como `API_KEY`, `breed_id`, y `vote_id`.
- Estas variables permiten reutilizar valores sin necesidad de configurarlos manualmente en cada solicitud.

### **2. Pre-request Scripts**
- Implementamos scripts previos para generar datos dinámicos, como valores de votos (`vote_value`), y para configurar headers de autenticación mediante la clave de API.

### **3. Scripts de Prueba**
- Añadimos scripts de validación (`Tests`) para verificar las respuestas de la API:
  - Validación de códigos de estado.
  - Verificación de propiedades en las respuestas JSON.
  - Almacenamiento de valores dinámicos (como `breed_id` y `vote_id`) para usarlos en solicitudes posteriores.

---

## **Pruebas Implementadas**

### **1. Solicitudes Básicas**
- **GET /v1/breeds**: Obtenemos una lista de razas y validamos:
  - Código de estado (200).
  - Que cada raza tenga un `id` y un `name`.
  - Almacenamos el `breed_id` de la primera raza para futuras pruebas.

- **POST /v1/votes**: Creamos un voto dinámico utilizando valores generados previamente y validamos:
  - Código de estado (201).
  - Que la respuesta contenga un `id` del voto creado.

- **DELETE /v1/votes/{vote_id}**: Eliminamos un voto previamente creado y verificamos:
  - Código de estado (200).
  - Confirmación del éxito en la eliminación.

### **2. Pruebas con Datos Dinámicos**
- Usamos scripts para extraer valores dinámicos de las respuestas (por ejemplo, `breed_id`) y configurarlos como variables de entorno para solicitudes posteriores.

### **3. Data-Driven Testing**
- Integramos un archivo JSON con datos de prueba (`data.json`) para realizar múltiples solicitudes `POST /v1/votes` con diferentes valores de entrada.
- Esto permitió validar la funcionalidad de la API con diferentes escenarios.

### **4. Validaciones de Rendimiento**
- Añadimos pruebas globales para medir el tiempo de respuesta de cada solicitud, asegurando que los tiempos sean menores a un umbral definido (500 ms).

---

## **Documentación de la Colección**
- Descripciones detalladas en cada solicitud para explicar:
  - Propósito de la solicitud.
  - Parámetros utilizados.
  - Validaciones realizadas.
- Uso de Markdown para enriquecer la presentación de la colección.
- Generación de documentación pública mediante la función **View in Web** para compartir el trabajo realizado.

---

## **Extensiones Avanzadas**

### ** Organización**
- Agrupamos las solicitudes en carpetas lógicas para mantener una estructura clara y fácil de navegar.

