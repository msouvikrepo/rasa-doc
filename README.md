# rasa-doc
Chatbot to recognize intents and drive business cases in german

# Rasa setup for german

It requires Python 3.x to run.

Also requires pip3 (Python package installer)
```sh
$ sudo apt-get install python3-pip
```

Install virtualenv
```sh
$ sudo pip3 install virtualenv 
```

Create and activate virtualenv
```sh
$ cd rasa_dir 
$ virtualenv venv_name
$ source venv_name/bin/activate
```

Build rasa from source
```sh
$ git clone https://github.com/RasaHQ/rasa.git
$ cd rasa
$ pip3 install -r requirements.txt
$ pip3 install -e .
```

Changing configs for german (de)

```sh
$ cd rasa/rasa/nlu/utils
```
In file 'spacy_utils.py', modify "model" parameter value to 'de', should look like this:

```py
defaults = {
        # name of the language model to load - if it is not set
        # we will be looking for a language model that is named
        # after the language of the model, e.g. `en`
        "model": 'de',
        # when retrieving word vectors, this will decide if the casing
        # of the word is relevant. E.g. `hello` and `Hello` will
        # retrieve the same vector, if set to `False`. For some
        # applications and models it makes sense to differentiate
        # between these two words, therefore setting this to `True`.
        "case_sensitive": False,
    }
```

Installing dependencies for spacy

```sh
$ pip3 install rasa[spacy]
$ python3 -m spacy download de_core_news_md
$ python3 -m spacy link de_core_news_md de
```

Installing Rasa X

```sh
$ pip3 install rasa-x --extra-index-url https://pypi.rasa.com/simple
```

Initialize rasa

```sh
$ rasa init
```

In the newly created directory from init (say 'trial_de'), change language and pipeline parameters of file config.yml,

```yml
language: de
pipeline: pretrained_embeddings_spacy
```

Replace nlu.md in directory 'data' with the file from this repository

Re-train rasa with new nlu data and launch shell bot

```sh
$ rasa train
$ rasa shell
```

Installation page : https://rasa.com/docs/rasa/user-guide/installation/
