<div align="center">

## 🌪️ Typhoon Intensity Data Visualisation & Deep Learning

<img src="https://github.com/user-attachments/assets/e531c3b2-3432-4b8a-9e28-c07baa8dccbf" width="800">

</div>

---

This project provides some methods for loading, visualising, and analyzing typhoon imagery and metadata from the **Australian portion of the [Digital Typhoon Dataset](https://agora.ex.nii.ac.jp/digital-typhoon/dataset/)**.  
It enables detailed exploration of typhoon evolution through satellite imagery, trajectory tracking with intensity visualisation, and probabilistic mapping of global typhoon occurrence regions.

---

### 🚀 Features

- **📂 Dataset Loading**
  - Automatically detects typhoon IDs and loads corresponding HDF5 image sequences and metadata CSVs.
  - Handles coordinate (`lat`, `lng`) and intensity (`grade`) attributes.

- **🌀 Visualisation**
  - Display static frames or create **animated GIFs** showing typhoon evolution over time.
  - Plot typhoon **trajectories** on world maps, color-coded by intensity.

- **🌍 Statistical Analysis**
  - Visualize **Gaussian-like probability regions** showing areas with the highest typhoon occurrence densities.
  - Project these probability “bubbles” over world maps, focusing on **Southeast Asia and Australasia**.
  - Color gradients indicate occurrence probability, with legends showing intensity ranges.

- **📈 Extensible Framework**
  - Modular structure for integrating additional analytical components.
  - Upcoming functionality for **machine learning model training** to predict features such as **typhoon intensity and trajectory trends**.

---

🧪 *This repository is a work in progress.*  
Future updates should include **predictive modeling** using historical typhoon data to forecast intensity via Deep Learning.
