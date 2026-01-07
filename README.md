Satellite Imagery–Based Property Valuation

Overview
This project focuses on predicting residential property prices using machine learning. It combines traditional tabular housing features with satellite imagery to study whether visual neighborhood context can improve valuation accuracy beyond numerical data alone.

Dataset
The dataset consists of historical housing records with price as the target variable.
Key tabular features include bedrooms, bathrooms, sqft_living, sqft_lot, floors, condition, grade, view, waterfront, sqft_living15, sqft_lot15, latitude, and longitude.
The target variable (price) was log-transformed during training to reduce skewness and improve model stability.

Satellite imagery was fetched using latitude–longitude coordinates at high zoom levels to capture neighborhood characteristics such as greenery, road layout, and density.

Methodology
First, baseline regression models were trained using only tabular data: Linear Regression, Random Forest, and XGBoost.
Next, satellite images were processed using a pre-trained ResNet-50 model to extract fixed image embeddings representing visual context.
For multimodal learning, scaled tabular features were concatenated with image embeddings and used to train an XGBoost regressor.

Results
Model performance was evaluated using RMSE and R² on a validation split.

Linear Regression (Tabular): R² ≈ 0.72
Random Forest (Tabular): R² ≈ 0.86
XGBoost (Tabular): R² ≈ 0.89
XGBoost (Tabular + Image): R² ≈ 0.90

The multimodal XGBoost model achieved a small but consistent improvement over the tabular-only baseline, indicating that satellite imagery provides complementary neighborhood-level information.

Explainability
Feature importance analysis showed that sqft_living, grade, and location are the strongest predictors. Visual analysis of satellite images and Grad-CAM highlighted green spaces, road networks, and open areas as influential regions.

Conclusion
Tree-based models, particularly XGBoost, are highly effective for property valuation using tabular data. Satellite imagery adds meaningful contextual information and demonstrates potential for improving real estate valuation when combined with structured features.

