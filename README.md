# dcgan



DCGAN ( Deep Convolutional Generative Adversarial Networks ) by Alec Radford et al. [paper](https://arxiv.org/abs/1511.06434) provides an improvement over the original GAN [paper](https://arxiv.org/abs/1406.2661) by Ian Goodfellow et al.


This project was built with the help of [nbdev](https://nbdev.fast.ai/) and [fastai](https://github.com/fastai/fastai) to highlight the ease of developing sophisticated deep learning models. Most of the code is inspired from this [project](https://github.com/tmabraham/UPIT/)

![sample](images/dcgan_arch.png)

## Install

`pip install git+https://github.com/numb3r33/dcgan.git`

## How to use

```
#ignore
path = untar_data(URLs.MNIST)
dls  = get_dls(path, bs=128)
```

```
#ignore
dc_gan = DCGAN(ch_in=1,
               z_dim=64
               )

learn = dcgan_learner(dls, dc_gan, opt_func=partial(Adam, betas=(0.5, 0.999)))
```

```
#ignore
learn.fit(n_epoch=75, lr=2e-4)
```

**How generator learns during various epochs of training.** One can see the quality of images improving over time.

![generator generation](images/gen_generation.png)

```
#ignore
learn.show_results(ds_idx=0)
```

**Result after training for 75 epochs**

![Result](images/final_res.png)
