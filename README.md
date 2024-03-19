Predicting Human Preference in Reinforcement Learning with Emotional Tone Analysis
Overview
This project explores the use of emotional tone analysis to predict human preference in reinforcement learning with human feedback. The goal is to determine if elements related to emotional tone can help predict whether a human rater would prefer a particular response.

Methodology
Data Preprocessing:
The project starts by reading in data from JSONL files (test.jsonl and train.jsonl) containing chosen and rejected responses.
The data is cleaned and transformed into a DataFrame with columns: "text", "Chosen", "Human", and "Assistant".
The DataFrame is further processed to create new columns: "C_Unique", "R_Unique", "C_Keywords", and "R_Keywords".
Emotional Tone Analysis:
The "C_Unique" and "R_Unique" columns, representing the unique parts of the chosen and rejected responses, are analyzed using an LLM (Language Model) to extract emotional tone keywords.
The LLM generates keywords describing the emotional tone of each response, which are stored in the "C_Keywords" and "R_Keywords" columns.
Keyword Extraction:
The generated emotional tone keywords are further processed using NLTK (Natural Language Toolkit) to extract meaningful keywords.
Stopwords and non-alphabetic tokens are removed, and repetitions of keywords are eliminated.
The resulting unique keywords are stored in new columns: "C_Keywords_Unique" and "R_Keywords_Unique".
Logistic Regression Analysis:
The project compares the performance of logistic regression models trained on both the unprocessed data (using "C_Unique_List" and "R_Unique_List") and the processed data (using "C_Keywords_Unique" and "R_Keywords_Unique").
The accuracy of the models is evaluated on their respective test sets to determine if the emotional tone analysis improves the prediction of human preference.
Results
The logistic regression analysis showed that the processed data, which underwent emotional tone analysis by the LLM, achieved higher accuracy compared to the unprocessed data. This suggests that incorporating elements related to emotional tone can aid in predicting whether a human rater would prefer a particular response.

Future Enhancements
Experiment with different LLMs and fine-tuning techniques to improve the emotional tone analysis.
Explore additional features and preprocessing techniques to further enhance the prediction accuracy.
Investigate the interpretability of the logistic regression models to gain insights into the specific emotional tone elements that contribute to human preference.
File Structure
Read_in_data.ipynb: Jupyter Notebook containing the code for data preprocessing and initial transformations.
Lor_reg_analysis.ipynb: Jupyter Notebook with the code for logistic regression analysis and model comparison.
LLM_Feature_judgement.ipynb: Jupyter Notebook showcasing the emotional tone analysis using the LLM.
output/: Directory containing intermediate CSV files generated during the data processing pipeline.
output B/: Directory storing the final processed CSV files with emotional tone keywords.
Dependencies
Python 3.x
Pandas
Scikit-learn
NLTK
Transformers (for LLM usage)
Usage
Install the required dependencies.
Run the Jupyter Notebooks in the following order:
Read_in_data.ipynb
LLM_Feature_judgement.ipynb
Lor_reg_analysis.ipynb
Analyze the results and accuracy metrics obtained from the logistic regression models.
Feel free to explore and modify the code to suit your specific requirements and further enhance the analysis.
