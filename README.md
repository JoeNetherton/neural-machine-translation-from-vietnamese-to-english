# neural-machine-translation-from-vietnamese-to-english

I implemented a sequence-to-sequence model with attention for the purpose of translation from Vietnamese to English. For comparison, the attention component of the model is able to be toggled- exemplifying it’s effect on translation quality. For training and evaluating the model, I used the English-Vietnamese parallel corpus of TED talks provided by the IWSLT Evaluation Campaign.

The model is considered to be a conditional language model because it is trained to learn the probability of next target word, given the target words so far and a source sentence in the current language. Once trained, the model outputs a sequence of words in the target language.

For example, the output of the trained model with and without attention is shown below (along with their corresponding BLEU scores for training and testing data) for the target sentence:

“What’s happening here? How is this possible?”

The model without the attention layer, at the end of training, reported a BLEU score of 5.84 on the test set and 5.99 on the training set. Subsequently, it produced the following output for the target sentence (<UNK/> signifies an unknown word):

“what is the <UNK/> of the <UNK/> of the <UNK/>?”

When the attention layer is included, after training, the BLEU score is vastly improved with a BLEU score of 15.34 on the test set and 15.12 on the final training epoch. Its output for the target sentence is:

“what’s going on here? why?”

