# Rasa Chabot

## :surfer: Introduction
The purpose of this repo is to showcase a contextual AI assistant built with the open source Rasa framework.

It is an alpha version and lives in our docs, helping developers getting started with our open source tools. It supports the following user goals:

- Understanding the Rasa framework
- Answering some FAQs around VLU
- Handling basic chitchat

## 👷‍ Installation

To install Sara, please clone the repo:
```sh
git clone https://github.com/ducdo5496/RasaChatbot
```
Create virtual enviroment:
```sh
python -m venv venv 
```
Active your environment:
```sh
venv\Scripts\activate
```
Update pip:
```sh
python -m pip install --upgrade pip
```
Install protobuf:
```sh
pip install protobuf==3.19.4
```
Install rasa:
```sh
pip install rasa==3.0.9
```

This will install the bot and all of its requirements.
Note that this bot should be used with python 3.8 or higher.


## 🤖 To run Rasa Chatbot:

Use `rasa train` to train a model (this will take a significant amount of memory to train,
if you want to train it faster, try the training command with
`--augmentation 0`).

Then, to run, first set up your action server in one terminal window:
```bash
rasa run actions --actions actions.actions
```

There are some custom actions that require connections to external services,
specifically `SubscribeNewsletterForm` and `SalesForm`. For these
to run you would need to have your own MailChimp newsletter and a Google sheet
to connect to. See the [development](#development) section for instructions on providing
credentials for external services.

In another window, run the bot:
```bash
rasa shell
```

## To test Rasa Chabot:

After doing a `rasa train`, run the command:

```bash
rasa test core --stories tests/test_stories.yml
```

## 👩‍💻 Overview of the files

`actions` - contains custom action code

`data/nlu.yml` - contains NLU training data

`data/stories.yml/` - contains stories 

`data/rules.yml/` - contains rules 

`domain.yml` - the domain file, including bot response templates

`config.yml` - training configurations for the NLU pipeline and policy ensemble

`credentials.yml` - this file contains the credentials for the voice & chat platforms

`endpoints.yml` - this file contains the different endpoints your bot can use.

## :gift: License
Licensed under the GNU General Public License v3. Copyright 2018 Rasa Technologies
GmbH. [Copy of the license](https://github.com/RasaHQ/rasa-demo/blob/main/LICENSE).
Licensees may convey the work under this license. There is no warranty for the work.
