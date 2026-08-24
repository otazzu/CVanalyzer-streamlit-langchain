# 📄 CVanalyzer — Sistema de Evaluación de CVs con IA

Analiza currículums en PDF y evalúa candidatos de manera objetiva contra una descripción de puesto específica, utilizando inteligencia artificial (Google Gemini).

## ✨ Funcionalidades

- Extracción de texto desde archivos PDF
- Análisis de experiencia, habilidades y formación del candidato
- Evaluación del ajuste al puesto (porcentaje 0-100)
- Identificación de fortalezas y áreas de desarrollo
- Recomendación final de contratación
- Interfaz web intuitiva con Streamlit

## 📋 Requisitos

- Python 3.11 o superior
- [UV](https://docs.astral.sh/uv/) — gestor de paquetes y entornos virtuales
- Una API key de Google AI Studio ([consíguela aquí](https://aistudio.google.com/apikey))

## 🚀 Instalación

### 1. Clona o descarga el proyecto

```bash
cd CVanalyzer
```

### 2. Configura tu API key

Copia el archivo de ejemplo y añade tu clave:

```bash
copy .env.example .env
```

Edita `.env` y reemplaza `tu_api_key_aqui` con tu API key real de Google:

```env
GOOGLE_API_KEY=tu_clave_real_aqui
```

### 3. Instala dependencias

```bash
uv sync
```

Este comando crea el entorno virtual `.venv` y instala todas las dependencias definidas en `pyproject.toml`.

### 4. Ejecuta la aplicación

```bash
uv run streamlit run app.py
```

> **Alternativa:** También puedes activar el entorno manualmente:
> ```bash
> # Windows
> .venv\Scripts\activate
> # macOS/Linux
> source .venv/bin/activate
> 
> streamlit run app.py
> ```

La aplicación se abrirá automáticamente en tu navegador en `http://localhost:8501`.

## 📁 Estructura del proyecto

```
CVanalyzer/
├── .env.example          # Plantilla de variables de entorno
├── .gitignore            # Archivos ignorados por Git
├── pyproject.toml        # Dependencias del proyecto
├── app.py                # Punto de entrada
├── models/
│   └── cv_model.py       # Modelo Pydantic de análisis
├── prompts/
│   └── cv_prompts.py     # Prompts de LangChain para el evaluador
├── services/
│   ├── cv_evaluator.py   # Lógica de evaluación con Gemini
│   └── pdf_processor.py  # Extracción de texto de PDFs
└── ui/
    └── streamlit_ui.py   # Interfaz web con Streamlit
```

## 🛠️ Tecnologías

| Herramienta | Uso |
|---|---|
| **Streamlit** | Interfaz web |
| **LangChain** | Orquestación de prompts y cadenas |
| **Google Gemini** | Modelo de IA para análisis |
| **Pydantic** | Validación y estructura de datos |
| **PyPDF2** | Lectura de archivos PDF |
| **UV** | Gestión de entorno virtual y dependencias |

## 📝 Uso

1. **Sube el CV** del candidato en formato PDF
2. **Describe el puesto** de trabajo (requisitos, responsabilidades, habilidades)
3. Haz clic en **"Analizar Candidato"**
4. Revisa el análisis completo: porcentaje de ajuste, habilidades, fortalezas y recomendación
