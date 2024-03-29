# Segment Anything Model(SAM)

SAM is a one-shot prompt based segmetnation model developed by meta.
https://github.com/facebookresearch/segment-anything
https://arxiv.org/abs/2304.02643

![person.png](/assets/outputs/person.png)

## Features

- Zero-shot text-to-bbox approach for object detection.
- GroundingDINO detection model integration.
- Easy deployment using the Lightning AI app platform.
- Customizable text prompts for precise object segmentation.

## Getting Started

### Prerequisites

- Python 3.7 or higher
- torch (tested 2.0)
- torchvision

### Installation

```
pip install torch torchvision
pip install -U git+https://github.com/luca-medeiros/lang-segment-anything.git
```
Or
Clone the repository and nstall the required packages:

```
git clone https://github.com/luca-medeiros/lang-segment-anything && cd lang-segment-anything
pip install torch torchvision
pip install -e .
```

### Usage

To run the Lightning AI APP:

`lightning run app app.py`

Use as a library:

```python
from  PIL  import  Image
from lang_sam import LangSAM

model = LangSAM()
image_pil = Image.open('./assets/car.jpeg').convert("RGB")
text_prompt = 'wheel'
masks, boxes, phrases, logits = model.predict(image_pil, text_prompt)
```

## Acknowledgments

This project is based on the following repositories:

- [GroundingDINO](https://github.com/IDEA-Research/GroundingDINO)
- [Segment-Anything](https://github.com/facebookresearch/segment-anything)
- [Lightning AI](https://github.com/Lightning-AI/lightning)

## License

This project is licensed under the Apache 2.0 License
