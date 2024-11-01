# AI RAG in a BOX Demo 

AI RAG Demo could be used to demonstrate the DB23ai capabilities On-Premise integrated with local LLM or remote Generative AI Service.


AI RAG Demo could be used to use:
- an internal LLM like OLLAMA.
- an internal LLM like LLAMA-CPP.
- OCI Generative AI Service with Cohere or other models.

## How to Install AI RAG in a BOX

### AI RAG in a BOX Deployment Using internal LLM like Ollama and DB23ai Vector Database On-Premise

You can find the information [here](./using_internal_llama3_db23ai.md)


### Other Deployment


#### AI RAG in a BOX Deployment Using internal LLM like Ollama and QDrant Vector Database

You can find the information [here](./using_internal_llama3.md)


#### AI RAG in a BOX Deployment Using Generative AI in VM 

You can find the information [here](./using_genai.md)

## How to Start / Stop AI RAG in a BOX

### For MAC OSX

Download the script "airagdb23ai_macosx.sh" depending on your OS.

Change the rights to be executable

```Code
chmod 777 airagdb23ai_macosx.sh
```

To start AI RAG IN BOX, execute next command:

```Code
./airagdb23ai_macosx.sh start
```

To stop AI RAG IN BOX and free memory, execute next command:

```Code
./airagdb23ai_macosx.sh stop
```

### For LINUX

Download the script "airagdb23ai_linux.sh" depending on your OS.

Change the rights to be executable

```Code
chmod 777 airagdb23ai_linux.sh
```

To start AI RAG IN BOX, execute next command:

```Code
./airagdb23ai_linux.sh start
```

To stop AI RAG IN BOX and free memory, execute next command:

```Code
./airagdb23ai_linux.sh stop
```

