# Metodología

!!! tip "Reproducibilidad"
    Las rutas son relativas al repo y los scripts están en `scripts/`.  
    Versiones: Python X.Y, OpenCV Z, etc.

## 1. Datos
- Fuente y licencia.
- División: **train/val/test** (porcentaje o cantidad).
- Anotaciones (formato, herramienta).

## 2. Pipeline
1. **Carga & limpieza:** reglas de descarte, balanceo.
2. **Preprocesamiento:** resize a 224×224, normalización, augmentations.
3. **Modelo/Procedimiento:** arquitectura o algoritmo, hiperparámetros.
4. **Entrenamiento/evaluación:** épocas, early stopping, validación k-fold.

```mermaid
flowchart LR
  A[Imágenes crudas] --> B[Preprocesado]
  B --> C[Entrenamiento/Inferencia]
  C --> D[Métricas/Reportes]
