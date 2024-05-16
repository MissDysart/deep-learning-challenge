# deep-learning-challenge
U of O Data Analytics - Module 21 Challenge

## Overview
The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. With machine learning and neural networks, use the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

## Results

* Data Preprocessing
    * The target for the model is IS_SUCCESSFUL (is the venture likely to succeed).
    * The features are APPLICATION_TYPE (binned), AFFILIATION, CLASSIFICATION (binned), USE_CASE, ORGANIZATION, 
        STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, and ASK_AMT.
    * The variables that were removed (before optimization) are EIN and NAME. SPECIAL_CONSIDERATIONS split into two features that were basically the same, so one of them was removed to try to optimize model performance.
* Compiling, Training, and Evaluating the Model
    * For the initial neural network model there were 3 layers (1 input, 1 hidden and 1 output) with 80 and 30 nodes in the first and second layers, respectively. The model only used the relu and sigmoid activation functions. These are pretty standard starting points. The number of nodes was between 2 and 3 times the number of input features.
    * The target performance for the model was 75%. The model was not able to acheive that target.
    * To try to increase the performance there were 5 attempts:
        1. Add more neurons. Changed the first hidden layer to 95 and the second to 60. This had little to no affect on loss or accuracy.
            * 268/268 - 0s - loss: 0.5679 - accuracy: 0.7258 - 473ms/epoch - 2ms/step Loss: 0.5678666830062866, Accuracy: 0.7258309125900269
        2. Add an additional layer with the same number of neurons as the 2nd layer. This had little to no effect on loss or accuracy.
            * 268/268 - 1s - loss: 0.5675 - accuracy: 0.7303 - 784ms/epoch - 3ms/step Loss: 0.5675201416015625, Accuracy: 0.7302623987197876
        3. Change the split of the training and testing data to 80% and 20%, respectively. Little change.
            * 215/215 - 0s - loss: 0.5658 - accuracy: 0.7262 - 491ms/epoch - 2ms/step Loss: 0.5657766461372375, Accuracy: 0.7262390851974487
        4. Reverse the split so testing data is 80%. Little change in the final loss and accuracy, though accuracy got as high as 75% while the model was running -- Epoch 50/50 215/215 [==============================] - 1s 3ms/step - loss: 0.5141 - accuracy: 0.7552.
            * 858/858 - 1s - loss: 0.5778 - accuracy: 0.7231 - 1s/epoch - 1ms/step Loss: 0.5777688026428223, Accuracy: 0.7231049537658691
        5. Add more features by changing the limits for the bins for both CLASSIFICATION and APPLICATION_TYPE. Also tried to lower the number of epochs from 100 to 50. This had the biggest improvement but did not reach the target accuracy.
            * 268/268 - 1s - loss: 0.5560 - accuracy: 0.7266 - 837ms/epoch - 3ms/step Loss: 0.5559502840042114, Accuracy: 0.7266472578048706

## Summary
With an overall performance of 72%, the model is acceptable. However, it would have been nice to optimize the performance above 75%. This result may not be acheivable without more data features.  Because Alphabet Soup wants to know whether an applicant will be successful or not and most of the features can be transformed into binary input variables during the preprocessing phase, a logistic regression model might be better suited for this task. The data would need to be preprocessed in the same way (with binning and dummies) then scaled with the standard scaler before training the logistical regression model.