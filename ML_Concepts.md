## ML


Data leakage:
Any feature available at the time of training but not at the time of testing and directly or indirectly related to the ground truth or result.

imbalanced:
for one type of output class size of the data or percentage of data is very high while for other class it is very low as a example 90 % data for one class and only 10% data for other so each time model predict for higher one and still have higher accuracy.

Guardrails:
As name suggest guard means it prevent something,
Users try to trick llm through a prompt to be generate some crucial information or harmful content using guardrails we define these limitations so that this type of response will not be generated. 

Ragas:
LLM as a Judge


Rag:
It is a technique to connect llm with external knowledgebase and then generate answers, generally llm's does not have knowledge about our personal or some data so instead of training from scratch(which is very costly process) we connect it with some external knowledgebase by following some set of instructions it generate answer.




"PCA, or Principal Component Analysis, is an unsupervised dimensionality reduction technique. It transforms the original correlated features into a smaller set of uncorrelated variables called principal components, while retaining maximum variance or information. It is commonly used to reduce computational complexity, remove redundancy, and visualize high-dimensional data."


"Convolution is an operation where a small kernel slides over an image and performs element-wise multiplication followed by summation to produce a feature map. It helps extract spatial features such as edges, textures, and patterns. In CNNs, these filters are learned during training."


"Pooling is a downsampling operation used in CNNs to reduce the spatial dimensions of feature maps while retaining important features. In max pooling, for example, we take the maximum value from a local region such as 2×2. This reduces computation and helps the network focus on important features.


"Since MSE squares the errors, outliers can have a very large impact. First, I would investigate whether the outliers are genuine or data errors. If they are invalid, I would correct or remove them. If they are genuine, I could use techniques like winsorization or target transformation, or choose a robust loss such as Huber Loss instead of MSE.


"A confusion matrix is a performance evaluation table for classification models. It shows the number of true positives, true negatives, false positives, and false negatives by comparing actual and predicted classes. From it, we can calculate metrics such as accuracy, precision, recall, and F1-score."


Activation Function:
This function sits at the end of neural network and introduce non linearity in result to capture complex patterns.
without activation function it works as a giant linear model. 
ReLU is commonly used in hidden layers, while sigmoid or softmax are commonly used in classification output layers."
non linearity means the relationship between x(input) and y(output) can't be define using linear relationship.
means if data contains curve like structure that can't we work with that.

"Non-linearity means the relationship between input and output cannot be represented simply by a straight-line or linear function. Real-world problems like image recognition contain complex patterns, so activation functions introduce non-linearity and allow neural networks to learn these patterns.


ML


Data leakage:
Any feature available at the time of training but not at the time of testing and directly or indirectly related to the ground truth or result.

imbalanced:
for one type of output class size of the data or percentage of data is very high while for other class it is very low as a example 90 % data for one class and only 10% data for other so each time model predict for higher one and still have higher accuracy.

Guardrails:
As name suggest guard means it prevent something,
Users try to trick llm through a prompt to be generate some crucial information or harmful content using guardrails we define these limitations so that this type of response will not be generated.

Ragas:
LLM as a Judge


Rag:
It is a technique to connect llm with external knowledgebase and then generate answers, generally llm's does not have knowledge about our personal or some data so instead of training from scratch(which is very costly process) we connect it with some external knowledgebase by following some set of instructions it generate answer.




"PCA, or Principal Component Analysis, is an unsupervised dimensionality reduction technique. It transforms the original correlated features into a smaller set of uncorrelated variables called principal components, while retaining maximum variance or information. It is commonly used to reduce computational complexity, remove redundancy, and visualize high-dimensional data."


"Convolution is an operation where a small kernel slides over an image and performs element-wise multiplication followed by summation to produce a feature map. It helps extract spatial features such as edges, textures, and patterns. In CNNs, these filters are learned during training."


"Pooling is a downsampling operation used in CNNs to reduce the spatial dimensions of feature maps while retaining important features. In max pooling, for example, we take the maximum value from a local region such as 2×2. This reduces computation and helps the network focus on important features.


"Since MSE squares the errors, outliers can have a very large impact. First, I would investigate whether the outliers are genuine or data errors. If they are invalid, I would correct or remove them. If they are genuine, I could use techniques like winsorization or target transformation, or choose a robust loss such as Huber Loss instead of MSE.


"A confusion matrix is a performance evaluation table for classification models. It shows the number of true positives, true negatives, false positives, and false negatives by comparing actual and predicted classes. From it, we can calculate metrics such as accuracy, precision, recall, and F1-score."


Activation Function:
This function sits at the end of neural network and introduce non linearity in result to capture complex patterns.
without activation function it works as a giant linear model.
ReLU is commonly used in hidden layers, while sigmoid or softmax are commonly used in classification output layers."
non linearity means the relationship between x(input) and y(output) can't be define using linear relationship.
means if data contains curve like structure that can't we work with that.

"Non-linearity means the relationship between input and output cannot be represented simply by a straight-line or linear function. Real-world problems like image recognition contain complex patterns, so activation functions introduce non-linearity and allow neural networks to learn these patterns.

================================================================


3. Quick interview table
Situation	Activation
Hidden layers	ReLU commonly
Binary classification	Sigmoid
Multi-class, one class only	Softmax
Multi-label classification	Sigmoid
RNN/LSTM internal states	Tanh commonly
ReLU dying-neuron issue	Leaky ReLU


"It depends mainly on where the activation is being used and the type of prediction task. For hidden layers, ReLU is a common choice because it is computationally efficient and helps with gradient propagation. For binary classification, I typically use sigmoid in the output layer because it produces a value between 0 and 1. For multi-class single-label classification, I use softmax because it converts the outputs into probabilities that sum to one. For multi-label classification, I use sigmoid independently for each class."


"The vanishing gradient problem occurs when gradients become extremely small during backpropagation, especially in deep networks. This causes earlier layers to learn very slowly or stop learning. It commonly occurs with activation functions like sigmoid and tanh because their derivatives can become very small. ReLU helps mitigate this problem because its derivative is 1 for positive inputs."

==============================================================================================================================================

SAP


Agents, automations, data, Human in the loop
 context engineering, interview focus more on AI.
every answer with a real example.

================================================================

Fine Tuning:

Language modeling,  auto regressive training--> next token predicting => get Foundation model(to predict the next word).

instruction fine tuning/ supervised fine tuning(make model for conversation)--> retrain existing model => Fine tune model

Fine tuned model-->(not aligned with human response like tone/manner) --> Preference Training/alignment --> (based on human feedback retrain our existing models)-->(rchf reinforcement learning, Dpo )

full or partial fine tuning Or PEPT(LORA)// retraining all parameters of a model.(unsloth)

infrencing: predicting(after training we generate the response as a testing called inferencing)(use to already trained model for just testing or just cheking the result).

check sunny savita fine tuning repo.
read about slm's(small language models)
lecture -3 for training.

you can't train or load the model in sagemaker notebook for that required

Each transformer is combination of 2 things encoder and decoder like gpt is also a type of transformer(consist both), each part(either encoder or decoder) consist two things Attention(Q, K,V) and Feed forward neural network.


Flow: Text(sentence) pass through a tokenization layer and break down in words, tokenizations specify some token number to each word (also add some extra numbers, to the padding or eos(end of the statement to know the end)) 
Then each tokens will pass through embedding layer(positional encoding layer) and converted into vectors with a specific position (all works in parallely).
This encoding passed to attention layer(Q,K,V) then Feed forward neural network)



Before Transformer: we uses RNN so it fails for long texts(slow, vanishing gradient problems(due to less change in gradient from last to starting layers(so weights does not update properly), that cause less relation between the words so words not have proper meaning(how words related to each other in same sentence) ).

Means( all words/tokens are passes sequentially at that time then the new token with the reponse of past one pass together to the new layer(NN) )

TO solve this we can use( Transformers, Resnet, changing gradient(for vanishing problem only).

Q,K,V(all are metrices)
vectors of word(embedding)
Final embedding metrics(V) contains (embeddings + positional_embeddings + relation between each tokens)



hosting the model is very costly to running the amazon sagemaker service cost you around 10 to 20k .
need to use huggingface or orhter model using sage maker(mlgm.xlarge instance)(first need to check is any instance available if not then make a request then you gent within 24hr for endpoint we need different instances for notebook, training or deployment all are costly). 

Apply rag over the fine tuned model is a good practice.

in retriever apply similarity search.

Lambda + Api Gateway + DynamoDB used to get the endpoint result(url) after deployment. Write down some code in Lambda function and also add(use)/create enviorment variables



Objective:   In any organization you need to build a llm application from scratch or fine tune( initially they have their large data) then using sagemaker we fine tune our model then it becomes easy to deploy the application over the cloud then over the period it is possible data will extend then fine tuning is a costly process so then we uses rag pipeline from there.




