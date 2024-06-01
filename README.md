</h1>Exemplary Notebooks</h1>
Collection of simple examples in modified form, e.g. more stable GAN variants; All in ONE Notebook without many dependencies, no bells and whistles - just clean code examples<br/>
This collection is work in progress - <b>any advice, requests, or reports of errors are welcome!</b><br/>
<br/>
This is meant as a starting point / minimal, modern working example for someone new to the topic, I try to provide a lot of practical explanations in the code itself<br/>
<br/>
<h1>Collection so far:</h2>
<h2><a href=https://github.com/DaiDaiLoh/ExemplaryNotebooks/blob/main/stableGAN.ipynb>GAN Example</a></h2>
Simple (conditional) GAN, with modern generator/discriminator, built to produce MNIST characters.<br/>
This version uses a more modern hinge-loss: don't train the discriminator/generator too much when they're already ahead, makes everything more stable;<br/>
Also uses a more modern convolution architecture. Should output decent generations after 3 epochs.<br/>
<br/>
<b><u>Sources/recommended reads:</u></b> <br/>
Original Paper: https://arxiv.org/abs/1406.2661<br/>
BigGAN, includes the techniques to create a nice and stable GAN: https://arxiv.org/abs/1809.11096<br/>
______________________________________________________________________________________
<h2><a href=https://github.com/DaiDaiLoh/ExemplaryNotebooks/blob/main/vqvae.ipynb>VQ-VAE Example</a></h2>
Simple VQ-VAE, built to produce CIFAR images.<br/>
Takes an input image, encodes it, quantises that to a number tokens, then decodes it.<br/>
<br/>
<b><u>Sources/recommended reads:</u></b> <br/>
VQ-VAE:  https://arxiv.org/abs/1711.00937<br/>
VQGAN: https://arxiv.org/abs/2012.09841<br/>
Improved VQGAN: https://arxiv.org/abs/2310.05400 (mainly uses a Wasserstein discriminator and makes sure all codewords are used properly)
