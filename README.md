# Cybersecurity-Suspicious-Web-Threat-Interactions
1. Introduction
This project focuses on analysing web traffic data to identify and classify potentially suspicious or malicious interactions.
The goals of this analysis are:
•	To load and preprocess the raw web traffic data.
•	To explore patterns in the data that may signal suspicious activity.
•	To build a machine learning model to distinguish between normal and suspicious traffic based on network metrics like bytes_in, bytes_out, and connection duration.
•	To evaluate the model’s performance using standard classification metrics.
The environment is set up using commonly used Python libraries such as:\

•	Pandas for data handling
•	NumPy for numerical operations
•	Seaborn and Matplotlib for visualization
•	scikit-learn for machine learning algorithms
3. Data Loading and Preprocessing

The dataset used for this analysis is titled CloudWatch_Traffic_Web_Attack.csv, which contains logs of web traffic potentially associated with cybersecurity threats. It was loaded using pandas.read_csv().
Initial Inspection:

•	df.head() was used to preview the dataset.
•	df.info() helped identify data types and non-null counts.
•	df.isnull().sum() checked for missing values in each column.
Observations:

•	The dataset contains several key features such as:
o	srcaddr, dstaddr (IP addresses)
o	bytes_in, bytes_out (network size metrics)
o	duration, start, end (temporal metrics)
o	detection_types (used later for labeling)
•	No major missing data was found at this stage, allowing direct feature engineering and analysis.
4. Label Creation

To enable supervised machine learning, the raw data needs a clear target variable that indicates whether a web traffic entry is suspicious or normal. This is achieved by using the detection_types column.
•	Marks entries as:
o	1 (Suspicious) if detection_types is 'waf_rule'
o	0 (Normal) otherwise
This approach assumes that "waf_rule" indicates detection by a Web Application Firewall, hence suspicious.
5. Exploratory Data Analysis (EDA)
Exploratory Data Analysis (EDA) helps uncover patterns, anomalies, and relationships in the dataset before applying machine learning models. The analysis focuses on understanding how different features behave in relation to the target label is_suspicious.
