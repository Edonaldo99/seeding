# Apple Music – Caso de Arquitectura de Datos
Proyecto desarrollado como parte del entregable de Consultoría de Arquitectura de Datos, aplicando conceptos de modelamiento documental, seeding de datos, consultas agregadas y diseño de API orientada a dashboard.

La idea del proyecto es simular un escenario realista de analytics para Apple Music: usuarios, artistas, canciones y reproducciones, con consultas que permiten analizar regalías, comportamiento de usuarios y tendencias regionales.

---

## 🎯 Objetivo del Proyecto
El objetivo fue implementar una propuesta completa de arquitectura de datos en MongoDB, capaz de responder cinco consultas analíticas clave, diseñar un dashboard visual que muestre los resultados y documentar los contratos de API necesarios para exponer la información a interfaces externas.

Este proyecto incluye:

- Modelamiento documental en MongoDB
- Población automática de datos con Node.js (seeding script)
- Consultas de analítica usando Aggregation Pipelines
- Prototipo de dashboard en v0.dev
- Diseño de 5 endpoints JSON (API Contract)
- Documentación completa para entrega

---

## Arquitectura Técnica
La solución se compone de cuatro partes principales:

1. **Base de Datos**
   - MongoDB ejecutado en contenedor Docker
   - Modelo de datos documental orientado a analítica (modelo estrella)
   - Colecciones:
     - `users`
     - `artists`
     - `songs`
     - `streams`

2. **Seeding**
   - Script en Node.js que genera:
     - 100 usuarios (incluye usuarios “zombis” sin actividad)
     - 50 canciones
     - 5000+ reproducciones simuladas
   - Datos realistas por región y género musical

3. **Consultas (Analytics)**
   - 5 consultas agregadas para análisis:
     1. Regalías por artista (30 días)
     2. Top 10 canciones por región (7 días)
     3. Usuarios premium sin streams
     4. Demografía de Reggaeton
     5. Fans intensivos de Bad Bunny

4. **Dashboard Prototipo**
   - Diseñado en v0.dev
   - Representa gráficamente los resultados
   - Vista amigable para análisis

5. **Diseño de API**
   - 5 endpoints documentados
   - Especificación en `/api-design/api-spec.md`
   - Respuestas en JSON
   - Capturas limpias exportadas con Carbon

---

## 🗂 Estructura del Repositorio

/
├── api-design/
│ └── api-spec.md
├── database/
│ ├── docker-compose.yml
│ ├── queries.js
│ └── schema-diagram.pdf
├── dashboard-v0/
│ ├── screenshots/
│ └── prompt.txt
├── seed.js
├── package.json
└── README.md


---

## Tecnologías Utilizadas

Docker

MongoDB

Mongo Express

Node.js

Aggregation Pipeline

Faker.js

v0.dev (UI generada con IA)

Carbon (capturas limpias de JSON)

Markdown

## Video de Presentación

El video de presentación explica:

Diseño del modelo

Simulación de datos

Queries analíticos

Dashboard final

Contrato del API

(Agregar el enlace cuando esté disponible)

## Conclusiones Finales

La arquitectura documental implementada permite analizar patrones de uso de Apple Music de manera eficiente y sin joins complejos. El modelo utiliza referencias extendidas como el nombre del artista dentro de songs, lo que facilita consultas rápidas para dashboards.

El seed genera datos realistas con distribución demográfica, hábitos de escucha, usuarios inactivos, y tendencias regionales. Así fue posible obtener métricas como “Top artistas por regalías”, “Top GT”, o “heavy listeners”.

El dashboard muestra cómo una empresa podría visualizar insights clave para toma de decisiones y cómo estos datos pueden ser consumidos por interfaces externas mediante un contrato de API documentado.

Este ejercicio demuestra el uso práctico de bases documentales, pipelines de agregación y visualización de insights desde datos simulados hacia un prototipo real de producto.

## Autor

Elder Donaldo Salazar Garrido
Estudiante de Ingeniería en Sistemas.