# Geodetector
[Source:Wang JF,Geodetector](http://www.geodetector.cn/)
## Define
`Spatial Stratified Heterogeneity (SSH)` refers to the phenomena that the within strata are more similar than the between strata. Examples are landuse types and climate zones in spatial data, seasons and years in time series, occupations, age groups, incomes strata. SSH occurs in all scales from universe to DNA, offers windows for human beings to understand the nature since Aristotle time.

Spatial stratified heterogeneity (SSH), referring to the within strata are more similar than the between strata, such as landuse types and climate zones, is ubiquitous in spatial data. SSH instead of random is a set of information, which has been being a window for humans to understand the nature since Aristotle time. In another aspect, a model with global parameters would be confounded if input data is SSH, the problem dissolves if SSH is identified so simple models can be applied to each stratum separately. Note that the “spatial” here can be either geospatial or the space in mathematical meaning.


where N and σ2 stand for the number of units and the variance of Y in study area, respectively; the population Y is composed of L strata (h = 1, 2, …, L), Nh and σh2 stand for the number of units and the variance of Y in stratum h, respectively. The strata of Y (red polygons in Figure 1) are a partition of Y, either by itself ( h(Y) in Figure 1) or by an explanatory variable X which is a categorical variable ( h(Y) in Figure 1). X should be stratified if it is a numerical variable, the number of strata L might be 2-10 or more, according to prior knowledge or a classification algorithm.

## Tasks
Each of the tasks can be accomplished by the Geodetector `q-statistic`
where N and σ2 stand for the number of units and the variance of Y in study area, respectively; 

Geodetector: measure SSH and to make attribution for/by SSH (Fig. 1)

![Fig.1 Principle of Geodetector](http://www.geodetector.cn/index.files/image018.jpg)

1. measure and find SSH among data;
2. test the coupling between two variables Y and X, according to their SSHs, without assumption of linearity of the association;
3. investigate **interaction between two explanatory variables** X1 and X2 to a response variable Y, without any specific form of interaction such as the assumed product in econometrics (Fig. 2).  
![Fig.2 Interaction between explanatory variables X1 and X2 impacting on a response variable Y: q(Y|X1X2)](http://www.geodetector.cn/index.files/image043.jpg)


## Interpretation of q value (Fig.1).

The value of q is strictly `within [0, 1]`.

1. If Y is stratified by `Y itself`:
  - q = 0 indicates that Y is absent of SH
  - q = 1 indicates that Y is SH perfectly
  - 100q% measures the degree of SH of Y.
2. If Y is stratified by an `explanatory variable X`
  - then q = 0 indicates that there is no coupling between Y and X
  - q = 1 indicates that Y is completely determined by X
  - X explains 100q% of Y.
  **Please notice that the q-statistic measures the association between X and Y, both linearly and nonlinearly.**

Geodetector q statistic helps understand **spatial confounding, sample bias and overfitting.**

1. `Confounding arises` if a global model was applied to a SH population, leading to statistical insignificance. The problem can be simply avoided if SH is identified (by Geodetector q statistic) then **modelling in the strata, separately**.
2. `A sample would be biased` if a population is SH and the sample do not cover all strata. The problem can be solved if SH is identified (by Geodetector q statistic) then **apply bias remedy models** such as `Heckman regression` and `Bshade method`.
3. Local models aim to overcome heterogeneity but often suffer `overfitting` and too many parameters to interpret. The problems can be avoided if **modelling in strats** or **stratifying the outputs of a local model** then interpreting the stratified parameters.

## Functions of Geodetector:

1. The `risk detector` maps response variable in strata: Y(X);
2. The `factor detector` q-statistic measures the degree of SH of a variable Y; and the determinant power of an explanatory variable X of Y;
3. The `ecological detector` identifies the difference of the impacts on Y between two explanatory variables X1 ~ X2;
4. The `interaction detector` reveals whether the risk factors X1 and X2 (and more X) have an interactive influence on a response variable Y (Fig.2).

## Tutorial of Geodetector
> Note: Y is numerical; **X MUST be categorical**, e.g. landuse types, seasons. If X is numerical it should be transformed to be categorical, e.g. GDP per capita is stratified into 5 strata

### script


### output
Geodetector output 4 files:
1. risk detector
2. factor detector
3. ecological detector
4. interaction detector.

#### 1.Risk detector 
The results of **each environmental risk factor** are presented in two table: 
1. The first table gives the **average Y in each stratum** of a risk factor. 
2. The second table gives the statistically significant difference in the average Y **between two strata** of X; if there is a significant difference, the corresponding value is “Y”, else it is “N”.

#### 2.Factos detector
Present the each environmental risk factor's **q values and p values**.

#### 3.Ecological detector
Present the statistically significant differences between two environmental risk factors. If Y(X1) (risk factor names in row) was significantly bigger than Y(X2) (risk factor names in column), the associated value is “Y”, while “N” expresses the opposite meaning.

#### 4.Interaction detector
“Interaction relationships” represent the interaction relationship for the two factors. The relationship is defined in a coordinate axis. It has 5 intervals, including - “(-∞，min(q(x), q(y)))”
- “(min(q(x), q(y)), max(q(x), q(y)))”
- “(max(q(x), q(y)), q(x) + q(y))”
- “q(x) + q(y)”
- “( q(x) + q(y),+∞)”

The interaction relationship is determined by the location of q(xÇy) in the 5 intervals.
