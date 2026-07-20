# Sentiment Analysis - Key Results & Insights
**Dataset:** Amazon Fine Food Reviews (393,933 unique reviews after dedup; 30,000 random sample analyzed)
**Methods:** VADER (lexicon + rule-based sentiment) for polarity, NRC Emotion Lexicon for 8 discrete emotions

## Sentiment Distribution
| Label | Text-based (VADER) | Star-rating (reference) |
|---|---|---|
| Positive | 88.1% | 77.9% |
| Negative | 9.8% | 14.5% |
| Neutral | 2.1% | 7.6% |

VADER agrees with the star-rating label 80.1% of the time. Most disagreement is on **Neutral**: people who give 3-star reviews still write in clearly positive or negative language ("good but too sweet"), so text sentiment rarely lands neutral — this is a known limitation of lexicon methods on mixed-opinion text, not a bug.

## Emotions (NRC Lexicon)
Most prevalent overall: **anticipation** and **trust**, followed by **joy** — consistent with food reviews being descriptive/recommend-focused ("will buy again," "great for," "trust this brand"). **Fear**, **anger**, **disgust**, **sadness** are concentrated almost entirely in the negative-sentiment segment, as expected, and can be used to distinguish *why* a review is negative (e.g., disgust → product quality/taste issue vs. fear → safety/ingredient concern).

## Trend Over Time (2004–2012)
Sentiment mix is stable across years — positive share holds around 87–91%, negative around 8–12%, with no meaningful long-term drift. This suggests overall satisfaction with this catalog didn't shift much over the period; sentiment swings are more useful as a **per-product** signal than a **platform-wide** one.

## Helpfulness Signal
Reviews with ≥5 helpfulness votes are **more negative** (16.6%) than the overall sample (9.8%). Shoppers disproportionately upvote critical reviews — a practical takeaway: negative reviews carry outsized influence on purchase decisions and deserve prioritized monitoring, not just volume-based tracking.

## Actionable Recommendations
- **Product development:** Route reviews tagged with high *disgust* or *fear* emotion scores to QA/safety review — these signal taste/quality or ingredient-safety complaints specifically, not generic dissatisfaction.
- **Marketing:** Positive-review language clusters around trust and joy — copy that emphasizes reliability/reassurance ("trusted," "always fresh") is likely to resonate, since it mirrors what happy customers already say.
- **Customer ops:** Prioritize responding to negative reviews with high helpfulness-vote counts — they have outsized visibility to other shoppers.
- **Monitoring:** Track sentiment at the product level, not platform level — aggregate trend is flat, but the per-product breakdown (see `sentiment_results.csv`) flags specific SKUs with high negative-sentiment concentration for follow-up.

## Files
- `sentiment_analysis.ipynb` — full pipeline (cleaning → sentiment → emotion → trends → charts)
- `sentiment_results.csv` — 30,000 reviews labeled with sentiment, compound score, and emotion scores
- `charts/` — 2 visualizations (distribution, word clouds)
