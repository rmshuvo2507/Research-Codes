# DELINEATION OF FRESH GROUNDWATER ZONE IN THE COASTAL AQUIFERS OF BANGLADESH

The notebook classifies groundwater as fresh when measured electrical conductivity is below 1,000 µS/cm. It compares SVM, RF, GBM, XGBoost, and KNN and produces non-saline groundwater potential maps for six districts located in the north of the Sundarbans. The main purpose of the research was to examine the extent of salinity intrusion pathway already occured in the coastal areas of Bangladesh. 

Install the packages with `python -m pip install -r requirements.txt`. Open the notebook in Jupyter, set `BASE_DIR` to the GIS project directory, and run the cells in order. The study rasters and shapefiles are not included in this repository due to their storage limits. 

VIF screening stops at 15. The expected final parameters are DD (Drainage Density), DIS_Rivers (Distance from Major Rivers), GwCl (Groundwater Chloride), GwEC (Groundwater Electric Conductivity), GwL (Groundwater Level), GwS (Groundwater Salinity), LULC (Land Use Land Cover), Soil_Perm (Soil Permeability), TPI (Topographic Position Index), and TRI (Topographic Ruggedness Index). 

The original stratified random 80:20 split, random seed of 42, model settings, and training only SMOTE procedure are retained. Validation includes accuracy, ROC AUC, precision recall curves, average precision, confusion matrices, sensitivity, specificity, precision, F1, Cohen's kappa, and classification reports for all five models. Outputs are written to `OUTPUT`.

Groundwater chemistry rasters are interpolated before the sample split, as in the original workflow. Because EC also defines the response, held out observations may influence predictor construction. These scores require caution when assessing performance at independent locations.
