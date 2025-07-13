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
1. Complete the code to create a pipeline for text classification.    
Use the appropriate method to save the pipeline locally.
```python
modelId = "distilbert-base-uncased-finetuned-sst-2-english"

my_pipeline = pipeline("text-classification", model=modelId)

# Save the model locally
my_pipeline.save_pretrained(f"models/{modelId}")
```
2. Complete the code to reload the saved model.   
Test the reloaded model with the given text.
```python
modelId = "distilbert-base-uncased-finetuned-sst-2-english"

my_pipeline = pipeline("text-classification", 
                        model=modelId)

my_pipeline.save_pretrained(f"models/{modelId}")

# Reload the saved model
reloaded_pipeline = pipeline("text-classification", model=f"models/{modelId}")

# Test the reloaded model
print(reloaded_pipeline("Hugging Face is great!"))
```
---
### Inspecting datasets
1. Import load_dataset_builder.   
Create the reviews_builder to inspect the dataset.
```python
# Import the function to load dataset metadata
from datasets import load_dataset_builder

# Initialize the dataset builder for the MMLU-Pro dataset
reviews_builder = load_dataset_builder("TIGER-Lab/MMLU-Pro")
```
2. Display the dataset metadata and review the available information.
```python
# Import the function to load dataset metadata
from datasets import load_dataset_builder

# Initialize the dataset builder for the MMLU-Pro dataset
reviews_builder = load_dataset_builder("TIGER-Lab/MMLU-Pro")

# Display dataset metadata
print(reviews_builder.info)
```
3. Calculate and display the dataset size in megabytes.
```python
# Import the function to load dataset metadata
from datasets import load_dataset_builder

# Initialize the dataset builder for the MMLU-Pro dataset
reviews_builder = load_dataset_builder("TIGER-Lab/MMLU-Pro")

# Display dataset metadata
print(reviews_builder.info)

# Calculate and print the dataset size in MB
dataset_size_mb = reviews_builder.info.dataset_size / (1024 ** 2)
print(f"Dataset size: {round(dataset_size_mb, 2)} MB")
```
### Loading datasets
* Use the correct function to load the "TIGER-Lab/MMLU-Pro" dataset and specify the "test" split.
```python
# Load the "test" split of the TIGER-Lab/MMLU-Pro dataset
my_dataset = load_dataset("TIGER-Lab/MMLU-Pro", split="test")

# Display dataset details
print(my_dataset)
```
