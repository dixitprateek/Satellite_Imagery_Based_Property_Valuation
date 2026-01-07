Satellite Imagery–Based Property Valuation

Overview  
This project aims to predict residential property prices using machine learning. The core objective is to evaluate the effectiveness of traditional tabular housing features and explore whether satellite imagery can provide additional neighborhood-level context to improve valuation accuracy.

Dataset  
The dataset consists of historical housing records with price as the target variable.  
Key tabular features include bedrooms, bathrooms, sqft_living, sqft_lot, floors, condition, grade, view, waterfront, sqft_living15, sqft_lot15, latitude, and longitude.  
The target variable (price) was log-transformed during training to reduce skewness and improve model stability.

Satellite images were programmatically fetched using latitude and longitude coordinates at a high zoom level to capture neighborhood characteristics such as greenery, road layout, and density.

Methodology  
Multiple regression models were trained using tabular data, including Linear Regression, Random Forest, and XGBoost.  
Satellite imagery was processed using a pre-trained ResNet-50 model to extract fixed image embeddings representing visual neighborhood context.  
For multimodal learning, scaled tabular features were concatenated with image embeddings and used to train an XGBoost regressor.

Results  
Model performance was evaluated using RMSE and R² on a validation split.

Linear Regression (Tabular): R² ≈ 0.72  
Random Forest (Tabular): R² ≈ 0.86  
XGBoost (Tabular): R² ≈ 0.89  
XGBoost (Tabular + Image): R² ≈ 0.90  

The multimodal XGBoost model achieved a modest but consistent improvement over the tabular-only baseline, indicating that satellite imagery provides complementary neighborhood-level information.

Explainability  
Feature importance analysis showed that sqft_living, grade, and location features are the strongest predictors.  
Visual inspection of satellite images and Grad-CAM analysis highlighted green spaces, road networks, and open areas as influential regions.


Author  
Prateek Dixit
(IIT Roorkee)
