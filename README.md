# Neural Network Charity Analysis

## Purpose:
Create a binary classifier that is capable of predicting whether applicants will be successful if funded by a charity foundation called Alphabet Soup. I will be using the knowledge of machine learning and neural networks, to complete this analysis.

## Results:

### Data Preprocessing
* One variable is considered as the target for the neural network learning model which is IS_SUCCESSFUL
* The following variables are considered to be the features for the model:
 1. APPLICATION_TYPE 
 2. AFFILIATION            
 3. CLASSIFICATION        
 4. USE_CASE              
 5. ORGANIZATION           
 6. STATUS                 
 7. INCOME_AMT              
 8. SPECIAL_CONSIDERATIONS  
 9. ASK_AMT    

* Two variables are neither targets nor features, and are removed from the input data, 'EIN' and 'NAME'.
* 
#### Compiling, Training, and Evaluating the Model
There are  120 neurons, 2 hidden layers, one output layer and used Relu and Sigmoid activation functions in this model.  
The number of neuron is three times the number of input variables after encoding and it is a good rule of thumb when building the initial model to have 2 to 3 times neuron compared to input variables. For the activation function selection, I chose Relu for the hidden layer becasue it more computationally efficient.

I was not able to achieve the target model performance of 75% and here are the steps i tired to increase model performance:
1. looked for noisy variable and found that AFFILATION has high variety in its values so I binned the rare values into "others" bin
2. ASK_AMT values were also having high variance so I filtered the dataframe to exclude rare occurances
3. Changed the activiation function to Sigmoid but it made accuarcy worse.
4. Increased epochs, did not change accuracy much
5. Reduced number of input variables from 43 to 40 and then to 37 did not change accuarcy much either
6. Increased number of neurons and layers. Slight improvement in accuarcy.

Summary: 
Overall results of this deep learning model
```
268/268 - 0s - loss: 1.9188 - accuracy: 0.6908 - 412ms/epoch - 2ms/step
Loss: 1.9187933206558228, Accuracy: 0.6908454895019531
```
I recommend to use Random Forest model as it could solve this classification problem more effeciently due to the following:
*	It can be used to rank the importance of input variables in a natural way.
* It can handle thousands of input variables without variable deletion.
* Is robust to outliers and nonlinear data.
* Run efficiently on large datasets.
