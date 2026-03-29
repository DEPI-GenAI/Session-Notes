# AE:
- latent space discrete, each point is thrown somewhere even for 2 imgs of the same person
- determinstic

# VAE:
- latent space is contieous => normal distru
- cons: 
	- KL => if got bigger => make the model focus on specific distru than the others => not generating, it's memorizing it => AE again.
	- KL High => get closer to distru

# GANs
- sharp, realistic img (pixels doesn't come from avg prob, no assumption to any distru) => no liklehood modelling
- no liklihood estimation => idk prob of sample
- Training instability => fighting networks => mode collapse (limited variation of data => knew which pics pass discr. then regenerate it)

-------------------------
# Diffusion
- am not adding noise incrementally
- if so => the model will learn how t de-noise the first phase of the pic real good(small portions of noise)
- sampling pics from uniformal distru, different pics + different noises
- 