# NO2-emission-prediction
# GeoAI Ground-Level NO2 Estimation Challenge  

This project addresses the challenge of estimating surface NO2 concentrations using machine learning models trained on publicly available remote sensing data. Leveraging ground truth data from air quality monitoring stations and Google Earth Engine (GEE)-processed data, the goal is to develop transparent, reproducible, and robust models.  

The models are evaluated both spatially and temporally to ensure adaptability across different weather conditions and seasons. Key aspects include clear documentation, reproducible code, and innovative approaches to NO2 monitoring and modeling.
*Thanks to Zindi and GeoAI for organizing this competition!
I joined the competition in the last 14 days, and it was a great experience.
Preprocessing
1. Feature Engineering:  
   - Created features based on longitude and latitude.  
   - Engineered some combination features to capture interactions between variables.
2. Data Cleaning:  
   - Removed three towns where the mean monthly NO₂ emissions were significantly different from the others. These anomalies negatively impacted the model's performance.  
3. Imputation:  
   - Used forward fill (`ffill`) and mean imputation to handle missing data.
Training
1. Model Ensembling:  
   - Used an ensemble of two tree-based models for predictions witha custom cross validation method to avoid the leak . 
Postprocessing
1. Adjustment by Coefficients :  
   - Adjusted results for each town using specific coefficients.  
   - Applied different coefficients for predictions before and after 01-01-2020.
2. Handling Similar Towns:  
   - For towns with very close counterparts in the training set, assigned values directly based on those counterparts.  
   - Alternatively, created a model trained only on the specific town's data (date and target). This overfit model was used for predictions on similar nearby towns.
This was our approach in brief.
