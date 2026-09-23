# Optimización de flujos de despliegue en un entorno de datos

En el mundo de la ingeniería de datos, la optimización de los flujos de despliegue es crucial para garantizar la eficiencia y seguridad en el procesamiento de datos. Este reto te llevará a través de las etapas necesarias para integrarte con herramientas de CI/CD, permitiendo el despliegue y la orquestación de pipelines de manera efectiva.

## Informacion General

| Campo | Valor |
|-------|-------|
| **Tema** | Fundamentos de DevSecOps |
| **Nivel** | advanced-l2 |
| **Tipo** | practical |
| **Tiempo estimado** | 5-7 horas |

## Fases del Reto

### Fase 0: Configuración del Proyecto

**Objetivo:** Obtener el proyecto base funcional enviando el Código Base a un asistente de IA, que lo analizará, corregirá errores y generará un ZIP listo para usar.

**Tiempo estimado:** 15-30 minutos

**Instrucciones:**

- Asegúrate de tener instalado para ejecutar el proyecto: Python 3.10+, pip, VS Code o similar.
- Copia todo el contenido del campo **Código Base** de este reto — incluyendo el texto de instrucciones que aparece al inicio.
- Abre un asistente de IA (Claude en claude.ai, ChatGPT o Gemini — se recomienda Claude), pega el contenido copiado en el chat y envíalo.
- El asistente analizará los archivos, corregirá errores y generará un archivo ZIP descargable. Descárgalo y extráelo en la carpeta donde quieras trabajar.
- Ejecuta `pip install -r requirements.txt` y luego arranca el proyecto. Si no hay errores, estás listo.

**Entregable:** El proyecto compila/arranca sin errores.

<details>
<summary>Pistas de conocimiento</summary>

- Copia el Código Base completo incluyendo el texto de instrucciones al inicio — esas instrucciones le indican al asistente exactamente qué hacer con los archivos.
- Si el asistente no genera el ZIP automáticamente al terminar el análisis, escríbele: "genera el ZIP ahora".
- Si el proyecto tiene errores al arrancar, comparte el mensaje de error con el mismo asistente para que lo corrija.

</details>

### Fase 1: Exploración del entorno de despliegue

**Objetivo:** Entender las herramientas y procesos actuales de despliegue en un entorno de datos.

**Tiempo estimado:** 1 hora

**Instrucciones:**

- Investiga las herramientas de CI/CD utilizadas en tu organización.
- Identifica los pasos actuales en el proceso de despliegue de un pipeline de datos.

**Entregable:** Documento que describa las herramientas y procesos actuales de despliegue.

<details>
<summary>Pistas de conocimiento</summary>

- Considera cómo las herramientas de CI/CD pueden automatizar y mejorar el despliegue de pipelines.
- Piensa en las posibles integraciones con otras herramientas y servicios.

</details>

### Fase 2: Diseño de un pipeline de despliegue optimizado

**Objetivo:** Diseñar un pipeline de despliegue que integre las herramientas de CI/CD de manera efectiva.

**Tiempo estimado:** 2 horas

**Instrucciones:**

- Diseña un pipeline de despliegue que incluya etapas de compilación, prueba y despliegue.
- Identifica los puntos de integración con las herramientas de CI/CD.

**Entregable:** Diagrama y descripción del pipeline de despliegue diseñado.

<details>
<summary>Pistas de conocimiento</summary>

- Considera cómo las etapas de compilación, prueba y despliegue se integran en el pipeline.
- Piensa en las posibles mejoras y optimizaciones que se pueden aplicar al pipeline.

</details>

### Fase 3: Implementación y validación del pipeline de despliegue

**Objetivo:** Implementar y validar el pipeline de despliegue diseñado, asegurando su eficiencia y seguridad.

**Tiempo estimado:** 2 horas

**Instrucciones:**

- Implementa el pipeline de despliegue diseñado en la fase anterior.
- Valida el pipeline asegurando que cumple con los estándares de eficiencia y seguridad.

**Entregable:** Pipeline de despliegue implementado y validado.

<details>
<summary>Pistas de conocimiento</summary>

- Considera cómo validar el pipeline para asegurar que cumple con los estándares de eficiencia y seguridad.
- Piensa en posibles mejoras y optimizaciones adicionales que se pueden aplicar al pipeline.

</details>

## Dimensiones Evaluadas

- **queEs**: ¿Qué es un pipeline de despliegue y cuáles son sus componentes principales?
- **paraQueSirve**: ¿Para qué sirve integrar herramientas de CI/CD en un pipeline de despliegue?
- **comoSeUsa**: ¿Cómo se integran las etapas de compilación, prueba y despliegue en un pipeline de despliegue?
- **erroresComunes**: ¿Cuáles son los errores comunes al diseñar y implementar un pipeline de despliegue?
- **queDecisionesImplica**: ¿Qué decisiones implica la implementación y validación de un pipeline de despliegue?

## Criterios de Evaluacion

- Explorar y entender el entorno de despliegue actual.
- Diseñar un pipeline de despliegue que integre las herramientas de CI/CD de manera efectiva.
- Implementar y validar el pipeline de despliegue diseñado, asegurando su eficiencia y seguridad.

## Como trabajar con un asistente de IA

- **AGENTS.md** — instrucciones nativas del repo (Cursor, Codex, Copilot, Gemini, Claude Code). Abrí el proyecto y el agente las carga solo.
- **PROMPT_MEJORA.md** — el mismo prompt, para copiar y pegar en un chat (claude.ai, ChatGPT, etc.).

---

*Reto generado automaticamente por Challenge Generator - Pragma*
