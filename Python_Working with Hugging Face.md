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
### Manipulating datasets
1. Filter the dataset for rows with the term "football" in the text column and save as filtered.   
Select a single example from the filtered dataset and save as example.
```python
# Filter the documents
filtered = wikipedia.filter(lambda row: "football" in row["text"])

# Create a sample dataset
example = filtered.select(range(1))

print(example[0]["text"])
```
---
##2. Text classification
---
### Grammatical correctness
* Create a pipeline for the task text-classification and use the model "abdulmatinomotoso/English_Grammar_Checker", saving the pipeline as grammar_checker.
* Use the grammar_checker to predict the grammatical correctness of the input sentence provided and save as output.
```Python
# Create a pipeline for grammar checking
grammar_checker = pipeline(
  task ="text-classification", 
  model ="abdulmatinomotoso/English_Grammar_Checker"
)

# Check grammar of the input text
output = grammar_checker("I will walk dog")
print(output)
```
### Question Natural Language Inference
* Create a text classification QNLI pipeline using the model "cross-encoder/qnli-electra-base" and save as classifier.
* Use this classifier to determine if the text provides enough information to answer the question.
```python
# Create the pipeline
classifier = pipeline(
    task="text-classification", 
    model="cross-encoder/qnli-electra-base"
)

# Predict the output
output = classifier("Where is the capital of France?, Brittany is known for its stunning coastline.")

print(output)
```
### Dynamic category assignment
* Build the pipeline and save as classifier.
* Create a list of the labels - "politics", "science", "sports" - and save as categories.
* Predict the label of text using the classifier and predefined categories.
```python
text = "AI-powered robots assist in complex brain surgeries with precision."

# Create the pipeline
classifier = pipeline(task="zero-shot-classification", model="facebook/bart-large-mnli")

# Create the categories list
categories = ["politics", "science", "sports"]

# Predict the output
output = classifier(text, categories)

# Print the top label and its score
print(f"Top Label: {output['labels'][0]} with score: {output['scores'][0]}")
```
---
### Summarizing long text
* Create the summarization pipeline using the task "summarization" and save as summarizer.
* Use the new pipeline to create a summary of the text and save as summary_text.
* Compare the length of the original and summary text.
```python
# Create the summarization pipeline
summarizer = pipeline(task="summarization", model="cnicu/t5-small-booksum")

# Summarize the text
summary_text = summarizer(original_text)

# Compare the length
print(f"Original text length: {len(original_text)}")
print(f"Summary length: {len(summary_text[0]['summary_text'])}")
```
### Adjusting the summary length
1. Create a summarization pipeline to summarize original_text to between 1 and 10 tokens.
```python
# Generate a summary of original_text between 1 and 10 tokens
short_summarizer = pipeline(task="summarization", model="cnicu/t5-small-booksum", min_new_tokens = 1, max_new_tokens = 10)

short_summary_text = short_summarizer(original_text)

print(short_summary_text[0]["summary_text"])
```
2. Repeat these steps for a summarization pipeline that has a minimum length of 50 and maximum of 150.
```python
# Repeat for a summary between 50 and 150 tokens
long_summarizer = pipeline(task="summarization", model="cnicu/t5-small-booksum", min_new_tokens = 50, max_new_tokens = 150)

long_summary_text = long_summarizer(original_text)

print(long_summary_text[0]["summary_text"])
```
---
### Tokenizing text with AutoTokenizer
* Import the required class from transformers, load the tokenizer using the correct method, and split input text into tokens.
```python
# Import necessary library for tokenization
from transformers import AutoTokenizer

# Load the tokenizer
tokenizer = AutoTokenizer.from_pretrained("distilbert-base-uncased-finetuned-sst-2-english")

# Split input text into tokens
tokens = tokenizer.tokenize("AI: Making robots smarter and humans lazier!")

# Display the tokenized output
print(f"Tokenized output: {tokens}")
```
### Using AutoClasses
* Download the model and tokenizer and save as my_model and my_tokenizer, respectively.
* Create the pipeline and save as my_pipeline.
* Predict the output using my_pipeline and save as output.
```python
# Download the model and tokenizer
my_model = AutoModelForSequenceClassification.from_pretrained("distilbert-base-uncased-finetuned-sst-2-english")
my_tokenizer = AutoTokenizer.from_pretrained("distilbert-base-uncased-finetuned-sst-2-english")

# Create the pipeline
my_pipeline = pipeline(task="sentiment-analysis", model= my_model, tokenizer = my_tokenizer)

# Predict the sentiment
output = my_pipeline("This course is pretty good, I guess.")
print(f"Sentiment using AutoClasses: {output[0]['label']}")
```
---
### Extracting text with PyPDF
* Import the required class from pypdf and use it to load the PDF file.
* Access each page and extract its content using the correct method.
```python
from pypdf import PdfReader

# Extract text from the PDF
reader = PdfReader("US_Employee_Policy.pdf")

# Extract text from all pages
document_text = ""
for page in reader.pages: 
    document_text += page.extract_text()

print(document_text)
```
### Building a Q&A pipeline
* Initialize a question-answering pipeline with the correct task and model.
* Pass the question and document_text to the pipeline.
* Print the result to view the answer.
```python
# Load the question-answering pipeline
qa_pipeline = pipeline(task="question-answering", model="distilbert-base-cased-distilled-squad")

question = "What is the notice period for resignation?"

# Get the answer from the QA pipeline
result = qa_pipeline(question=question, context=document_text)

# Print the answer
print(f"Answer: {result['answer']}")
```
