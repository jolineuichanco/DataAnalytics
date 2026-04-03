# 🛣️ DAPI Project 2: Predictions for Highway Operations

> **DAPI Analytics Project**

![Highway](https://images.unsplash.com/photo-1559117725-6588a8acb599?auto=format&fit=crop&w=1200&h=300&crop=focalpoint&fp-x=0.5&fp-y=0.5)

---

### 📅 Project and presentation due on 4/10/2026

---

## Motivation

You are part of an analytics team that is trying to inform amenities design for an interstate highway by evaluating drivers' preferences. In other words, what type of amenities should be built along the highway.

The data comes from an experiment where a promotional coupon is offered to a driver. The promotion is based on a type of amenity such as Bar, Carry out & Take away, Coffee House, or Restaurant. If the driver accepts the promotion it can be inferred that their preference is toward the same type of amenity service along the highway.

With the coupon a survey is also conducted. The survey describes different driving scenarios including the destination, current time, weather, passenger, etc., and then asks the driver whether he/she will accept the promotion.

## Challenge

Run a predictive model to assess the likelihood of a driver accepting the promotional coupon. Then, interpret your model to recommend amenities for an upcoming highway. Recommendations and insights must be linked to the features of importance of your selected model.

In addition, we will evaluate the performance of your model using the team submission file. This file consists of a prediction of 2,684 drivers with a `1` if they accept the coupon and `0` if they do not. This file will be evaluated using **accuracy** and **F-score**.

---

## Submission Requirements

This project is competition style, asking teams to build a predictive model, tune it, and score a set of 2,685 records. In addition, teams need to interpret and provide operations analytics recommendations which should emerge from the data and the results of predictive modeling.

At the end, teams should complete and submit the following:

1. **Data Review, EDA, and Feature Engineering:** A written report (in pdf) that describes your pre-modeling process: your observations from your data review and EDA, and a documentation of what you did to prepare the data, such as any data transformation and feature engineering
2. **A 15-min Presentation:** Summary of the business problem, results, and recommendations. Submit slides (see "Presentation Expectations" below).
3. **Model Generation in Python:** Development of models, tuning, and selection of a best model. Submit as ipynb file.
4. **Predictions:** Predictions on a set of new users. Visualize results as a histogram (include in your slides). Submit csv. Use this file name: `team#_submission.csv`
   > 💡 *TIP: Don't change the layout of the submission file, only add your predictions.*

---

## Grading

| Component | Weight |
|---|---|
| Presentation | 20% |
| Model performance and technical approach | 50% |
| Recommendations | 30% |

---

## Presentation Expectations

Presentations should be **15 minutes** and include:

- **Summary slide:** Business problem and a preview of your insights and recommendation
- **EDA insights and feature engineering:** Present 2-3 EDA findings that are specific to the angle your team pursued. If applicable, pair it with the feature engineering decision it inspired ("We observed X, so we created Y, and it matters because Z"). Note that you are only expected to present the most important/interesting findings (the full approach to EDA and feature engineering should be discussed in the pre-modeling pdf report.)
- **Review of modeling attempts:** *(please use a table to summarize attempts)* A "model" is a combination of a model family (e.g., logistic regression vs decision tree), features, and hyperparameters. The table should show how each model compares with respect to performance. Briefly narrate the progression: what did you try first, what improved performance, what didn't help, and why you moved from one approach to the next.
- **Selected model and features of importance:** Identify your final model and explain why you selected it. Show the feature importance plot. 
- **Model interpretation:** Are there any insights that the model reveals?
- **Implications and recommendations:** Include concrete, actionable recommendations. Mention any caveats or limitations to your recommendation.
- **Supplementary Appendix** (not presented): (1) Data review, (2) Full EDA gallery, (3) Prediction Histogram

---

## Datasets

### 📊 [Data for Model Training](https://drive.google.com/file/d/1Me8WMi72bO7uy4-s_L87dOQ3KrAiP1zE/view?usp=sharing)

### 📊 [Data for Scoring and Submission Process](https://drive.google.com/drive/folders/1eK2cD0lYrzr5dhZHSzFZdFTtdi7RavSu)

---

## Data Dictionary

| Variable | Description | Values |
|---|---|---|
| `id` | Unique number given to the driver doing the survey | — |
| `destination` | Driver's destination | No Urgent Place, Home, Work |
| `passanger` | Passengers in the car | Alone, Friend(s), Kid(s), Partner |
| `weather` | Current weather | Sunny, Rainy, Snowy |
| `temperature` | Temperature (°F) | 55, 80, 30 |
| `time` | Current time | 2PM, 10AM, 6PM, 7AM, 10PM |
| `coupon` | Type of coupon offered | Restaurant(<$20), Coffee House, Carry out & Take away, Bar, Restaurant($20-$50) |
| `expiration` | Coupon expiration | 1d, 2h |
| `gender` | Driver's gender | Female, Male |
| `age` | Driver's age | 21, 46, 26, 31, 41, 50plus, 36, below21 |
| `maritalStatus` | Marital status | Unmarried partner, Single, Married partner, Divorced, Widowed |
| `has_Children` | Has children | 1, 0 |
| `education` | Education level | Some college - no degree, Bachelors degree, Associates degree, High School Graduate, Graduate degree, Some High School |
| `occupation` | Occupation | Unemployed, Architecture & Engineering, Student, Education & Training & Library, Healthcare Support, Healthcare Practitioners & Technical, Sales & Related, Management, Arts Design Entertainment Sports & Media, Computer & Mathematical, Life Physical Social Science, Personal Care & Service, Community & Social Services, Office & Administrative Support, Construction & Extraction, Legal, Retired, Installation Maintenance & Repair, Transportation & Material Moving, Business & Financial, Protective Service, Food Preparation & Serving Related, Production Occupations, Building & Grounds Cleaning & Maintenance, Farming Fishing & Forestry |
| `income` | Annual income range | $37500–$49999, $62500–$74999, $12500–$24999, $75000–$87499, $50000–$62499, $25000–$37499, $100000 or More, $87500–$99999, Less than $12500 |
| `Bar` | Monthly bar visits | never, less1, 1\~3, gt8, 4\~8 |
| `CoffeeHouse` | Monthly coffeehouse visits | never, less1, 4\~8, 1\~3, gt8 |
| `CarryAway` | Monthly take-away orders | 4\~8, 1\~3, gt8, less1, never |
| `RestaurantLessThan20` | Monthly restaurant visits (<$20/person) | 4\~8, 1\~3, less1, gt8, never |
| `Restaurant20To50` | Monthly restaurant visits ($20–$50/person) | 1\~3, less1, never, gt8, 4\~8 |
| `toCoupon_GEQ15min` | Driving distance to coupon location > 15 min | 0, 1 |
| `toCoupon_GEQ25min` | Driving distance to coupon location > 25 min | 0, 1 |
| `direction_same` | Coupon location in same direction as destination | 0, 1 |
| `direction_opp` | Coupon location in opposite direction of destination | 0, 1 |
| `Y` | **Target:** Whether the coupon is accepted | 1 (accepted), 0 (not accepted) |

---

## Tips

> 💡 When building recommendations from predictive models, you **MUST** consider features of importance in your model.

![Feature Importance Example](https://codaio.imgix.net/docs/Akhczj5I5i/blobs/bl-zDw7rsYOZE/3d11316542a41a70ed1da02f29573e8ae52810137b7bf6d840bbfa36014016c76a5514aaa04b6cf407b884afa366e6464ab7870ddd616b6a62a8ca5d37a329b3c726dd87a4ee26b1ab52d87f84acbf556b5fb540a1aa7708d96cdf04f3dadb4761726ff8?fit=max&fm=webp&lossless=true)

---

## Teams

See Project 2 teams on Brightspace

