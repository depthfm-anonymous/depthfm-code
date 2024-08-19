<p align="center">
 <h2 align="center"><img src=assets/figures/radio.png width=28> DepthFM: Fast Generative Monocular Depth Estimation with Flow Matching</h2>
 <p align="center"> 
    Anonymous authors
</p>

 </p>
 
 
[![Website](assets/figures/badge-website.svg)](https://depthfm-anonymous.github.io/)

![Cover](/assets/figures/dfm-cover.png)


## 📻 Overview

We present **DepthFM**, a method that advances monocular depth estimation by framing it as direct transport between paired image and depth distributions. 
We find that flow matching effectively addresses this, as its straight trajectories through solution space provide efficiency and high quality. 
On the other hand, depth estimation has long faced challenges in training and data efficiency due to optimization difficulties and data annotation. 
To address this, we incorporate external knowledge from pretrained foundation diffusion models and discriminative depth estimators. 
On standard benchmarks of complex natural scenes, our approach achieves competitive performance by improving sampling, training, and data efficiency, despite being trained on minimal synthetic data.


## 🛠️ Setup

This setup was tested with `Ubuntu 22.04.4 LTS`, `CUDA Version: 12.2`, and `Python 3.11.5`.

First, clone the github repo...


Plz download the weights from

[Google drive of the weights](https://drive.google.com/drive/folders/1m0q8Dj24n96Q-anR7XmAgVUag7VJyzca?usp=sharing)


Now you have either the option to setup a virtual environment and install all required packages with `pip`

```bash
pip install -r requirements.txt
```

or if you prefer to use `conda` create the conda environment via

```bash
conda env create -f environment.yml
```

Now you should be able to listen to DepthFM! 📻 🎶


## 🚀 Usage

You can run the python script `inference.py` as follows

```bash
python inference.py \
   --num_steps 2 \
   --ensemble_size 4 \
   --img assets/dog.png \
   --ckpt checkpoints/depthfm.ckpt
```

The argument `--num_steps` allows you to set the number of function evaluations. We find that our model already gives very good results with as few as one or two steps. Ensembling also improves performance, so you can set it via the `--ensemble_size` argument. Currently, the inference code only supports a batch size of one for ensembling.

