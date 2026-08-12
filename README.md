# Mapa Interactivo de Oportunidades Comerciales — Jujuy

[![Estado](https://img.shields.io/badge/Estado-Activo-success.svg)]()

Una herramienta analítica y comercial basada en la **Oferta Productiva Jujuy 2024–2025**. Esta aplicación web permite explorar un mapa interactivo de 155 empresas jujeñas, clasificadas según su probabilidad de importar bienes o requerir insumos específicos, optimizando así la priorización de contactos comerciales y el análisis del ecosistema productivo.

## 🚀 Características Principales

*   **Visualización Geoespacial:** Mapa interactivo desarrollado con Leaflet, que agrupa empresas por localidad mediante clústeres y dimensiona los marcadores según la densidad de entidades comerciales.
*   **Modelo de Scoring (Probabilidad):** Las empresas están segmentadas en tres niveles (Alta, Media, Baja probabilidad) mediante un sistema de puntuación (sobre 100) basado en métricas clave:
    *   *Sector/Insumos (hasta 40 pts)*
    *   *Escala societaria (hasta 30 pts)*
    *   *Bonus por orientación exportadora (15 pts)*
    *   *Bonus tecnológico (10 pts)*
*   **Filtros Dinámicos Integrados:** Búsqueda en tiempo real por nombre o rubro, filtrado por categorías de industria y un gráfico de barras para la distribución interactiva por nivel de probabilidad.
*   **Fichas Analíticas de Empresa:** Tarjetas detalladas que exponen el rubro, la justificación del puntaje obtenido, y datos de contacto directo (teléfono, email, dirección).
*   **Diseño Responsivo y Profesional:** Interfaz adaptada para uso tanto en dispositivos móviles como en dashboards de escritorio, con una paleta de colores corporativa y tipografías de alta legibilidad.

## 🛠️ Tecnologías Utilizadas

El proyecto está construido íntegramente con tecnologías frontend, sin dependencias de un servidor backend, facilitando su despliegue rápido y escalabilidad.

*   **HTML5 / CSS3** (Diseño estructurado utilizando variables CSS nativas y tipografías de Google Fonts: *Fraunces*, *IBM Plex Sans* e *IBM Plex Mono*).
*   **Vanilla JavaScript** (Lógica asíncrona de filtrado, cálculo de distribuciones, renderizado del DOM y manejo del estado).
*   **[Leaflet.js](https://leafletjs.com/)** (Biblioteca open-source para el renderizado interactivo del mapa).
*   **OpenStreetMap** (Proveedor de teselas cartográficas base).

## 📦 Instalación y Uso

Al ser un documento HTML autónomo (Single File Component style), no requiere un proceso de construcción (build) complejo ni configuración de bases de datos.

1. Clona este repositorio en tu entorno local:
   ```bash
   git clone https://github.com/diego305/vendedor.git
   ```
2. Navega al directorio del proyecto:
   ```bash
   cd vendedorjujuy
   ```
3. Abre el archivo `index.html` directamente en tu navegador web preferido, o sírvelo a través de un servidor local (recomendado para evitar bloqueos CORS con algunos navegadores):
   ```bash
   python -m http.server 8000
   ```
   Y accede a `http://localhost:8000`.

## 📊 Estructura de los Datos

La información comercial de las organizaciones se inyecta directamente en el entorno de ejecución a través de un arreglo JSON (`DATA`). Cada registro cuenta con el siguiente esquema de variables:

```json
{
  "empresa": "Nombre de la Entidad",
  "rubro": "Descripción de la actividad / Nomenclador",
  "sectorPts": 40,
  "escalaPts": 30,
  "expBonus": 0,
  "techBonus": 0,
  "score": 70,
  "tier": "Alta",
  "justificacion": "Detalle del cálculo analítico",
  "lat": -24.1858,
  "lng": -65.2995,
  "locApprox": false
}
```
*Nota operativa: Para actualizar el set de datos del mapa, simplemente se debe reemplazar o extender el array `DATA` con los nuevos registros manteniendo esta arquitectura.*

## 🤝 Contribuciones

Las contribuciones para refinar los algoritmos de scoring, optimizar el rendimiento de la interfaz gráfica o integrar nuevas fuentes de datos productivos de la provincia son bienvenidas. 
1. Haz un Fork del repositorio.
2. Crea una rama para tu mejora (`git checkout -b feature/MejoraAnalitica`).
3. Haz commit de tus cambios (`git commit -m 'Agrega nueva métrica al scoring'`).
4. Haz Push a la rama (`git push origin feature/MejoraAnalitica`).
5. Abre un Pull Request.

## 📄 Licencia

Este proyecto se distribuye bajo la Licencia MIT. Consulta el archivo `LICENSE` para más detalles.
README.md
Mostrando README.md.
