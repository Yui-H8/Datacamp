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
### Calculating the cost
* Extract the input token usage from the response.
* Complete the cost calculation to add the output token cost.
```python
client = OpenAI(api_key="<OPENAI_API_TOKEN>")

response = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=[{"role": "user", "content": prompt}],
    max_completion_tokens=max_completion_tokens
)

input_token_price = 0.15 / 1_000_000
output_token_price = 0.6 / 1_000_000

# Extract token usage
input_tokens = response.usage.prompt_tokens
output_tokens = max_completion_tokens
# Calculate cost
cost = (input_tokens * input_token_price + output_tokens * output_token_price)
print(f"Estimated cost: ${cost}")
```
---
### Content generation
* Create a request to create a slogan for a new restaurant; set the maximum number of tokens to 100.
```python
client = OpenAI(api_key="<OPENAI_API_TOKEN>")

# Create a request to the Chat Completions endpoint
response = client.chat.completions.create(
  model="gpt-4o-mini",
  messages=[{"role": "user", "content": "Create a request to create a slogan for a new restaurant"}],
  max_completion_tokens=100
)

print(response.choices[0].message.content)
```
Answer: <script.py> output:
    **Subject: Request for Slogan Ideas for Our New Restaurant**
    
    Dear [Creative Team/Marketing Specialist],
    
    I hope this message finds you well! We are in the exciting process of launching our new restaurant, [Restaurant Name], and we would love your expertise in crafting a memorable slogan that captures our essence.
    
    Our restaurant will feature [brief description of the cuisine/style, e.g., "authentic Italian dishes made with locally sourced ingredients"] and aims to create an inviting atmosphere where guests feel at home.
### Generating a product description
* Create a detailed prompt to generate a product description for SonicPro headphones, including:
- Active noise cancellation (ANC)
- 40-hour battery life
- Foldable design
* Experiment with max_completion_tokens and temperature settings to see how they affect the output.
```python
client = OpenAI(api_key="<OPENAI_API_TOKEN>")

# Create a detailed prompt
prompt = """
"Write a compelling and detailed product description for the SonicPro headphones, emphasizing the following features:

Active Noise Cancellation (ANC): Describe the advanced noise-canceling technology, highlighting how it creates an immersive audio experience by blocking out external distractions.

40-hour Battery Life: Explain the impressive battery performance, focusing on how the headphones allow for long-lasting usage without frequent charging, perfect for travel or extended listening sessions.

Foldable Design: Highlight the foldable nature of the headphones, making them compact and easy to store, ideal for on-the-go use and saving space when not in use.

Include a balance of technical details and customer-friendly language that would appeal to both tech enthusiasts and casual listeners."
"""

response = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=[{"role": "user", "content": prompt}],
    # Experiment with max_completion_tokens and temperature settings
    max_completion_tokens=100,
    temperature=1
)
print(response.choices[0].message.content)
```
* temperature=1(0=Deterministic, 2=Random)
    
Answer: 
#### **SonicPro Headphones: Elevate Your Audio Experience**

Discover a new world of sound with the SonicPro Headphones, the perfect fusion of cutting-edge technology and user-friendly design. Whether you're a dedicated audiophile or just someone who appreciates quality sound, the SonicPro headphones are designed to deliver an unmatched listening experience.

#### **Active Noise Cancellation (ANC)**     
Immerse yourself fully in your favorite melodies, podcasts, or audiobooks with our advanced Active Noise Cancellation technology. The SonicPro headphones

---
Shot prompting : AIに例を提示して精度を上げること、モデルの応答を導くためにプロンプトに例を含めること　　　
1. Zero-shot 指示のみ
2. One-shot 応答を導くための単一の例
3. Few-shot 複数の例＝テキストを定義済みに分類するのに役立つ
### Zero-shot prompting with reviews
* Define a prompt to classify the sentiment of the statements provided using the numbers 1 to 5 (positive to negative).
* Create a request to the Chat Completions endpoint to send this prompt to gpt-4o-mini.
```python
client = OpenAI(api_key="<OPENAI_API_TOKEN>")

# Define a multi-line prompt to classify sentiment
prompt = """____:
1. Unbelievably good!
2. Shoes fell apart on the second use.
3. The shoes look nice, but they aren't very comfortable.
4. Can't wait to show them off!"""

# Create a request to the Chat Completions endpoint
response = client.chat.completions.create(
  model="gpt-4o-mini",
  messages=[{"role": "user", "content": prompt}],
  max_completion_tokens=100
)

print(response.choices[0].message.content)
```
Answer: It looks like you're categorizing reviews for a product, likely shoes. Here’s an organized representation of the feedback based on the sentiment of each point:

**Positive Reviews:**
1. Unbelievably good!
4. Can't wait to show them off!

**Negative Reviews:**
2. Shoes fell apart on the second use.
3. The shoes look nice, but they aren't very comfortable.

Feel free to let me know if you need any further analysis or assistance!

<script.py> output:
    It seems like you're looking for a conclusion or summary for a set of reviews. Here’s a suggestion:
    
    ---
    
    **Overall Impression of the Shoes:**
    
    The reviews reflect a mixed experience with the shoes. Some users are thrilled with their aesthetics and quality, describing them as "unbelievably good" and expressing excitement to showcase them. However, others have faced significant issues, noting that the shoes fell apart after minimal use and that they compromise on comfort. Potential buyers should weigh the stylish design against the durability

### One-shot prompting: will it be enough?
* Add the example Love these! = 5 to the start of the prompt, and add = after each review in the prompt to indicate how the result should be formatted.
```python
client = OpenAI(api_key="<OPENAI_API_TOKEN>")

# Add the example to the prompt
prompt = """Classify sentiment as 1-5 (negative to positive):
1. Love these! = 5
2. Unbelievably good! ____
3. Shoes fell apart on the second use. ____
4. The shoes look nice, but they aren't very comfortable. ____
5. Can't wait to show them off! ____"""

response = client.chat.completions.create(model="gpt-4o-mini", messages=[{"role": "user", "content": prompt}], max_completion_tokens=100)
print(response.choices[0].message.content)
```
Answer: Here are the sentiment classifications:

1. Love these! = 5
2. Unbelievably good! = 5
3. Shoes fell apart on the second use. = 1
4. The shoes look nice, but they aren't very comfortable. = 2
5. Can't wait to show them off! = 5
### Few-shot prompting: all the examples!
* Add the Comfortable, but not very pretty = 2 example to the prompt and re-run the request.
```python
client = OpenAI(api_key="<OPENAI_API_TOKEN>")

# Add the final example
prompt = """Classify sentiment as 1-5 (negative to positive):
1. Comfortable, but not very pretty = 2
2. Love these! = 5
3. Unbelievably good! = 
4. Shoes fell apart on the second use. = 
5. The shoes look nice, but they aren't very comfortable. = 
6. Can't wait to show them off! = """

response = client.chat.completions.create(model="gpt-4o-mini", messages=[{"role": "user", "content": prompt}], max_completion_tokens=100)
print(response.choices[0].message.content)
```
Answer: Here are the sentiment classifications:

3. Unbelievably good! = 5
4. Shoes fell apart on the second use. = 1
5. The shoes look nice, but they aren't very comfortable. = 3
6. Can't wait to show them off! = 5
