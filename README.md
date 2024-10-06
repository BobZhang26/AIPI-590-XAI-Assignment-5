[![Python Application Test with Github Actions](https://github.com/BobZhang26/Bob_PythonTemplate1/actions/workflows/cicd.yml/badge.svg)](https://github.com/BobZhang26/Bob_PythonTemplate1/actions/workflows/cicd.yml)
## AIPI 590 - XAI | Assignment 5 
### Description
Generate local explanations for individual predictions from a pre-trained blackbox model (ie ResNet34, Inception, BERT, YOLO, GPT-2). You may use LIME, SHAP, or Anchors for this assignment. At least one visualization of your explanation is required.
Include a discussion that explains why you chose the explanation technique you did. In this discussion, include strengths, limitations, and potential improvements to your approach.

In this assignment, we will be using explainable technique to explain the functionality of some inherently not interpretable models. We used pretrained gpt-2 model provided by hugging face (https://huggingface.co/gpt2) to explain the generated text by gpt2. 

SHAP (SHapley Additive exPlanations) is a widely used method in machine learning that helps explain model outputs. It shows how much each feature contributes to a prediction, making it easier to interpret complex models like deep learning or ensemble methods, which are often seen as "black boxes."

For an input sentence ["The professor handed me the ancient book, its pages yellowed with time,"], the model returned ["and I began to read"]

<img width="1601" alt="Screenshot 2024-10-06 at 17 16 36" src="https://github.com/user-attachments/assets/fcc43edf-7e20-41ca-9079-3a0893be4e76">

The SHAP bar plot below shows the contribution (SHAP values) of different tokens (words or sub-words) in a text sequence toward the model's decision in predicting the next word/token.
![image](https://github.com/user-attachments/assets/c67abbcf-8746-4b2e-84c9-01bc936e2611)

SHAP (SHapley Additive exPlanations) is one of the most popular techniques for explaining machine learning models, including complex models like GPT-2 used in text generation. SHAP is particularly useful for understanding which parts of an input influence a model's output, allowing us to gain insights into how different tokens (words, sub-words) in a sequence contribute to the generation of the next token or overall text.
There several reasons we want to use SHAP for GPT-2 text generation:
1. SHAP is model-agnostic, meaning it can be applied to any machine learning model, including deep neural networks like GPT-2, where the architecture (transformer-based) is often considered a "black box". It provides a unified framework for explaining both simple and complex models.
2. SHAP allows us to explain the impact of individual tokens in the input sequence on the model’s generated text. This is crucial for text generation models, where small changes in input can significantly affect the model’s predictions. For example, in GPT-2 text generation, SHAP can help us understand how specific words influence the likelihood of the next word in the sequence, giving transparency into the reasoning behind the model's output.
3. SHAP can capture interactions between tokens by assigning contributions not just to individual tokens but also to combinations of them. In text generation, words often influence one another in subtle ways, and SHAP is capable of identifying these interactions.

**Limitations**:
1. Subword-Level Analysis: GPT-2 and other transformers typically use subword tokenization (e.g., Byte Pair Encoding), which can make interpreting SHAP explanations difficult. The model might assign importance to subwords (partial words), which are harder to interpret meaningfully compared to full words.
2. Although SHAP explains the input-output relationships, it doesn't explain the internal workings of GPT-2 (such as attention patterns or how the model processes different layers). Thus, it only offers a `partial explanation` of what drives text generation in transformer models.

**Improvements**:
By developing model-specific SHAP implementations, enhancing contextual analysis, and handling subword tokenization more effectively, SHAP could become an even more powerful tool for interpreting complex language models like GPT-2.

