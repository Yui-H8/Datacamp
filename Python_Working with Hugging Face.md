# Working with Hugging Face
---
### Listing models on Hugging Face Hub
* Import the HfApi class and create an instance of it.
* Use the appropriate method to list all models and print first two.
```python
from huggingface_hub import HfApi

# Create an instance of the HfApi class
api = HfApi()

# List only the first 2 models available on the Hub
models = list(api.list_models(limit=2))

# Print the first 2 models
for model in models:
    print(model)
```
# Building a text generation pipeline
* Complete the missing code to build a text generation pipeline using the "gpt2" model.
* Provide a custom sentence of your choice as the input prompt.
* Configure the pipeline to generate up to 10 tokens and produce 3 outputs.
```python
from transformers import pipeline 

my_pipeline = pipeline(task="text-generation", model="gpt2")

# Generate three text outputs with a maximum length of 10 tokens
results = my_pipeline("Once upon a time", max_length= 10, num_return_sequences=3)

# Display each result
for result in results:
    print(result['generated_text'])
```
### Saving and reloading Hugging Face models

