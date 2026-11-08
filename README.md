# PMI-rec

A deep learning based method for identifying product manufacturing information (PMI) in engineering drawings (EDs).

> **Paper**: Yikai Zong, Yunhong Xu, Maolin Cai, Xiaomeng Tong, Fangwei Ning, Yuxin Zhang.
> *A deep learning based method for identifying product manufacturing information in engineering drawings.*
> **Journal of Intelligent Manufacturing**, published online 11 November 2025.
>
> - Paper (DOI): https://doi.org/10.1007/s10845-025-02731-0
> - Code: https://github.com/ZXWCAX/PMI-rec

```bibtex
@article{zong2025pmi,
  title={A deep learning based method for identifying product manufacturing information in engineering drawings},
  author={Zong, Yikai and Xu, Yunhong and Cai, Maolin and Tong, Xiaomeng and Ning, Fangwei and Zhang, Yuxin},
  journal={Journal of Intelligent Manufacturing},
  year={2025},
  publisher={Springer},
  doi={10.1007/s10845-025-02731-0}
}
```

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
