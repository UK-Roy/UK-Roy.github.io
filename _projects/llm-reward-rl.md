---
layout: page
title: Reward Function Generation using Large Language Models
description: Reinforcement learning system where reward functions are generated using large language models.
category: hobby
order: 11
year: 2024
role: Self Learning Project
preview: panda.png
github: https://github.com/UK-Roy/LLM-based-Reward-based-RL-training
---

## Objective
To explore the use of large language models for automatically generating reward functions in reinforcement learning tasks.

## My Role
- Integrated LLMs with RL training pipelines  
- Trained Panda robot in Panda-Gym environment  

## Reward Engineering with LLaMA2

I provide the environment code as plain text and prompt **LLaMA2** to generate a reward function description.  
The generated description is then implemented explicitly inside the environment.

**Prompt:**  
[reward_prompt_llama2.txt]({{ "/assets/files/reward_prompt_llama2.txt" | relative_url }})

### Reward function signature
```python
def compute_reward(self, achieved_goal, desired_goal, info):
    ...
    return reward

```
{% include figure.liquid
  path="assets/img/project_preview/panda.png"
  caption="Panda Robot is pushing an object based on the given reward by the LLaMA2"
  class="img-fluid rounded z-depth-1"
  zoomable=true
%}

## Links
- GitHub: [Code]({{ page.github }})
