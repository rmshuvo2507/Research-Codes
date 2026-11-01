# Research Codes

## DELINEATION OF FRESH GROUNDWATER ZONE IN THE COASTAL AQUIFERS OF BANGLADESH

The notebook classifies groundwater as fresh when measured electrical conductivity is below 1,000 µS/cm. It compares SVM, RF, GBM, XGBoost, and KNN and produces groundwater probability maps for the study area excluding the Sundarbans.

Install the packages with `python -m pip install -r requirements.txt`. Open the notebook in Jupyter, set `BASE_DIR` to the GIS project directory, and run the cells in order. The study rasters and shapefiles are required and are not included in this repository. The directory structure follows the original GIS project: `DEM_V2`, `Study Area`, `LULC`, `Rainfall CRU`, `Groundwater`, `Soil Data`, `NDVI`, and `FINAL LAYERS`. The existing distance from rivers and LULC rasters must be available in the final raster directory before alignment.

VIF screening stops at 15. The expected final parameters are DD, DIS_Rivers, GwCl, GwEC, GwL, GwS, LULC, Soil_Perm, TPI, and TRI. The notebook checks that the study inputs reproduce this selection.

The original stratified random 80:20 split, random seed of 42, model settings, and training only SMOTE procedure are retained. Validation includes accuracy, ROC AUC, precision recall curves, average precision, confusion matrices, sensitivity, specificity, precision, F1, Cohen's kappa, and classification reports for all five models. Outputs are written to `OUTPUT`.

Groundwater chemistry rasters are interpolated before the sample split, as in the original workflow. Because EC also defines the response, held out observations may influence predictor construction. These scores require caution when assessing performance at independent locations.

Saved notebook outputs are cleared. The revised ML and validation cells were checked with synthetic data; the full GIS analysis must be rerun with the study inputs.
