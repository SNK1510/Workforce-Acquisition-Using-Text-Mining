# Workforce Acquisition Using Text Mining
The inspiration for this project is the situation most of us are in, international students in the job market in the USA. There is an imbalance between the number of jobs created and the number of graduates every year and this is the reason for fierce competition in job applications. Every job posting has hundreds of job applications. For a company that has multiple job postings, it is the number of job postings times the hundreds of applications. It is practically an impossible task to go through every application to find the best person for the job.

While wait times and rejections are all situations we face as students, being on the other hand as a recruiter is no jolly ride either. To deal with all the applications and resumes that come through, to go through documents and identify suitable candidates is a mammoth task. 

In this project is a simple tool that works on two data sets - The resume dataset and the Job description dataset to find the best possible resume matches for each Job Description (JD)


## Datasets used:
1) AmazonJobs.csv
This csv file consists of around 232 rows of data and two columns - Job ID and Job Description. This data was scraped from the Amazon Careers site using Selenium. The code file for this has been attached.

2) UpdatedResumeDataset.csv - This is a generic resume dataset that was found on Kaggle. Each line of the file is a resume.


## Data Preprocessing - 
Since the size of the data was small, the files were initially cleaned using Excel to remove incomprehensible words like those in other languages, words that made no sense. The next set of steps in data cleaning were done after importing these files in Python. The steps performed were as follows - 
* Removal of non-ASCII characters
* Removal of punctuations and special characters
* Removal of unwanted, generic and repetitive words like - 'Skillset','education','background','qualifications','proficiency' etc based on observation
* Converted all text to lowercase for ease of analysis

## Cosine Similarity
The objective is to find the similarity between two documents (resume and JD) using cosine similarity. Cosine similarilty evaluates the similarity of two vectors by finding the cosine of the angle between two vectors - by computing their product and dividing it by the product of the magnitudes of the two vectors. The similarity value ranges between 0 and 1, because cosine values can only range from 0 to 1. 

We can comment on the similarity of two documents by looking at their cosine value. If it is 0.63, that means the documents are 63% similar, the angle between the two documents (which are vectorized) is about 51 degrees.

### TF - IDF 
Term Frequency - Inverse Document Frequency (TF-IDF) - It is a way to balance the importance of words in a document. Frequently occuring words have lower importance and rarely occuring words have high importance

The TF Vectorizer from Scikitlearn library to TF-IDF values were computed to convert the documents into a matrix of TF features. This also helped with removing stop words and tokenized words and prepared the documents for cosine similarity. The 'comp_description' function returns the resumes with the top cosine values for any JD.

## LDA - 
This was used for Topic Modelling - identifying the top topics in the documents and the top words that would come under each topic.gensim.simple_preprocess was used for tokenizing the documents. The LDAmodel function from the gensim library was used to get all the topics

## Results

![image](https://user-images.githubusercontent.com/27859890/189416787-e1b94347-e5ec-477f-aa81-92e67ddee290.png)








