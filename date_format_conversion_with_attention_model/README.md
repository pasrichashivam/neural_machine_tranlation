# Neural Machine Translation with Attention in Keras.

## Here seq2seq model is create with attention mechanism which can translate the human readable dates (8 march 2018) to standard date format (2018-03-08).

## What is seq2seq model.
 * seq2seq model takes sequence as input (source) and gives seq as output (target) (where input and output seq can be of different lengths).
 * seq2seq model uses 2 networks.
   1. Encoder: Takes input (source) sequence and gives some output (feature vectors)
   2. Decoder: Takes the output of Encoder model (feature vector) and generate target seq.

## In date translation example encoder-decoder model looks like this.
     ![enc_dec](images/encode_decode.jpg?raw=true "enc_dec")

## Encoder-Decoder Network with attention mechanism.
 * We do not read whole text in one go and then do the translation.
 * Rather we first understand that 8 correspond to date '08', March correspond to month '03' 2018 corespond to year '2018'
 * This step is acheved by attention mechanism.

## In date translation example encoder-decoder model with attention mechanism looks like this.
     ![enc_dec_attention](images/encode_decode_attention.jpg?raw=true "enc_dec_attention")

## Full Model overview:
 * In encoder network Bidirectional LSTM is used, It will take characters as input sequence and output the feature vector.
 * Lets take example of translating the month 'march' to '03'.
 * As shown in image with bold marker lines, attentions coming from the 'm', 'a', 'r' character is more as compare to other characters so the context vector created from these three attention weights will have higher values.
 * This context vector will determine which characters to focus on to determine the month from date.
 * Then the decoder network will take this context vector and previous state as input to make prediction.





