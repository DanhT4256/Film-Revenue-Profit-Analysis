# Film Revenue & Profit Analysis

## Project overview

**Project title:** Predict Film Revenue and Profit to Attract Investors

**Research question:** What factors should an investor consider when deciding whether to invest in the production of a film?

This project explores how film production budgets, worldwide gross revenue, profit, return on investment (ROI), release timing, and genre relate to film financial performance. It also compares baseline machine-learning models for predicting worldwide gross revenue and profit.

> **Attribution note:** This project is an independent analysis built using datasets and supporting files referenced below. The dataset and source materials are not claimed as original work by the project author. Please consult the linked repositories/files for their original context, ownership, and applicable reuse terms.

## Data sources and attribution

The analysis notebook references the following sources:

1. **Dataset/source repository — `ntdoris/movie-revenue-analysis`**  
   https://github.com/ntdoris/movie-revenue-analysis  
   This is the source repository previously associated with the project's `final_dataset.csv`. The dataset is used as the basis for the film revenue and profit analysis. Credit for the source dataset belongs to its original publisher.

2. **Google Drive CSV used to load the main dataset in the analysis workflow**  
   https://drive.google.com/file/d/1mSIHqg4aa1ZiKZCKEu72YVbq8x5GVSX-/view?usp=sharing  
   This file is explicitly referenced by the analysis code when loading the main `df` dataset.

3. **Google Drive CSV used for the genre summary analysis**  
   https://drive.google.com/file/d/1brezr_Nlwao_AO5QyrvFKmN3M1bckETb/view?usp=sharing  
   This file is explicitly referenced by the analysis code when loading `df_2_genres` for genre-level comparisons.

The two Google Drive links are included to document the actual file references in the analysis workflow. Their precise original authorship and licensing are not independently verified here; retain attribution to the original provider and confirm reuse permissions before redistributing the files.

**Code availability:** The analysis code will be uploaded to this GitHub repository separately. This README intentionally does not link to the Colab notebook.

## Project objectives

- Explore the relationship between production budget and worldwide gross revenue.
- Compare gross revenue and ROI patterns across release months.
- Examine differences in financial outcomes across film genres.
- Build and compare baseline prediction models for worldwide gross revenue and profit.

## Data preparation

The analysis reports that 147 duplicate records were removed and identifies 99 `-inf` values in the `profit_margin` column. The original analysis proposes that these records may correspond to cancelled or unreleased films, but this is a hypothesis rather than a verified fact.

A second dataset, `df_2`, is created after excluding the `-inf` records. The main exploratory analysis also focuses on films released from 2010 onward, according to the assumptions documented in the analysis.

## Selected charts

The following figures are existing outputs from the analysis notebook. No new charts have been generated for this README.

### Production budget vs. worldwide gross

![Production budget vs. worldwide gross](images/production_budget_vs_worldwide_gross.png)

### Average gross by release month

![Average gross by release month](images/average_gross_by_month.png)

### Average ROI by genre

![Average ROI by genre](images/average_roi_by_genre.png)

## Main observations

- The production-budget distribution is right-skewed: many films have lower-to-moderate budgets, while a smaller number have substantially higher budgets.
- The notebook's scatter plot indicates a positive association between production budget and worldwide gross revenue. This does not establish that a higher budget causes higher revenue.
- Gross revenue and ROI vary by release month in the notebook's analysis.
- Financial outcomes also vary across genres. Average gross, average budget, profit, and ROI are different measures and should not be treated as interchangeable.
- The model results reported in the analysis suggest moderate explanatory power for worldwide gross revenue and lower explanatory power for profit. They are baseline results, not validated investment advice.

## Model results

The analysis reports the following tuned model metrics:

| Prediction target | Model | MSE | R² |
|---|---|---:|---:|
| Worldwide gross revenue | Linear Regression | 2.260046621774825e+16 | 0.5726395575896677 |
| Worldwide gross revenue | Random Forest | 2.362938587361107e+16 | 0.5531833412843197 |
| Profit | Linear Regression | 2.2600466217748244e+16 | 0.4045764343215693 |
| Profit | Random Forest | 2.238397225186981e+16 | 0.4102801046737312 |

These values are transcribed from the analysis and have not been independently rerun.

## Tools

- Python
- pandas
- Matplotlib
- Seaborn
- scikit-learn
- Jupyter / Google Colab (development environment; code will be uploaded to this repository separately)

## Limitations

- The available features may not capture all relevant drivers of film performance, such as marketing expenditure, distribution terms, competition, cast, and audience sentiment.
- The proposed interpretation of `-inf` records as cancelled or unreleased films requires verification.
- Model predictions contain uncertainty and should not be used as stand-alone investment recommendations.
- The source files' original licensing and exact authorship should be confirmed before redistributing data.

## Potential next steps

- Verify the origin and meaning of the `-inf` records.
- Document dataset licensing and any required attribution in the repository.
- Add relevant predictors if they are available and permitted for use.
- Evaluate model errors in interpretable units and validate the models on suitable held-out data.
- Review chart labels and source-code assumptions before presenting results publicly.
