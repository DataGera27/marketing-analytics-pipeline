# 📊 Marketing Analytics Pipeline

## 📝 Descripción
Pipeline completo de análisis de datos de marketing con Python, SQL y Power BI. Este proyecto automatiza la recopilación, procesamiento y visualización de métricas de marketing.

## 🎯 Objetivos
- Automatizar la extracción de datos de marketing
- Procesar y limpiar datos
- Crear reportes y dashboards en Power BI
- Facilitar la toma de decisiones basada en datos

## 📁 Estructura del Proyecto

marketing-analytics-pipeline/ ├── data/ │ ├── raw/ # Datos sin procesar │ ├── processed/ # Datos procesados │ └── sample_output/ # Resultados de ejemplo ├── sql/ │ └── schema.sql # Estructura de base de datos ├── python/ │ ├── main.py # Script principal │ ├── requirements.txt # Dependencias Python │ └── utils/ # Funciones auxiliares │ ├── logger.py # Configuración de logs │ └── init.py # Inicialización del paquete ├── power_bi/ # Reportes y dashboards ├── automation/ # Scripts de automatización ├── documentation/ # Documentación del proyecto ├── .env.example # Variables de entorno (ejemplo) ├── .gitignore # Archivos a ignorar ├── README.md # Este archivo └── LICENSE # Licencia del proyecto
Code


## 🚀 Requisitos

- **Python 3.9+**
- **SQL Server o PostgreSQL**
- **Power BI Desktop** (para reportes)
- **Git**

## 📦 Dependencias Python

Las dependencias están listadas en `python/requirements.txt`:

- `pandas` - Manipulación de datos
- `numpy` - Cálculos numéricos
- `sqlalchemy` - ORM para bases de datos
- `python-dotenv` - Manejo de variables de entorno
- `requests` - Llamadas HTTP a APIs

## 💻 Instalación

### 1. Clonar el repositorio

```bash
git clone https://github.com/DataGera27/marketing-analytics-pipeline.git
cd marketing-analytics-pipeline

2. Crear entorno virtual
bash

python -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate

3. Instalar dependencias
bash

pip install -r python/requirements.txt

4. Configurar variables de entorno
bash

cp .env.example .env
# Edita el archivo .env con tus credenciales

🎯 Uso
Ejecutar el pipeline completo
bash

python python/main.py

Crear la estructura de base de datos
bash

mysql < sql/schema.sql
# o en PostgreSQL
psql -U usuario -d base_datos -f sql/schema.sql

📊 Flujo de Datos
Code

1. Extracción (APIs/BD) 
   ↓
2. Limpieza (Python/Pandas)
   ↓
3. Almacenamiento (SQL)
   ↓
4. Visualización (Power BI)

📝 Archivos Principales
Archivo	Descripción
python/main.py	Punto de entrada del pipeline
python/utils/logger.py	Sistema de logging
sql/schema.sql	Estructura de base de datos
.env.example	Configuración de ejemplo
README.md	Este archivo
🔧 Configuración
Variables de Entorno
env

DB_HOST=tu_servidor
DB_PORT=5432
DB_NAME=marketing_db
DB_USER=tu_usuario
DB_PASSWORD=tu_contraseña
API_KEY=tu_clave_api
LOG_LEVEL=INFO

📚 Documentación

Para documentación más detallada, consulta la carpeta documentation/.
🤝 Contribuciones

    Fork el repositorio
    Crea una rama para tu feature (git checkout -b feature/AmazingFeature)
    Commit tus cambios (git commit -m 'Add some AmazingFeature')
    Push a la rama (git push origin feature/AmazingFeature)
    Abre un Pull Request

🐛 Reportar Bugs

Si encuentras un bug, por favor abre un Issue.
📄 Licencia

Este proyecto está bajo la licencia MIT. Ver archivo LICENSE para más detalles.
👤 Autor

DataGera27

    GitHub: @DataGera27
    Email: geramary0327270@gmail.com

📅 Última Actualización

Julio 2026

¡Gracias por usar Marketing Analytics Pipeline! 🎉
