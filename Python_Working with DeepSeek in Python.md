# Working with DeepSeek in Python
---
### Your first DeepSeek request!
To preview what's ahead, the Python code for sending a request to a DeepSeek model is ready for you.      
Pass any question or instruction to the content argument and see how DeepSeek responds!
* Enter your prompt replacing INSERT YOUR PROMPT HERE, experiment, and submit your answer when ready!
```python
response = client.chat.completions.create(
    model="deepseek-ai/DeepSeek-V3",
    max_tokens=50,
  
    # Enter your prompt
    messages=[{"role": "user", "content": "In one sentence, how did DeepSeek revolutionize LLMs?"}]
)

print(response.choices[0].message.content)
```
*Answer* : DeepSeek revolutionized LLMs by introducing highly efficient, long-context models with advanced retrieval-augmented generation (RAG) capabilities, enabling superior performance in complex reasoning and knowledge-intensive tasks.
