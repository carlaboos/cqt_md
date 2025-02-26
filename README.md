# cqt_md
# Repository accompanying "From Query to Concept: A Novel Taxonomy for Question Classification Using German Forum Data"
## Contains all the necessary scripts and data to recreate the results of my master's thesis

## From the Conclusion:
### This thesis offers the first systematic, data- driven exploration of the linguistic dimensions underlying conceptual question types in a major German question-and-answer forum. While the findings show that conceptual question types do not map neatly onto individual factors, they reveal statistically meaningful tendencies. Certain categories gravitate toward narrative or argumentative styles, whereas others remain neutral, subjective, or purely factual. This complexity aligns with real-world discourse, where overlapping registers prevail rather than neat categorical boundaries. By demonstrating the feasibility of coupling a question classification taxonomy with multi-dimensional analysis, the study successfully sets the stage for more refined sub-register modelling in interactive online spaces. Future interdisciplinary work, building on the taxonomy, factor framework, and annotated data set presented here, can further unravel the dynamic nature of questioning in digital communities.


## Here's what each file is for:

1. **DataCleaning:   Clean messy data**
- required files:
  - dataset1.csv
  - dataset2.csv
- result:
  - cleaned_dataset.csv
---------------------------------------------------------------------
2. **QuestionExtraction.ipynb:   Extract individual questions from within user enquiries**
- required files:
  - cleaned_dataset.csv
  - representative_sample_10000(5-20).csv (after manual annotation)
- result:
  - extracted_questions.csv
  - representative_sample_with_context.csv
---------------------------------------------------------------------
3. **TokenCount.ipynb:   Compute token count distribution + Examine distribution of 3- and 4-token questions**
- required files:
  - extracted_questions.csv
  - lmroman10-regular.otf (for font in graphics)
- result:
  - questions_for_processing.csv
  - sample_with_tokens.csv
  - TokenCountDistribution.pdf
  - representative_sample_10000(5-20).csv
--------------------------------------------------------------------- 
4. **QuestionExtractionIAA.ipynb:   Extract questions from manually annotated data set to be used for IAA**
- required files:
  - representative_sample_10000(5-20).csv (tagged version)
- result:
  - extracted_questions_for_IAA.csv
--------------------------------------------------------------------- 
5. **InterAnnotatorAgreement.ipynb:   Compute IAA between annotator 1 (originally labelled data set) and annotator 2**
- required files:
  - lmroman10-regular.otf (for font in graphics)
  - extracted_questions_for_IAA_annotator1_after.csv
  - extracted_questions_for_IAA_annotator2_after.csv
- result:
  - confusion_matrix_conceptual.pdf
  - confusion_matrix_functional.pdf
---------------------------------------------------------------------
6. **FactorAnalysis.ipynb:   Compute factor analysis. Currently: 7 factor solution**
- required files:
  - lmroman10-regular.otf (for font in graphics)
  - representative_sample_with_context_withoutDiscard.csv
  - enriched_data.csv
  - factor_loadings.csv
- result:
  - enriched_data.csv
  - factor_loadings.csv
  - WordCountDistribution.pdf
  - FeatureCountDistribution.pdf
  - ScreePlot.pdf
  - factor_loadings.csv
  - factor_scores_CQT.pdf
  - factor_scores_CQT_Factor_1.pdf
  - factor_scores_CQT_Factor_2.pdf
  - factor_scores_CQT_Factor_3.pdf
  - factor_scores_CQT_Factor_4.pdf
  - factor_scores_CQT_Factor_5.pdf
  - factor_scores_CQT_Factor_6.pdf
  - factor_scores_CQT_Factor_7.pdf
---------------------------------------------------------------------
7. **SpacyFineTuning.ipynb:   Try but fail to fine-tune a German spaCy model**
- required files:
  - TRAINING_DATA.json
- result:
  - train_data.json
  - dev_data.json
  - training_data.spacy
  - dev_data.spacy
  - config.cfg
---------------------------------------------------------------------
