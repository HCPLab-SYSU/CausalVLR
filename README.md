<div align="center">

<div align="center">
  <a href="https://www.sysu-hcp.net/">
    <img src="images/hcp.png" width="400"/>
  </a>
  <a href="">
    <img src="images/LOGO.png" width="400"/>
  </a>
</div>

# CausalVLR

CausalVLR is a Python open-source framework for causal relation discovery and causal inference that implements most advanced causal learning algorithms for various visual-linguistic reasoning tasks, such as **Medical Report Generation**, **Video Question Answering**, and other causal reasoning tasks to be integrated.

[![Python](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![PyTorch](https://img.shields.io/badge/pytorch-2.0+-orange.svg)](https://pytorch.org/)
[![License](https://img.shields.io/badge/license-Apache%202.0-green.svg)](LICENSE)

[📘Documentation](docs/) |
[🛠️Installation](docs/Installation_Guide.md) |
[🚀Quick Start](docs/Quick_Start.md) |
[👀Model Zoo](#model-zoo) |
[🆕Update News](#whats-new) |
[🤔Reporting Issues](https://github.com/yourusername/CausalVLR/issues)

</div>

---

## 📄 Table of Contents

- [📚 Introduction](#introduction)
- [🚀 What&#39;s New](#whats-new)
- [👨‍🏫 Get Started](#get-started)
- [👀 Model Zoo](#model-zoo)
- [🔬 Related Research](#related-research)
- [🎫 License](#license)
- [🖊️ Citation](#citation)
- [🙌 Contribution](#contribution)
- [🤝 Acknowledgement](#acknowledgement)

## 📚 Introduction

CausalVLR is a Python open-source framework based on PyTorch for causal relation discovery and causal inference that implements most advanced causal learning algorithms for various visual-linguistic reasoning tasks.

<div align="center">
<img src="./images/framework.png" width="800" alt="Framework Overview"/>
</div>

<details open>
<summary><b>Major Features</b></summary>

- **Modular Design**

  We decompose the causal framework of visual-linguistic tasks into different components and one can easily construct a customized causal-reasoning framework by combining different modules.

- **Support of Multiple Tasks**

  The toolbox directly supports multiple visual-linguistic reasoning tasks such as **Medical Report Generation (MRG)**, **Video Question Answering (VQA)**, and other causal reasoning applications to be integrated.

- **Most Advanced**

  The toolbox stems from the codebase developed by cutting-edge research, implementing published methods such as CMCRL (Cross-Modal Causal Representation Learning) and CRA (Cross-modal Causal Relation Alignment), with most advanced performance.

- **Unified API**

  Provides consistent pipeline APIs for different tasks, making it easy to switch between models and datasets with minimal code changes.

❗ **Note:** The framework is actively being developed. Feedbacks (issues, suggestions, etc.) are highly encouraged.

### ✨ **CMCRL** - Cross-Modal Causal Representation Learning for Radiology Report Generation

<div align="center">
<img src="images/VLCI.gif" width="700" alt="VLCI Method Demo"/>
</div>

**Radiological Cross-modal Alignment and Reconstruction Enhanced (RadCARE)** with **Visual-Linguistic Causal Intervention (VLCI)** achieves state-of-the-art performance on medical report generation benchmarks.

#### Results on IU X-Ray Dataset

| Model            | B@1       | B@2       | B@3       | B@4       | C         | R         | M         |
| :--------------- | :-------- | :-------- | :-------- | :-------- | :-------- | :-------- | :-------- |
| R2Gen            | 0.470     | 0.304     | 0.219     | 0.165     | -         | 0.371     | 0.187     |
| CMCL             | 0.473     | 0.305     | 0.217     | 0.162     | -         | 0.378     | 0.186     |
| PPKED            | 0.483     | 0.315     | 0.224     | 0.168     | 0.351     | 0.376     | 0.190     |
| CA               | 0.492     | 0.314     | 0.222     | 0.169     | -         | 0.381     | 0.193     |
| AlignTransformer | 0.484     | 0.313     | 0.225     | 0.173     | -         | 0.379     | 0.204     |
| M2TR             | 0.486     | 0.317     | 0.232     | 0.173     | -         | 0.390     | 0.192     |
| **CMCRL (Ours)** | **0.505** | **0.334** | **0.245** | **0.189** | **0.456** | **0.397** | **0.204** |

#### Results on MIMIC-CXR Dataset

| Model            | B@1       | B@2       | B@3       | B@4       | C     | R     | M     | CE-P      | CE-R  | CE-F1     |
| :--------------- | :-------- | :-------- | :-------- | :-------- | :---- | :---- | :---- | :-------- | :---- | :-------- |
| R2Gen            | 0.353     | 0.218     | 0.145     | 0.103     | -     | 0.277 | 0.142 | 0.333     | 0.273 | 0.276     |
| CMCL             | 0.334     | 0.217     | 0.140     | 0.097     | -     | 0.281 | 0.133 | -         | -     | -         |
| PPKED            | 0.360     | 0.224     | 0.149     | 0.106     | 0.237 | 0.284 | 0.149 | -         | -     | -         |
| AlignTransformer | 0.378     | 0.235     | 0.156     | 0.112     | -     | 0.283 | 0.158 | -         | -     | -         |
| DCL              | -         | -         | -         | 0.109     | 0.281 | 0.284 | 0.150 | 0.471     | 0.352 | 0.373     |
| **CMCRL (Ours)** | **0.400** | **0.245** | **0.165** | **0.119** | 0.190 | 0.280 | 0.150 | **0.489** | 0.340 | **0.401** |

### ✨ **CRA** - Cross-modal Causal Relation Alignment for Video Question Grounding

<div align="center">
<img src="images/CRA.png" width="700" alt="CRA Method"/>
</div>

**Selected as CVPR 2025 Highlight!** CRA eliminates spurious cross-modal correlations and improves causal consistency between question-answering and video temporal grounding through front-door and back-door causal interventions.

#### Results on NExT-GQA Dataset

| Method         | What     | How      | When     | Where    | Why      | All      |
| :------------- | :------- | :------- | :------- | :------- | :------- | :------- |
| HGA            | 63.7     | 85.9     | 78.7     | 52.1     | 56.7     | 63.0     |
| IGV            | 64.1     | 87.1     | 78.9     | 53.5     | 57.1     | 63.7     |
| HME            | 64.0     | 87.6     | 79.0     | 52.3     | 57.6     | 63.8     |
| ATP            | 65.0     | 88.6     | 81.4     | 54.5     | 58.5     | 65.0     |
| **CRA (Ours)** | **66.2** | **89.4** | **82.1** | **55.8** | **59.3** | **66.4** |

## 👨‍🏫 Get Started

Please see our [documentation](docs/) for the general introduction of CausalVLR.

### Installation

Please refer to [Installation Guide](docs/Installation_Guide.md) for detailed installation instructions.

**Quick Installation:**

```bash
# Clone repository
git clone https://github.com/yourusername/CausalVLR.git
cd CausalVLR

# Create environment and install
conda env create -f requirements.yml
conda activate causalvlr
pip install -e .
```

### Quick Start

#### Medical Report Generation

```bash
# Train VLCI model on IU X-Ray dataset
python main.py -c configs/MRG/iu_xray/vlci.json
```

```python
from causalvlr.api.pipeline.MRG import MRGPipeline
import json

# Load configuration
with open('configs/MRG/iu_xray/vlci.json', 'r') as f:
    config = json.load(f)

# Create and train pipeline
pipeline = MRGPipeline(config)
pipeline.train()

# Evaluate
results = pipeline.inference()
print(f"BLEU-4: {results['metrics']['BLEU_4']:.4f}")
```

#### Video Question Answering

```bash
# Train CRA model on NExT-GQA dataset
python main.py --config configs/VQA/CRA/CRA_NextGQA.yml
```

```python
from causalvlr.api.pipeline.VQA import CRAPipeline
import yaml

# Load configuration
with open('configs/VQA/CRA/CRA_NextGQA.yml', 'r') as f:
    config = yaml.safe_load(f)

# Create and train pipeline
pipeline = CRAPipeline(config)
pipeline.train()

# Test
results = pipeline.inference()
print(f"Accuracy: {results['accuracy']:.4f}")
```

For more details, see [Quick Start Guide](docs/Quick_Start.md).

## 👀 Model Zoo

Please feel free to let us know if you have any recommendation regarding datasets with high-quality.

| Task                      | Model        | Benchmark                                                                                           | Paper                                                     |
| ------------------------- | ------------ | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------- |
| Medical Report Generation | CMCRL (VLCI) | [IU X-Ray](https://openi.nlm.nih.gov/), [MIMIC-CXR](https://physionet.org/content/mimic-cxr/2.0.0/) | [TIP 2025](https://arxiv.org/pdf/2303.09117.pdf)          |
| Video Question Grounding  | CRA          | [NExT-GQA](https://github.com/doc-doc/NExT-GQA), [STAR](https://bobbywu.com/STAR/)                  | [CVPR 2025](https://arxiv.org/pdf/2503.07635) (Highlight) |
| Video Question Answering  | TempCLIP     | NExT-QA, STAR                                                                                       | -                                                         |

## 🔬 Related Research

Our research group has conducted extensive investigations in causal reasoning across multiple domains. The following works demonstrate our comprehensive exploration of causal inference principles in vision, language, and multimodal systems.

### Video Understanding & Question Answering

**Cross-Modal Causal Relational Reasoning for Event-Level Visual Question Answering**
_Yang Liu, Guanbin Li, Liang Lin_
IEEE Transactions on Pattern Analysis and Machine Intelligence (TPAMI), Vol. 45, No. 10, October 2023

**Visual Causal Scene Refinement for Video Question Answering**
_Yushen Wei, Yang Liu, Hong Yan, Guanbin Li, Liang Lin_
ACM International Conference on Multimedia (ACM MM), 2023

### Medical AI & Diagnosis

**Towards Causality-Aware Inferring: A Sequential Discriminative Approach for Medical Diagnosis**
_Junfan Lin, Keze Wang, Ziliang Chen, Xiaodan Liang, Liang Lin_
IEEE Transactions on Pattern Analysis and Machine Intelligence (TPAMI), Vol. 45, No. 11, November 2023

### Image Generation & Synthesis

**Scene Graph to Image Synthesis via Knowledge Consensus**
_Yang Wu, Pengxu Wei, Liang Lin_
Association for the Advancement of Artificial Intelligence (AAAI), 2023

**ScaleLong: Towards More Stable Training of Diffusion Model via Scaling Network Long Skip Connection**
_Zhongzhan Huang, Pan Zhou, Shuicheng Yan, Liang Lin_
IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR), 2023

### Large Language Models & Reasoning

**CausalGPT: Towards Multi-Agent Causal Reasoning for Faithful Knowledge Reasoning**
_Ziyi Tang, Ruilin Wang, Weixing Chen, Keze Wang, Yang Liu, Tianshui Chen, Liang Lin_
arXiv preprint arXiv:2308.11914, 2023

### Robustness & Debiasing

**Masked Images Are Counterfactual Samples for Robust Fine-Tuning**
_Yao Xiao, Ziyi Tang, Pengxu Wei, Cong Liu, Liang Lin_
IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR), 2023

**A Causal Debiasing Framework for Unsupervised Salient Object Detection**
_Xiaowei Lin, Zhentao Wu, Guanbin Li, Yupei Chen_
Association for the Advancement of Artificial Intelligence (AAAI), 2022

**Diagnosing and Rectifying Fake OOD Invariance: A Restructured Causal Approach**
_Ziliang Chen, Yongsen Zheng, Zhao-Rui Lai, Quanlong Guan, Liang Lin_
Association for the Advancement of Artificial Intelligence (AAAI), 2024

### Recommendation Systems

**CIPL: Counterfactual Interactive Policy Learning to Eliminate Popularity Bias for Online Recommendation**
_Yongsen Zheng, Jinghui Qin, Pengxu Wei, Ziliang Chen, Liang Lin_
IEEE Transactions on Neural Networks and Learning Systems (TNNLS), Vol. 35, No. 12, December 2024

**HutCRS: Hierarchical User-Interest Tracking for Conversational Recommender System**
_Mingjie Qian, Yongsen Zheng, Jinghui Qin, Liang Lin_
Conference on Empirical Methods in Natural Language Processing (EMNLP), 2023

### Reinforcement Learning

**Reward-Adaptive Reinforcement Learning: Dynamic Policy Gradient Optimization for Bipedal Locomotion**
_Changxin Huang, Guangrun Wang, Zhibo Zhou, Ronghui Zhang, Liang Lin_
IEEE Transactions on Pattern Analysis and Machine Intelligence (TPAMI), Vol. 45, No. 6, June 2023

### Creativity Evaluation

**A Causality-Aware Paradigm for Evaluating Creativity of Multimodal Large Language Models**
_Zhongzhan Huang, Shanshan Zhong, Pan Zhou, Shanghua Gao, Marinka Zitnik, Liang Lin_
IEEE Transactions on Pattern Analysis and Machine Intelligence (TPAMI)

## 🎫 License

This project is released under the [Apache 2.0 license](LICENSE).

## 🖊️ Citation

If you find this project useful in your research, please consider cite:

```bibtex
@misc{liu2023causalvlrtoolboxbenchmarkvisuallinguistic,
      title={CausalVLR: A Toolbox and Benchmark for Visual-Linguistic Causal Reasoning},
      author={Yang Liu and Weixing Chen and Guanbin Li and Liang Lin},
      year={2023},
      eprint={2306.17462},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={https://arxiv.org/abs/2306.17462},
}

@ARTICLE{11005686,
  author={Chen, Weixing and Liu, Yang and Wang, Ce and Zhu, Jiarui and Li, Guanbin and Liu, Cheng-Lin and Lin, Liang},
  journal={IEEE Transactions on Image Processing},
  title={Cross-Modal Causal Representation Learning for Radiology Report Generation},
  year={2025},
  volume={34},
  pages={2970-2985},
  doi={10.1109/TIP.2025.3568746}}

@inproceedings{chen2025cross,
  title={Cross-modal Causal Relation Alignment for Video Question Grounding},
  author={Chen, Weixing and Liu, Yang and Chen, Binglin and Su, Jiandong and Zheng, Yongsen and Lin, Liang},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  year={2025}
}
```

## 🙌 Contribution

Please feel free to open an issue if you find anything unexpected. We are always targeting to make our community better!

We appreciate all the contributors who implement their methods or add new features and users who give valuable feedback.

## 🤝 Acknowledgement

CausalVLR is an open-source project that integrates cutting-edge research in causal visual-language reasoning. We wish that the toolbox and benchmark could serve the growing research community by providing a flexible toolkit to reimplement existing methods and develop new models.

### Related Projects

This toolbox integrates and builds upon the following works:

- **CMCRL**: [Cross-Modal Causal Representation Learning for Radiology Report Generation](https://arxiv.org/pdf/2303.09117.pdf)
- **CRA-GQA**: [Cross-modal Causal Relation Alignment for Video Question Grounding](https://arxiv.org/pdf/2503.07635)

We thank the authors for their excellent work and open-source contributions.
