1.1 Welcome
Machine Learning
  - Grew out of work in AI
  - New capability for computers
  
  Examples:
    - Database mining
        Large datasets from growth of automation/web.
        E.g., Web click data, medical records, biology, engineering
    - Applications can't program by hand.
        E.g., Autonomous helicopter, handwriting recognition, most of Natural Language Processing(NLP), Computer Vison.
    - Self-customizing programs(用户自定制化程序) software learn by itself
        E.g., Amazon, Netflix product recommendations
    - Understanding human learning(brain, real AI).

--------------------------------------------------------------------------------------------------------------------------------------- 
1.2 What is Machine Learning?
Definition: (1)Field of study that gives computers that ability to learn without being explicitly programmed. (Arthur Samuel 1959)
(2)"A computer program is said to learn from experience E with respect to some task T and some performance measure P, if its performance
on T, as measured by P, improves with experience E."
E.g., T: Classifying emails as spam(垃圾邮件) or not spam.  E: Watching you label emails as spam or not spam.  P: The number(or fraction)
of emails correctly classified as spam/not spam.

Machine learning algorithms: （most used）
  - Supervised learning(监督学习)
  - Unsupervised learning(无监督学习)
In general, any machine learning problem can be assigned to one of two broad classifications:
  - Supervised learning and Unsupervised learning.

Others: Reinforcement learning, recommender systems. (Also ML algorithms)
Also talk about: Practical advice for applying learning algorithms. (takes a lot of time too!)

---------------------------------------------------------------------------------------------------------------------------------------
1.3 Supervised Learning(监督学习)
E.g., Housing price prediction: 用一次函数还是二次函数来拟合
Supervised Learning: "right answers" given
That is, we gave it a data set of houses in which for every example in this data set, we told it what is the right price so what is the
actual price that, that house sold for and the toss of the algorithm was to just produce more of these right answers such as for this 
new house, you know, that your friend may be trying to sell.
Define with a bit more terminology: 
 - Regression(回归问题): Predict continuous valued output(price)

![PPT1](https://github.com/SicongLiang/Machine-Learning/blob/master/week1/1.JPG)

E.g., Breast cancer(malignant(恶性的), benign(良性的))
 - Classification(分类问题): Discrete valued output(0 or 1)

![PPT2](https://github.com/SicongLiang/Machine-Learning/blob/master/week1/2.JPG)

In other ML problems, we have more than one feature, more than one attribute.

![PPT3](https://github.com/SicongLiang/Machine-Learning/blob/master/week1/3.JPG)
PS: O stands for benign, and X stands for malignant
Learning algorithm might do is throw the straight line through the data to try to separate out the malignant rumors from the benign ones
- Clump Thickness(块的厚度)
- Uniformity of Cell Szie
- Uniformity of Cell Shape

And it turns out one of the most interesting learning algorithms that we'll see in this class is a learning algorithm that can deal with, not just two or three or five features, but an infinite number of features.
E.g., Support Vector(支持向量机) algorithm: 存在一个简洁的数学方法，能让电脑处理无限多的特征。

Recap: Supervised learning, in every example in our data set(训练集), we are told what is the "correct answer" that we would have quite liked the algorithms have predicted on that example.

---------------------------------------------------------------------------------------------------------------------------------------
1.4 Unspervised Learning

![PPT4](https://github.com/SicongLiang/Machine-Learning/blob/master/week1/4.JPG)
- Unsupervised learning allows us to approach problems with little or no idea what our results should look like. We can derive structure from data where we don't necessarily know the effect of the variables.
- We can derive this structure by clustering the data based on relationships among the variables in the data.
- With unsupervised learning there is no feedback based on the prediction results.

Example:
 - Clustering: Take a collection of 1,000,000 different genes, and find a way to automatically group these genes into groups that are somehow similar or related by different variables, such as lifespan, location, roles, and so on.
 - Non-clustering: The "Cocktail Party Algorithm", allows you to find structure in a chaotic environment. (i.e. identifying individual voices and music from a mesh of sounds at a cocktail party).

![PPT5](https://github.com/SicongLiang/Machine-Learning/blob/master/week1/5.JPG)
E.g., Google News automatically cluster them together

![PPT6](https://github.com/SicongLiang/Machine-Learning/blob/master/week1/6.JPG)
E.g., Understanding genomic. Measure how much they do or do not have a certain gene.

![PPT7](https://github.com/SicongLiang/Machine-Learning/blob/master/week1/7.JPG)
E.g., Other applications: Organize computing clusters, social network analysis, market segmentation and astronomical data analysis

Cocktail party problem  分离音频（两个人说话、一个人在音乐背景下说话）

![PPT8](https://github.com/SicongLiang/Machine-Learning/blob/master/week1/8.JPG)
![PPT9](https://github.com/SicongLiang/Machine-Learning/blob/master/week1/9.JPG)
- Octave to first prototype the learning algorithm

---------------------------------------------------------------------------------------------------------------------------------------
2.1 Model Representation
- First algorithm: Liner regression(线性回归) to know the overall process of supervised learning

![PPT10](https://github.com/SicongLiang/Machine-Learning/blob/master/week1/10.JPG)
E.g., Housing Prices

Training set(训练集) and Notations 
![PPT11](https://github.com/SicongLiang/Machine-Learning/blob/master/week1/11.JPG)

![PPT12](https://github.com/SicongLiang/Machine-Learning/blob/master/week1/12.JPG)
E.g., Univariate(One variable) linear regression

---------------------------------------------------------------------------------------------------------------------------------------
2.2 Cost Function(代价函数)
- Figure out how to fit the best possible straight line to our data 
We can measure the accuracy of our hypothesis function by using a cost function. This takes an average difference (actually a fancier version of an average) of all the results of the hypothesis with inputs from x's and the actual output y's.

![PPT13](https://github.com/SicongLiang/Machine-Learning/blob/master/week1/13.JPG)
- cost function(squared error function平方误差函数, squared error cost function平方误差代价函数)

---------------------------------------------------------------------------------------------------------------------------------------
2.3 Cost Function - Intuition I
- If we try to think of it in visual terms, our training data set is scattered on the x-y plane. We are trying to make a straight line (defined by hθ(x)) which passes through these scattered data points.

Our objective is to get the best possible line. The best possible line will be such so that the average squared vertical distances of the scattered points from the line will be the least. Ideally, the line should pass through all the points of our training data set. In such a case, the value of J(θ0,θ1) will be 0. The following example shows the ideal situation where we have a cost function of 0.

![PPT14](https://github.com/SicongLiang/Machine-Learning/blob/master/week1/14.JPG)

When θ1=1, we get a slope of 1 which goes through every single data point in our model. Conversely, when θ1=0.5, we see the vertical distance from our fit to the data points increase.

![PPT15](https://github.com/SicongLiang/Machine-Learning/blob/master/week1/15.jpg)

This increases our cost function to 0.58. Plotting several other points yields to the following graph:
![PPT16](https://github.com/SicongLiang/Machine-Learning/blob/master/week1/16.jpg)

Thus as a goal, we should try to minimize the cost function. In this case, θ1=1 is our global minimum.

---------------------------------------------------------------------------------------------------------------------------------------
2.4 Cost Function - Intuition II
- A contour plot is a graph that contains many contour lines. A contour line of a two variable function has a constant value at all points of the same line. An example of such a graph is the one to the right below.
![PPT17](https://github.com/SicongLiang/Machine-Learning/blob/master/week1/17.jpg)

Taking any color and going along the 'circle', one would expect to get the same value of the cost function. For example, the three green points found on the green line above have the same value for J(θ0,θ1) and as a result, they are found along the same line. The circled x displays the value of the cost function for the graph on the left when θ0 = 800 and θ1= -0.15. Taking another h(x) and plotting its contour plot, one gets the following graphs:
![PPT18](https://github.com/SicongLiang/Machine-Learning/blob/master/week1/18.jpg)

When θ0 = 360 and θ1 = 0, the value of J(θ0,θ1) in the contour plot gets closer to the center thus reducing the cost function error. Now giving our hypothesis function a slightly positive slope results in a better fit of the data.
![PPT19](https://github.com/SicongLiang/Machine-Learning/blob/master/week1/19.jpg)

The graph above minimizes the cost function as much as possible and consequently, the result of θ1 and θ0 tend to be around 0.12 and 250 respectively. Plotting those values on our graph to the right seems to put our point in the center of the inner most 'circle'.

---------------------------------------------------------------------------------------------------------------------------------------
