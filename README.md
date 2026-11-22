
# Sciencia AI – Sentiment Analysis

**Data Source Assessment and Review Data Validation for a User Sentiment Analytics Platform**

## 1. Project Overview

This project is part of the Sciencia AI sentiment analytics initiative. It explores the feasibility of collecting and analyzing public user reviews from digital platforms to identify customer sentiment, product pain points, and potential areas for product improvement.

The current phase focuses on evaluating data source accessibility, validating review data quality, and conducting preliminary sentiment and issue classification analysis.

## 2. Project Objectives

- Evaluate the accessibility and suitability of potential user review data sources.
- Test practical review data collection from Google Play.
- Assess data completeness, duplication, and language quality.
- Apply sentiment analysis to identify positive, neutral, and negative user feedback.
- Classify negative reviews into product-related issue categories.
- Explore how review insights can support product and business decisions.

## 3. Data Collection

A bounded Google Play data collection test was conducted using the third-party Python package `google-play-scraper`.

Three applications were selected for testing:

- Notion
- Duolingo
- Spotify

**Collection results:**

| Metric | Result |
|---|---:|
| Applications tested | 3 |
| Reviews collected | 600 |
| Reviews per application | 200 |
| Collection batches per application | 2 |
| Duplicate review IDs across batches | 0 |
| Reviews retained after preliminary English-language filtering | 489 |

**Important:** `google-play-scraper` is an unofficial third-party tool. This test demonstrates practical data accessibility under the conditions tested; it does not establish official Google API support, guaranteed permission, or long-term collection reliability.

## 4. Data Processing and Quality Assessment

The collected reviews were examined for:

- Missing review text and key metadata
- Duplicate review IDs across collection batches
- Language identification and filtering
- Review text availability and usability

The preliminary dataset contained 489 reviews retained as English-language reviews for further analysis. Language identification is approximate and may not perfectly classify short, mixed-language, or ambiguous reviews.

## 5. Preliminary Sentiment Analysis

VADER was applied to the 489 retained reviews to classify sentiment using compound scores.

| Sentiment | Number of Reviews | Percentage |
|---|---:|---:|
| Positive | 346 | 70.8% |
| Negative | 84 | 17.2% |
| Neutral | 59 | 12.1% |

A small number of predictions were manually reviewed and corrected. These corrections were documented separately and should not be interpreted as a fully validated human-labeled dataset.

## 6. Issue Classification

Negative reviews were classified into 12 issue categories:

1. Advertising
2. Bugs and Errors
3. Content Quality
4. Data Loss and Reliability
5. Features and Functionality
6. Login and Access
7. Performance
8. Playback Experience
9. Pricing
10. Product Design
11. Recommendations
12. Usability

A total of 78 out of 84 negative reviews received at least one issue label, representing **92.86% labeling coverage**.

Multiple labels can be assigned to a single review when it describes more than one issue. Labeling coverage does not represent classification accuracy.

## 7. Preliminary Findings

The initial analysis suggests different patterns of user complaints across the three applications:

- **Notion:** Features and functionality, performance, bugs, and usability.
- **Duolingo:** Content quality, features and functionality, and product design.
- **Spotify:** Pricing, playback experience, and advertising.

These findings are exploratory and reflect only the collected sample. They should not be interpreted as representative of the overall user population or as definitive comparisons of product quality.

## 8. Limitations

- The Google Play collection test used an unofficial third-party scraper.
- The sample is limited to three applications and 200 reviews per application.
- Long-term collection reliability and repeatability have not been established.
- Language detection may produce errors, particularly for short or mixed-language reviews.
- VADER may misinterpret context, sarcasm, negation, and informal language.
- Issue classification relies on keyword-based rules and limited manual review.
- G2 access and review-text availability have not yet been established.

## 9. Next Steps

- Further document Google Play collection behavior and access limitations.
- Verify whether available G2 access supports retrieval of actual review text.
- Refine issue classification and validate labels through additional manual review.
- Explore additional review sources based on demonstrated accessibility and data quality.
- Evaluate the feasibility of a repeatable data ingestion workflow.

## 10. Repository Structure

```text
sciencia-ai-sentiment-analysis/
├── README.md
├── requirements.txt
├── .gitignore
├── 01_source_assessment/
├── 02_data_collection/
├── 03_test_results/
├── 04_analysis/
└── data/
```

---

**Project Status:** Preliminary data source validation and exploratory sentiment analysis completed. Further source validation and methodology refinement are ongoing.
