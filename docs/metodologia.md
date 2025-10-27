# Metodología

El trabajo se desarrolló como una práctica experimental de visión por computador utilizando imágenes reales capturadas por el equipo y procesadas en Python con OpenCV, NumPy y Matplotlib. Se estructuró en cinco etapas: calibración de cámara, transformaciones de intensidad, transformaciones geométricas, ecualización de histograma y segmentación por color.

## 1. Calibración de la cámara
Se tomaron múltiples imágenes de un tablero de ajedrez desde distintas posiciones. Para cada imagen se detectaron esquinas internas con cv2.findChessboardCorners, se refinaron subpíxel con cv2.cornerSubPix, y se emparejaron con sus coordenadas reales. Con todos los pares 2D↔3D se estimaron los parámetros intrínsecos (matriz K), los coeficientes de distorsión radial y tangencial y los parámetros extrínsecos (rotación y traslación) mediante cv2.calibrateCamera. Se registró el error RMS de reproyección como métrica de calidad y se generaron imágenes corregidas (sin distorsión) para comparar visualmente el efecto, sobre todo en los bordes.

## 2. Transformaciones de intensidad a nivel de píxel
Se capturaron dos fotografías de la misma fachada, una de día (≈6 a. m.) y otra de noche (≈7 p. m.), desde el mismo punto. Sobre estas imágenes se implementaron manualmente operaciones de brillo (suma constante), contraste (escalamiento respecto a la media) y corrección gamma (ajuste no lineal de luminancia). También se realizaron combinaciones punto a punto entre ambas imágenes: suma, resta, multiplicación y división, controlando saturación y divisiones por cero. Esto permitió observar diferencias de iluminación y pérdida de detalle entre ambas condiciones. 

## 3. Transformaciones geométricas
Se definió una función que cargó una imagen base y aplicó en secuencia varias transformaciones afines: traslaciones, rotaciones alrededor del centro y escalamiento. Después de cada transformación se guardó el fotograma intermedio. Con esos fotogramas se construyó una animación (GIF/HTML) para visualizar de forma continua la evolución espacial de la imagen.

## 4. Ecualización de histograma
Se analizaron las imágenes de fachada día/noche en términos de distribución de intensidades. Cada imagen se pasó a espacio YUV y se aplicó ecualización de histograma sobre el canal Y (luminancia). Luego se reconstruyó la imagen en RGB y se compararon histogramas antes y después. Esto permitió evaluar cómo la ecualización mejora contraste global, especialmente en condiciones nocturnas.

## 5. Segmentación y conteo por color
Se capturó una escena con varios objetos de colores distintos. La imagen se convirtió a HSV y se definieron rangos de color (H, S, V) para cada categoría. Con cv2.inRange se generaron máscaras binarias por color y luego se aplicaron operaciones morfológicas para limpiar ruido. Finalmente, se extrajeron contornos, se dibujaron sobre la imagen original y se calculó tanto el número de objetos de cada color como el área aproximada (en píxeles) de cada objeto.