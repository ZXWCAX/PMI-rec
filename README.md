**Step 1: Clone the Repository**
```bash
git clone https://github.com/ZXWCAX/PMI-rec.git
cd PMI-rec
git lfs pull
```

**Step 2: Set Up the Environment**
```bash
conda create -n PMI python=3.12
conda activate PMI
pip install opencv-python pandas Pillow pyclipper Shapely tqdm openai numpy openai openpyxl scikit-image matplotlib
```

Note:
If you are only using CPU for inference:
```bash
pip install onnxruntime
```
if using gpu for inference:
```bash
pip install onnxruntime-gpu
```

**Step 3: inference**
```bash
python detect.py
```

<br>
<br>

**EX.1: Change the ED**

Modify line 11 of detect.py:
```python
raw_img_path = 'test_image/2025-A-1-4706.png'
```

**EX.2: Change the providers**

Modify line 88 of detect.py:
CPU:
```python
providers = ['CPUExecutionProvider']
```
GPU:
```python
providers = ['CUDAExecutionProvider']
```

**EX.3: General PMI**

Configure your own MLLM API key or set `raw_img_path` to `False` to disable General PMI recognition from line 11 to line 18.
```python
General_PMI_mllm_det = True
client = OpenAI(
    api_key="XX-XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX",
    base_url="https://dashscope.aliyuncs.com/compatible-mode/v1",
)
mllm_model_name = "qwen-vl-max"
```
