## SENDY-RIDERS-RESPONSE-CASE-STUDY

This Repository demonstrate the flow of solving real world challenge using data science.

[Sendy](https://www.sendyit.com/) links customers who have delivery needs with vetted transporters (from bikes to trucks), using a web and mobile application platform as well as an API. Customers select their vehicle of choice, get their price quote upfront and pay using various payment options. The system optimises the route and dispatches the order to the closest available drivers and riders (called Partners). 

The datasets provided by Sendy includes dispatch details and rider metrics based on orders made via the Sendy platform. The question is to predict whether a Partner will accept, reject or ignore an order that has been dispatched to them. A Partner will receive an order through the phone application and has a few seconds to accept the order. Alternatively, the Partner can actively reject the order. If the Partner doesn’t take an action we consider the order ignored. After a few seconds, Sendy will dispatch the order to the next available Partner.

##PART A: FRAMING A DATA SCIENCE PROBLEM

The objective was about to create the machine learning Model to predict whether a rider will **accept**, **decline** or **ignore** an order sent to them.
Here Sendy company interested to know a specific reaction of a given rider depending on the order requests.

Before hand, just to reframe the hypothesis to a data science problem.

**Hypothesis:**
Picking the best rider to service the order will improve the experience of the customer and potentially save on time since the rider won’t cancel, creating a more efficient service overall.

**Qn.** Why does riders react negatively (`ignored` or `cancelled`)? need to find the way to solve this problem

**Data Science Framing of Problem:** <br>
Since the nature of problem/challenge fall in Classification category, To test the hypothesis, Machine Learning Classifiers will be required to predict which reaction of a rider in regards to a particular dispatch.

Contribution features such as:
- The number of order hits to a rider at a particular time.
- The value or amount of money for a particular order.
- The time the order placed
- The weekday the order placed
- The location 
- The client type (personal or busness)

Sendy company wants to minimize the rate of  negative response (`ignore` and `decline`) of a particular order across the platform. Therefore the machine learning model should be able to catch perfectly all negative reactions `decline` and `ignore` and make sure doesn't classify `accepted` order as negative reactions

After building the model, we can inspect the model interpretability using `Sklearn Feature importance` and SHAP to identify the greatest features that explain reaction of a rider in a particular dispatch. Also to evaluate it's performance with various metrics to see how far the model can predict rider reactions. For our case we opt to go with confusion matrix and accuracy because target labels are not well balanced.


## PART B: EXPLORATORY DATA ANALYSIS(EDA)

After problem and hypothesis framing, the next task was EDA with the dataset given. To make the process a breeze, I used the powerful yet simple SWEETVIZ library.

Also I did Bivariate & multivariate Analysis on the features to understand the distribution and correlations.

The EDA work and observations can be found in this detailed and separate Notebook attached Main Files


## PART C: DATA WRANGLING

After EDA, I understood the data better and the next step was feature engineering. This involved taking a deeper dive into the data and generating new features that would better predict the reaction of the rider on a particular order.

Here i generated `hours` per order to complete,`distances` and `rating factors`

Also some distribution analysis on the generated features using histogram plots.

Work relating to this task can be found in the separate Notebook attached Main Files


## PART D: MODEL BUILDING AND EVALUATION

After the features had been formed, I used the polished dataset to build the Classifcation model. This involved testing out several Classifiers and chosing the best. 

I ended up with catboost , perfoms better when categorical features are not ecoded. I opt to let catboost handle categorical features by itself.

Evaluation metrics used are accuracy and confusion matrix

The notebook to the task can be found in the separate Notebook attached Main Files.


## REPORTING, INSIGHTS AND RECOMMENDATION

Arguably the most critical component. This is where your client sees the value of the work you have been doing. For this, I prepared an executive summary slide detailing the findings, insights and recommendations.

The presentation can be found on this [slide](https://docs.google.com/presentation/d/1TYbxKa3U3KwxyUwL8msCRRUExCBO7uvZl7RN-uYKzmQ/edit?usp=sharing).


)
