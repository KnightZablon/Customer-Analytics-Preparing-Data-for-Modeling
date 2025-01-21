# Customer-Analytics-Preparing-Data-for-Modeling

In this project, I worked with a dataset provided by Training Data Ltd., aiming to clean and optimize it for use in predicting whether students were looking for a new job. This would later help direct them to prospective recruiters. The goal was to create an efficient storage solution without reducing the size of the dataset, which was crucial for handling large amounts of data.

Steps I Took:
Loading the Dataset: I began by loading the dataset customer_train.csv into a pandas DataFrame (ds_jobs). This dataset contained anonymized student information, including features such as student ID, city, gender, work experience, education level, training hours, and whether the student was looking for a new job.

Exploratory Data Analysis (EDA): To identify columns with categorical data, I performed an initial analysis by printing the unique values for each categorical column in the dataset. This helped me categorize the columns into different types, including ordinal, nominal, and two-factor categories.

Creating Ordered and Two-Factor Category Mappings:

I created a dictionary for ordered categorical data, where the categories had a clear ranking (e.g., education levels and company size).
I also created a dictionary for columns containing two-factor categories (e.g., relevant experience, job change) and mapped these values to boolean values (True/False).
Efficient Data Type Conversion: To optimize the dataset and reduce its size:

I converted columns with two-factor categories (relevant_experience, job_change) to boolean values.
I changed integer columns, such as student_id and training_hours, to int32 to reduce memory usage.
I converted the city_development_index column to float16 for more efficient storage.
I used pandas' CategoricalDtype for columns with ordered categories (such as experience and education_level).
Remaining categorical columns were converted to pandas' category type to save memory.
Filtering Data: I applied filters to the dataset based on certain criteria:

I filtered out students with less than 10 years of experience or those working in companies with fewer than 1000 employees. This helped reduce the dataset size while keeping the focus on more experienced students at larger companies.
Summary of Category Counts: I printed out the value counts for categorical columns (e.g., gender, relevant experience, education level, etc.) to better understand the distribution of the data. This was useful for identifying imbalances or rare categories that could affect modeling.

Outcome:
After applying these transformations, the dataset was significantly optimized for storage. The data types were reduced to more memory-efficient types, and unnecessary rows were removed through filtering. The optimized dataset was now ready for modeling, with a reduced footprint that would allow for faster training and prediction times, making it feasible to work with large datasets more effectively.

This cleanup process demonstrated how data manipulation and efficient storage solutions can improve model performance and speed, which is crucial when working with large-scale datasets.
