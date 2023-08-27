# Module 21 Challenge: Deep Learning Challenge

## Overview of the Analysis

# Purpose of the analysis:
* The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. With your knowledge of machine learning and neural networks, you’ll use the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.
From Alphabet Soup’s business team, you have received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years
  
* Target variable: IS_SUCCESSFUL
                    This variable has 2 possibilities, either successfull or not successfull. It is what the model wants to predict based on the features.
   
With this, the goal of this model is to identify when a project is unlikely to be unsuccesful.

## Optimization
 Once the Data preprocessing was done, I traines the machine learning model with 3 layers to see the original result

<img width="719" alt="Captura de pantalla 2023-08-27 a la(s) 17 11 23" src="https://github.com/pyunes/deep-learning-challenge/assets/128106993/9fea0e35-b849-447e-8bf7-7648cb15c4d9">
 
 With this original approach I could achieve a 72% of optimization.
 Subsequently, I increased the number of layers but no matter the amout of layers I increased, the accuracy wouldn't increase significantly.


## Conclusion
Given that I couldn't attain the target accuracy of 75%, I wouldn't suggest any of the models above. I would exploore other options as to be more strict on the preprossesing part and increase the number of layers to 5 would help to bring a higher target.

 
  
