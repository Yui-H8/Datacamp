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
---
### Building a DeepSeek request
Throughout the course, you'll write Python code to prompt DeepSeek models via the openai library. Entering your own API key is not necessary to create requests and complete the exercises in this course.

The OpenAI class has already been imported for you from the openai library.

> Please note that although base_url is set to "https://api.together.xyz/v1" , the official DeepSeek API, the requests in these exercises are actually being rerouted to together.ai's API.

* Create an OpenAI API client (keep <TogetherAI API Key> unchanged).   
create a request for the "deepseek-ai/DeepSeek-V3" model to the Chat Completions endpoint.
```python
# Create the OpenAI client
client = OpenAI(api_key="<TogetherAI API Key>", base_url="https://api.together.xyz/v1")

# Create a request to the chat model
response = client.chat.completions.create(
    model="deepseek-ai/DeepSeek-V3",
    max_tokens=200,
    messages=[
        {"role": "user", 
         "content": "Write a polite reply accepting an AI Engineer job offer. Only output the reply."}]
)

print(response.choices[0].message.content)
```
### Specifying a DeepSeek model
OpenAI offers multiple models for different use cases. In this exercise, you'll specify the model and define the role to structure your API requests.
* Specify the deepseek-ai/DeepSeek-V3 model.
* Assign the correct role in the messages list.
```python
client = OpenAI(api_key="<TogetherAI API Key>", base_url="https://api.together.xyz/v1")

response = client.chat.completions.create(
    # Specify the model
    model="deepseek-ai/DeepSeek-V3",
    max_tokens=200,
    messages=[
        # Assign the correct role
        {"role": "user", 
         "content": "Write a post to announce my new AI Engineer role on LinkedIn. Only output the post."}]
)

print(response.choices[0].message.content)
```
> <script.py> output:
    **Exciting News! 🚀**  
    
    I’m thrilled to share that I’ve started a new role as an **AI Engineer**!  
    
    This is an incredible opportunity to dive deeper into machine learning, NLP, and cutting-edge AI technologies while working alongside talented teams to build innovative solutions.  
    
    A huge thank you to everyone who has supported me on this journey—mentors, colleagues, and friends—your guidance has been invaluable.  
    
    I’m excited for this next chapter and can’t wait to contribute, learn, and grow in the world of AI. Let’s connect and collaborate!  
    
    #AI #MachineLearning #NewRole #CareerGrowth #ArtificialIntelligence

### Digging into the response
