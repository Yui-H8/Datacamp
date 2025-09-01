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
