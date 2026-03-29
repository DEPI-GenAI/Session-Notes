## Generative AI
- problems with rnn, lstm, gru?
	- long input sequence => more complicated to store 
	- all sentence is represented in1 vector => focused on the last words more than the first ones

### Attention is all you need
- what are the parts in the sentence i have to focus on? => selective focus!
- no 1 vector holds all sentence semantics/positions/etc
- Q,K,V => each token => value + contribute in the answer of each Query
- K => how the word is relevant to the rest of the sentence
- X=word, WQ: random initialized
- element wise multiplication of each word key with the query => scale => softmax => probs * value(the features of the words 
- ![[Pasted image 20260131104242.png]]
---
### Extra Session

- ![[Pasted image 20260131165823.png]]1. masked attention => so that it won't see the upcoming words(my task is to predict the next thing)

---
encoder decoder => seq2seq
decoder only => generative models/llms

