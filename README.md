# ANN Classification - Bank Customer Retention
This is a simple project that aims to create a basic Artificial Neural Network to predict if bank customers are going to maintain/close their accounts.

## Data Set
The dataset used in an artificial dataset containing details about bank customers. The raw dataset file can be fetched from [this folder](https://github.com/sinanw/ann_bank_customer_retention/tree/main/data/raw).<br/>

This dataset is labeled and contains information about bank customers, including their credit score, geographic location, gender, age, tenure with the bank, account balance, number of products held, credit card status, membership status, estimated salary, and whether they exited the bank (presumably closed their account).

## Data Classification Details
The project is implemented in two distinct steps simulating the essential data processing and analysis phases. <br/>
- Each step is represented in a corresponding notebook inside [notebooks](notebooks).
- Intermediary data files are stored inside the [data](data) path.

### PHASE 1 - Data Preprocessing
> Corresponding notebook:  [data-preprocessing.ipynb](https://github.com/sinanw/ann_bank_customer_retention/blob/main/notebooks/1-data-preprocessing.ipynb)

Implemented data exploration and cleaning tasks:
1. Loading the raw dataset file into pandas DataFrame.
2. Exploring dataset summary and statistics.
3. Dropping irrelevant columns.
4. Encoding categorical features using [LabelEncoder](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.LabelEncoder.html) and [OneHotEncoder](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.OneHotEncoder.html).
5. Scaling independent features using [StandardScaler](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.StandardScaler.html).
6. Storing the processed dataset to a csv file.

### PHASE 2 - ANN Training and Evaluation
> Corresponding notebook:  [ann-training.ipynb](https://github.com/sinanw/ann_bank_customer_retention/blob/main/notebooks/2-ann-training.ipynb)

Model architecture and training details:
- ANN using [TensorFlow Sequential](https://www.tensorflow.org/api_docs/python/tf/keras/Sequential).
- Default input layer.
- First hidden layer with 6 units and [relu](https://www.tensorflow.org/api_docs/python/tf/keras/activations/relu) activation function.
- Second hidden layer with 6 units and [relu](https://www.tensorflow.org/api_docs/python/tf/keras/activations/relu) activation function.
- Output layer with a single unit and [sigmoid](https://www.tensorflow.org/api_docs/python/tf/keras/activations/sigmoid) activation function.
- Optimizer: [Adam](https://www.tensorflow.org/api_docs/python/tf/keras/optimizers/Adam).
- Loss function: [Binary Crossentropy](https://www.tensorflow.org/api_docs/python/tf/keras/metrics/binary_crossentropy).
- Batch size: 32
- Epochs: 100

Evaluation method: 
- Evaluation technique: [Train Test Split](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.train_test_split.html).
- Test size: 20%
- Obtained results:

| Model    | Accuracy | Recall   | Precision | F1      |
|----------|----------|----------|-----------|---------|
| ANN | 85.5%    | 44.7%    | 73.3%     | 55.5%   |