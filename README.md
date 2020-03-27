# CycleGAN-pytorch
slightly modified code based on [junyanz/pytorch-CycleGAN-and-pix2pix](https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix)

* dataset => private toy dataset

# TODO

# Command Line

## Installation
`pip install -r requirements.txt`

## CycleGAN train/test
* To view training results and loss plots, run `python -m visdom.server` and click the URL [http://localhost:8097](http://localhost:8097).
* Train the model
`python train.py --data_root ./horse2zebra --name h2z_cyclegan --model cycle_gan`
* Test the model
`python test.py --data_root ./horse2zebra --name h2z_cyclegan --model cycle_gan`

* image preprocess
`python image_preprocess.py  --data_root ./dataset/rakugakiicon`

## Commands

`nohup python train.py --dataroot ./dataset/cezanne2photo --name cezanne2photo_ugatit --model ugatit --n_epochs 500000 --n_epochs_decay 500000 &`

`python train.py --dataroot ./dataset/cezanne2photo --name cezanne2photo_ugatit --model ugatit --n_epochs 500000 --n_epochs_decay 500000 --light`


### drawing2paint / cyclegan

`python train.py --dataroot ./dataset/draw2paint --name d2p_cyclegan --model cycle_gan`

### drawing2paint / cyclegan

`python train.py --dataroot ./dataset/draw2paint --dataset_mode colorization --name d2p_color_cyclegan --model cycle_gan_colorization --continue_train --no_flip`

### drawing2paint / adain_style

`python train.py --dataroot ./dataset/draw2paint --dataset_mode unaligned --name d2p_adain_style2 --model adain_style --niter 160000 --niter_decay 0 --batch_size 8  --num_threads 16 --lr_policy linear_style --no_flip --preserve_color`

`python train.py --dataroot ./dataset/draw2paint --name d2p_adain_style_pretrained --model adain_style --niter 160000 --niter_decay 0 --batch_size 8  --num_threads 16 --lr_policy linear_style --no_flip --preserve_color --use_pretrained_decoder`



### drawing2paint / cyclegan + adain_style

`python train.py --dataroot ./dataset/draw2paint --name d2p_cycle_adain_style_pretrained --model cycle_gan_colorization --no_flip --use_pretrained_decoder`


### drawing2paint / cycle_gan + vgg

`python train.py --dataroot ./dataset/draw2paint --name d2p_cycle_vgg_pretrained --model cycle_gan_vgg_model --no_dropout`


### art2photo / cycle_gan

`python train.py --dataroot ./dataset/art2photo --name a2p_cycle --model cycle_gan --no_dropout`

`python train.py --dataroot ./dataset/art2photo --name a2p_cycle --model cycle_gan --no_dropout --continue_train`

### horse2zebra / cycle_gan

`python train.py --dataroot ./dataset/horse2zebra --name h2z_cycle2`

### horse2zebra / double_cycle_gan_colorization

`python train.py --dataroot ./dataset/horse2zebra --name h2z_doublecycle --model double_cycle_gan_colorization`

### draw2paint / double_cycle_gan_colorization

`python train.py --dataroot ./dataset/draw2paint --name d2p_doublecycle2 --model double_cycle_gan_colorization`

`python train.py --dataroot ./dataset/draw2paint --name d2p_doublecycle3 --model double_cycle_gan_colorization`

`python train.py --dataroot ./dataset/draw2paint --name d2p_doublecycle4 --model double_cycle_gan_colorization --dis_weight 0.25`

`python train.py --dataroot ./dataset/draw2paint --name d2p_doublecycle5 --model double_cycle_gan_colorization`

`python train.py --dataroot ./dataset/draw2paint --name d2p_doublecycle6 --model double_cycle_gan_colorization`

`python train.py --dataroot ./dataset/draw2paint --name d2p_doublecycle4 --model double_cycle_gan_colorization --continue_train`

### draw2paint / cycle_gan_colorization

`python train.py --dataroot ./dataset/draw2paint --name d2p_cycle_gan_colorization --model cycle_gan_colorization`