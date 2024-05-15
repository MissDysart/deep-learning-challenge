# deep-learning-challenge
U of O Data Analytics - Module 21 Challenge

## Overview
The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. With your knowledge of machine learning and neural networks, you’ll use the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

## Results

Optimization
Attempt #1: Add more neurons. Changed the first hidden layer to 95 and the second to 60. This had little to no affect on loss or accuracy. 268/268 - 0s - loss: 0.5679 - accuracy: 0.7258 - 473ms/epoch - 2ms/step Loss: 0.5678666830062866, Accuracy: 0.7258309125900269

Attempt #2: Add third layer with the same number of neurons as the 2nd layer. This had little to no effect on loss or accuracy. 268/268 - 1s - loss: 0.5675 - accuracy: 0.7303 - 784ms/epoch - 3ms/step Loss: 0.5675201416015625, Accuracy: 0.7302623987197876

Attempt #3: Change the split of the training and testing data to 80% and 20%, respectively. Little change: 215/215 - 0s - loss: 0.5658 - accuracy: 0.7262 - 491ms/epoch - 2ms/step Loss: 0.5657766461372375, Accuracy: 0.7262390851974487

Attempt #4: reverse the split so testing data is 80%. Little change in the final loss and accuracy, though accuracy got as high as 75% while the model was running - Epoch 50/50 215/215 [==============================] - 1s 3ms/step - loss: 0.5141 - accuracy: 0.7552. 858/858 - 1s - loss: 0.5778 - accuracy: 0.7231 - 1s/epoch - 1ms/step Loss: 0.5777688026428223, Accuracy: 0.7231049537658691

Attempt #5: add more features by changing the limits on CLASSIFICATIONS and APPLICATION_TYPES. Also tried to lower the number of epochs from 100 to 50. This had the biggest improvement but did not reach the target accuracy. 268/268 - 1s - loss: 0.5560 - accuracy: 0.7266 - 837ms/epoch - 3ms/step Loss: 0.5559502840042114, Accuracy: 0.7266472578048706

## Summary
Because Alphabet Soup wants to know whether an applicant will be successful or not and most of the features are binary input variables, a logistic regression model might be better suited for this task.