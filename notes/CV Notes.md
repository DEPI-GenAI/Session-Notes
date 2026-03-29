# CV
- cymk => live shows(we ain't dealing with it that much)
- LAB => color val is static(doesn't get affected with light/shimmer)
- HSV: hue, saturation, value
-  https://setosa.io/ev/image-kernels/
- poloclub.github.io/cnn-explainer/#article-relu
- adamharley.com/nn_vis/cnn/3d.html
- katnoria.com/gradvizv1/

### Edge detection => CV+ML
- evaluated till it reached face detection => haar cascade(cascade in ensemble methods) (biased for white ppl) => hard t configure kernel numbers!

### CV + DL
- the problem with dl i had t flatten it pixel by pixel to enter the dl model => 784 pixel as input to start with => HUGE LAYER => many neurons in the overall model
- nn doesn't understand spatial location => due to flatten the pic => each pixel on its own => no context
- due to large models => large parameters(weights)

#### modern CV
- from classical cv => window filter
- from dl => figuring out weights
====>>>>> CNN!
- window from cv => spatial preserved
- weights of window => dl tuned them(parameter sharing: same parameters for the whole pic)

### FCNN VS CNN
- transition invariance => object moved/light changed/etc => still recognized it
- ![708](<./media/Pasted image 20251215213708.png>)
- explainable AI
- won't use sigmoid(0,1) nor tanh(-1,1) => dims the photo!
- finally, i flatten the input t enter it to ann t take decision


## CNNs
- LeNet-1998: 
	- earliest CNN arch => 3CNNs + window 5x5
	- why strides: make the model see overlapping parts of img with each other => to save spatial info(not attention)
- AlexNet:
	- introduced ReLU
	- window 11x11
	- first DL t defeat ML(lenet didn't get that much accuracy)
	- changed the window size by going forward
	- he thought i should  have big window at first
	- figured out maxpool
	- ![902](<./media/Pasted image 20251220093902.png>)

- VGG(x = layers number)
	- static kernel(not 11 then 3)
	- the small the window, the better
	- strongest model t handle feature extraction
	- strongest in transfer learning(trial and error)

- GoogleNet(Inception-v1)
	- some features can't be detected by 3x3 only/static => i need more sometimes
	- have many feature maps with each kernel => concatenate them

- ResNet(-50)
	- solved limitations of the layers depth
	- skip connections: feed same feature map to further layers
	- concatenate over the depth axis + pass the real img as well(after max pooling them)

## Task Oriented
- Object Detection
	- = Task regression(position of element in img) + classification => advanced task from localization(same but works on 1 element)
	- ![146](<./media/Pasted image 20251220100146.png>)
	- bounding box => the right answer from Region of interest
	- no one uses R-CNN or its advances unless in critical tasks => as it's extra heavy
	- i need reinforcement learning => in which layer? i decide
	- selective search==> too many rois + less accuracy
	- then DL => feature map then selective
	- controlled gate(LSTM,GURU) => decide which rois to use => computaionaly expensive => 4Gates => each gate had forward n back prob

- YOLO: best in detection - Task oriented
	- divide img t squares
	- class prob map
	- bounding box => many ROIs, which centered around the box => choose it
	- 1-Stage detection => easy to reach 24/30 fps
	- problem with tiny objects
	- grid-based(divide img to grid squares)
	- ONNX: optimize models => depending on requirements => shift from pytorch to tensorflow and the inverse
		- boost prediction => quantization + some files t handle prediction

## Transfer Learning
1. Transfer Learning: 
	1. first part => base
	2. best: VGG/ResNet
2. Fine-tune:
	1. train the last layer
3. ![cmp](<./media/Pasted image 20251220102803.png>)