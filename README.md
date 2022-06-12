# Capstone Project

**Author**: [Nat Berryman](https://github.com/natberr)

## Project Overview

The purpose of this regression model is to predict the global sales of Video Games by analysing the Video Game Sales
dataset from Kaggle https://www.kaggle.com/datasets/xtyscut/video-games-sales-as-at-22-dec-2016csv.

### Business Problem

VG Corp. have moved into the Video Game industry and want a predictive model to understand what video games to produce.

To assist VG Corp. in making the right decisions I intended to determine what certain varibales have on sale prices:
1. Platform
2. Genre
3. Publisher
4. Critic/User Score

### The Data

This project uses the Video Game Sales dataset, which can be found in  `Video_Games_Sales_as_at_22_Dec_2016.csv` in the data folder in this repo.

**Data Cleaning**
- Dropped unnecessary data
- Replaced or removed null values
- Put Publisher data into Small, Medium and Large buckets
- Ensured Critic Score and User Score used consistent metrics by mulitplying User Score by 10
- Split data set between continuous and categorical data
- As model matures, I added platform into developer buckets E.G. SNES and Gameboy into Nintendo bucket


### Exploratory Data Analysis

**Key Features include:**
- D
- Square Foot living space
- Grade
- Latitude
- Square Foot Above
- Square Foot Living 15 (neighbors)

**Notes:** 
- Zip code excluded as data-type is a string
- Latitude correlates with price more than Longitude

I then created price vs zip code graph to explore price distribution across zip codes and then plotted to a heatmap.
Using these visualization I created  a new variable – **km_from_cbd**

Used mean normalization to standardise the data
Used Histogram, KDE plot and joint plot to explore data

### Models

**Model 1**
- Used selected features identified in repo.
- R^ 0.527, however multiple variables had negative R^
- Residual graph was good

![](./images/Model1_OLS.png)
![](./images/model1_resid.png)

**Model 2**
- Used fewer variable in features (kept bathrooms, sqft living, sqft living15 and high grade)
- R^ 0.413
- Residual graph was good

![](./images/Model2_OLS.png)
![](./images/model2_resid.png)

**Model 3**
- Selected features included all variables with positive R^
- R^ 0.524
- Residual graph was good

![](./images/Model3_OLS.png)
![](./images/model3_resid.png)

### Conclusions

- I determined Model 3 was the must accurate model by using all features with postive R^ and removing variables with negative R^.
- Selected features all statistically significant with p-value <0.05
- sqft living15 coef – 0.2791
- sqft living coef – 0.3956
- distance from CBD coef - 0.3434
- bathrooms coef – 0.0645
- high grade rating coef– 0.4590
- These Coef figures mean for unit increase in any one of these variables there was in increase in price by ~0.3 units.

![](./images/price_predict2.png)

### For More Information

Please review the full analysis in [my Jupyter Notebook](http://localhost:8888/notebooks/Desktop/AcademyXI/ProjectTwo/dsc-phase-2-project/Project_Two/kc_house_price_regression_modelling.ipynb) or my [presentation pack](http://localhost:8888/files/Desktop/AcademyXI/ProjectTwo/dsc-phase-2-project/Project_Two/Regression%20Modelling%20Presentation.pdf).

For any additional questions, please contact **Nat Berryman** - nathaniel.berryman@gmail.com

### Repository Structure

```
├── data
├── images
├── kc_house_price_regression_modelling.ipynb
├── README.md
└── regression modelling presentation.pdf
```