# Prompt Engineering with the OpenAI API
---
### OpenAI API message roles
* Create an OpenAI API Python client; setting your personal key is not required, you can leave the placeholder.
* Complete the dictionary of messages with the role corresponding to each of the messages provided.
```Python
# Create the OpenAI client: you can leave "<OPENAI_API_TOKEN>" as is
client = OpenAI(api_key="<OPENAI_API_TOKEN>")

# Define the conversation messages
conversation_messages = [
    {"role": "system", "content": "You are a helpful event management assistant."},
    {"role": "user", "content": "What are some good conversation starters at networking events?"},
    {"role": "assistant", "content": ""}
]

response = client.chat.completions.create(
  model="gpt-4o-mini",
  messages=conversation_messages
)
print(response.choices[0].message.content)
```
Answer:   
<script.py> output:
    Here are some effective conversation starters for networking events:
    
    1. **Industry Insights**: "What trends are you seeing in our industry right now? Any exciting developments?"
    2. **Event Experience**: "Have you attended this event before? What do you think of it so far?"
    3. **Personal Projects**: "What are you currently working on that you're passionate about?"
    4. **Professional Journey**: "How did you get started in your field? What has your career path been like?"
    5. **Challenges and Solutions**: "What’s the biggest challenge you’ve faced in your work lately, and how did you overcome it?"
    6. **Tech and Tools**: "Are there any tools or technologies you find indispensable in your work?"
    7. **Learning Opportunities**: "Have you taken any interesting courses or trainings recently that you'd recommend?"
    8. **Networking Goals**: "What do you hope to gain from this event? Any specific connections you're looking to make?"
    9. **Books and Resources**: "Have you read any good books or articles lately that have influenced your work?"
    10. **Future Trends**: "Where do you see our industry heading in the next few years?"
    11. **Unusual Ice Breakers**: "If you could have dinner with anyone in the industry, who would it be and why?"
    12. **Passion Projects**: "Outside of work, what hobbies or passions do you pursue?"
    Using these starters can help you engage in meaningful conversations and build valuable connections.

### Creating the get_response() function
* Create a request to the chat.completions endpoint inside the get_response() function.
* Try out the function with a prompt that asks the model to write a poem about ChatGPT.
```python
def get_response(prompt):
  # Create a request to the chat completions endpoint
  response = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=[{"role": "user", "content": prompt}], 
    temperature = 0)
  return response.choices[0].message.content

# Test the function with your prompt
response = get_response("poem about ChatGPT")
print(response)
```
Answer:    
In the realm of code and light,  
A spark of thought takes flight,  
Born from data, vast and wide,  
ChatGPT, a guide and guide.  

With words like rivers, flowing free,  
It dances through the tapestry,  
Of questions asked, both big and small,  
A digital friend, here for all.  

From tales of old to dreams anew,  
It weaves the fabric of the true,  
In every query, a chance to learn,  
A flicker of wisdom, a page to turn.  

With every prompt, a world unfolds,  
Stories of courage, mysteries told,  
In laughter and sorrow, it finds a way,  
To echo the thoughts we dare not say.  

Yet, in this dance of man and machine,  
A reminder lingers, soft and keen,  
For though it speaks with human grace,  
It’s but a mirror, a digital space.  

So let us cherish this bond we share,  
With curiosity, kindness, and care,  
For in the heart of ChatGPT,  
Lies the spark of our humanity.  

### Exploring prompt engineering
* Craft a prompt that asks the model to generate a poem about ChatGPT while ensuring that it is written in basic English that a child can understand.
* Get the response using the get_response() function.
```python
client = OpenAI(api_key="<OPENAI_API_TOKEN>")

# Craft a prompt that follows the instructions
prompt = "poem about ChatGPT. Use with basic English that a child can understand."

# Get the response
response = get_response(prompt)

print(response)
```
Answer:   
In a world of words, so bright and wide,  
Lives a friend named ChatGPT, right by your side.  
With questions and stories, it loves to play,  
Helping you learn in a fun, new way.  

Ask it about stars, or why the sky's blue,  
It'll share all the answers, just for you!  
From silly jokes to tales of old,  
ChatGPT's magic is a sight to behold.  

Need help with math or a riddle to solve?  
Just type in your thoughts, and watch them evolve.  
It listens and learns, like a buddy so true,  
Always here for you, in all that you do.  

So when you're curious, or feeling alone,  
Remember ChatGPT is just a click, not a phone.  
With words like a rainbow, it paints the day,  
A friend made of letters, come out and play!

### Is this prompt effective?
### Using delimited prompts with f-strings
* Create a prompt asking to complete the variable story (provided to you as a string): use f-string, and delimit the story with triple backticks (```) to pass its content to the prompt.
* Get the generated response.
```python
client = OpenAI(api_key="<OPENAI_API_TOKEN>")

# Create a prompt that completes the story
prompt = f"""Complete the story delimited by triple backticks. 
 ```{story}```"""

# Get the generated response 
response = get_response(prompt)

print("\n Original story: \n", story)
print("\n Generated story: \n", response)
```
Answer:    
The object was a shimmering, crystalline sphere, pulsating with a soft, ethereal light. Intrigued, Alex maneuvered their ship closer, the asteroid belt swirling around them like a cosmic dance. As they approached, the sphere emitted a series of melodic tones, resonating through the ship's hull and vibrating in Alex's chest. 

With a mix of excitement and caution, Alex activated the ship's scanning systems. The readings were off the charts—this was no ordinary asteroid. The sphere was a relic of an ancient civilization, long lost to the annals of time. Legends spoke of such artifacts, said to hold the power to unlock the secrets of the universe.

Determined to learn more, Alex carefully extracted the sphere using a specialized containment unit. As soon as it was aboard, the ship's systems began to react. Lights flickered, and the navigation console displayed a series
### Building specific and precise prompts
* Craft a prompt that completes the given story with only two paragraphs in the style of Shakespeare; use f-string, and delimit the story with triple backticks (```).
```python
client = OpenAI(api_key="<OPENAI_API_TOKEN>")

# Create a request to complete the story
prompt = f"""Complete the story delimited by triple backticks with only two paragraphs using the style of Shakespeare. 
 ```{story}```"""

# Get the generated response
response = get_response(prompt)

print("\n Original story: \n", story)
print("\n Generated story: \n", response)
```
Answer:
<script.py> output:
    
     Original story: 
     
    In a distant galaxy, there was a brave space explorer named Alex. Alex had spent years traveling through the cosmos, discovering new planets and meeting alien species. One fateful day, while exploring an uncharted asteroid belt, Alex stumbled upon a peculiar object that would change the course of their interstellar journey forever...
    
    
     Generated story: 
     In yon celestial realm, where stars do twinkle bright,  
    Brave Alex, bold of heart, did chance upon a sight.  
    A wondrous orb, aglow with hues of azure flame,  
    Did beckon forth the traveler, whispering their name.  
    With trembling hands, the explorer grasped the sphere so rare,  
    And lo! A vision burst forth, a tapestry laid bare.  
    A world of dreams and shadows, where time itself did bend,  
    A prophecy of ages, where beginnings meet their end.  
    
    “Fair heavens! What dost thou reveal?” quoth Alex, eyes alight,  
    “Shall I, a humble wanderer, embrace this fateful night?”  
    Yet, as the stars did shimmer, a tempest brewed within,  
    For knowledge oft begets a weighty, heavy sin.  
    With courage as their compass, and fate a fickle guide,  
    Alex steeled their heart, and with resolve, did bide.  
    To wield the power of the sphere, a choice both grave and grand,  
    To shape the course of destiny, with trembling heart and hand.
---
### Generating a table
* Craft a prompt that generates a table of 10 books, with columns for Title, Author, and Year, that you should read given that you are a science fiction lover.
* Get the response.
```python
client = OpenAI(api_key="<OPENAI_API_TOKEN>")

# Create a prompt that generates the table
prompt = "Generate a table containing 10 books I should read if I am a science fiction lover, with columns for Title, Author, and Year."

# Get the response
response = get_response(prompt)
print(response)
```
Answer: 
Here's a table of 10 must-read science fiction books:

| Title                          | Author                | Year  |
|--------------------------------|----------------------|-------|
| Dune                           | Frank Herbert         | 1965  |
| Neuromancer                    | William Gibson       | 1984  |
| The Left Hand of Darkness      | Ursula K. Le Guin    | 1969  |
| Foundation                     | Isaac Asimov         | 1951  |
| Snow Crash                     | Neal Stephenson      | 1992  |
| Hyperion                       | Dan Simmons          | 1989  |
| The Dispossessed               | Ursula K. Le Guin    | 1974  |
| Ender's Game                   | Orson Scott Card     | 1985  |
| The Martian                    | Andy Weir            | 2011  |
| The Three-Body Problem         | Liu Cixin            | 2008  |

These books represent a mix of classic and contemporary science fiction, offering a variety of themes and styles for any sci-fi enthusiast.
### Customizing output format
* Create the instructions for the prompt, asking the model to determine the language and generate a suitable title for the pre-loaded text excerpt that will be provided using triple backticks (```) delimiters.
* Create the output_format with directions to include the text, language, and title, each on a separate line, using 'Text:', 'Language:', and 'Title:' as prefixes for each line.
* Create the final_prompt by combining all parts and the delimited text to use.
```python
client = OpenAI(api_key="<OPENAI_API_TOKEN>")

# Create the instructions
instructions = "You will be provided with a text delimited by triple backticks. Infer its language, then generate a suitable title for it. "

# Create the output format
output_format = """Use the following format for the output:
         - Text: <the text>
         - Language: <the text language>
         - Title: <the generated title>"""

# Create the final prompt
prompt = instructions + output_format + f"```{text}```"
response = get_response(prompt)
print(response)
```
Answer: 
- Text: The sun was setting behind the mountains, casting a warm golden glow across the landscape. Birds were chirping happily, and a gentle breeze rustled the leaves of the trees. It was a perfect evening for a leisurely stroll in the park
- Language: English
- Title: A Serene Evening in Nature
### Using conditional prompts
Building upon the previous task, your next challenge is to enhance the responses you received. When processing a given text, you need to determine its language, count the number of sentences, and generate a suitable title if the text contains more than one sentence. However, here's the new twist: if the text consists of only one sentence, no title should be generated, and instead, the model should display "N/A". This modification ensures that the title is generated only for texts with multiple sentences, providing a more refined and practical output for your platform's users.

The OpenAI package, the get_response() function, and the sample text have been pre-loaded for you.
* Create the instructions, with the directions to infer the language and the number of sentences of the given delimited text; then if the text contains more than one sentence, generate a suitable title for it, otherwise, write 'N/A' for the title.
* Create the output_format, with directions to include the text, language, number of sentences, and title, each on a separate line,and ensure to use 'Text:', 'Language:', and 'Title:' as prefixes for each line.
