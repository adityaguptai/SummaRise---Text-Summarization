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

<hr>
## [2] Pointer Generator Networks [Will be soon updated]

## Note:
<b> ### Other Models wil soon be updated
 ### Android App and Chrome Extension will soon be launched for Summarization of Articles/Blogs
</b>
