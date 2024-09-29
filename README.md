# Background

We are working for an analytics consultancy company. A mid-size private bank, “World Plus”, requested you to deliver a pitch to win a major contract with them to develop and deploy a lead prediction system.

Lead conversion plays an important role in the success of any banking operation; involving the identification and targeting of prospective customers who are most likely to convert (purchase a product or service). World Plus provides a range of banking products, including loans, investment options, savings accounts, and credit products. They employ various communication channels such as call centres, live chat, email, and social media to effectively sell these products to their existing customers.

World Plus faces challenges in accurately identifying leads. They aim to implement a lead prediction system to pinpoint prospective customers who will convert and buy their new term deposit product. Through this system, they can strategically target these prospective customers via their communication channels and avoid unnecessary expenses on uninterested customers. This is particularly important because sales and marketing operations are costly in terms of both time and money. Several other consultancy companies have been approached as well, and the final decision on who will get the contract will largely depend on the outcome of a demonstration of the data mining approach to this problem based on a dataset that World Plus provided.

The dataset1 contains 220,000 records of historic customer data (that collected during a previous product offering).

# Project objectives
Lead conversion is important in banking operation’s success but sales and marketing activities are costly in time and money. World-Plus, a mid-size private bank, want to deploy lead prediction system to identify potential customers who will convert and buy new term products to have strategies for those customers through communication channels. From World-Plus’ data set, we have two objectives in this project.

• Objective 1 (Priority): minimising cost by identifying potential customers accurately.

• Objective 2: increasing revenue by reaching as many potential customers as possible.

# Modelling: 
We implemented four models to classify prospective bank customers: Support Vector Machine (SVM), Random Forest, Logistic Regression and eXtreme Gradient Boosting (XGB). The binary variable, ‘Target’, referred to lead conversion in given dataset and was used to analyse the models’ results and determine their accuracy. Due to their unique advantages, these supervised models were selected to predict Target variable.

We implemented two distinct strategies for models: one with feature selection and one without. This approach is crucial because while feature selection based on information gain can mitigate overfitting, it might also miss important interactions between variables, potentially impacting model performance. Considering the operation efficiency and time cost, 10% of training data is used for parameter tuning, and K-fold cross-validation is set to 5 to select optimal model from these parameters. Once the best parameters are identified, we train model on the entire training set. Unlike basic models that directly classify customers, our model predicts the probability of a customer making a purchase, allowing for the manual setting of different threshold values for future model comparison. Finally, the model's performance is evaluated using a separate test set.

# Results
XGB, our chosen model, excels in handling large and complex datasets, delivering accurate predictions while mitigating overfitting. However, there are still potential limitations during the deployment stage.
Firstly, despite enhanced interpretability with XAI tools, it remains more intricate than simpler models like decision trees, posing a problem when explaining model decisions is necessary. Secondly, while XGBoost performs well with large-scale datasets, its prediction speed may lag behind simpler models, crucial in applications requiring rapid responses. Finally, the model's use of numerous trees (ntrees=200) demands significant computational resources. This could become a potential issue if World Plus Bank has limited computational resources.


