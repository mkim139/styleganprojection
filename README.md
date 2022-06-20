# StyleGAN1 Latent Projection (Pytorch)
Image projection to latent space w of StyleGAN1, implementation is based on StyleGAN2 paper

Pytorch implementation 참고 https://github.com/lernapparat/lernapparat/blob/master/style_gan/pytorch_style_gan.ipynb
StyleGAN2 논문/Github 참고 https://github.com/NVlabs/stylegan2

* 위 pytorch implementation을 수정하여, StyleGAN2 논문에서 제안한 Latent vector encoding시 Noise Penalty 구현  
* Latent Vector를 optimize하면서 Stochastic Noise도 같이 optimize하면 더 정확한 latent representation을 발견할 수 있음  
* 하지만, Noise를 optimize하게 되면, noise가 Latent의 역할을 넘나드려 할 수 있음 (overfitting)  
* Noise Penalty를 주어 Noise가 latent의 역할까지 구현하지 못하도록 제어  
* VGG loss, Log Cosh loss, lssim loss, lpip loss를 추가하여 사진의 structural detail을 배울수 있도록 도움  
* Learning rate scheduling도 논문(StyleGAN2)과 동일하게 구현
* Latent vector L1 regularization을 구현하여, latent vector가 모델이 '얼굴'로 수용할 수 있는 범위에서 너무 많이 벗어나지 못하도록 구현
