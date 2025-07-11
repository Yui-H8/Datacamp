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
