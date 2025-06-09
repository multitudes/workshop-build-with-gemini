# Workshop: Build with Gemini

This workshop teaches how to build with Gemini using the Gemini API and Python SDK.


No, this is not creating a Python function - it's creating a **function declaration** that describes an API endpoint to Gemini. It's more like a schema or contract that tells Gemini:

1. What the function is called (`get_current_temperature`)
2. What it does (via the `description`)
3. What parameters it accepts (`location`)
4. The type and format of those parameters

Here's the structure:
```python
weather_function = {
    "name": "get_current_temperature",        # Function name
    "description": "Gets the current temperature for a given location.",
    "parameters": {                           # Parameter specification
        "type": "object",
        "properties": {
            "location": {                     # Parameter name
    ython
def get_current_temperature(location: str) -> dict:
    """Gets the current temperature for a given location."""
    # ... actual implementation ...
    return {"temperature": 25, "unit": "Celsius"}
```
            "type": "string",            # Parameter type
                "description": "The city name",
            },
        },
        "required": ["location"],            # Required parameters list
    },
}
```

Later in the code, you'd need to implement the actual Python function that performs this operation. This is just telling Gemini what function exists and how to use it.

The actual Python function implementation comes later in the notebook:
```python
def get_current_temperature(location: str) -> dict:
    """Gets the current temperature for a given location."""
    # ... actual implementation ...
    return {"temperature": 25, "unit": "Celsius"}
```

> [!NOTE]
> I recommend first going through the notebooks and exercises in the [notebooks](https://github.com/patrickloeber/workshop-build-with-gemini/blob/main/notebooks/) folder. You'll find the same notebooks but with the solutions in [solutions](https://github.com/patrickloeber/workshop-build-with-gemini/blob/main/solutions/).

**Prerequisites**: You need an API key from [Google AI Studio](https://aistudio.google.com/apikey). Everything can be done on the free tier.

Course outline:

- [Part1: Quickstart + Text prompting](https://github.com/patrickloeber/workshop-build-with-gemini/blob/main/notebooks/part-1-text-prompting.ipynb)
    - Text understanding
    - Streaming response
    - Chats
    - System prompts
    - Config options
    - Long context
    - Token usage
    - Final excercise: Chat with book

- [Part 2: Multimodal understanding (image, video, audio, docs, code)](https://github.com/patrickloeber/workshop-build-with-gemini/blob/main/notebooks/part-2-multimodal-understanding.ipynb)
    - Image
    - Video
    - Audio
    - Documents (PDFs)
    - Code
    - Final excercise: Analyze supermarket invoice

- [Part 3: Thinking models + agentic capabilities (tool usage)](https://github.com/patrickloeber/workshop-build-with-gemini/blob/main/notebooks/part-3-thinking-and-tools.ipynb)
    - Thinking models
    - Structured outputs
    - Code execution
    - Grounding with Google Search
    - Function calling
    - Final excercise: Give Gemini access to the PokéAPI to answer Pokémon questions

**Next steps**: There's even more you can do with Gemini:

- [Image creation and editing with Gemini 2.0](https://github.com/patrickloeber/genai-tutorials/blob/main/notebooks/gemini-image-editing.ipynb)
- [Live API: Talk to Gemini and share your camera](https://aistudio.google.com/live) & [Live API cookbook](https://github.com/google-gemini/cookbook/blob/main/quickstarts/Get_started_LiveAPI.ipynb)

- [API docs quickstart](https://ai.google.dev/gemini-api/docs/quickstart?lang=python)  
- [Text generation docs](https://ai.google.dev/gemini-api/docs/text-generation)  
- [Long context docs](https://ai.google.dev/gemini-api/docs/long-context)  

Next steps:
- [Part 2: Multimodal understanding (image, video, audio, docs, code)](https://github.com/patrickloeber/workshop-build-with-gemini/blob/main/notebooks/part-2-multimodal-understanding.ipynb)  

https://github.com/pytube/pytube


More helpful resources:

- [Audio understanding docs](https://ai.google.dev/gemini-api/docs/audio?lang=python)
- [Visio understanding docs](https://ai.google.dev/gemini-api/docs/vision?lang=python)
- [Philschmid blog post: From PDFs to Insights](https://www.philschmid.de/gemini-pdf-to-data)
- [Structured output docs](https://ai.google.dev/gemini-api/docs/structured-output?lang=python)
- [Video understanding cookbook](https://github.com/google-gemini/cookbook/blob/main/quickstarts/Video_understanding.ipynb)

Next steps:

- **[Part 3: Thinking models + agentic capabilities (tool usage)](https://github.com/patrickloeber/workshop-build-with-gemini/blob/main/notebooks/part-3-thinking-and-tools.ipynb)**




More helpful resources:

- [Thinking docs](https://ai.google.dev/gemini-api/docs/thinking)
- [Structured output docs](https://ai.google.dev/gemini-api/docs/structured-output?lang=python)
- [Code execution docs](https://ai.google.dev/gemini-api/docs/code-execution?lang=python)
- [Grounding docs](https://ai.google.dev/gemini-api/docs/grounding?lang=python)
- [Function calling docs](https://ai.google.dev/gemini-api/docs/function-calling?example=weather)

🎉🎉**Conratulations, you completed the workshop!**🎉🎉

**Next steps**: There's even more you can do with Gemini which we didn't cover in this workshop:

- [Image creation and editing with Gemini 2.0](https://github.com/patrickloeber/genai-tutorials/blob/main/notebooks/gemini-image-editing.ipynb)
- [Live API: Talk to Gemini and share your camera](https://aistudio.google.com/live) & [Live API cookbook](https://github.com/google-gemini/cookbook/blob/main/quickstarts/Get_started_LiveAPI.ipynb)

