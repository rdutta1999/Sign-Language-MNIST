# Sign Language MNIST
Identifying Alphabets from Sign Languages

Download the **Dataset** from [Sign Language MNIST](https://www.kaggle.com/datamunge/sign-language-mnist/download) on Kaggle. Place the **Train** and **Test** csv files along with the IPYNB file in the **same directory**.

Each training and test case represents a label (0-25) as a one-to-one map for each alphabetic letter A-Z (and no cases for 9=J or 25=Z because of gesture motions). As a result, there are 24 classes which have examples in the Dataset.

However, while creating the model, **26** nodes have been used in the Output Layer (corresponding to 26 classes), because the model will/should learn to predict **0** for classes **9(=J)** and **25(=Z)** which have no examples.

**Keras ImageDataGenerator** has been used for performing Data Augmentation.

We use a custom **CNN** model which has a **Global Average Pooling Layer** at the end instead of Dense layers to prevent overfitting.

We train the model using **Adam** as the optimizer for **50** epochs and use **Checkpoints** to save the model when it has the highest Validation accuracy.

We then predict the labels on the test cases and save the predictions in the form of a csv file as **test_output.csv**.
