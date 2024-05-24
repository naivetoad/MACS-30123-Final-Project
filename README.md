# Multinomial Logistic Regression and Latent Dirichlet Allocation on arXiv Dataset
## [arXiv Dataset](https://www.kaggle.com/datasets/Cornell-University/arxiv)
## [Exploratory Data Analyis](https://github.com/macs30123-s24/final-project-arxiv/blob/3edf5ec8382d9f0fc19f41fc0de09ea734f7a080/EDA.ipynb)
## [Multinomial Logistic Regression](https://github.com/macs30123-s24/final-project-arxiv/blob/3edf5ec8382d9f0fc19f41fc0de09ea734f7a080/Classification.ipynb)
## [Latent Dirichlet Allocation](https://github.com/macs30123-s24/final-project-arxiv/blob/3edf5ec8382d9f0fc19f41fc0de09ea734f7a080/LDA.ipynb)
## Report

## Overview
This project focuses on leveraging the extensive repository of scholarly articles available on arXiv to extract meaningful insights using scalable computing methods. The arXiv dataset, a publicly accessible dataset on Kaggle, containing information of approximately 2.5 million articles across multiple scientific disciplines, presents an invaluable opportunity to explore shifts and trends in scientific research. Given its vast size and complexity, this project employs Apache Spark through Amazon EMR clusters in JupyterHub notebooks to ensure efficient data processing and analysis. This project aims to make metadata of arXiv more accessible and insightful for researchers and a broader range of interested individuals. 

### Social Problems
In the modern era of scientific discovery, the dissemination of research findings has accelerated, leading to an overwhelming volume of publications. Researchers often struggle to stay abreast of the latest developments in certain fields because the large quantity of articles can obscure significant trends and emerging areas of study. The arXiv dataset, while a treasure trove of information, exemplifies this challenge due to its extensive and diverse collection of papers. The core research problem addressed in this project is the need to categorize and analyze this vast body of knowledge efficiently. By doing so, we aim to uncover underlying trends, identify prominent research topics, and streamline the process of finding relevant research. This need is particularly acute in the face of global challenges, where rapid and informed responses are essential.

### Justification of Large-Scale Computing
The use of scalable computing methods is crucial for several reasons:

Volume of Data: The arXiv dataset’s 2.5 million articles necessitate robust data processing capabilities to manage large-scale data efficiently. Traditional data analysis tools would be inadequate for handling such a massive dataset within a reasonable timeframe.

Complexity of Analysis: Advanced techniques like Latent Dirichlet Allocation for topic modeling and Logistic Regression for classification require substantial computational resources. Scalable computing enables the execution of these complex algorithms on large datasets, ensuring comprehensive analysis.

Real-time Processing: With continuous updates to the arXiv dataset, real-time data processing is essential to keep analyses current and relevant. Scalable methods facilitate the continuous ingestion and processing of new data, allowing for up-to-date insights.

Resource Optimization: Distributed computing frameworks such as Apache Spark optimize resource utilization through parallel processing, significantly reducing computational load and improving efficiency.

### Large-Scale Computing Methods
The project begins with data extraction from an S3 bucket (where we store the original dataset in a json format), using Apache Spark on Amazon EMR clusters to read and process the JSON file containing the arXiv dataset. The EMR cluster configuration includes 8 r5.xlarge instances, each providing 4 vCores and 32 GiB of memory. This robust setup ensures that the large volumes of data can be handled efficiently, allowing for rapid data processing and analysis. Initial exploratory data analysis (EDA) helps understand the dataset's structure and basic statistics, providing a foundation for subsequent analyses. Utilizing the scalable infrastructure provided by AWS EMR, the project efficiently handles the extensive data, ensuring that the computational resources are utilized effectively. This setup enables the processing of the arXiv dataset's substantial size, ensuring that the analysis remains efficient and effective.

Latent Dirichlet Allocation (LDA) is employed to uncover the underlying topics within the abstracts of the articles. The process involves several critical steps:

1. Data Preprocessing: Text data is preprocessed by converting it to lowercase, removing punctuation, and tokenizing the text. This ensures uniformity and prepares the data for effective analysis.

2. Stop Words Removal: Common words that do not contribute to topic differentiation are removed to enhance the quality of the topic modeling.

3. Vectorization: The processed text data is converted into numerical vectors, enabling the application of machine learning algorithms.

4. Model Training: The LDA model is trained on the vectorized data to identify latent topics. This model uncovers the primary themes and trends within the dataset, which are crucial for understanding the distribution of research topics over time.

5. The topics extracted through LDA are then analyzed and visualized, providing insights into the prominence of different research areas and their evolution.

A classification model is built to categorize articles into predefined fields based on their abstracts. This involves:

1. Data Preprocessing: Similar to the LDA preprocessing, with additional steps to handle categorical labels corresponding to different scientific fields.
2. Pipeline Creation: A data processing pipeline is established, consisting of tokenization, stop words removal, vectorization, and label indexing. This pipeline ensures a streamlined and consistent approach to data preparation.
3. Model Training: A Logistic Regression model is trained on the processed data to classify articles into various fields. This model helps in understanding the distribution of research across different disciplines and evaluating the accuracy of automatic classification.
4. Model Evaluation: The model's performance is evaluated using accuracy metrics and ROC AUC (Receiver Operating Characteristic Area Under Curve) for each class. This evaluation assesses the model's effectiveness in distinguishing between different scientific fields.

The results from the topic modeling and classification tasks are visualized to provide clear and interpretable insights. For example, the number of yearly publications by topic is plotted to reveal trends over time. Such visualizations help in identifying patterns and shifts in research focus, making the data more accessible and understandable for researchers.

### Conclusion
This project serves as our exploratory work after learning this course. Though mature, it demonstrates the significant potential of scalable computing methods in handling and analyzing large datasets. By leveraging Apache Spark and machine learning techniques, we can extract valuable insights from the extensive arXiv repository, facilitating a better understanding and discovery of scientific research trends. The methodologies employed here are not only applicable to the arXiv dataset but can also be extended to other large-scale datasets across various domains of social science research. This project underscores the importance of scalable computing in modern data analysis, highlighting its role in advancing scientific knowledge and discovery.
