# SummaRise Text-Summarization
Understanding about Text Summarization and Implementing various Models used for Text Summarization

Read Notebook [Summarise Notebook.ipynb](/Summarise_Notebook.ipynb)
# Model for Text Summarization

## [1] Seq2Seq and Encoder-Decoder Recurrent Neural Networks

### Seq2Seq

The seq2seq models encodes the content of an article (encoder input) and one character (decoder input) from the summarized text to predict the next character in the summarized text

The implementation can be found in [keras_text_summarization/library/seq2seq.py](keras_text_summarization/library/seq2seq.py)

There are three variants of seq2seq model implemented for the text summarization   
* Seq2SeqSummarizer (one hot encoding)
    * training: run [demo/seq2seq_train.py](demo/seq2seq_train.py ) 
    * prediction: demo code is available in [demo/seq2seq_predict.py](demo/seq2seq_predict.py) 
* Seq2SeqGloVeSummarizer (GloVe encoding for encoder input)
    * training: run [demo/seq2seq_glove_train.py](demo/seq2seq_glove_train.py) 
    * prediction: demo code is available in [demo/seq2seq_glove_predict.py](demo/seq2seq_glove_predict.py) 
* Seq2SeqGloVeSummarizerV2 (GloVe encoding for both encoder input and decoder input)
    * training: run [demo/seq2seq_glove_v2_train.py](demo/seq2seq_glove_v2_train.py)
    * prediction: demo code is available in [demo/seq2seq_glove_v2_predict.py](demo/seq2seq_glove_v2_predict.py) 
    
### Other RNN models

There are currently 3 other encoder-decoder recurrent models based on some recommendation [here](https://machinelearningmastery.com/encoder-decoder-models-text-summarization-keras/)

The implementation can be found in [keras_text_summarization/library/rnn.py](keras_text_summarization/library/rnn.py)

* One-Shot RNN (OneShotRNN in [rnn.py](keras_text_summarization/library/rnn.py)):
The one-shot RNN is a very simple encoder-decoder recurrent network model which encodes the content of an article and decodes the entire content of the summarized text
    * training: run [demo/one_hot_rnn_train.py](demo/one_hot_rnn_train.py)
    * prediction: run [demo/one_hot_rnn_predict.py](demo/one_hot_rnn_predict.py)
* Recursive RNN 1 (RecursiveRNN1 in [rnn.py](keras_text_summarization/library/rnn.py)):
The recursive RNN 1 takes the artcile content and the current built-up summarized text to predict the next character of the summarized text.
    * training: run [demo/recursive_rnn_v1_train.py](demo/recursive_rnn_v1_train.py)
    * prediction: run [demo/recursive_rnn_v1_predict.py](demo/recursive_rnn_v1_predict.py)
* Recursive RNN 2 (RecursiveRNN2 in [rnn.py](keras_text_summarization/library/rnn.py)):
The recursive RNN 2 takes the article content and the current built-up summarized text to predict the next character of the summarized text + one layer of LSTM decoder.
    * training: run [demo/recursive_rnn_v2_train.py](demo/recursive_rnn_v2_train.py)
    * prediction: run [demo/recursive_rnn_v2_predict.py](demo/recursive_rnn_v2_predict.py)

The trained models are available in the demo/models folder 

### Sample Output
#### Article 1   
After a week of nonstop criticism from Democrats and Republicans alike for comments many condemned as racially charged, Donald Trump claims to be altering his campaign to be a little more inclusive. While the presumptive G.O.P. has long promised to “make America great again,” Trump now says he’s adding two words to slogan to illustrate just how non-racist he really is.

“You know, I have the theme ‘make America great again,’ and I've added a couple of things,” Trump announced to supporters at a campaign rally in Richmond, Virginia, on Friday night. “Right now I’m adding make America great again—I’m adding ‘for everyone,’ because it’s really going to be for everyone. It’s not going to be for a group of people, it’s going to be for everyone. It’s true.”

The allegedly amended slogan, which has yet to appear on any official signage or Trump merchandise, comes after the presidential candidate spent the first half of June repeatedly denouncing Gonzalo Curiel, the federal judge of Mexican heritage presiding over the Trump University class action lawsuit, as inherently biased against him. (Curiel was born in Indiana.) His comments were widely condemned by the Washington political establishment, including Senate Minority Leader Mitch McConnell, who suggested he may be an idiot, and House Speaker Paul Ryan, who called Trump’s statement the “textbook definition of a racist comment.”

Trump, who hasn’t apologized or taken back any of his comments, indicated on Friday that he realized his words have had a negative effect on his campaign and declared he is not a racist.

“I am the least racist person. The least racist person that you’ve ever seen. I mean give me a break,” he said at the rally. “I am the least racist person that you’ve ever looked at, believe me.”

<b>Generated Headline:</b>  donald trump is changing his campaign refusal to blame it get i

<b>Original Headline:</b>  Donald Trump Is Changing His Campaign Slogan to Prove He’s Not Racist

#### Article 2 
Lavrov and Kerry discuss Syrian settlement October 28, 2016 TASS 
Russian Foreign Ministry Sergey Lavrov and U.S. Secretary of State John Kerry discussed the Syrian settlement as well as the situation in Yemen and Libya by telephone on Oct. 28. 
The Russian Foreign Ministry said that the conversation had taken place at the U.S. side’s request. 
"The foreign policy chiefs continued discussing ways of settling the Syrian conflict, including the normalization of the situation around Aleppo, with account taken of fundamental approaches contained in the previously reached Russian-U.S. agreements. For that, the United States should ultimately separate moderate opposition (in Syria) from terror groups," the Russian Foreign Ministry said. 
"Lavrov and Kerry also discussed assistance to the solution of crises in Yemen and Libya as well as separate issues of bilateral agenda," the Russian Foreign Ministry stressed.

<b>Generated Headline:</b>  lavrov and kerry discuss syrian war<br>
<b>Original Headline:</b>  Lavrov and Kerry discuss Syrian settlement

### Installation & Configuration

```bash
pip install requirements.txt

cd demo
 
```
For training make sure you have tensorflow-gpu and CUDA installed

### Execution

There are already pre-trained models available at (demo/models) it can be used directly or you can train on your own

To train a deep learning model, say Seq2SeqSummarizer, run the following commands:
```bash
python seq2seq_train.py
```

To summarise a sequence of sample texts run
```bash
python main.py
```

To summarise one sentence of your own run
```bash
python main1sent.py
```

Also for train and validation there is Accuracy and Loss graphs available at [demo/reports] 

Data source : [https://github.com/GeorgeMcIntire/fake_real_news_dataset](https://github.com/GeorgeMcIntire/fake_real_news_dataset)

### References

* https://machinelearningmastery.com/encoder-decoder-models-text-summarization-keras/
* https://github.com/chen0040/keras-text-summarization

</br>

## [2] Pointer Generator Networks [Will be soon updated]

## Note:
<b> 
* Other Models wil soon be updated </br>
* Android App and Chrome Extension will soon be launched for Summarization of Articles/Blogs
</b>
