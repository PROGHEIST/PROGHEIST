# initialize llm
## llm.py 

```python
from langchain_openai import ChatOpenAI
from django.conf import settings

llm = ChatOpenAI(
    model = settings.MODEL_NAME,
    api_key = settings.API_KEY,
    base_url = settings.BASE_URL,
    temperature = 0.7
)

def ask_chatbot(question):
    response = llm.invoke(question)
    return response.content
```

# send question to llm
## views.py

```python
from langchain_openai import ChatOpenAI
from django.conf import settings

llm = ChatOpenAI(
    model = settings.MODEL_NAME,
    api_key = settings.API_KEY,
    base_url = settings.BASE_URL,
    temperature = 0.7
)

def ask_chatbot(question):
    response = llm.invoke(question)
    return response.content
```
