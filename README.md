# Geodetector

## Define
`Spatial Stratified Heterogeneity (SSH)` refers to the phenomena that the within strata are more similar than the between strata. Examples are landuse types and climate zones in spatial data, seasons and years in time series, occupations, age groups, incomes strata. SSH occurs in all scales from universe to DNA, offers windows for human beings to understand the nature since Aristotle time.

## Tasks
Each of the tasks can be accomplished by the Geodetector `q-statistic`

Geodetector: measure SSH and to make attribution for/by SSH (Fig. 1)
![Fig.1 Principle of Geodetector](http://www.geodetector.cn/index.files/image018.jpg)

1. measure and find SSH among data;
2. test the coupling between two variables Y and X, according to their SSHs, without assumption of linearity of the association;
3. investigate **interaction between two explanatory variables** X1 and X2 to a response variable Y, without any specific form of interaction such as the assumed product in econometrics (Fig. 2). 
![Fig.2 Interaction between explanatory variables X1 and X2 impacting on a response variable Y: q(Y|X1X2).](http://www.geodetector.cn/index.files/image043.jpg)


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

1. `Confounding arises` if a global model was applied to a SH population, leading to statistical insignificance. The problem can be simply avoided if SH is identified (by Geodetector q statistic) then `modelling in the strata, separately`.
2. `A sample would be biased` if a population is SH and the sample do not cover all strata. The problem can be solved if SH is identified (by Geodetector q statistic) then `apply bias remedy models` such as `Heckman regression` and `Bshade method`.
3. Local models aim to overcome heterogeneity but often suffer `overfitting` and too many parameters to interpret. The problems can be avoided if `modelling in strata` or `stratifying the outputs of a local model` then interpreting the stratified parameters.

## Functions of Geodetector:

1. The `risk detector` maps response variable in strata: Y(X);
2. The `factor detector` q-statistic measures the degree of SH of a variable Y; and the determinant power of an explanatory variable X of Y;
3. The `ecological detector` identifies the difference of the impacts on Y between two explanatory variables X1 ~ X2;
4. The `interaction detector` reveals whether the risk factors X1 and X2 (and more X) have an interactive influence on a response variable Y (Fig.2).
