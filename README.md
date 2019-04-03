# voice-enabled-chatbot


If we have topics like the weather, location information, inventory information etc the
application should be able to converse in that particular topic. Like, if we have questions
such as:-
Hey, what is the weather today? - Weather Information
I want to know if there are any shopping stores near me. - Location Information
Will it rain today? - Weather Information
Can you tell me availability of item in Store X? - Inventory Information
Initially the application should be able to identify each particular topic and then return the
appropriate response. After that, the chatbot should carry on the conversation regarding that
particular topic. For ex:
User - I want to know if there are any shopping stores near me.
Chatbot - These are the nearest stores:- A, B, C. Where do you wanna go?
User - I want to go to the most popular one among them
Chatbot- All right, showing you directions to C.
So, mainly the chatbot should formulate appropriate responses to incoming questions and
carry on the conversation. Keeping in mind, the conversation would be in natural language
and the user is returned sufficient information.




Before starting Conversation, bot will fetch the location of the user and other details to give personalized results.

Step 1: Speech-2-Text:  Given a speech through Microphone, Store it and Convert it using SpeechRecognition and PyAudio.

Step 2: Topic Modelling: Get Entity and Intent of chat using model with a corpora. To get the trained model, we will use the classifier to categorize it to weather, location and inventory. After that using RASA-NLU with Spacy library, we will get the entities.

Step 3:  After Finding Intent and Entity, we will set model in following method:
Intent  = Weather: Based on entity specified, We will use weather API to get data about location.
Intent = Location: Following Conversation flow:
Get Stores located or Any Nearby Stores
Choose Store
Inventory Details about Store

Step 4: Use cache mechanism to give result about recently used query.


References Using: a) https://medium.com/@rahulvaish/speech-to-text-python-77b510f06de
         b) https://link.springer.com/content/pdf/10.1007%2F978-3-642-36973-5_88.pdf