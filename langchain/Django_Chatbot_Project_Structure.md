# Django Chatbot Project Structure

A clean, scalable structure for a Django app would look like this:

``` text
chatbot/
│── __init__.py
│── llm.py
│── prompts.py
│── history.py
│── services.py
│── views.py
│── urls.py
```

## `llm.py`

``` python
from langchain_openai import ChatOpenAI
from django.conf import settings

llm = ChatOpenAI(
    model=settings.MODEL_NAME,
    api_key=settings.API_KEY,
    base_url=settings.BASE_URL,
    temperature=0.7,
)
```

## `prompts.py`

``` python
from langchain_core.prompts import ChatPromptTemplate, MessagesPlaceholder
from .llm import llm

prompt = ChatPromptTemplate.from_messages([
    ("system", "You are a helpful assistant."),
    MessagesPlaceholder(variable_name="history"),
    ("human", "{input}"),
])

chain = prompt | llm
```

## `history.py`

``` python
from langchain_core.chat_history import InMemoryChatMessageHistory
from langchain_core.runnables.history import RunnableWithMessageHistory

from .prompts import chain

store = {}


def get_history(session_id):
    if session_id not in store:
        store[session_id] = InMemoryChatMessageHistory()
    return store[session_id]


chatbot = RunnableWithMessageHistory(
    chain,
    get_history,
    input_messages_key="input",
    history_messages_key="history",
)
```

## `services.py`

``` python
from .history import chatbot


def ask_chatbot(question, session_id):
    response = chatbot.invoke(
        {"input": question},
        config={
            "configurable": {
                "session_id": session_id
            }
        },
    )

    return response.content
```

## `views.py`

``` python
from rest_framework.views import APIView
from rest_framework.response import Response

from .services import ask_chatbot


class ChatAPIView(APIView):
    def post(self, request):
        question = request.data.get("question")

        if not request.session.session_key:
            request.session.create()

        session_id = request.session.session_key

        answer = ask_chatbot(question, session_id)

        return Response({
            "answer": answer
        })
```

## Why this structure?

-   **`llm.py`** → AI model configuration only.
-   **`prompts.py`** → Prompt templates and chains.
-   **`history.py`** → Conversation history management.
-   **`services.py`** → Business logic (`ask_chatbot`).
-   **`views.py`** → Handles HTTP requests and responses.

This organization follows the **Single Responsibility Principle (SRP)**
and makes it much easier to extend your chatbot later with **RAG**,
**tools**, **multiple prompts**, or **database-backed chat history**.
