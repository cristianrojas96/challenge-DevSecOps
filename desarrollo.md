# Desarrollo del reto: Optimización de flujos de despliegue en un entorno de datos

---

## Fase 0: Configuración del proyecto

### Problemas encontrados y cómo se resolvieron

| # | Problema | Causa | Solución |
|---|---|---|---|
| 1 | `ERROR: No matching distribution found for Jenkins==2.346` al instalar `requirements.txt` | La librería `Jenkins` no existe en PyPI. Jenkins es la herramienta que ejecuta el pipeline, no una dependencia de Python. | Se eliminó de `requirements.txt` |
| 2 | `pytest` estaba en `requirements.txt` | `pytest` no se requiere en producción; es para desarrollo, para probar el código. | Se creó `requirements-dev.txt` (incluye `-r requirements.txt` + `pytest`) |
| 3 | `pytest` falla con `ModuleNotFoundError: No module named 'src'` | Sin `tests/__init__.py`, pytest agrega `tests/` a `sys.path` y no encuentra `src` | Se agregó `tests/__init__.py`; ahora la raíz del proyecto queda en `sys.path` |

### Aprendizajes

- La regla de "subir hasta no encontrar `__init__.py`" es de pytest, no de Python.
- `python src/main.py` pone `src/` en `sys.path`; `python -m src.main` pone la carpeta desde donde se ejecuta.
- Los `__init__.py` se suben al repositorio; `.venv/` y `__pycache__/` no.

---

## Fase 1: Exploración del entorno de despliegue

### 1. Contexto y alcance

Se analiza el proceso de despliegue de productos de datos que incluyen desde infraestructura y procesamiento (dbt o Glue) hasta orquestación en Airflow, basado en el conocimiento adquirido al trabajar con el cliente.

### 2. Pipeline actual en la organización (Azure DevOps)

#### Herramientas y destino

- **Herramienta de CI/CD:** Azure DevOps Pipelines
- **Nube:** los productos de datos se despliegan en AWS.
- Se despliegan distintos componentes según la necesidad de cada producto de datos.

#### Componentes que se despliegan

| Componente | Herramienta / servicio | CI | CD |
|---|---|---|---|
| Infraestructura | Terraform, que despliega componentes en AWS | Detección de secretos con Gitleaks y TruffleHog, entre otras validaciones | Requiere aprobaciones |
| DAGs | Airflow (MWAA) como orquestador | Gitleaks, configuración de versión de Python, dependencias de MWAA, linters | Gitleaks y el despliegue del DAG |
| Código de Glue | AWS Glue | Detección de secretos con Gitleaks y ejecución de pruebas con cobertura, entre otras validaciones | Aprobación para producción (Approval PDN) y otra validación con Gitleaks |
| Proyectos dbt | dbt (serverless) | Detección de secretos con Gitleaks, inspección del proyecto dbt y carga de los modelos a un S3 temporal | Validación con Gitleaks; los modelos se ejecutan desde Airflow |

#### Proceso de ejecución

- El pipeline **no se ejecuta automáticamente** al hacer merge: una persona entra a Azure DevOps, busca su pipeline y lo ejecuta (Continuous Delivery manual).
- Hay **aprobaciones por seguridad**: debe existir un responsable que verifique qué se va a desplegar antes de que el pipeline continúe.

#### Seguridad y Calidad

- Se hace uso de credenciales temporales de AWS.
- Se ejecuta Gitleaks para detectar secretos en el código.
- Uso de herramientas como Checkov y TFLint para Terraform
- Uso de Sonar para analisis de calidad de codigo



