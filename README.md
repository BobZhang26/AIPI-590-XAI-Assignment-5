[![Python Application Test with Github Actions](https://github.com/BobZhang26/Bob_PythonTemplate1/actions/workflows/cicd.yml/badge.svg)](https://github.com/BobZhang26/Bob_PythonTemplate1/actions/workflows/cicd.yml)
## AIPI 590 - XAI | Assignment 5 
### Description
Generate local explanations for individual predictions from a pre-trained blackbox model (ie ResNet34, Inception, BERT, YOLO, GPT-2). You may use LIME, SHAP, or Anchors for this assignment. At least one visualization of your explanation is required.
Include a discussion that explains why you chose the explanation technique you did. In this discussion, include strengths, limitations, and potential improvements to your approach.

In this assignment, we will be using explainable technique to explain the functionality of some inherently not interpretable models. We used pretrained gpt-2 model provided by hugging face (https://huggingface.co/gpt2) to explain the generated text by gpt2. 

SHAP (SHapley Additive exPlanations) is a widely used method in machine learning that helps explain model outputs. It shows how much each feature contributes to a prediction, making it easier to interpret complex models like deep learning or ensemble methods, which are often seen as "black boxes."

For an input sentence ["The professor handed me the ancient book, its pages yellowed with time,"], the model returned ["and I began to read"]
