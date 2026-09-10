# Roadmap — ReporterIA

## v1.0 — Prototipo funcional

Objetivo: demostrar el pipeline completo.

- Audio
- Whisper
- Reglas
- Plantillas
- MedGemma
- Ollama
- JSON
- Orquestación
- Gradio

**Estado: completado.**

---

## v1.1 — Reglas y validación

- revisar errores recurrentes;
- mejorar reglas;
- separar reglas generales de reglas por plantilla;
- validar campos;
- mejorar el manejo de información ausente;
- explorar JSON Schema.

---

## v1.2 — Evaluación

Construir un conjunto pequeño de casos controlados y definir una salida esperada.

Medir progresivamente:

- WER;
- precisión de extracción;
- cumplimiento de plantilla;
- omisiones;
- información agregada incorrectamente;
- tiempo de procesamiento.

La pregunta pasa de:

> ¿Funciona?

a:

> ¿Qué tan bien funciona y en qué condiciones falla?

---

## v1.3 — Nuevas plantillas

Expandir progresivamente hacia:

- radiología;
- entrega de turno;
- notas clínicas;
- resúmenes estructurados.

La lógica de procesamiento debería permanecer reutilizable.

---

## v2.0 — Experimentación con entrenamiento

Solo después de contar con:

- casos de evaluación;
- métricas;
- errores caracterizados;
- dataset apropiado.

Explorar:

- fine-tuning;
- LoRA/PEFT;
- comparación entre modelos;
- estrategias de entrenamiento.

El entrenamiento será una herramienta para resolver problemas identificados, no un objetivo en sí mismo.
