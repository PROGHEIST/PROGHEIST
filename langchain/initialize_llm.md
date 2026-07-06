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
from django.shortcuts import render
from rest_framework.views import APIView
from rest_framework import status
from rest_framework.response import Response
from .services.llm import ask_chatbot

class ChatbotAPIView(APIView):
    def post(self, request):
        question = request.data.get("question")

        if not question:
            return Response(
                {"error": "question is required."},
                status=status.HTTP_400_BAD_REQUEST
            )
        
        answer = ask_chatbot(question)
        return Response({
            "question": question,
            "answer": answer
        })
```
