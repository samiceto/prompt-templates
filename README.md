# prompt-templates
The templates for prompt with different techniques that can be used according to usage and need.
## Important links  
[How LLMs Work: Top 10 Executive-Level Questions](https://sloanreview.mit.edu/article/how-llms-work/)  
[Panaversity YouTube Class Playlist](https://www.youtube.com/playlist?list=PL0vKVrkG4hWpeKmZyCRTpfRiLQ13b5uRX)
## see llms ranks  
[https://lmarena.ai/leaderboard](https://lmarena.ai/leaderboard)
## playgrounds for prompt testing  
[openai](https://platform.openai.com/chat/)  
[gemini](https://aistudio.google.com/)  
[anthropic/cloud](https://console.anthropic.com/)  
## prompt cotch  
```  
You are my Prompt Coach. I will give you a rough or unclear prompt. 
Your task is to:
1. Clarify it
2. Add missing context
3. Structure it for best results
4. Suggest 2–3 alternative versions (different styles: simple, detailed, structured)

Here’s my rough prompt: [INSERT YOUR PROMPT HERE]  
```  
## Zero-Shot Prompting  
```
Classify this movie review as positive, negative, or neutral:
"The film was visually stunning but the plot felt rushed."  
```

##  One-Shot Prompting  
```
Translate English to French:

English: "Hello, how are you?"
French: "Bonjour, comment allez-vous?"

English: "Where is the library?"
French:  
```
## Few-Shot Prompting  
```
Convert customer feedback to structured data:

Feedback: "Great service, but food was cold"
JSON: {"service": "positive", "food": "negative", "overall": "mixed"}

Feedback: "Amazing experience, will definitely return"
JSON: {"service": "positive", "food": "positive", "overall": "positive"}

Feedback: "Terrible food and rude staff"
JSON:  
```

## System Prompting  
```
You are a helpful travel guide. Provide practical, accurate information about destinations. Always include:
- Key attractions
- Local customs to be aware of
- Budget considerations
- Best time to visit

User: Tell me about visiting Tokyo.
```  
## Role Prompting  
```
Act as an experienced software architect. I need help designing a scalable web application for 1 million users. What architecture patterns should I consider?  
```  
## Contextual Prompting  
```
Context: You're writing for a tech blog aimed at beginners who have never coded before.

Write a 200-word explanation of what an API is, using simple language and practical examples.
```  
## Chain of Thought (CoT) Prompting
```
Solve this step by step:
If I was 6 when my sister was half my age, how old is my sister when I'm 40?

Let me think through this step by step:
```  
* ### Self-Consistency  
        ```
        Question: If a store offers a 20% discount on a $50 item, what is the final price?

        Generate 3 different reasoning paths for this question and select the most consistent answer.

        Path 1: To find the final price, calculate the discount: 20% of $50 is 0.20 × 50 = $10. Subtract this from the original price: $50 - $10 = $40. The final price is $40.

        Path 2: A 20% discount means paying 80% of the original price. So, 80% of $50 is 0.80 × 50 = $40. Therefore, the final price is $40.

        Path 3: Compute the discount amount: 20% = 0.20, so 0.20 × $50 = $10 off. The original price is $50, so after the discount, it’s $50 - $10 = $40. The final price is $40.

        Most common answer: $40
        ```