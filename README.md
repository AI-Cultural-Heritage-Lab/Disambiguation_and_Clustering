This respository contains the code for disambiguation and clustering of the questions from the Boder transcripts.
It primarily pertains to the work done for the 2025 Undergraduate Research Week.

After cloning the repository, create a .env file with the following contents:
```
OPEN_AI_KEY=YOUR OPEN AI API KEY
HF_TOKEN=YOUR HUGGINGFACE SECRET TOKEN
```

Also, to install the requirements, run the following code in the terminal:
```
pip install -r requirements.txt
```

Here is a brief explanation of what each of the files contains:
- Undergraduate_Research_Week_Notebooks
    - Original.ipynb
        - Starter code for question disambiguation, clustering, and analysis
        - Was the backbone for the other notebooks and approaches later used
    - SBERT_Clustering.ipynb
        - Adapted from Michelle's clustering notebook
        - Uses SBERT to embed the disambiguated questions and cluster them via K-Means
    - Batch_Disambiguation.ipynb
        - Contains the code to disambiguate all of the Boder questions
        - Uses batch processing to increase compute efficiency
    - Question_Analysis.ipynb
        - Preprocesses and generates distributions of lengths of questions
        - Done to ensure samples used for fine-tuning were representative of all questions
    - Preprocessing_Version_A.ipynb
        - Uses same preprocessing approach as Michelle with a couple bug fixes
            - Accounted for substrings more thoroughly
            - Fixed case sensitive issues
    - Preprocessing_Version_B.ipynb
        - Prompted GPT instead of using a rule-based approach
        - Manually edited spools and parentheticals
- Data
    - Cleaned_Boder_Transcripts.csv
        - id_new
        - id_old
        - sent_num
        - speaker
        - words
        - ellipses
        - file_cat
        - que_ans
    - Full_Info_Boder
        - file_num	
        - file_part	
        - Time	
        - Speaker	
        - text	
        - chain_of_thought	
        - contains_unresolved_pronoun	
        - enough_context_provided	
        - disambiguated_text	
        - context	
        - tokens	
        - chain_of_thoughts	
        - step_by_step_reasoning	
        - question_with_clarified_context	
        - added_words	
        - removed_words	
        - needs_context_rewriting	
        - needs_pronoun_disambiguation	
        - final_text	
        - is_flagged		
        - unnamed (text_embeddings)
        - unnamed (final_text_embeddings)