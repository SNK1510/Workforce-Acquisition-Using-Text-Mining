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

