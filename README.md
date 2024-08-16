</h1>Exemplary Notebooks</h1>
Collection of simple visual deep learning examples in modified form, e.g. more stable GAN variants; All in ONE Notebook without many dependencies, no bells and whistles - just clean code examples<br/>
This collection is work in progress - <b>any advice, requests, or reports of errors are welcome!</b><br/>
<br/>
This is meant as a starting point / minimal, modern working example for someone new to the topic, I try to provide a lot of practical explanations in the code itself<br/>
<br/>
<h1>Collection so far:</h2>
<a href=https://github.com/DaiDaiLoh/ExemplaryNotebooks/blob/main/stableGAN.ipynb>GAN</a> - <a href=https://github.com/DaiDaiLoh/ExemplaryNotebooks/blob/main/WGAN-GP.ipynb>WGAN-GP</a> - <a href=https://github.com/DaiDaiLoh/ExemplaryNotebooks/blob/main/vqvae.ipynb>VQ-VAE</a> - <a href=https://github.com/DaiDaiLoh/ExemplaryNotebooks/blob/main/VQGAN.ipynb>VQGAN</a> - <a href=https://github.com/DaiDaiLoh/ExemplaryNotebooks/blob/main/MNIST_AutoregressiveImageTransformer.ipynb>Autoregressive Transformer for image generation</a>
<br/>
<h2><a href=https://github.com/DaiDaiLoh/ExemplaryNotebooks/blob/main/stableGAN.ipynb>GAN Example</a></h2>
Simple (conditional) GAN, with modern generator/discriminator, built to produce MNIST characters.<br/>
This version uses a more modern hinge-loss: don't train the discriminator/generator too much when they're already ahead, makes everything more stable;<br/>
Also uses a more modern convolution architecture. Should output decent generations after 3 epochs.<br/>
<br/><br/>
<span style="color: red"><b>If you value your sanity, always use a WGAN (below) if you can. Rather spend 10 more minutes on implementing than 20 hours on debugging a black box</b></font><br/>
</span><br/>
<b><u>Sources/recommended reads:</u></b> <br/>
Original Paper: https://arxiv.org/abs/1406.2661<br/>
BigGAN, includes the techniques to create a nice and stable GAN: https://arxiv.org/abs/1809.11096<br/>
Wasserstein GAN, regularising the discriminator gradient such that it always outputs something useful and we no longer have vanishing gradient: https://arxiv.org/abs/1701.07875<br/>


<h2><a href=https://github.com/DaiDaiLoh/ExemplaryNotebooks/blob/main/WGAN-GP.ipynb>Wasserstein GAN with Gradient Penalty (WGAN-GP) Example</a></h2>
Simple Wasserstein GAN with gradient penalty (WGAN-GP). Simple version: A GAN, but much more well behaved because we regularise<br/>
the discriminator (now called critic) to rather rate the input than to just binarily categorise it.<br/>
In practise, that means we enforce the gradient to be 1 for every input to the critic, hence our generator has a much easier time<br/>
to train.<br/><br/>
<span style="color: red"><b>Should be understandable on its own, but I recommend to look at some GAN (see above) first</b></font><br/>
</span><br/>
<b><u>Sources/recommended reads:</u></b> <br/>
Original Paper (Wasserstein GAN): https://arxiv.org/abs/1701.07875<br/>
Wasserstein GAN, but with gradient penalty (as we use here): https://arxiv.org/abs/1704.00028<br/>
<br/>


<h2><a href=https://github.com/DaiDaiLoh/ExemplaryNotebooks/blob/main/vqvae.ipynb>VQ-VAE Example</a></h2>
Simple VQ-VAE, built to produce CIFAR images.<br/>
Takes an input image, encodes it, quantises that to a number tokens, then decodes it.<br/>
<br/>
<b><u>Sources/recommended reads:</u></b> <br/>
Original Paper:  https://arxiv.org/abs/1711.00937<br/>
VQGAN, i.e. extra discriminator to "sharpen" the output and to "re-invent" high-frequent details (e.g. scales on a fish) that usually get lost when compressing: https://arxiv.org/abs/2012.09841<br/>
Improved VQGAN makes sure all codewords are used properly and have more global information: https://arxiv.org/abs/2310.05400<br/>
Producing global instead of local tokens, which makes better use of varying information content in an image, as a VQ-VAE essentially only uses "local" patches: QG-VAE / QGGAN https://arxiv.org/abs/2407.11913
<br/>


<h2><a href=https://github.com/DaiDaiLoh/ExemplaryNotebooks/blob/main/VQGAN.ipynb>VQGAN Example</a></h2>
Simple VQGAN, built to produce ImageNet images, but also works on CIFAR.<br/>
Takes an input image, encodes it, quantises that to a number tokens, then decodes it. Opposing to a VQ-VAE, this applies an additional "sharpening" to the output, re-inventing high-frequency details like the scales of a fish.<br/>
<br/>
<b><u>Sources/recommended reads:</u></b> <br/>
VQ-VAE:  https://arxiv.org/abs/1711.00937<br/>
VQGAN: https://arxiv.org/abs/2012.09841<br/>
Improved VQGAN makes sure all codewords are used properly and have more global information: https://arxiv.org/abs/2310.05400<br/>
Producing global instead of local tokens, which makes better use of varying information content in an image, as a VQ-VAE essentially only uses "local" patches: QG-VAE / QGGAN https://arxiv.org/abs/2407.11913
<br/>



<h2><a href=https://github.com/DaiDaiLoh/ExemplaryNotebooks/blob/main/MNIST_AutoregressiveImageTransformer.ipynb>Autoregressive Image Generation Transformer</a></h2>
Minimal example of a (encoder only) transformer that autoregressively produces greyscale values to produce MNIST. You can use this in combination with e.g. my VQGAN and some tweaking to produce actually nice images.<br/>
<br/>
<b><u>Sources/recommended reads:</u></b> <br/>
The Transformer Paper, Vaswani et al.: https://arxiv.org/abs/1706.03762 (difficult read)<br/>
(Alternative, that's a bit more understandable: https://jalammar.github.io/illustrated-transformer/ - note that this explains a full transformer, we need only the encoder part)<br/>
Taming Transformers for High-Resolution Image Synthesis (VQGAN): https://arxiv.org/abs/2012.09841
<br/>


