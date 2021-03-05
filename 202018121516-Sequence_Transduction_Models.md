#### Sequence Transduction Models

Transduction refers to predicting specific examples given specific examples from a domain, in contrast to induction (deriving function from data) or deduction (deriving values from function for points of interest). Transduction instead derives values of the unknown function for points of interest from the given data (The Nature of Statistical Learning Theory, 1995).

![[Screenshot 2020-12-18 at 15.19.54.png]]

An example of a transductive algorithm is the k-NN algorithm. It doesn't model the data, but instead uses it each time a prediction is required.

Transduction is usually used in the field of natural language processing (sequence prediction):

"Another option is to treat the RNN as a transducer, producing an output for each input it reads in" (Neural Network Methods in Natural Language Processing, 2017).

"Many natural language processing (NLP) tasks can be viewed as transduction problems, that is learning to convert one string into another. Machine translation is a prototypical example of transduction and recent results indicate that Deep RNNs have the ability to encode long source strings and produce coherent translations" (Learning to Transduce with Unbounded Memory, 2015).

#PhD #Permanent #ML #DeepLearning