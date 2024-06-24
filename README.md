# Multimodal-Deep-Learning-and-XAI-for-Cerebral-Hemorrhage-Diagnosis

team 3



Images are the largest source of data in healthcare and, at the same time, one of the most difficult sources to analyze. 

Our goal is to use multimodal medical imaging to provide a separate yet complementary structure and function information of a patient study 

The motivation for multimodal imaging is to obtain a superior and exquisite image that will provide more reliable statistics than single images


## Data

Our diagnostic tools include Computed tomography (CT) and Magnetic resonance imaging (MRI) from 81 different patients.

The data are labeled into 5 different categories, which are the types of cerebral hemorrhage

![image](https://github.com/hguhcbuf/Multimodal-Deep-Learning-and-XAI-for-Cerebral-Hemorrhage-Diagnosis/assets/69788954/b8a0b885-9cfc-4b76-a2a3-effe591fe738)



## Image Registration Process

Before image fusion process, because some mathing CT-MRI images are not aligned very well we go through image registration process.

It is a simple process where a number of landmarks are defined on the same locations in two images. The landmarks are then matched by an algorithm, and the images are thus registered. 

The CT image is used as the reference and the MRI image is aligned depending on the user-selected landmarks.

![image](https://github.com/hguhcbuf/Multimodal-Deep-Learning-and-XAI-for-Cerebral-Hemorrhage-Diagnosis/assets/69788954/bc0f8a88-aa60-4267-8720-c55456da835b)


## Multimodal Deep Learning

Amoung the different types of multimodal-deep learning, we focus on late fusion and early fusion. The results are compared with single frame CNN.

![image](https://github.com/hguhcbuf/Multimodal-Deep-Learning-and-XAI-for-Cerebral-Hemorrhage-Diagnosis/assets/69788954/0d315525-d7ab-4734-bf4c-345b7e617a23)

## CNN Architecture

![image](https://github.com/hguhcbuf/Multimodal-Deep-Learning-and-XAI-for-Cerebral-Hemorrhage-Diagnosis/assets/69788954/3fb9099e-f517-45d5-80ad-ab9c12f268c4)

## Single Frame and Late Fusion Result Heatmap

![image](https://github.com/hguhcbuf/Multimodal-Deep-Learning-and-XAI-for-Cerebral-Hemorrhage-Diagnosis/assets/69788954/ee07f088-d6bb-4b4a-965d-0ea1cecf202d)

## Early Fusion Algorithm

Some researches claim the wavelet transform (WT) often contribute more useful information. Therefore, we chose to apply it to our fusion model.

Apply wavelet decomposition on CT image to generate approximate coefficient LL1 and three detail coefficients: LH1(horizontal), LV1(vertical), LD1(diagonal)
Apply wavelet decomposition on MRI the same way
Apply fusion based on VGG network on four generated pairs and generate fused LL, LH, LV and LD band.
Apply inverse wavelet transform on the four bands generated to obtain final fused image.

![image](https://github.com/hguhcbuf/Multimodal-Deep-Learning-and-XAI-for-Cerebral-Hemorrhage-Diagnosis/assets/69788954/e3ff4a56-d7c4-4f4f-921b-2f79ee1264de)

![image](https://github.com/hguhcbuf/Multimodal-Deep-Learning-and-XAI-for-Cerebral-Hemorrhage-Diagnosis/assets/69788954/168825db-46c0-440f-898d-dc2188d4c4cc)

![image](https://github.com/hguhcbuf/Multimodal-Deep-Learning-and-XAI-for-Cerebral-Hemorrhage-Diagnosis/assets/69788954/f7d35653-6029-4ae1-bdac-b81f877b479a)

![image](https://github.com/hguhcbuf/Multimodal-Deep-Learning-and-XAI-for-Cerebral-Hemorrhage-Diagnosis/assets/69788954/1eaf3b07-beec-41d3-bcc5-983765db766c)

## Early Fusion Test Data Heatmap

500 test image data

Accuracy : 95.2%

![image](https://github.com/hguhcbuf/Multimodal-Deep-Learning-and-XAI-for-Cerebral-Hemorrhage-Diagnosis/assets/69788954/d95ec046-e6bd-4af6-a4de-9aab0717b2ca)

## Data Augmentation Trials to Fix Imbalanced Training Data

Train images were augmented to match the number of 'no hemorrhage' data but no significant enhancement was shown in the test result

![image](https://github.com/hguhcbuf/Multimodal-Deep-Learning-and-XAI-for-Cerebral-Hemorrhage-Diagnosis/assets/69788954/e2f51089-34a0-4d64-83c1-07aece0f2c17)

## Hemorrhage Dianosis by MD

![image](https://github.com/hguhcbuf/Multimodal-Deep-Learning-and-XAI-for-Cerebral-Hemorrhage-Diagnosis/assets/69788954/9058b7e4-697b-4585-a7df-6fb41a05a692)

## XAI reuslt (Grad-CAM)

![image](https://github.com/hguhcbuf/Multimodal-Deep-Learning-and-XAI-for-Cerebral-Hemorrhage-Diagnosis/assets/69788954/cf6f0a4e-ab56-4a66-ab52-686953ed4625)
