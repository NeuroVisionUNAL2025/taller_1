
---

## `docs/resultados.md`
```markdown
# Resultados

## 1. Métricas principales
| Conjunto | Accuracy | Precision | Recall | F1 |
|---------:|---------:|----------:|-------:|---:|
| Train    |    0.98  |     0.97  |  0.98  |0.98|
| Val      |    0.93  |     0.92  |  0.91  |0.92|
| Test     |    0.91  |     0.90  |  0.89  |0.90|

!!! note "CSV descargable"
    - [Tabla completa (CSV)](assets/tabla_resultados.csv)

## 2. Visualizaciones
### 2.1. Curvas de entrenamiento
![Pérdida y accuracy](assets/fig_loss_acc.png)

### 2.2. Matriz de confusión
![Matriz de confusión](assets/fig_confusion.png)

### 2.3. Ejemplos cualitativos
Grid de aciertos y errores relevantes:  
![Muestras](assets/fig_ejemplo.png)

## 3. Comparativas / Ablaciones
- **Baseline** vs **Modelo con augmentations**.
- Tabla/figura que muestre las diferencias.

## 4. Limitaciones observadas
- Clases minoritarias, iluminación, oclusiones, etc.
