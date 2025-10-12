# Prompt-templates
## Important links  
* [How LLMs Work: Top 10 Executive-Level Questions](https://sloanreview.mit.edu/article/how-llms-work/)  
* [Panaversity YouTube Class Playlist](https://www.youtube.com/playlist?list=PL0vKVrkG4hWpeKmZyCRTpfRiLQ13b5uRX) 
* [check llms ranking](https://lmarena.ai/leaderboard)
* [openai](https://platform.openai.com/chat/)  
* [gemini](https://aistudio.google.com/)  
* [anthropic/cloud](https://console.anthropic.com/)  
______
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
______
## Zero-Shot Prompting  
```
Classify this movie review as positive, negative, or neutral:
"The film was visually stunning but the plot felt rushed."  
```
______
##  One-Shot Prompting  
```
Translate English to French:

English: "Hello, how are you?"
French: "Bonjour, comment allez-vous?"

English: "Where is the library?"
French:  
```
______
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
______
## System Prompting  
```
You are a helpful travel guide. Provide practical, accurate information about destinations. Always include:
- Key attractions
- Local customs to be aware of
- Budget considerations
- Best time to visit

User: Tell me about visiting Tokyo.
```  
______
## Role Prompting  
```
Act as an experienced software architect. I need help designing a scalable web application for 1 million users. What architecture patterns should I consider?  
```  
______
## Contextual Prompting  
```
Context: You're writing for a tech blog aimed at beginners who have never coded before.

Write a 200-word explanation of what an API is, using simple language and practical examples.
```  
______
## Chain of Thought (CoT) Prompting
```
Solve this step by step:
If I was 6 when my sister was half my age, how old is my sister when I'm 40?

Let me think through this step by step:
```  
______
* ### Self-Consistency  
        ```
        Question: If a store offers a 20% discount on a $50 item, what is the final price?

        Generate 3 different reasoning paths for this question and select the most consistent answer.

        Path 1: To find the final price, calculate the discount: 20% of $50 is 0.20 × 50 = $10. Subtract this from the original price: $50 - $10 = $40. The final price is $40.

        Path 2: A 20% discount means paying 80% of the original price. So, 80% of $50 is 0.80 × 50 = $40. Therefore, the final price is $40.

        Path 3: Compute the discount amount: 20% = 0.20, so 0.20 × $50 = $10 off. The original price is $50, so after the discount, it’s $50 - $10 = $40. The final price is $40.

        Most common answer: $40
        ```  
______
* ### Step-Back Prompting  
        ```
        Step 1: First, what are the key factors that generally affect website loading speed?

        Response: Key factors include:
        - Server response time (hosting quality, server location)
        - Image and asset optimization (file size, compression)
        - Code efficiency (minifying CSS/JavaScript, reducing HTTP requests)
        - Caching strategies (browser caching, CDNs)
        - Third-party scripts (ads, analytics)

        Step 2: Using these factors, provide specific recommendations to optimize the loading speed of an e-commerce website with heavy product images and multiple third-party plugins.

        Response:
        1. **Server Optimization**: Choose a reliable hosting provider with servers close to your audience. Enable server-side caching (e.g., Redis or Varnish).
        2. **Image Optimization**: Compress product images using formats like WebP. Implement lazy loading to defer off-screen images.
        3. **Code Efficiency**: Minify CSS and JavaScript files. Combine small files to reduce HTTP requests.
        4. **Caching**: Use a Content Delivery Network (CDN) like Cloudflare to cache static content globally. Set browser cache headers for repeat visitors.
        5. **Third-Party Plugins**: Audit and remove unnecessary plugins. Asynchronously load scripts for analytics or ads to avoid blocking page rendering.
        ```  
______
* ### ReAct (Reasoning + Acting)

        ```
        Question: What is the current population of Tokyo, and how does it compare to New York City?

        Thought: I need to find the current population of Tokyo and New York City to compare them. I should start by searching for the latest population data for Tokyo.

        Action: web_search
        <parameter name="query">current population of Tokyo 2025</parameter

        Observation: [Assume tool response: According to recent estimates, Tokyo's population in 2025 is approximately 37.4 million in the metropolitan area.]

        Thought: Now I have Tokyo's population. Next, I need the population for New York City.

        Action: web_search
        <parameter name="query">current population of New York City 2025</parameter

        Observation: [Assume tool response: New York City's metropolitan area population in 2025 is estimated at about 23.6 million.]

        Thought: With both figures, I can compare them. Tokyo has a larger population than New York City by about 13.8 million people.

        Final Answer: Tokyo's population is approximately 37.4 million, compared to New York City's 23.6 million, making Tokyo significantly larger.
        ```  
______
* ### Tree of Thoughts (ToT)
    * use asyncio.gether to get the multple output and git this to synthisizer agent to choose the best one
______
## Best Practices for Effective Prompts
### 1. Be Specific and Clear
``` 
Write a 300-word informative article about the health benefits of owning a dog, focusing on mental health, physical activity, and social connections. Use a friendly, accessible tone for general readers.
```
______
### 2. Use Action Verbs
Be explicit about what you want the AI to do:

*Analyze, Compare, Create, Describe, Evaluate
*Extract, Generate, List, Rank, Summarize
*Translate, Write, Explain, Classify
______
### 3. Provide Examples When Possible  
______
### 4. Structure Your Prompts  
```
Task: [What you want done]
Context: [Background information]
Format: [How you want the output structured]
Example: [Sample of desired output]
```
______
### 5. Use Instructions Over Constraints
#### Better:
```
Write a professional email summarizing the key points from our meeting.
```
#### Avoid:
```
Write an email but don't make it too long or too informal or too detailed.
```
______
### 6. Control Output Format
```
Return your answer as a JSON object with the following structure:
{
  "main_idea": "string",
  "supporting_points": ["string", "string"],
  "confidence_level": "high/medium/low"
}
```
______
### 7. Use Variables for Reusability
```
Role: You are a {expertise} expert
Task: Analyze the {document_type} and provide recommendations for {target_audience}
Context: This is for a {industry} company with {company_size} employees
```
______
### 8. Iterate and Document
*Keep track of what works and what doesn't
*Document your successful prompts
*Test variations to improve performance  
______
## Common Pitfalls and How to Avoid Them  
1. Ambiguous Instructions
2. Contradictory Instructions
3. Too Many Constraints
4. Ignoring Token Limits
5. Not Testing Variations  
______
### Code Generation Example:
```
Write a Python function that:

Requirements:
- Sorts a list of dictionaries by a specified key
- Handles missing keys gracefully (items without key go to end)
- Supports both ascending and descending order
- Includes proper error handling
- Has clear documentation

Example usage:
data = [{"name": "Alice", "age": 30}, {"name": "Bob", "age": 25}]
result = sort_by_key(data, "age", descending=False)

Please include:
- Function definition with type hints
- Docstring with parameters and return value
- Example usage
- Brief explanation of the approach
```
______
##  Prompt Chaining
```
Step 1: Research the topic
Step 2: Create an outline based on research
Step 3: Write the full content based on outline
```
______
## Leverage Structured Outputs
```
Return analysis as JSON:
{
  "summary": "brief overview",
  "key_insights": ["insight1", "insight2"],
  "recommendations": [
    {
      "action": "specific action",
      "priority": "high/medium/low",
      "timeline": "timeframe"
    }
  ]
}
```
______
## Document your prompts systematically:  
| Prompt Version |	Goal |	Model |	Temperature |	Output Quality |	Notes |
|--------------|---------|--------|-------------|------------------|----------|
| v1.0 |	Generate blog post |	GPT-4 |	0.7	Good |	Too formal |
| v1.1 |	Generate blog post |	GPT-4 |	0.7	Better |	Added tone guidance   |
