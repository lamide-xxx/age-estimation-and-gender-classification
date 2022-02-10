# age-estimation-and-gender-classification

In this file, I trained two CNN models(one from scratch and the other through transfer learning) to estimate a person's age and gender by given a face image. 

MODEL A (trained from scratch)
With 1M parameters (all trainable), Model A has 8 core layers - 4 convolutional and 4 fully connected. After each convolutional layer, a max-pooling layer, which is now called a sub-sampling layer (Karim, 2019), is applied. After the 4th convolutional and max-pooling layers, the model branches out into two different dense layers, with one branch dedicated to predicting age, and the other predicting gender. This approach of a common base is taken as both tasks are sharing the same data and lower visual features are general.


MODEL B (Pretrained Model)
Model B was trained using a Transfer Learning technique – Fixed Feature Extraction. This approach, as opposed to Fine-tuning, was taken to reduce the number of trainable 
parameters of the network, and ultimately reduce training times. The chosen pretrained model is the VGG16 model, which is trained on the large ImageNet dataset (14 million 
images). Freezing the convolutional base of this model, a custom set of fully-connected layers were added on top of it and trained. Similar to model A, the architecture above 
(figure 5) shows Model B branching out into two fully-connected layers for the two output predictions.

In summary, both models achieve high and very similar levels of performance, having roughly the same values in tables 1 and 2. Model B displayed a better performance for gender prediction, while Model A shows a better performance for age prediction. Model B’s pretrained nature is reflected in its learning curves as it stabilizes its learning 
process in 10 epochs (~30 minutes), whereas it takes Model A 40 epochs to do this (~30 minutes).Although the epochs taken translate to roughly the same amount of training time on each model, Model B achieving stability in less training epochs gives the idea that it might have better overall performance on unseen data
