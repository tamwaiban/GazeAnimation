## GazeAnimation - Official Tensorflow Implementation


![](img/0.gif)
![](img/26.gif)
![](img/28.gif)
![](img/3.gif)
![](img/4.gif)
![](img/5.gif)


> ***Dual In-painting Model for Unsupervised Gaze Correction and Animation in the Wild***<br>
> Jichao Zhang, Jingjing Chen, [Hao Tang](https://ha0tang.github.io/), [Wei Wang](https://weiwangtrento.github.io/), [Yan Yan](https://userweb.cs.txstate.edu/~y_y34/), [Enver Sangineto](https://disi.unitn.it/~enver.sangineto/index.html), [Nicu Sebe](http://disi.unitn.it/~sebe/)<br>
> In ACMMM 2020.<br>

> Paper: https://arxiv.org/abs/2008.03834<br>


### Citation

```
@inproceedings{zhang2018sparsely,
  title={Dual In-painting Model for Unsupervised Gaze Correction and Animation in the Wild},
  author={Jichao Zhang, Jingjing Chen, Hao Tang, Wei Wang, Yan Yan, Enver Sangineto, Nicu Sebe},
  booktitle={ACMMM 2020},
  year={2020}
}
```

## Network Architecture

![](img/model.png)

## Dependencies

```bash
Python=3.6
pip install -r requirements.txt

```
Or Using Conda

```bash
-conda create -name GazeA python=3.6
-conda install tensorflow-gpu=1.9
```
Other packages installed by pip.

## Usage

- Clone this repo:
```bash
git clone https://github.com/zhangqianhui/GazeAnimation.git
cd GazeAnimation

```

- Download the CelebAGaze dataset

  Download the tar of CelebAGaze dataset from [Google Driver Linking](https://drive.google.com/file/d/1_6f3wT72mQpu5S2K_iTkfkiXeeBcD3wn/view?usp=sharing).
  
  ```bash
  cd your_path
  tar -xvf CelebAGaze.tar
  ```
  
  Please edit the options.py and change your dataset path

- Pretraining Model

You can edit label_dir and data_dir

- Train the model using command line with python 
```bash
python train.py --use_sp --gpu_id='1' --exper_name='log8_7' --crop_w=50 --crop_h=30
```
- Test the model
```bash
python test.py --exper_name='log8_7' --gpu_id='0' --crop_h=30 --crop_w=50 --test_sample_dir='test_sample_dir' --checkpoints='checkpoints'
```

Or Using scripts for training 
```bash
bash scripts/train_log8_7.sh
```
Using scripts for testing and pretained model can be downloaded [Pretrained Model](https://drive.google.com/file/d/1GYyGGQm06ahI0V4mBzSCaT1Fh4kzHb76/view?usp=sharing) 
```bash
bash scripts/test_log8_7.sh
```

## Experiment Result 

### Gaze Correction

<p align="center"><img width="100%" src="img/correction.png" /></p>


### Gaze Animation


![](img/9.gif)
![](img/10.gif)
![](img/11.gif)
![](img/12.gif)
![](img/13.gif)
![](img/14.gif)
![](img/16.gif)
![](img/17.gif)
![](img/18.gif)
![](img/19.gif)
![](img/22.gif)
![](img/23.gif)



# Related works

- [Sparsely Grouped Multi-task Generative Adversarial Networks for Facial Attribute Manipulation](https://github.com/zhangqianhui/Sparsely-Grouped-GAN)

- [GazeCorrection:Self-Guided Eye Manipulation in the wild using Self-Supervised Generative Adversarial Networks](https://github.com/zhangqianhui/GazeCorrection)

- [PA-GAN: Progressive Attention Generative Adversarial Network for Facial Attribute Editing](https://github.com/LynnHo/PA-GAN-Tensorflow)

