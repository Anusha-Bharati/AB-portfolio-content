# When My Model Looked Too Good: Data Leakage in the Titanic Project

> Draft research note. Replace the placeholders below with your actual experiment results before publishing.

## The question

Can passenger characteristics be used to predict Titanic survival without accidentally giving the model information it would not legitimately have at prediction time?

## What I built

I used Python, Pandas and Scikit-learn to explore the Titanic dataset and trained Logistic Regression and Random Forest classification models.

## The problem I encountered

While developing the model, I encountered data leakage: information from outside the legitimate training process was influencing model evaluation and making the results look more trustworthy than they really were.

## How I investigated it

Add your exact leakage source here. Explain:

- what preprocessing or feature caused the leakage;
- when it was applied relative to the train/test split;
- what metric looked suspicious;
- how you changed the pipeline.

## Before and after

Add the real metrics from the leakage-prone and corrected experiments here. Do not publish invented values.

## What I learned

A model can appear to perform well while the experimental setup is flawed. Model evaluation is not only about choosing a metric; it also depends on ensuring that training data, preprocessing and feature construction reflect the information that would genuinely be available at prediction time.

## Next steps

- Compare Logistic Regression and Random Forest under the corrected pipeline.
- Review feature importance and model errors.
- Add cross-validation if appropriate.
- Document remaining limitations.
