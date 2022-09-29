## Installation

### Requirements
- Linux with Python 3.6
- PyTorch 1.4.0
- TAP: follow [TAP installation instructions](https://github.com/microsoft/TAP).



### Example conda environment setup
```bash
conda create -n tag python=3.6 -y
conda activate tag
git clone https://github.com/HenryJunW/TAG
cd TAG
python setup.py develop
```


Alternatively, you could install the conda environment from existing yaml file
```bash
conda env create --name tap --file=tag.yml
```