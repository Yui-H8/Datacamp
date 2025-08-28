# Working with the OpenAI API
---
### Your first OpenAI API request!
* Enter your prompt replacing INSERT YOUR PROMPT HERE, experiment, and submit your answer when ready!
```python
response = client.chat.completions.create(
    model="gpt-4o-mini",
    max_completion_tokens=100,
  
    # Enter your prompt
    messages=[{"role": "user", "content": "INSERT YOUR PROMPT HERE"}]
)

print(response.choices[0].message.content)
```
Question: Why is learning the OpenAI API valuable for developers?    
Answer: Learning the OpenAI API is valuable for developers for several reasons:
1. **Access to Advanced AI Capabilities**: The OpenAI API provides access to powerful models like GPT-3 and GPT-4, which can perform a variety of tasks including natural language understanding, text generation, translation, summarization, and more. These capabilities can enhance applications significantly.
2. **Enhancing User Experience**: By integrating AI, developers can create more interactive and engaging user experiences. Features such as chatbots
      
Q2: Suggest three tasks I could automate with the OpenAI API in my job.    
A: Sure! Here are three tasks you could consider automating with the OpenAI API in your job:
1. **Content Generation**: Automate the creation of marketing materials, social media posts, or blog articles. By providing the API with a brief or specific guidelines, you can generate high-quality written content tailored to your audience or objectives. This can save time and ensure consistency in tone and messaging.
2. **Data Analysis and Reporting**: If your job involves analyzing data and creating reports, you
---
### Building an OpenAI API request
* Create an OpenAI API client (keep <OPENAI_API_TOKEN> unchanged).
* create a request to the Chat Completions endpoint.
```python
# Create the OpenAI client
client = OpenAI(api_key="<OPENAI_API_TOKEN>")

# Create a request to the Chat Completions endpoint
response = client.chat.completions.create(
  model="gpt-4o-mini",
  messages=[
    {"role": "user", 
     "content": "Write a polite reply accepting an AI Engineer job offer."}]
)

print(response.choices[0].message.content)
```
### Specifying an OpenAI model
* Specify the gpt-4o-mini model.
* Assign the correct role in the messages list.
```python
client = OpenAI(api_key="<OPENAI_API_TOKEN>")

response = client.chat.completions.create(
  # Specify the model
  model="gpt-4o-mini",
  messages=[
    # Assign the correct role
    {"role": "user", 
     "content": "Announce my new AI Engineer role on LinkedIn."}]
)

print(response.choices[0].message.content)
```
Answer: Sure! Here’s a suggestion for your LinkedIn announcement:

---

🌟 Exciting News! 🌟

I am thrilled to share that I've joined [Company Name] as an AI Engineer! 🎉

In this new role, I will have the opportunity to work on innovative projects that leverage artificial intelligence to solve complex problems and create impactful solutions. I’m eager to collaborate with a talented team that shares my passion for technology and innovation.

I want to extend my gratitude to everyone who has supported me on my journey. Your encouragement and guidance have been invaluable!

Here’s to new beginnings and the exciting challenges ahead! 🚀

#NewRole #AI #ArtificialIntelligence #CareerUpdate #Excited

---

Feel free to customize it to match your personality and any specific details you want to include!


### Digging into the response
* Extract the content from the response, which is nested inside the message attribute.
```Python
client = OpenAI(api_key="<OPENAI_API_TOKEN>")

response = client.chat.completions.create(
  model="gpt-4o-mini",
  messages=[{"role": "user", "content": "Quick productivity tip."}]
)

# Extract the content from the response
print(response.choices[0].message.content)
```
---
## 2. Summarizing and editing text
---
### Find and replace
* Create a request to the Chat Completions endpoint; use a maximum of 100 tokens.
* Extract and print the text response from the API.
```python
cclient = OpenAI(api_key="<OPENAI_API_TOKEN>")

prompt="""Replace car with plane and adjust phrase:
A car is a vehicle that is typically powered by an internal combustion engine or an electric motor. It has four wheels, and is designed to carry passengers and/or cargo on roads or highways. Cars have become a ubiquitous part of modern society, and are used for a wide variety of purposes, such as commuting, travel, and transportation of goods. Cars are often associated with freedom, independence, and mobility."""

# Create a request to the Chat Completions endpoint
response = client.chat.completions.create(
  model="gpt-4o-mini",
  messages=[{"role": "user", "content": prompt}],
  max_completion_tokens=100
)

# Extract and print the response text
print(response.choices[0].message.content)
```
Answer: A plane is a vehicle that is typically powered by jet engines or propellers. It has wings and is designed to carry passengers and/or cargo through the air. Planes have become a ubiquitous part of modern society, and are used for a wide variety of purposes, such as commuting, travel, and transportation of goods over long distances. Planes are often associated with freedom, adventure, and the ability to connect people across the globe.
### Text summarization
* Use an f-string to insert finance_text into prompt.
* Create a request, sending the prompt provided; use a maximum of 400 tokens.
```python
client = OpenAI(api_key="<OPENAI_API_TOKEN>")

# Use an f-string to format the prompt
prompt = f"""Summarize the following text into two concise bullet points:
{finance_text}"""

# Create a request to the Chat Completions endpoint
response = client.chat.completions.create(
  model="gpt-4o-mini",
  messages=[{"role": "user", "content": prompt}],
  max_completion_tokens=400
)

print(response.choices[0].message.content)
```
