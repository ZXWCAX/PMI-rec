**Step 1: Clone the Repository**
```bash
git clone https://github.com/ZXWCAX/PMI-rec.git
cd PMI-rec
git lfs pull

**Step 2: Set Up the Environment**
```bash
conda create -n PMI python=3.12
conda activate PMI
pip install opencv-python pandas Pillow pyclipper Shapely tqdm openai numpy openai openpyxl scikit-image matplotlib

Note:
If you are only using CPU for inference:
```bash
pip install onnxruntime

if using gpu for inference:
```bash
pip install onnxruntime-gpu
