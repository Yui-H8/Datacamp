# AI for Consulting
---
**Description**

Discover for AI is augmenting consultancy roles to allow you to deliver results faster and more effectively! In this course, you'll learn how to augment and automate some of the core tasks in the consultancy workflow: from research and analysis to client delivery. Learn to leverage AI to synthesize information across various sources like documents and images, extract insights by performing calculations and generating summary plots, and build engaging visualizations for the stakeholders that you'll be presenting to. Along the way, you'll learn how to mitigate the risks of using AI for consultancy, such as hallucinations in citations and key information. Supercharge your consultancy workflows today!

---
### Your First Copilot Conversation
You've just joined the consulting team at Meridian Advisory, a boutique management consultancy that helps organizations improve performance and drive digital transformation.

As part of your onboarding, your manager has asked you to explore how generative AI tools, such as Microsoft Copilot, could enhance the firm's consulting workflows and client outcomes.

Your task is to identify practical ways generative AI might support research, analysis, and client delivery. Your findings will form the foundation of a short presentation you'll deliver to your team later this week.

1. Welcome to Microsoft Copilot
   * You've been automatically logged into your own Copilot account!
   * Make sure to close any undesirable pop-ups to avoid distraction.
   * The page should load showing a blank chat window.
   * Navigate to the next steps to get started.
2. Write a simple prompt to Copilot, asking for a list of five use-cases for generative AI in consultancy.
      
*Nice work! You successfully prompted Copilot to explore AI use cases in consultancy. This first interaction helps you see how Copilot can brainstorm practical applications. You’ll explore some more as you move through the course!*

### GSCE: The Prompting Formula That Works
After exploring AI use-cases, your manager is impressed with your initiative. She now wants to see you apply what you've learned.

A retail client is considering expanding into the European market and needs a quick competitive landscape analysis. Your manager emphasizes that getting good results from AI starts with structured prompting.

Using the GSCE framework (Goal, Style, Context, Examples), craft a prompt that will help you analyze the competitive landscape for your client's European expansion. For this exercise, focus on Goal, Style, and Context—Examples are not required.

1. Craft a prompt that will help you analyze the competitive landscape for your client's European expansion:
   * Start a new Copilot Chat to clear any previous conversation.
   * In the prompt box, begin writing your prompt by stating the Goal—what specific output you want from Copilot. Don't send the prompt just yet!
2. Add Style guidance to your prompt—specify the tone, structure, or format you want. For example, a neutral analytical tone and formatting using Porter's Five Forces framework with bullet points for each competitor.
3. Add Context to your prompt—include relevant background information such as client industry, target market, and any constraints. Do not send the prompt yet.
4. Review your complete GSCE prompt to ensure it includes Goal, Style, and Context. Send it to Copilot and observe how the structured prompt influences the output quality.
> Goal: Analyze a retail competitive landscape in European market for my client. / Style: a neutral analytical and formatting using Porter's Five Forces framework with bullet points for each competitor. / Context: client industry is retail, they want to expand into Euro.

*Well done! You've successfully applied the GSCE framework to craft a structured prompt. Notice how including Goal, Style, and Context helps Copilot deliver more relevant and actionable insights. This approach will serve you well throughout your consulting projects!*

### Turn Multiple Sources Into One Story
You're advising a US-based EV-charging company considering market entry into Germany. Before your client's leadership meeting tomorrow, you need to synthesize findings from three different sources into a single comparison table and flag any inconsistencies. The sources include a Trade.gov market intelligence article, an academic paper on EV subsidies, and a government infographic on charging infrastructure.

Your task is to create a comparison table that compares these sources across four key topics (Market Size, Policy Instruments, Charging Infrastructure, and Consumer Behavior) to check for any contradictions or data inconsistencies.

1. Start a new chat for the new task, and upload files using the + button.
   * Provide Copilot with the three research sources, which you can upload from Desktop > Resources:
   * The Trade.gov market intelligence german_ev_infrastructure.pdf (Original Source)
   * The academic paper public_purchasing_subsidies.pdf (Original Source)
   * The government infographic german_electric_mobility.pdf (Original Source)
     
Note: You can use Ctrl + Left-Click to select multiple files at once inside the VM's file explorer window.

2. Prompt Copilot to create a comparison table with rows for Market Size, Policy Instruments, Charging Infrastructure, and Consumer Behavior, with one column per source (Website, Paper, Infographic).
3. In a second prompt, ask Copilot to check the table for any contradictions or inconsistencies across the sources, considering that they come from different years.

```
Incorrect
Almost there, but missing a key step! You attached all three files and requested a structured comparison table with the correct row and column setup. However, you did NOT ask Copilot to check for contradictions, inconsistencies, or discrepancies across the sources. Always request a consistency check to ensure data reliability.
```
*You did it! You've used Copilot to synthesize information from multiple sources into a structured comparison table and validated the data for consistency. This approach saves hours of manual research and helps ensure accuracy in your client deliverables.*

### When Data Comes in Pictures
You're continuing your research on the German EV market for your US-based client.

You've noticed that one of the research sources you're working with is an infographic.jpg stored as an image (Original Source). Yesterday, a colleague mentioned that when we ask a model to process visual content, we are using not only its natural language capabilities but also its visual capabilities.

This makes you wonder whether which method is more reliable: uploading an image file or using a link to the image.
1. Start a new Copilot Chat to clear any previous conversation.
   * Prompt Copilot to transcribe the text in the infographic by providing the website link: https://energiewende.bundeswirtschaftsministerium.de/EWD/Redaktion/EN/Newsletter/2021/08/Meldung/direkt-answers-infographic.html
2. Now, upload the infographic.jpg file from the Resources folder on your Desktop and prompt Copilot to transcribe the text from the image.
   * Compare this output to the previous response.
3. Which response best reflects the model's behavior when extracting information from visual content?

*Which response best reflects the model's behavior when extracting information from visual content?*

---
### SCR and Pyramid: Structure Your Story
You're advising ShopSphere, a retail technology company planning to launch an AI-powered shopping platform. Your manager has compiled an Excel file (ai_shopping_platform.xlsx) that aggregates market size, consumer behavior, competitive landscape, and regulatory data.

She has asked you to create a research narrative that organizes this information using the SCR framework (Situation, Complication, Resolution). This structured approach will help the leadership team quickly understand the market opportunity and key challenges.
1. Start a new Copilot Chat to clear any previous conversation.
   * Upload the ai_shopping_platform.xlsx file from the Resources folder on your Desktop
2. Prompt Copilot to generate a research narrative using the SCR framework.
   * Your prompt should ask for a narrative structured as Situation, Complication, and Resolution, and specify that it must rely solely on the data in the uploaded Excel file.

*Prompt Copilot to generate a research narrative using the SCR framework.
Your prompt should ask for a narrative structured as Situation, Complication, and Resolution, and specify that it must rely solely on the data in the uploaded Excel file.*

### Is This Narrative Ready?
You're reviewing an AI-generated research narrative that a colleague created using Microsoft Copilot. The narrative was supposed to follow the Pyramid Principle—starting with a clear top-line message supported by MECE (Mutually Exclusive, Collectively Exhaustive) points.

Here's what Copilot produced:

"The European EV charging market presents interesting dynamics. Infrastructure is growing rapidly, with Germany leading installations. France is also expanding its network significantly. Consumer adoption varies by region, influenced by government incentives. Germany offers substantial purchase subsidies. The regulatory environment continues to evolve across all markets. Infrastructure growth in Western Europe has been particularly strong. Electric vehicle sales are increasing year over year."

Your manager asks you to review this narrative before it goes to the client. You recall the quality checks from your training: question AI output if the narrative feels unclear, if the tone is off, if it doesn't match the framework, or if key insights are missing.

Which of the following issues are present in this AI-generated narrative?
```
〇 Missing a clear top-line message that summarizes the key insight
〇 Supporting points overlap and are not MECE
The tone is too informal for client delivery
〇 The narrative lacks a logical flow and feels like a list of disconnected facts
The content contains factually incorrect information
```
> At least one answer is incorrect: The points about "Infrastructure is growing rapidly" and "Infrastructure growth in Western Europe has been particularly strong" overlap. MECE requires each point to be distinct without repetition.
> Correct! The narrative jumps straight into details without stating the main conclusion upfront. A proper Pyramid structure requires a clear top-line message like "Germany is the most attractive market for EV charging expansion" before supporting points.

*Spot on! You correctly identified that this narrative lacks a clear top-line message, has overlapping (non-MECE) points, and reads as disconnected facts rather than a structured story. These are exactly the issues to watch for when reviewing AI-generated content before client delivery.*
