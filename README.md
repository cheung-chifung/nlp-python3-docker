# nlp-python3-docker

This is a docker image with popular NLP frameworks for text segmentation purpose.

Includes:

- Python3
- nltk (for English)
- jieba (for Chinese)
- mecab (for Japanese)

Corpus are also includes.

## Usage

```shell
docker run -it cheungchifung/nlp-python3-docker:latest python
```

```python
>>> import MeCab
>>> m = MeCab.Tagger('-d /usr/local/lib/mecab/dic/mecab-ipadic-neologd')
>>> m.parse("pythonが大好きです").split()
['python', '名詞,固有名詞,組織,*,*,*,*', 'が', '助詞,格助詞,一般,*,*,*,が,ガ,ガ', '大好き', '名詞,形容動詞語幹,*,*,*,*,大好き,ダイスキ,ダイスキ', 'です', '助動詞,*,*,*,特殊・デス,基本形,です,デス,デス', 'EOS']
```

```python
>>> import nltk
>>> sentence = """At eight o'clock on Thursday morning Arthur didn't feel very good."""
>>> tokens = nltk.word_tokenize(sentence)
>>> tokens
['At', 'eight', "o'clock", 'on', 'Thursday', 'morning', 'Arthur', 'did', "n't", 'feel', 'very', 'good', '.']
```

```python
>>> import jieba
>>> seg_list = jieba.cut("他来到了网易杭研大厦")
>>> print(", ".join(seg_list))
Building prefix dict from the default dictionary ...
Dumping model to file cache /tmp/jieba.cache
Loading model cost 1.667 seconds.
Prefix dict has been built succesfully.
他, 来到, 了, 网易, 杭研, 大厦
```
