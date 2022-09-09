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
This was used for Topic Modelling - identifying the top topics in the documents and the top words that would come under each topic.gensim.simple_preprocess was used for tokenizing the documents. The LDAmodel function from the gensim library was used to get all the topics. Topic clusters were created using pyLDAvis library.

## Results

This is the output of the cosine similarity function, for a particular jd, the function gave the top resume matches, in descending order.
![image](https://user-images.githubusercontent.com/27859890/189416787-e1b94347-e5ec-477f-aa81-92e67ddee290.png)


These are the topic clusters formed- 

**For the JD dataset**

![image](https://user-images.githubusercontent.com/27859890/189417309-99a196ea-91f5-4e38-92ed-02fb82ee0d73.png)

**For the resume dataset**

![image](https://user-images.githubusercontent.com/27859890/189417445-6c0cd385-d795-47ab-aaed-3562ea4d922f.png)


Word Cloud using matplotlib and wordcloud libraries - 


**For the JD dataset**

![image](https://user-images.githubusercontent.com/27859890/189417686-b77a6526-bb28-46dd-93d5-d7c4ae0f2904.png)


![image](https://user-images.githubusercontent.com/27859890/189417722-57f4967a-d341-49b9-b26e-825fec55c63f.png)

**For the resume dataset**

![image](https://user-images.githubusercontent.com/27859890/189417820-c4b386a0-0cfb-4854-8b60-1dd43e9f2929.png)

### Coherence and Perplexity scores
Coherence scores tell us how interpretable the topics are to humans. Perplexity score tells us how well our model predicts  sample. A lower perplexity score indicates a better generalization performance. In this context, topic modelling provides the top skills present in the dominant topics which will help organizations gauge the top skills in the market.

![image](https://user-images.githubusercontent.com/27859890/189422038-417afc92-f344-4929-a2b2-af0b23e3c75e.png)




## Conclusion
This model can definitely use some improvements, in terms of cleaning the documents better, analysing tokens and topics more clearly, but we can say this works fair. This is a generic model that uses Amazon's JD data, but with advanced web scraping techniques, we can expand this analysis to job descriptions found anywhere in any format.














