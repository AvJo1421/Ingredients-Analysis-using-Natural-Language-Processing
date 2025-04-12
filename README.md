# Ingredients-Analysis-using-Natural-Language-Processing
## Overview
Supermarkets offer a wide range of food products, and most people select items based on their appearance or brand appeal. Only a few take the time to turn the packet around and check the ingredients—and even then, we're not all nutritionists who understand what those ingredients truly mean. This project aims to leverage Natural Language Processing (NLP) to analyze and interpret food ingredients more effectively.

# Methodology
![CNER workflow](https://github.com/user-attachments/assets/0e1ff020-b818-401a-b473-5a6c63a8bb4a)

# Understanding Terminologies
1. ***Customized Named Entity Recognition (CNER)***
- We all have learnt about NER which is Named Entity Recognition (NER). NER is pretrained to recognize some entities like Location, Name etc.
- This project is an attempt to leverage NER and it's customization abilities for ingredients' analysis. We do this with the help of Customized Named Entity Recognition (CNER).
- ***What is Customized Named Entity Recognition (CNER):***  CNER is a Natural Language Processing (NLP) technique used to identify and classify specific entities (like food ingredients) in text into predefined categories (e.g., Healthy, Unhealthy, Additive). “Customized” here implies training a model for domain-specific needs (i.e., food ingredients), rather than using a generic model.

2. **Annotation**
- We will be tagging (labelling) a particular ingredient with a customized entity. This is done with help of an NER Annotator.
- This is an important and first step of creating a CNER model. This step will be followed by the use of spacy and Docbin

3. **Docbin**
- A binary format used in spaCy for storing annotated data efficiently.
- We are training a custom NER model to label ingredients as various entities, we can take your labeled examples (like "Sugar" and we can mark it as "Sugar_ibgredint"), convert them into spaCy Doc objects, and store them in a DocBin. This file (train.spacy) can then be used directly during training for efficient loading and processing.

4. **Spacy Library**
- A popular NLP library in Python.
- Used for training custom NER models, i.e., models that can recognize user-defined entities.

5. **Rules for Biffurcation**
- After we tag using an NER annotator, store in Docbin and train using Spacy, a product with ingredients will be classified into custom entitites using CNER/
- Now, we have built an intricate if-else logic to classify that product into 5 levels of healthy, which are as follows:
   1. Grade A
   2. Grade B
   3. Grade C
   4. Grade D
   5. Grade E
   6. Unknown (Our model is not perfect, so it can miss out on some products, so we need to have this level as well)
 
6. **Model Training**
- Once we have classified all the food products into the 6 levels using the CNER and if-else logic, we will be creating a small scale ML model for classification of batch of ingredients into the 6 new levels.
- This will be done with the help of TF-IDF vectorizer.
- **What is TF-IDF vectorizer?:** TF-IDF (Term Frequency–Inverse Document Frequency) transforms text into numerical features by evaluating how important a word is in a document relative to the entire corpus. It reduces the weight of common words (like “the”, “is”) and increases the weight of rare, informative words—making it useful for tasks like text classification and clustering.
   
