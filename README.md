# llm-memory

This repository contains the code for modifying the Llama3.2 model's self-attention mechanism by replacing it with cross-attention layers. This approach requires no additional fine-tuning or training and aims to demonstrate that additional context can be injected without incurring a high context length cost.

## Key Idea

Traditional large language models (LLMs) face significant computational costs due to their quadratic attention complexity as the context length increases. By leveraging cross-attention, we can efficiently inject external context without exceeding the model’s native context window.

Comparison of Attention Costs

 - Self-Attention (Traditional LLMs):
   - Context length: m
   - Prompt length: n
   - Attention cost: $O((m+n)^2)$

 - Cross-Attention (LLM-Memory):
   - Context length: m
   - Prompt length: n
   - Attention cost: $O(n^2) + O(max(m, n)^2)$

This significantly reduces the computational overhead when handling large contexts while maintaining the model's performance.

## File Content

 - llm.ipynb
   - Main code that contains the demonstration of how self attention can be replaced.
 - convert.py
   - Conversion code that converts the checkpoint downloaded from llama website into transformers format. 
