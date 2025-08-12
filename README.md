# CEIA-VpC2-TP

**Trabajo Práctico Final** del curso **Visión por Computadora 2**  
19° Cohorte CEIA · B03 · 2025

---

## 📄 Descripción del proyecto
Clasificación de imágenes médicas [**CT de tórax**](https://www.kaggle.com/datasets/mohamedhanyyy/chest-ctscan-images) para detectar y diferenciar entre:
- Adenocarcinoma
- Carcinoma de células grandes
- Carcinoma de células escamosas
- Tejido normal

Se desarrolló un flujo completo:
1. **Análisis exploratorio** del dataset (EDA)
2. Extracción de características y *baseline* con **Random Forest**
3. Entrenamiento de **CNNs preentrenadas** sobre [RadImageNet](https://github.com/BMEII-AI/RadImageNet) (ResNet50 y DenseNet121)
4. Evaluación, comparación y conclusiones

---

## 📊 Dataset
- Fuente: RadImageNet (≈1.35M imágenes médicas)
- Subconjunto de **~300k CT de tórax**
- División: `train / valid / test`
- Preprocesamiento: normalización, escala de grises, `224x224` px

---

## 🧪 Metodología
- **Baseline**: extracción de features globales (intensidad, contraste, histograma) → Random Forest
- **Deep Learning**: transfer learning desde pesos preentrenados en RadImageNet
- **Data Augmentation**: rotaciones leves, traslación, flip controlado, ruido gaussiano, blur, random erasing

---

## ⚙️ Requerimientos

```bash
pip install -r requirements.txt
```

---

## ▶️ Ejecución
1. Clonar repositorio:

```bash
git clone https://github.com/joshpg190498/CEIA-VpC2-TP.git
cd CEIA-VpC2-TP
```
2. Descargar el dataset de Kaggle y colocarlo en la carpeta raíz.
3. Descargar pesos de RadImageNet y colocarlos en `RadImageNet_pytorch/`
4. Ejecutar notebooks en orden:
   - `1_trabajo_practico_final_EDA_Baseline.ipynb`
   - `2_trabajo_practico_final_ResNet_wandb.ipynb`
   - `3_trabajo_practico_final_DenseNet_wandb.ipynb`

---

## 📈 Resultados
- El **baseline** separa bien *normal* vs *enfermo*, pero falla en subtipos
- Las **CNN preentrenadas** logran mejor desempeño en clasificación fina entre subtipos

---

## 📑 Presentación
[📽 Diapositivas del proyecto](https://docs.google.com/presentation/d/e/2PACX-1vQf9dKKqNPn-8MDOKPEgrccMwRs6gnWVMX0BAcJE0Gy2H6XMsGEjm_r8sAWKD7D-Kadc2_vos7EYHZ_/pub?start=false&loop=false&delayms=3000)

---

## 👥 Autores
- **[Barquinero, Mauro]**
- **[Campos, Mariano]**
- **[Ojeda, Juan Cruz]**
- **[Pérez, José]**