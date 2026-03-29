# DL

## History
- 1945 perceptron math model
- 1950 perceptron model => XOR problem
- 1970 -> 1985: freezing
- 1986: back-propagation
- 1980s: LeNet/CNN, LSTM, RNN => MNIST(post cards nums)
- 2012: NVIDIA's GPU + AlexNet using GPU(won imagenet)!
- ![517](<./media/Pasted image 20251208194517.png>)


## Backprop
- 1 loss function at the end
- calc differentiation between loss function + each node
- made the DNN actually get to light
- wasn't there DNN as sigmoid/tanh had vanishing gradients and no data or computational power

## Perceptron
- single neuron
- doesn't take its decision linearly; uses some activation functions
- activations
	- sigmoid: map output between 0,1 (gives us prob)
	- tanh: still mapping inputs (-1,1)
	- ReLU: dead neurons(different form dropout)
- ![157](<./media/Pasted image 20251208203157.png>)
- forward pass, loss, derivative, gradient

## Activations
- Step function: linear => didn't learn anything asln
- sigmoid: smash output between 0,1 => most populer in output neurons
- tanh: LSTM, RNN
- ReLU: default activation

## Loss
- choose differentiable func
### Classification
- Binary cross entropy: prob bt 2 things
- Cross entropy: prob bt many
### Regression
- MAE: needs sub-derivative, not recommended
- MSE: great.
- hopper
- RMSE

## Optimizer
- updating weights بنسبة قد إيه
- Gradient decent
	- SGD: each row, update weights => noisy, yet faster![23](<./media/Pasted image 20251208212423.png>)
	- BGD: whole dataset updating weights => needs memory for the whole data fitting in memory(good with small data) => more accurate!![507](<./media/Pasted image 20251208212507.png>)
	- mini-BGD => batch_size ![625](<./media/Pasted image 20251208212625.png>)
	- local minimum => danger zoneeee
- Gradient decent with momentum!
	- ![27](<./media/Pasted image 20251208212727.png>)
	- smooth updates, not always winning, solution for local minimum
	- prob with hyperparameters
- ADAM
	- solve hyperparams automatically, solving the GD+momentum

- ![026](<./media/Pasted image 20251208213026.png>)ocal on right, global on left
- ![52](<./media/Pasted image 20251208213052.png>) when initialized near to local, some failed
- ADAM is the best! decision based on previous actions.
- initialization matters! HE, Xavier 

## Notes?
- linear regression VS backprop
- backprop paper???
- SGD / BGD / MBGD
- data leakage

## Overfit - Underfit
- ![59](<./media/Pasted image 20251213093959.png>)
- ![26](<./media/Pasted image 20251213094726.png>)
- underfitting
- test data too simple
- small test data
- different eval method
- label noise
### Regularization
- L1(lasso),L2 => one penalizes model till it rmv this feature as a whole
- L1 => lasso => using weights => min it till it reaches zero => used in feature selection/discard
- L2 => W^2 => not reach 0 but penalizes model

## PyTorch
- responsible of auto grade


## Quiz
- batch norm => normalizes the data distru that speed up trainning
- gradient clipping: threshold for exploading gradients
- SGD:
- lr: log(lr) => suppose starting with long learning that lowers as i approach the right answer
- weight decay: penality on loss func to lower weights
- 
