# GenAI

## README: Automated Resume Matching and Interview Question Generation

### Overview
This project demonstrates a simple method for matching resumes to a job description using TF-IDF (Term Frequency-Inverse Document Frequency) and cosine similarity. Additionally, it generates personalized interview questions based on the content of each resume and the job description.

### Features
1. **Resume Matching**: The program ranks resumes based on their similarity to a given job description.
2. **Interview Question Generation**: Automatically generates interview questions tailored to each candidate's experience and skills.

### Dependencies
- Python 3.x
- `scikit-learn`
- `random`
- `pprint`

### Installation
To use this code, make sure you have Python 3.x installed along with the required packages:
```bash
pip install scikit-learn
```

### Usage
1. **Data Preparation**:
   - Define the job description and a list of resumes. Each resume should be a string that includes the candidate's name, title, experience, skills, and education.

2. **Resume Matching**:
   - The `match_resumes` function calculates the similarity between the job description and each resume using TF-IDF and cosine similarity. It returns a ranked list of resumes based on their relevance to the job description.

3. **Interview Question Generation**:
   - The `generate_interview_questions` function creates a list of personalized interview questions based on the presence of specific keywords in the resume.

### Example
Here's a quick example to show how it works:

```python
# Job Description
job_description = "Looking for an AI Engineer with experience in machine learning, Python, and data science."

# Sample Resumes
resumes = [
    """Resume 1:
    Name: John Doe
    Title: AI Engineer
    Experience:
    3 years as an AI Engineer at TechCorp
    Developed machine learning models in Python
    Expertise in TensorFlow, Keras, and data science
    Skills: Python, TensorFlow, Machine Learning, Data Science, Deep Learning
    Education: B.Tech in Computer Science""",
    """Resume 2:
    Name: Jane Smith
    Title: Software Developer
    Experience:
    4 years as a Software Developer at CloudBase
    Specialized in Java and cloud computing
    Built scalable cloud applications
    Skills: Java, Cloud Computing, REST APIs, Docker
    Education: B.Sc. in Software Engineering""",
    """Resume 3:
    Name: Michael Brown
    Title: Data Scientist
    Experience:
    5 years as a Data Scientist at DataMinds
    Analyzed large datasets using Python and R
    Implemented machine learning algorithms
    Skills: Python, R, Machine Learning, Data Analysis, SQL
    Education: M.Sc. in Data Science"""
]

# Match Resumes and Generate Interview Questions
ranked_resumes = match_resumes(job_description, resumes)

for resume, score in ranked_resumes:
    pprint(f"Resume: {resume}\nScore: {score}\nQuestions: {generate_interview_questions(resume, job_description)}\n")
```

### Output
The output includes the resume, its similarity score to the job description, and the personalized interview questions generated based on the resume content.

```plaintext
Resume: Resume 1:
...
Score: 0.67
Questions: ['Can you explain your experience with Python?', 'Can you explain your experience with machine learning?', 'Can you explain your experience with data science?', 'Can you explain your experience with deep learning?']

Resume: Resume 3:
...
Score: 0.55
Questions: ['Can you explain your experience with Python?', 'Can you explain your experience with machine learning?', 'Can you explain your experience with data science?']

Resume: Resume 2:
...
Score: 0.25
Questions: ['Can you tell us about your relevant experience?']
```

### Customization
- **Keywords**: The keywords for generating interview questions can be adjusted in the `generate_interview_questions` function based on the job description and the required skills.
- **Ranking Algorithm**: The ranking is currently based on cosine similarity. This can be modified or extended with additional criteria if needed.

### Limitations
- The current implementation assumes that resumes and job descriptions are provided in text format and focuses on key terms related to AI and machine learning.
- The model does not account for the context or nuances in experience levels.

### Future Enhancements
- Improve keyword extraction for more accurate question generation.
- Expand the model to handle more complex resume structures and multiple job descriptions.

### License
This project is open-source and available under the MIT License. Feel free to use and modify the code as needed.

### Contact
For any questions or suggestions, feel free to reach out.
