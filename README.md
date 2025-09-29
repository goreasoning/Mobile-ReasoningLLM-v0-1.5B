# Mobile-ReasoningLLM-v0

This repository contains the evaluation code for Mobile-ReasoningLLM-v0, which starts to update the reference model in the reinforcement learning after R1-like reinforcement learning and its variants, including curriculum learning.

In this work, we comprehensively consider starting to free the weights of the reference model in the continued learning of Reasoning LLMs that have already been learned after R1-like reinforcement learning and its variants. In our version zero, we further demonstrate that our design of reinforcement learning enhances the reasoning ability of small language models, with SoTA results for 5 reasoning benchmarks for Mobile-Reasoning-LLM-1.5B.

## News
- Sep 27, 2025: 🚀 Mobile-ReasoningLLM-v0 models are publicly available on [Hugging Face](https://huggingface.co/deepgo/Mobile-ReasoningLLM-v0)

## Evaluation
### Step 1. Math Reasoning Tasks
- Temperature=0.6 and max-length=64,000 is recommended.
- It is advisable to include a directive in your prompt such as: "Please reason step by step, and put your final answer within \boxed{}."

### Step 2. Code Reasoning Tasks
- Temperature=0.6 and max-length=65,536 is recommended.
- It is advisable to include a directive in your prompt such as: "You are an expert Python programmer. You will be given a question (problem specification) and will generate a correct Python program that matches the specification and passes all tests."

## Training Cost
It takes the following number of days to train Mobile-ReasoningLLM-v0 on 1T Tokens using 8 NVIDIA A800 80G GPUs following pre-training, R1 reinforcement learning, R1-curriculum reinforcement learning, and updates to the reference model in the continued R1 reinforcement learning.

| Model Size | Training Time |
|------------|---------------|
| 1.5B       | ~30 days     |

## Results on Zero-Shot Reasoning Tasks
### Mobile-ReasoningLLM-1.5B-v0
| Model                           | AIME24 (pass1@avg16) | AIME25 (pass1@avg16) | MATH-500 (pass1@avg16) | GSM8k (pass1@avg16) | LCB-v6 |
|---------------------------------|----------------------|----------------------|------------------------|---------------------|--------|
| Qwen3-0.6B-base                | 11.3                | 17.0                | 73.0                   | 79.2               | 14.9  |
| MobileLLM-R1-1B                | 15.5                | 16.3                | 74.0                   | 67.5               | 19.9  |
| DeepSeek-Qwen-1.5B             | 29.1                | 23.4                | 83.4                   | 77.3               | 19.9  |
| FastCurl-1.5B-V3               | 49.6                | 32.9                | **90.5**               | ---                | ---   |
| Open-Nemotron-1.5B             | 49.7                | 40.4                | 83.4                   | 76.7               | 28.3  |
| **Mobile-ReasoningLLM-1.5B-v0**| **63.1**            | **49.6**            | 88.0                   | 80.2               | **30.7** |
| Qwen3-1.7B                     | 47.0                | 37.0                | 89.4                   | **90.3**           | 29.8  |

## Acknowledgement
This training is partially based on Hugging Face [Transformers](https://github.com/huggingface/transformers) repo under [Apache License](https://github.com/huggingface/transformers/blob/main/LICENSE).

## Contact
Xinhandi, DeepMiddleGo (deepearthgo at gmail dot com)

## License
Mobile-ReasoningLLM-v0 is DeepMiddleGo licensed as of now.
