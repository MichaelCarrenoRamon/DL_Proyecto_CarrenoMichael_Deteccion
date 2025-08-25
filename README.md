# 🏍️ Detección de uso de casco en motociclistas con YOLOv8

Este proyecto implementa un sistema de **detección automática del uso de cascos en motociclistas** utilizando tres variantes de **YOLOv8** (`nano`, `small` y `medium`).  
El objetivo es comparar el rendimiento de los modelos y determinar cuál logra un mejor equilibrio entre **precisión** y **eficiencia computacional**.

---

## 📂 Ruta elegida y dataset

- **Ruta elegida:** Detección de objetos.  
- **Dataset:** [Helmet Detection Dataset - Kaggle](https://www.kaggle.com/datasets/andrewmvd/helmet-detection) (Licencia CC BY 4.0).  
- **Clases:** `helmet`, `no_helmet`.  
- **Formato original:** VOC, convertido a formato YOLO.  
- **División:**  
  - 70% entrenamiento  
  - 20% validación  
  - 10% prueba  

---

## ⚙️ Cómo ejecutar

Este proyecto puede ejecutarse en **Google Colab** o en local (Jupyter Notebook).  
Se recomienda usar **GPU** (por ejemplo, NVIDIA T4 en Colab).

1. Abrir el notebook en Colab:
   - [![Abrir en Colab](https://drive.google.com/drive/folders/1so2NlO_HlODBnwwim4ImRl7GQGlcC3Rh?usp=drive_link)]

2. Configurar el entorno con:
   ```bash
   pip install ultralytics opencv-python matplotlib

---

## ⚙️ Modelos utilizados
Se entrenaron tres variantes de YOLOv8 en **Google Colab** con GPU NVIDIA T4:

- **YOLOv8n (Nano):** ligero y rápido, ideal para dispositivos móviles.  
- **YOLOv8s (Small):** balance entre velocidad y precisión.  
- **YOLOv8m (Medium):** mayor precisión, costo computacional más alto.  

---

## 📈 Resultados principales
| Modelo   | Precisión (P) | Recall (R) | mAP@50 | mAP@50-95 |
|----------|---------------|------------|--------|-----------|
| YOLOv8n  | 0.72          | 0.86       | 0.81   | 0.49      |
| YOLOv8s  | 0.74          | 0.89       | 0.83   | 0.52      |
| YOLOv8m  | **0.77**      | **0.91**   | **0.86** | **0.55** |

📌 El mejor modelo fue **YOLOv8m**, logrando un mAP@50 de **0.86** en validación.

---

## 🖼️ Ejemplos de inferencia
Ejemplos de detecciones realizadas en el conjunto de prueba:

<p align="center">
  <img src="YOLO_results/yolov8m_helmet/train_batch0.jpg" width="30%">
  <img src="YOLO_results/yolov8n_helmet3/train_batch0.jpg" width="30%">
  <img src="YOLO_results/yolov8s_helmet/train_batch0.jpg" width="30%">
</p>

---
ages/ejemplo3.jpg
## 🚀 Cómo ejecutar el proyecto

1. Clonar el repositorio:
   ```bash
   git clone https://github.com/MichaelCarrenoRamon/DL_Proyecto_CarrenoMichael_Deteccion.git
   cd DL_Proyecto_CarrenoMichael_Deteccion

🚀 Cómo entrenar y evaluar

- Entrenamiento de un modelo YOLOv8:

yolo detect train data=data.yaml model=yolov8n.pt epochs=10 imgsz=640


- Evaluación del modelo entrenado:

yolo detect val model=runs/detect/train/weights/best.pt data=data.yaml


- Predicción sobre imágenes de prueba:

yolo detect predict model=runs/detect/train/weights/best.pt source=images/test/

---

## 👨‍💻 Autor

Michael Enrique Carreño Ramón
Facultad de Ingeniería en Tecnologías de la Información
Universidad Técnica de Machala
📧 michaelcarreno30@gmail.com