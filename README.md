### NAME : Thilakeswaran KP
### REG NO : 212223230232
## Design and Implementation of LangChain Expression Language (LCEL) Expressions

### AIM:
To design and implement a LangChain Expression Language (LCEL) expression using prompt, model, and output parser, and evaluate its functionality with multiple prompt parameters.

### DESIGN STEPS:

#### STEP 1:
Import necessary libraries (langchain, openai, dotenv).
#### STEP 2:
Define a prompt template with two parameters (concept, audience).
#### STEP 3:
Initialize the LLM model (ChatOpenAI).
#### STEP 4:
Use an output parser (StrOutputParser) for clean responses.
#### STEP 5:
Combine prompt, model, and parser into an LCEL chain and invoke with inputs.

### PROGRAM:
```
import os
import openai

from dotenv import load_dotenv, find_dotenv
_ = load_dotenv(find_dotenv()) # read local .env file
openai.api_key = os.environ['OPENAI_API_KEY']

from langchain.prompts import ChatPromptTemplate
from langchain.chat_models import ChatOpenAI
from langchain.schema.output_parser import StrOutputParser

prompt = ChatPromptTemplate.from_template(
    "Explain {concept} in a way that a {audience} can understand."
)
model = ChatOpenAI()
output_parser = StrOutputParser()

chain = prompt | model | output_parser

chain.invoke({"concept": "Deep Learning", "audience" : "ADVANCE  "})
```

### OUTPUT:
<img width="1595" height="427" alt="Screenshot 2025-09-19 112654" src="https://github.com/user-attachments/assets/8c0e1fac-79a9-4918-ba4e-381a3301889b" />

### RESULT:
Hence, the LCEL expression using LangChain with prompt, model, and output parser is successfully designed, implemented, and executed to generate context-specific explanations.
