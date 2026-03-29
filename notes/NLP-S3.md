## Notes
- activation function => change shape of info/neglect non important stuff
- so, kinda does feature extraction!
- فيه نتورك نصها cnn ونصها rnn لل image captioning
- 
## Intro
- why won't we solve nlp prob with ml? ML => has 0 memory + the task are too complex => can be used in sentiment analysis(classify)
- what about dl? 
	- input => output
	- statement length => varies
	- memory problem => only current state
	- آخره word to vec لل Q&A task
- what about CNN?
	- more into pixels/spatial context, not words context
	- RNN? 
		- input variation problem? take tallest context + embed the rest with zeros
		- fold RNN => output + state(part of my input sent to the next cell)
		- types
			- 1-1 => predict next letter, takes 1 input => 1 output
			- many-1 => sentiment analysis => squishes the output of prev block => send it to next block => get final block's output
			- 1-many => image captioning/music generation?
			- many-many => chatbot/translation/speech recognition
		- problems
			- vanishing gradients => long learning process
			- long-term-memory-loss => الكلام اللي في اول الجملة لو هي طويلة هينساه
- step function => linear; relu => vanishing gradients; sigmoid => limited range; tanh => best solution
- so, we made LSTM & GURU
	- LSTM
		- ![[Pasted image 20260126195027.png]]
		- cell state => defines which i'd keep/what's inside for too long in the memory
		- hidden state =>  the current stuff am learning
		- forget gate => current state + old state =>  decides which stuff i'd remove from my memory => 0:forget, 1:keep
		- input gate => decides how t update long memory, which stuff
		- output gate => 

		- heavy computation
		  
	- GRU
		- reset => remove some stuff from memory
		- update => 