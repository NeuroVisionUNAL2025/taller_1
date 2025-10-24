# 📷 Taller 1 - Calibración de cámara y transformaciones de intensidad

---

## 🧠 Descripción

Este proyecto forma parte del curso **Visión por Computador** y tiene como objetivo realizar la **calibración de una cámara** utilizando un patrón tipo *checkerboard* (tablero de ajedrez), así como implementar **transformaciones de intensidad a nivel de píxel** de forma manual.

A través de este taller se busca:
- Comprender los fundamentos de la calibración de cámaras.
- Analizar el comportamiento de la luz en imágenes capturadas en distintas condiciones.
- Aplicar operaciones de manipulación de imágenes y segmentación básica.

---

## 🧩 Estructura del proyecto

```
NeuroVision
Taller1/
│
├── frames_transformaciones/   (para guardar el GIF)
├── imagenes/
│   ├── calibracion/
│   │   ├── IMG_1555.JPG
│   │   ├── IMG_1556.JPG
│   │   └── ...
│   └──  universidad/
│       ├── IMG_1592.JPG
│       ├── IMG_1593.JPG
│       ├── ...
│       ├── IMG_1618.JPG   (foto de la fachada diurna)
│       ├── IMG_1620.JPG.  (foto de la fachada nocturna) 
│       └── ...
├── README.md
├── requirements.txt
└── Taller1.ipynb   (documento principal)

```

Las imágenes de calibración deben encontrarse en:
```
/content/drive/Shareddrives/NeuroVision/Taller1/imagenes/calibracion/
```

---

## ⚙️ Instalación

No es necesario instalar dependencias adicionales; todas se encuentran especificadas dentro del notebook principal:

```python
import cv2
import numpy as np
import os
import glob
import matplotlib.pyplot as plt
from google.colab import drive
```

### 🔐 Acceso a Google Drive
Antes de ejecutar el código, asegúrese de **dar acceso completo a Google Colab** a su Google Drive, para que el notebook pueda acceder automáticamente a los archivos compartidos sin errores.

---

## 🧾 Contenido del proyecto

El taller consta de **cinco puntos principales**:

### 1️⃣ Calibración de la cámara  
Se utiliza una serie de imágenes del tablero de ajedrez para **estimar los parámetros intrínsecos y de distorsión** de la cámara, aplicando funciones de **OpenCV**.

### 2️⃣ Transformaciones de intensidad  
Se implementan operaciones a nivel de píxel sobre imágenes tomadas desde el mismo punto (una de día y otra de noche), para **ajustar brillo, contraste y tonalidades** manualmente.

### 3️⃣ Transformaciones de rotación y traslación  
Se aplican **rotaciones** y **traslaciones** sobre las imágenes, analizando cómo afectan la perspectiva y posición espacial del contenido visual.

### 4️⃣ Distribución de intensidades  
Se calcula e interpreta el **histograma de intensidades** de las imágenes, explorando técnicas como **ecualización de histograma** para mejorar el contraste.

### 5️⃣ Segmentación de imágenes  
Se implementan métodos básicos de **segmentación**, incluyendo **umbralización (thresholding)** y **operaciones morfológicas** para separar regiones de interés.

---

## 🤝 Autores y agradecimientos

**Equipo:** [NeuroVision]  
**Universidad Nacional de Colombia**  
**Curso:** Visión por Computador  
**Fecha:** Octubre 2025  

---

## 📄 Licencia

Este proyecto fue desarrollado con fines **académicos y educativos**.  
Uso libre citando la fuente correspondiente.  

---

## 🚀 Estado del proyecto

 🟢 *Terminado*
