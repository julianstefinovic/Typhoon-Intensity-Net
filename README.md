<div align="center">

## 🌪️ Typhoon Data Visualisation & Deep Learning

<div style="display: flex; justify-content: center; align-items: center; gap: 10px;">
  <img src="https://github.com/user-attachments/assets/e531c3b2-3432-4b8a-9e28-c07baa8dccbf" width="400" style="height: 250px; object-fit: cover;">
  <img src="https://github.com/user-attachments/assets/e26c8dc0-c7d0-4d89-be47-eaa7b209824e" width="400" style="height: 250px; object-fit: cover;">
</div>

</div>

---

This project provides some methods for loading, visualising, and analysing typhoon imagery and metadata from the **Australian portion of the [Digital Typhoon Dataset](https://agora.ex.nii.ac.jp/digital-typhoon/dataset/)**.  
It enables detailed exploration of typhoon evolution through satellite imagery, trajectory tracking with intensity visualisation, and probabilistic mapping of global typhoon occurrence regions.

---

### 🚀 Data Exploration & Visualisation

- **📂 Dataset Loading**
  - Automatically detects typhoon IDs and loads corresponding HDF5 image sequences and metadata CSVs.
  - Handles coordinate (`lat`, `lng`) and intensity (`grade`) attributes.

- **🌀 Visualisation**
  - Display static frames or create **animated GIFs** showing typhoon evolution over time.
  - Plot typhoon **trajectories** on world maps, colour-coded by intensity.

- **🌍 Statistical Analysis**
  - Visualise **Gaussian-like probability regions** showing areas with the highest typhoon occurrence densities.
  - Project these probability “bubbles” over world maps, focusing on **Southeast Asia and Australasia**.
  - Colour gradients indicate occurrence probability, with legends showing intensity ranges.

---

### 🤖 Deep Learning - Training, Evaluation & Visualisation

- **🧠 Deep Learning: Typhoon Intensity Classification**
  - Implements a **ConvLSTM-based neural network** for predicting typhoon intensity classes (0–5) from sequences of infrared satellite images.
  - Includes a **convolutional encoder** for spatial feature extraction and a **ConvLSTM cell** for modelling temporal evolution across frames.
  - Outputs predicted intensity grades through a fully connected classification head.

- **⚙️ Training & Validation**
  - Uses **PyTorch** with `tqdm` progress bars to show real-time training and validation progress.
  - Displays **step-level training loss** during each iteration.
  - Performs **validation automatically every N training steps** (configurable via `val_interval`).
  - Tracks the **average running training loss** between validation intervals for more accurate comparison with validation loss.
  - After training, plots both **training and validation loss curves** aligned by validation checkpoint.

- **📊 Evaluation & Metrics**
  - Evaluates model performance on a held-out **test set**.
  - Computes and displays a **confusion matrix** with colour-coded class distributions.
  - Calculates and prints **per-class accuracies** for all intensity categories.
  - Provides a detailed breakdown of model performance, including average accuracy.

- **🖼️ Qualitative Visualization**
  - Randomly selects **25 test samples** for visual inspection in a **5×5 grid**.
  - Displays the **first frame** of each sequence with:
    - **Predicted and real labels** clearly annotated.
    - **Green borders** for correct classifications and **red borders** for incorrect classifications.
  - Enables quick visual verification of model predictions versus ground truth.

- **💾 Model Saving & Loading**
  - Trained models can be saved and reloaded for future inference:
    ```python
    # Save model
    torch.save({
        'model_state_dict': model.state_dict(),
        'optimizer_state_dict': optimizer.state_dict(),
        'epoch': epoch,
        'train_losses': train_losses,
        'val_losses': val_losses
    }, "convlstm_classifier.pth")

    # Load model
    model = ConvLSTMClassifier().to(device)
    checkpoint = torch.load("convlstm_classifier.pth", map_location=device)
    model.load_state_dict(checkpoint['model_state_dict'])
    model.eval()
    ```
  - Supports continued training or standalone inference from saved checkpoints.

- **📈 Extensible Framework**
  - Modular design supports easy integration of new model definitions

---

🧪 **This repository is a work in progress.**  
Future versions may expand on predictive modelling, exploring different deep learning architectures for forecasting typhoon intensity.
