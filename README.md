# Animal Image Classification with PyTorch

This repository contains an **image classification project** using PyTorch.  
The model classifies images of animals into multiple categories.

## 📥 Data & Model Download

Large files are stored on Google Drive to keep the repo lightweight:

- **Model:** `best_improved_model.pth`  
- **Dataset folder:** `data/` (contains subfolders per class)

Google Drive (folder):  
https://drive.google.com/drive/folders/1aERYZt_sOPlYZ_N-cQBYtQkZ5AMh55BJ?usp=drive_link

### Option A — Download manually
1. Open the folder link above.
2. Download **`best_improved_model.pth`** and the **`data/`** folder.
3. Place them at the repository root so the structure looks like:
   ```
   .
   ├── data/
   │   ├── Bear/
   │   ├── Camel/
   │   ├── Chicken/
   │   ├── Elephant/
   │   ├── Horse/
   │   ├── Lion/
   │   └── Squirrel/
   ├── best_improved_model.pth
   ├── Imageclassification_KK.ipynb
   ├── requirements.txt
   └── README.md
   ```

### Option B — Download via CLI (with `gdown`)
```bash
pip install gdown
# Download the entire folder (creates a local directory with contents)
gdown --folder "https://drive.google.com/drive/folders/1aERYZt_sOPlYZ_N-cQBYtQkZ5AMh55BJ?usp=drive_link"
# Move into place if needed, e.g.:
# mv best_improved_model.pth .
# mv data ./data
```

> Note: If `gdown --folder` prompts about confirmation, add `-O .` to set output dir.  
> Alternatively, download individual files by their file URLs.

## 🧱 Project Files
- `Imageclassification_KK.ipynb` — main notebook with data loading, preprocessing, model training, evaluation, and results.
- `Imageclassification_KK (copy).ipynb` — backup copy of the notebook.
- `best_improved_model.pth` — trained PyTorch model with the best performance.
- `data/` — dataset (images in class-specific folders).

## 🧠 Model
- Implemented with **PyTorch** (CNN or transfer-learning backbone).
- Optimizer: **Adam**
- Loss: **CrossEntropyLoss**
- Metrics: accuracy and loss curves are plotted.

## 🚀 Quickstart

### 1) Create & activate virtual environment
```bash
python3 -m venv .venv
source .venv/bin/activate   # macOS/Linux
.venv\Scripts\Activate.ps1  # Windows PowerShell
```

### 2) Install dependencies
```bash
pip install -r requirements.txt
```

### 3) Get data & model
- Use the Drive link above (manual or `gdown`).
- Ensure `data/` and `best_improved_model.pth` are at the repo root.

### 4) Run Jupyter Notebook
```bash
jupyter notebook
```
Open `Imageclassification_KK.ipynb` and run all cells.

### 5) Optional: quick inference script
```bash
python inference.py --image path/to/image.jpg --model best_improved_model.pth
```

## 📊 Results
- Final trained model achieves **(insert accuracy here, e.g., ~92%)** on the test set.
- Notebook includes plots of training/validation loss and accuracy.

## 🔧 Requirements
See `requirements.txt`, which includes:
- torch, torchvision
- matplotlib, numpy, pandas, scikit-learn
- jupyter
- gdown (optional; for Drive downloads)

## 📝 Notes
- The dataset folder `data/` should be placed in the root of the repo.
- The trained model file `.pth` can be large; you may exclude via `.gitignore` or use Git LFS.
- For reproducibility, fix seeds: `torch.manual_seed(1337)`.
