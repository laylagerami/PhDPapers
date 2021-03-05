#### Encoder-Decoder Architecture

From [[https://d2l.ai/chapter_recurrent-modern/encoder-decoder.html]].

Encoder-decoder architectures are useful for sequence transduction models [[202018121516-Sequence_Transduction_Models]], where input and output are variable-length sequences (i.e., the length of input and output are not a fixed number, such as words in a sentence).

The two components in such an architecture are the *encoder*, which takes a variable-length sequence as input and transforms it into a state with a fixed shape, and a *decoder*, which maps this encoded state into a variable-length sequence. The 'state' can also be called a latent space representation?

![[Screenshot 2020-12-18 at 15.25.34.png]]




#Permanent #PhD #ML #DeepLearning