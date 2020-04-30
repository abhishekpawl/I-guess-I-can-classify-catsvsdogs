# shallow-neural-network-to-classify-catsvsdogs

I have trained a 5-layer neural network.

The first layer contains (40x40x3) units that correspond to the features as I have resized the rgb format of the images from the shape (40, 40, 3) to (40x40x3, 1). The second layer contains 10 units. The third layer contains 10 units. The fourth layer contains 5 units. And the final layer contains a unit that does the binary classification.

I have the randomly initialized the weights and initialized b to 0. 

For forward propagation I have calculated:

Z[l] = W[l].A[l-1] + b[l]
A[l] = G[l](Z[l]) and so on where G[l] defines the activation function for the layer 'l'. For the last layer I have used sigmoid as the activation function and for other layers I have ysed ReLU as the activation funvtion.

For cost, I have found out the logistic loss for each iteration.

For backward propagation:

dZ[l] = dA[l]xG[l]'(Z[l])
dW[l] = (1/m) x dZ[l].A[l-1].T
db[l] = (1/m) x summation of dZ
dA[l-1] = W[l].T . dZ[l] and so on.

Then I have upgraded the parameters using gradient descent:
W = W - learning_ratexdw
b = b - learning_ratexdb

Then I have run the model with the optimized parameters.
