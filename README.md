# CSC413-Final
The model we intend to build is a type of text generation model with the Shakespeare style. To achieve that we want to build an RNN model and train it with the famous Shakespeare work--- Hamlet.<br />
Model:<br />
Our model has three parts:<br />
An embedding layer that takes a character index (sparse representation of a one-hot vector representing the character), and returns an embedding x(t) for the character.
A recurrent neural network layer. We will use an nn.GRU unit uses the following function(image1). At each time step, this layer will take the previously hidden state h(t−1) and the embedding of a new generated token x(t) and compute the new hidden state h(t) representing tokens not yet generated.<br />
The projection MLP takes the hidden state and computes the distribution of the next character to generate.<br />
For example, generate a sentence “He closes with you in this consequence:” is like the following picture(image2).<br />
Data:<br />
Since all Shakespeare’s work doesn’t have any copyright problems, we just download the Hamlet novel in txt form. We process the data so that it turns into 4167 sentences. We intend to use those 4167 sentences to train our model.<br />
We clear the front space and “\n” in each sentence because we don’t want those to show up too frequently.<br />
Training:
We first train based on one sentence. The training curve is like this(image3): <br />

Then we try to train the model with batches and change the hyper-parameters like learning rate and batch size to get the best effect on the model.
We eventually use the batch size of 32 and the learning rate to be 0.001 as the final choice.<br />
Results:  <br />
In the end, we try to use the trained model to generate articles. Even though some sentences do not follow the grammar, the words our model generates are almost right to read. <br />
However, there are still repeat a sentence that shows up frequently and sentences that do not have a lot of connection. We guess that it might be our training data is still too small. And our model generates character by character, it may have the ability to generate the word and sentences correctly. But it‘s not powerful for the article.<br />
Ethical Consideration:<br />
We don’t face any ethical problems.<br />
Authors:<br />
Zuo Ziqiang  <br />
The images are in the repository.<br />
