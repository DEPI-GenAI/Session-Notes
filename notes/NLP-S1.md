# NLP

## Basics

- ![pipeline](./media/image.png)
1. Preprocessing:
   - corpse => words/dataset after refining/filtering/preprocessing
     1. Tokenization: 
       - dividing words/sentences into smaller parts => so i'd handle it
       - sentence size => variable;;; can't give model variable sized input.
         - sentence tokenization: 
           - whole dataset to sentences => each sentence to numbers/vectors
           - harder as i don't know end of sentences
           - slower, uses cpu/memory more
           - why memory? as i save them as sentence => more metadata
         - word tokenizer
           - lose the sentence meaning
           - uses spaces t separate words
           - uses regex
           - faster => spacing/dividing rules simpler
     2. Stemming: 
      - delete suffix/prefix
      - sometimes => it could be extra stupid
      - fast => if task won't care verb forms
     3. Lemmatization: 
      - source/dictionary word
     4. remove stop wprds
      - ![stop words](./media/image-1.png)
     5. POS - oart of speech
      - makes the model understand the def of the word
      - parse tree got from there
     6. NER - Named Identity: person, location, tree, etc
   - why?
   to lower size of the words in vectorization

2. Vector representation
   1. BOW
      1. either count each word
      2. or encode each word => number
      3. problems:
         1. out of bag words => either: error
         2. lose meaning+semantic/grammer awareness => flatten the word
         3. sparse matrix VS dense matrix => sparse matrix has all words in my bag, not all words in my sentence all the time
         4. high dim with sparse matrix
         5. used in easy tasks that doesn't care bout semantic meaning
         6. no relation between words
         7. ![BOW](./media/image-1.png)
         8. same representation for different words
   2. N-GRAM
      1. ![n-gram](./media/image-3.png)
      2. take some words in same ram(attention)
      3. good with noisy data
      4. morphological langs
      5. preserve order/context => better context
      6. problems:
         1. go to all Ns till i reach the N i specified
   3. TF-IDF
      1. TF - Term frequency: how many times appeared in sentence => the more in sentence => the importance
      2. IDF - Inverse: how many times appeared in dataset => penalizes word appeared so many in dataset 
      3. repetetion in the sentence => != repetition in dataset
      4. still skips the semantic meaning
   4. BERT
      1. bi-directional encoder representation from transformers
      2. understand context => far till it understands king => queen from their vectorization![bert](./media/image-2.png)
      3. keeps sentence order + bi-directional
      4. handles out of vocab error => understands them
      5. understands whole sentence => vector presentation for each sentence
      6. very expensive training + limited tokens
      7. not generative, just gives presentation
   5. Word-Embedding
   