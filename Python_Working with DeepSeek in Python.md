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
One key skill in working with APIs is extracting the right data from a structured response. Now, you'll practice retrieving the necessary text from an OpenAI API response.
* Extract the content from the response, which is nested inside the message attribute.
```python
client = OpenAI(api_key="<TogetherAI API Key>", base_url="https://api.together.xyz/v1")

response = client.chat.completions.create(
  model="deepseek-ai/DeepSeek-V3",
  messages=[{"role": "user", "content": "Quick, one-sentence productivity tip."}]
)

# Extract the content from the response
print(response.choices[0].message.content)
```
*Asswer*    
<script.py> output:
    "Prioritize your top three tasks each morning and tackle them first to maintain focus and momentum."
### Reasoning models and DeepSeek R1



---
### Getting models to think
 Time to make the switch from chat models to reasoning models! These are great for deeper reasoning tasks like data analysis, code debugging, math, or research.

In this exercise, you'll use reasoning models to solve a typical math problem that might be presented to high-school math students.
> math_problem    
Calculate the area of a house in m^2 comprised of two rooms of sizes 3mx2m and 4mx5m.
* Create a request to send the math_problem prompt to the "deepseek-ai/DeepSeek-R1" model via the Chat Completions endpoint.
```python
client = OpenAI(api_key="<TogetherAI API Key>", base_url="https://api.together.xyz/v1")

# Create a request to the chat model
response = client.chat.completions.create(
    model="deepseek-ai/DeepSeek-R1",
    max_tokens=400,
    messages=[
        {"role": "user", 
         "content": math_problem}],
  stream=False
)

print(response.choices[0].message.content)
```
*Answer*   
```python
> <script.py> <think>
<think>
I need to calculate the area of a house that has two rooms. One room is 3 meters by 2 meters, and the other is 4 meters by 5 meters. I need to find the total area in square meters.

First, I should recall that the area of a rectangle is found by multiplying the length by the width. So for each room, I'll do that and then add them together.

Starting with the first room: 3m by 2m. So, area = length × width = 3 × 2.

3 times 2 is 6. So, that room is 6 square meters.

Now, the second room: 4m by 5m. Area = 4 × 5 = 20 square meters.

To find the total area of the house, I add the areas of both rooms: 6 + 20.

6 + 20 is 26. So, the total area should be 26 square meters.

I should make sure that the units are consistent. Both are in meters, and I'm multiplying meters by meters to get square meters, so that seems correct.

Also, the problem says "comprised of two rooms," so I think adding them is straightforward. There's no indication of any overlap or anything, so I don't need to subtract anything.

Let me double-check the dimensions: 3x2 and 4x5. Yep, 3 times 2 is 6, 4 times 5 is 20, 6 plus 20 is 26.

I can think of it as total area = (3*2) + (4*5) = 6 + 20 = 26 m².

The problem says "a house" but it's just two rooms, so I think that's all.

I should write it properly.

So, area of first room: 3 m × 2 m = 6 m²
```
*The response from the model was likely cut-off, as the model generates lots of thoughts along the way which go beyond the limit we set with max_tokens=400 (more on this in Chapter 2). How about we take a closer look at those thoughts?*
