## Word Embedding
### 1. Word2Vec:

1. Continuous BOW: fast
	1. if word ain't repeating => accuracy is low
	2. window size: how many words after/before the wannato predict word
	3. ![[Pasted image 20260124102143.png]]
2. Skip gram
	1. slow
	2. doesn't care bout word repetition

### Embedding
- transform words to 768 dim matrix
- presents similar stuff with similar vectors => doesn't actually understand them,  how?
	- measures patterns in sentences 
	- it saw many sentences with both words 
	- it has textual similarity
- represent the word using 768 dimensions(features)
- general purpose: trained on general stuff, can't be specialized 
- similarity focused: 
- domain specific: 

- vector dimensionality
	- lower: squeeze groups into similar dimensions
	- higher: high storage+compute power
- symmetry: similarity(a,b) vs similarity(b,a)
	- symmetric; won't care
	- asymmetric; cares => recommendation sys
- Bias
	- training
	- retrieval
### k-similarity
- whenever i get response for a model => i use top k answers in the model, i don't fully depend on similarity as it's not enough(doesn't mean it's right)


### Bert
- contextual embedding model: الايمبد بيحصلها جينيريت في كل جملة بناء على المعنى\السياق
- context awareness, suitable for many nlp tasks
- heavy on computation + slow
- based on transformers
### Glove
- static word embedding: كل كلمة ليها ايمبيد ثابت باختلاف السياق
- fast loookup
- cons: don't care bout semantic => similar to bag of words

### alters
- openai: text embedding 3 large / small => SOA(state of art) => cross domains, good as ai assistance
- mini-lm-l5-v2 => 384, local, cheap computationally, struggle with logn docs + cross domain
- all-mpnet-base-v2: 768 => same problems but more general
- BGE: search optimized embedding model => good with rag, optimized with search tasks => strong with agents----english focused
- 