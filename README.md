# Text-Summarization-LLM
Text summarization using BART (Bidirectional and Auto-Regressive Transformers)


BART (Bidirectional and Auto-Regressive Transformers) combines the bidirectional encoding of BERT with the autoregressive decoding of GPT. It's essentially a sequence-to-sequence model with:

Encoder: Processes the entire input text bidirectionally (looking at words in context of both what comes before and after) 

Decoder: Generates the summary one token at a time


The "CNN" in the model name refers to the CNN/Daily Mail dataset it was fine-tuned on, which contains news articles paired with human-written summaries.


Steps to generate text summary:


Encoding: The document is processed through the encoder, which builds semantic representations of each token in context

Importance Weighting: Through attention mechanisms, the model assigns importance weights to various parts of the text

Content Selection: The decoder selects the most salient information to include

Generation: The decoder generates a fluent summary that preserves the key points


Unlike extractive summarization (which just pulls out existing sentences), BART performs abstractive summarization, meaning it can rephrase and combine information in new ways. The model doesn't simply extract the most important sentences - it understands concepts and can express them in different words, making the summaries more concise and fluid than simple extraction would allow.


## Implementation details:


-> facebook/bart-large-cnn model is loaded

-> Adjusted the model [arameters based on the summary style required

-> Set the parameters for pipeline for mpre control - temperature, number of beams

-> Used text chunking mechanism to generate summary


## Requirements:

Pytorch

Transformers

Numpy


## Output:


Given the input text, generates concise summary, detailed summary, and bullet points.

Also evaluates the generated summary.

