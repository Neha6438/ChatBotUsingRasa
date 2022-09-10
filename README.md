# ChatBotUsingRasa
### Creating chatbot using a RASA Framework
RASA chatbot is an conversional AI wih RASA NLU and RASA Core.The conversional AI dramatically change the way of interect with users

### Whats an RASA?
Rasa is an open source machine learning framework for automated text and voice-based conversations. Understand messages, hold conversations, and connect to messaging channels and APIs.

### Rasa has two main components:
1. Rasa NLU (Natural Language Understanding): Rasa NLU is an open-source natural language processing tool for intent classification (decides what the user is asking), extraction of the entity from the bot in the form of structured data and helps the chatbot understand what user is saying.
2. Rasa Core: a chatbot framework with machine learning-based dialogue management which takes the structured input from the NLU and predicts the next best action using a probabilistic model like LSTM neural network rather than if/else statement. Underneath the hood,  it also uses reinforcement learning to improve the prediction of the next best action.

In other words, the Rasa NLU’s job is to interpret the input provided by the user in the form of structured data and Rasa Core’s job is to decide the next set of actions performed by the chatbot. Rasa Core and Rasa NLU are independent of each other and can be used separately.

### How to Install Rasa:
It is highly recommended to use a virtual environment before installing RASA. For creating the virtual environment, the command in anaconda is:
conda create -n rasa
activate rasa

Now, we will install the Rasa in our environment, we will install using pip install. We also need to install TensorFlow in our environment (it will be installed default by Rasa). Installing rasa will take some time.
pip install rasa

Now, we will initialize the bot using rasa init. This will create the stating project files for the chatbot and train the initial model.
rasa init

project files in directory

__init__.py:  An empty file that helps python to locate your actions.
actions.py: This file is used for creating custom actions. In case you want to call an external server or fetch external API data, you can define your actions here.
config.yml: This file defines the configuration of the NLU and core model. If you are using any model outside the NLU model, you have to define the pipeline here.
credentials.yml: This file is used to store credentials for connecting to external services such as Facebook Messenger, Slack, etc
data/nlu.md: In this file, we define our intents (what the user could ask the bot to do? ).  These intents are then used in training the NLU model.
data/stories.md: Stories are the sample conversation between a user and bot in the form of intents, responses and actions. Rasa stories are a form of training data used to train the Rasa’s dialogue management models.
domain.yml: This file lists the different intent (the things which you expect from the user) with bot’s responses and actions which it can perform.
endpoints.yml: This defines the details for connecting channels like Slack, FB messenger, etc. for storing chats data in the online databases like Redis, etc.
models/<timestamps>.tar.gz: the initial model, all the trained models stored in the models folder. For retraining the model, we use rasa train command.
For starting the local environment we use rasa x command. It started with something

Now, navigate to the address provided by rasa server, we will see the browser window in which a chat window opens, that we can use to chat with the assistant.
