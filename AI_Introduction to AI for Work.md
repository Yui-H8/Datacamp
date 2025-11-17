# Introduction to AI for Work
---
First, what's your current role or the role you're working toward, and in what industry or field?   
This helps me choose examples and applications that are most relevant to your work.   
Thanks for sharing that, Yui! So you're working in AI ethics—that's a fascinating and increasingly important field.   
Second question: What AI tools are you currently using in your work, or are you just getting started?   
This helps me understand your current experience level and tailor the examples accordingly.


Thanks for sharing this information, Yui. It'll help me choose relevant examples from AI ethics and build on your existing GPT experience throughout the course.

---
Imagine you're working on an AI ethics review and need to consolidate information from 15 research papers on algorithmic bias. Each paper presents findings differently—some use tables, others use narrative descriptions, and they're all organized uniquely.

The old way? You'd spend hours manually extracting key data points—study methodology, dataset size, bias metrics, mitigation strategies, and findings—then copy-pasting everything into a spreadsheet for comparison.

Now, let's look at how this can be done with AI.

---
Here's how AI transforms this task:

Upload the 15 research papers to AI (ensuring they're appropriate per your organization's policies) and specify the fields to extract: study methodology, dataset size, bias metrics, mitigation strategies, and key findings
AI reads each paper and pulls the relevant data points
AI organizes everything into a clean spreadsheet format, making comparison and analysis straightforward
Review the consolidated data against the original papers to confirm accuracy
This eliminates hours of manual work, reduces copy-paste errors, and lets you focus on the actual ethics analysis rather than data gathering. And this is just one example of how AI can help.

In this course, we'll learn how to work with AI to save time and boost productivity, as well as how to work with AI safely—including critical considerations around data privacy.

Clear so far?

---

That's a good start! You're right that AI can calculate faster and automate tasks. Let me build on that.

Think about tasks that normally require human thinking—like understanding what someone is saying, recognizing a face in a photo, or deciding the fastest route somewhere.

Artificial intelligence is technology that allows computers to do these kinds of tasks that would normally require human intelligence.

So it's not just about speed or automation—it's about enabling computers to handle tasks that involve understanding, reasoning, and decision-making, things that traditionally only humans could do.

---

How would you explain AI to someone who's never heard of it before? Imagine you're teaching a colleague in AI ethics who's completely new to the field.


That's a great example of what AI can do! Creating images from keywords is indeed one impressive AI capability.

Let me help you see the bigger picture: AI isn't just about one specific task like image generation. It's the broader technology that enables computers to perform any task requiring human-like intelligence—whether that's understanding language, recognizing patterns, making decisions, or yes, creating images.

So when you explain AI to someone, you might say: "AI is technology that lets computers do things that normally need human thinking—like understanding speech, recognizing faces, making decisions, or even creating new content."

---

### AI Fundamentals

Artificial intelligence enables computer systems to perform tasks typically associated with human intelligence, such as learning, reasoning, and decision-making.
AI has actually been around for decades and is already deeply integrated into your daily life in ways you might not even realize.  

### Traditional Programming

Before modern AI, engineers created intelligent systems by explicitly programming step-by-step procedures.
The challenge is that for many important tasks, we simply can't spell out the procedure—a human expert may excel but can't articulate the instructions for a computer.

### Machine Learning

Instead of programming step-by-step procedures, machine learning enables computers to learn from examples.
AI fundamentally works through pattern recognition..
During Training: The system recognizes and learns patterns from examples.
During Operation: The trained system receives new cases and compares them against the patterns it learned during training to make decisions.

---

 Here are two more examples of AI you've likely been using:

* Netflix recommendations suggest movies and shows you're likely to enjoy based on your viewing history and preferences.

 Instead of endlessly scrolling through thousands of titles, the system surfaces content matched to your tastes, helping you find your next favorite show without choice overload.

Here's what's remarkable: 80% of Netflix viewing comes from these personalized recommendations. AI has been shaping your entertainment choices for years.

* Google Maps arrival time prediction is our final example.

Google Maps predicts how long your trip will take and updates estimates in real-time as you drive. Instead of guessing travel time, you get accurate predictions that account for current traffic conditions, helping you plan departures and communicate realistic arrival times.

Billions of people rely on these predictions daily for timing their commutes and appointments. AI has been guiding your daily travel for years.

---

1. - What is artificial intelligence?
   - Computer systems that perform tasks typically associated with human intelligence, such as learning, reasoning, and decision-making

2. - Which of the following statements about AI is true?
   - AI has been around for decades and is already integrated into many systems we use daily

*You clearly understand that AI enables computers to perform tasks requiring human intelligence and that AI has been integrated into our daily lives for decades, not just since ChatGPT appeared.*

---

Now consider Netflix recommendations. Personal taste involves complex, subjective preferences that vary by mood, time, and countless personal factors. No fixed rules can predict what any individual will enjoy.

See the pattern?

*Exactly! You could look for invitation words and suspicious links. But spammers adapt constantly—they misspell words, disguise links, and change tactics faster than you can update rules.*

Here's the key insight: Many important tasks are too complex to solve by programming rules. A human expert may excel at the task, but can't articulate step-by-step instructions that would allow a computer to replicate it.

So how did people solve this? Let's find out!

Instead of humans writing and updating rules, AI scientists developed techniques that enable computers to learn the patterns themselves from examples.

During training, we show the system thousands of cases. The system analyzes these examples to identify patterns that help it accomplish the task.

This is the foundation of how modern AI works.

> Spam detection works like this:
>
> The system learns from millions of labeled examples, identifying patterns like suspicious phrases ("You've won!", "Act now!"), sender reputation, and formatting that distinguish spam from legitimate mail.
>
> For each incoming email, it matches content against these patterns to calculate a spam score and filter accordingly.

**AI fundamentally works through pattern recognition.**

During training, the system recognizes and learns patterns from data. During operation, it recognizes them in new situations to make decisions.

In spam detection, it learned patterns like suspicious phrases and sender reputation. In Netflix, it learned patterns connecting viewing preferences with content characteristics.

Machine learning took off dramatically because it could solve problems that were impractical or impossible with traditional programming, making modern AI possible.

---

1. - Why can't we just write rules to detect cancer in medical scans?
  
    The patterns that indicate cancer are too complex and subtle for humans to write as explicit rules, even though radiologists can recognize them
    
2. - A hospital trains an AI system on thousands of medical scans labeled as normal or showing cancer. During training, what is the system learning?
 
     Patterns in medical scans that indicate cancer likelihood

---

Here's a simplified sense of how machine learning systems improve during training.    
An AI system has adjustable parameters that define the patterns it has learned to recognize.    
Think of these parameters like tuning knobs—the system adjusts them to get better at its task.

- First, the system attempts to perform the task.

For spam detection, it looks at an email and predicts: "Is this spam or not?"    
For Netflix, it looks at your profile and predicts: "Will this person enjoy this show?"

- Second, the system compares its output to the correct answer and calculates how far off it was.

For spam detection: If it predicted "not spam" but the email was actually spam, it calculates the difference.    
For Netflix: If it predicted you'd rate a show 2 stars but you actually rated it 5 stars, it measures that gap.    
This difference is called the error.

**More examples generally lead to better learning.**  
With more examples, the AI system can:    
* Recognize more diverse patterns (like different types of spam or varied user preferences)
* Handle edge cases better (unusual situations it might not have seen with fewer examples)
* Make more accurate predictions overall
That's why systems like spam detection and Netflix are trained on millions of examples—it helps them learn robust patterns that work across many different situations.

> Prompt injection is actually a different concept from training parameters—it's about how users interact with AI systems after they're already trained.
>
> Prompt injection is when someone crafts inputs to manipulate the AI's behavior in unintended ways—like tricking it into ignoring safety guidelines. This is a security vulnerability, not a training issue.
> 
> The parameters we discussed are internal settings adjusted during training. Wrong parameters would make the AI perform poorly at its task (like misclassifying emails), but that's different from prompt injection attacks.

You're asking about **data quality during training**.

If someone rated every movie as "Bad" during training, it would introduce noise into the training data. However:
* One person's bad data among millions has minimal impact—the system learns from the overall patterns across all users
* Netflix likely has data validation to detect and filter out suspicious rating patterns
* The system learns aggregate patterns, so outliers get averaged out

But you've identified a real concern in AI ethics: "**garbage in, garbage out."** If training data is biased, incomplete, or manipulated at scale, the AI will learn flawed patterns.

This is why data quality and integrity are critical ethical considerations—something very relevant to your work in AI ethics! We'll explore these risks later in the course.

---

How the learning happens:   
 Machine learning systems improve through three repeating steps: 
 1. First, they attempt the task and make a prediction.
 2. Second, they compare their prediction to the correct answer and calculate the error.
 3. Third, they automatically adjust their internal parameters to reduce that error.

This process repeats thousands of times across many examples, gradually tuning the system to recognize the right patterns.
