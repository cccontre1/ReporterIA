# ReporterIA

### Prototipo experimental para la generación de documentos clínicos estructurados mediante IA

**Versión:** v1.0 — Primer prototipo funcional  
**Autora:** Camila Contreras  
**Tipo:** Proyecto educativo y experimental  
**Entorno principal:** Google Colab + GPU

---

## Sobre el proyecto

ReporterIA es un proyecto personal de exploración del uso de modelos de inteligencia artificial para transformar lenguaje clínico no estructurado en documentos estructurados.

En esta primera versión, el caso de uso elegido es la generación de reportes radiológicos a partir de un dictado de audio.

El objetivo de esta versión no es construir un sistema clínico listo para producción, sino desarrollar y comprender un pipeline completo que integre:

**audio → transcripción → reglas → modelo de lenguaje → estructura → documento**

El proyecto nace como una experiencia de aprendizaje y se irá desarrollando progresivamente a medida que avance mi formación en inteligencia artificial, ciencia de datos y evaluación de modelos.

---

## ¿Qué hace esta versión?

El prototipo permite:

1. Grabar o cargar un dictado de audio.
2. Transcribirlo mediante Faster-Whisper.
3. Seleccionar una plantilla de salida.
4. Enviar la información a un modelo MedGemma ejecutado localmente mediante Ollama.
5. Solicitar una salida estructurada.
6. Generar un informe a partir de la estructura obtenida.
7. Visualizar el resultado mediante una interfaz Gradio.

```text
                  AUDIO
                    │
                    ▼
             Faster-Whisper
                    │
                    ▼
              Transcripción
                    │
                    ▼
          Reglas + plantilla
                    │
                    ▼
              MedGemma
              + Ollama
                    │
                    ▼
          Salida estructurada
                    │
                    ▼
          Informe / metadata
                    │
                    ▼
                Gradio
```

---

## Tecnologías

- Python
- Google Colab
- Faster-Whisper
- MedGemma
- Ollama
- Gradio
- PyTorch
- GPU / CUDA

---

## Estado del proyecto

### v1.0 — Primer prototipo funcional

Esta versión constituye la primera línea base funcional del proyecto.

El objetivo principal es comprobar que el flujo completo puede ejecutarse de extremo a extremo y disponer de una base sobre la cual realizar nuevas iteraciones.

### Próximas etapas

El desarrollo posterior contempla:

- mejorar y sistematizar las reglas;
- ampliar las plantillas;
- incorporar validaciones más robustas;
- construir casos de evaluación;
- definir métricas;
- estudiar los errores del pipeline;
- comparar configuraciones de modelos;
- explorar posteriormente técnicas de entrenamiento o fine-tuning.

Una parte importante del aprendizaje será distinguir cuándo un problema puede resolverse mediante mejores instrucciones y reglas y cuándo sería razonable considerar entrenamiento adicional de un modelo.

---

## Más allá de radiología

Aunque el primer caso de uso es la generación de reportes radiológicos, la arquitectura busca mantener cierta independencia respecto del tipo de documento.

La idea es explorar posteriormente otros documentos clínicos estructurados, por ejemplo:

- entregas de turno;
- notas de evolución;
- resúmenes clínicos;
- otros formatos de documentación estructurada.

La intención es mantener separadas las capacidades generales del pipeline de las plantillas específicas de cada tipo de documento.

---

## Consideraciones sobre el uso clínico

Este proyecto es **educativo y experimental**.

No corresponde a un sistema médico validado, no reemplaza el criterio de profesionales de la salud y no debe utilizarse para tomar decisiones clínicas.

Los ejemplos y pruebas del repositorio deben utilizar información sintética, ficticia o adecuadamente anonimizada.

Una de las líneas futuras será estudiar mecanismos de evaluación y validación más rigurosos.

---

## Limitaciones de v1.0

Esta versión todavía presenta varias limitaciones:

- no cuenta con una evaluación cuantitativa formal;
- las reglas dependen en buena medida de instrucciones entregadas al modelo;
- las plantillas son experimentales;
- no existe entrenamiento propio de los modelos;
- la validación semántica todavía es básica;
- el entorno principal es Google Colab;
- la reproducibilidad completa fuera de Colab todavía requiere trabajo adicional.

Estas limitaciones forman parte del alcance de esta primera versión.

---

## Decisiones de diseño

### Modelos locales

Se utiliza Ollama para ejecutar el modelo de lenguaje localmente dentro del entorno disponible.

### Salida estructurada

El uso de una estructura intermedia busca reducir la dependencia de texto libre y facilitar futuras validaciones.

### Plantillas separadas

Las plantillas se consideran un componente independiente del procesamiento para facilitar la incorporación de nuevos tipos de documentos.

### Trazabilidad

El prototipo conserva información de la transcripción y del procesamiento para facilitar la revisión de los resultados.

---

## Ejecución

El proyecto fue desarrollado principalmente para Google Colab.

Abrir:

`notebooks/ReporterIA_v1.0.ipynb`

y ejecutar las celdas en orden.

El último módulo levanta una interfaz Gradio. En Colab se genera un enlace temporal y la configuración intenta abrir la interfaz automáticamente en el navegador.

### Requisitos generales

- Cuenta de Google con acceso a Colab.
- Entorno con GPU recomendado.
- Conexión a Internet para instalar dependencias y descargar modelos.

---

## Estructura del repositorio

```text
ReporterIA/
├── README.md
├── LICENSE
├── .gitignore
├── requirements.txt
│
├── notebooks/
│   └── ReporterIA_v1.0.ipynb
│
├── src/
│   └── README.md
│
├── config/
│   └── README.md
│
├── evaluation/
│   └── README.md
│
├── docs/
│   ├── TECHNICAL_AUDIT.md
│   ├── ROADMAP.md
│   └── VERSION.md
│
└── assets/
    └── README.md
```

En v1.0 el notebook continúa siendo el principal artefacto de desarrollo. Las demás carpetas anticipan la evolución natural del proyecto.

---

## Sobre esta primera versión

Esta versión representa mi primer prototipo funcional de ReporterIA.

El foco está puesto en aprender mediante la construcción: integrar herramientas, comprender el comportamiento de los modelos, identificar errores y establecer una base que permita evaluar y mejorar el sistema en versiones posteriores.

El proyecto seguirá evolucionando junto con mi aprendizaje.

---

## Licencia

Este proyecto se distribuye bajo licencia MIT. Ver `LICENSE`.
