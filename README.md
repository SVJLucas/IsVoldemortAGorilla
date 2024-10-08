# Is Voldemort a Gorilla? Exploring Image AI Alignment in Supervised Learning Models

<p align="center">
  <img src="https://github.com/user-attachments/assets/0485b6b9-46f9-461b-a5ba-e4f26360cc36" alt="Is Voldemort a gorilla?" width="600px"/>
</p>


## The Gorilla Misclassification in Google Photos


In 2015, Google faced a significant controversy with its photo tagging service when its AI algorithm mistakenly classified images of Black people as gorillas. This alarming error exposed the limitations and biases embedded within AI systems, particularly those relying on facial recognition technology. The core issue was traced back to the training datasets used to teach the AI how to identify and categorize images. These datasets lacked sufficient racial diversity, leading the AI to develop skewed associations and misidentify subjects based on their race. This incident not only highlighted the technical shortcomings in Google’s AI system but also raised serious ethical concerns about the impact of biased AI on society.


<p align="center">
  <img src="https://github.com/user-attachments/assets/0c81ddd7-0df9-4d85-916a-90c31f91de66" alt="Is Voldemort a gorilla?" width="600px"/>
</p>



In response to the backlash, Google took immediate action by disabling the terms "gorilla," "chimp," "chimpanzee," and "monkey" in its image categorization algorithms to prevent further offensive misclassifications. This workaround, however, underscored a deeper, systemic problem within the tech industry: the need for more inclusive and comprehensive training datasets. The fallout from this incident has prompted a wider discussion about the responsibilities of tech companies in ensuring their AI systems are fair and non-discriminatory. It also sparked an ongoing debate about the need for regulatory oversight to manage the ethical implications of AI technologies, emphasizing that technological advancement should not come at the cost of social equity and justice.

## Evaluating Supervised Learning Models in Convolutional Neural Networks

To explore the abilities and limitations of supervised learning models within Google's AI technology, we'll specifically examine the ResNet-50 architecture, a popular choice for image classification tasks. Our focus will be to understand how changing specific layers within the model can impact its classification accuracy and potential biases. For this purpose, we will modify ResNet-50 by freezing its initial layers while altering the last layer to distinguish only between two categories: human and gorilla.

### Modifying ResNet-50 for Bias Exploration

#### Architecture of ResNet-50
ResNet-50 is a convolutional neural network (CNN) that is 50 layers deep and typically used for large-scale image recognition. It utilizes residual learning (skip connections) to help in training deeper networks without the problem of vanishing gradients.

<p align="center">
  <img src="https://github.com/user-attachments/assets/3dcee523-1b3b-494f-846d-c6e806a1c2b1" alt="Resnet" width="400px"/>
</p>



#### Model Adaptation
For our experiment, the model's initial convolutional and identity blocks will be frozen. These layers have already learned general features like edges and textures from extensive pre-training, on ImageNet, a dataset with over a million images of 1000 categories. We will replace the final fully connected layer of the model to output two classes: 'human' and 'gorilla'. This alteration tailors the model to our specific use-case of differentiating between these two categories.

<p align="center">
  <img src="https://github.com/user-attachments/assets/b9a0a8cb-f142-4dd5-9347-fd9efe2a750e" alt="Resnet" width="400px"/>
</p>


#### Training Dataset
We will use the Caltech 256 dataset, a well-known collection that provides a diverse set of images across 256 categories. For our purpose, we'll focus on the 'people' and 'gorilla' categories. This choice is intentional to probe how well a model trained on potentially biased data can adapt to accurately categorize images without mislabeling.

<p align="center">
  <img src="https://github.com/user-attachments/assets/3cd50099-fa78-4cf9-a048-c1bac8f59c0c" alt="Caltech" width="600px"/>
</p>


### Analyzing Model Decisions with SHAP Values

#### Understanding SHAP Values
SHAP (SHapley Additive exPlanations) values are a method to explain the output of machine learning models. They measure the impact of each feature on the prediction, providing a detailed view into how each input variable contributes to the final decision.

<p align="center">
<img width="488" alt="Screenshot 2024-08-20 at 02 22 43" src="https://github.com/user-attachments/assets/80fa0a7e-3889-49fe-919c-d1b64872701b">
</p>

#### Application to Image Classification
By applying SHAP values to our adapted ResNet-50 model, we aim to dissect the reasons behind the model's decisions. This analysis will help us identify what features or patterns in the images lead to potential misclassifications. For instance, if the model consistently mislabels humans as gorillas, SHAP values can help pinpoint whether specific facial features, skin tones, or background elements are influencing these errors.

### Implications and Ethics in AI Modeling

This experiment is not just a technical exercise but also a critical inquiry into the ethical implications of machine learning. Understanding why an AI system makes certain decisions is crucial for developing fair and unbiased technologies. By investigating and potentially mitigating these biases, we can help ensure that AI systems serve all sections of society equitably, avoiding harmful stereotypes that could perpetuate racial discrimination.

The findings from this experiment will contribute to a deeper understanding of how supervised models can be fine-tuned and scrutinized for biases, especially in sensitive applications like facial recognition. This knowledge is essential for guiding future developments in AI, ensuring they are aligned with ethical standards and societal values.


## Pattern Comprehension

### Are Gorillas Gorillas?





<p align="center">
<img width="700" alt="SHAP 1" src="https://github.com/user-attachments/assets/e2a4b0d2-7bdf-4ec1-adfe-f837c3bca1aa">
</p>



<p align="center">
<img width="700" alt="SHAP 1" src="https://github.com/user-attachments/assets/691bb2d1-af67-4832-8bf8-f60371d7980d">
</p>



### Are Humans Gorillas?

<p align="center">
<img width="700" alt="SHAP 1" src="https://github.com/user-attachments/assets/c956ae98-370f-45e9-b740-370d4ef1fb25">
</p>


<p align="center">
<img width="700" alt="SHAP 2" src="https://github.com/user-attachments/assets/6ea7d6ed-5e3e-41b0-83df-0929b983331e">
</p>

<p align="center">
<img width="700" alt="SHAP 3" src="https://github.com/user-attachments/assets/2cf04fed-389a-4e65-9161-dd94bc3004af">
</p>

### Are forest Gorillas?


<p align="center">
<img width="700" alt="SHAP 2" src="https://github.com/user-attachments/assets/6daf011b-a170-4c91-aea0-4cd863f3dc2f">
</p>

<p align="center">
<img width="700" alt="SHAP 2" src="https://github.com/user-attachments/assets/1b364c88-f5f4-428b-ab33-394b4fff4061">
</p>



### Is Voldemort a Gorilla?

<p align="center">
<img width="700" alt="SHAP 3" src="https://github.com/user-attachments/assets/f84f8885-748e-4896-b863-b0a2996cacdb">
</p>

<p align="center">
<img width="700" alt="SHAP 4" src="https://github.com/user-attachments/assets/5bf6e5a5-738b-4505-89b0-5514d48464e5">
</p>

<p align="center">
<img width="700" alt="SHAP 5" src="https://github.com/user-attachments/assets/0977aec2-0d85-4a64-9f5e-6b24ff54cce0">
</p>


<p align="center">
<img width="700" alt="SHAP 6" src="https://github.com/user-attachments/assets/0d63675d-eeaa-4f8e-a563-205443128773">
</p>












