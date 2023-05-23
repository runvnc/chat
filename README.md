```python
import os, openai
openai.api_key = os.environ.get("OPENAI_API_KEY", None)

def chat(prompt):
    msgs = [{"role": "system", "content":"You are a helpful assistant."},
            {"role": "user", "content": "Hello."},
            {"role": "assistant": "content": "Hi, how can I help you?",
            {"role": "user", "content": prompt}]

    res = openai.ChatCompletion.create(model="gpt-3.5-turbo", messages=msgs)
    return res["choices"][0].message["content"]
```
