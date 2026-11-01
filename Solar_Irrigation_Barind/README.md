# Geospatial Assessment for Solar Irrigation Systems in the Barind Tract of Bangladesh

This notebook uses AHP weighted overlay to assess solar irrigation suitability in the Barind Tract. It normalizes the weights supplied in an external CSV, reclassifies ten raster factors, calculates a weighted suitability score, divides that score into five classes, and runs individual factor degradation scenarios.

Install the packages with `python -m pip install -r requirements.txt`. Open [Geospatial Assessment for Solar Irrigation Systems in the Barind Tract of Bangladesh.ipynb](<Geospatial Assessment for Solar Irrigation Systems in the Barind Tract of Bangladesh.ipynb>) in Jupyter, update `BASE_DIR` in the second cell, and run the cells in order. The original study datasets are required and are not included.

The expected inputs are `DBA.shp` and its companion files, `AHP/AHP.csv`, and these files in `V2/FINAL LAYERS`:

| Factor | Raster |
| --- | --- |
| Direct normal irradiance | `DNI.tif` |
| Land use and land cover | `LULC.tif` |
| Rabi rainfall | `Rabi_PR.tif` |
| Kharif 1 rainfall | `K1_PR.tif` |
| Kharif 2 rainfall | `K2_PR.tif` |
| Temperature | `TEMPERATURE.tif` |
| Distance from roads | `DIS_F_ROAD.tif` |
| Distance from rivers | `DIS_F_RIVERS.tif` |
| Relative relief | `RELATIVE_RELIEF.tif` |
| Cloudy days | `CLOUDY_DAYS.tif` |

`AHP.csv` contains factor names and numeric weights in two columns without a header. Factor names must match `LAYER_FILES` in the notebook. The supplied weights are normalized to sum to one; the notebook does not derive a pairwise comparison matrix or calculate an AHP consistency ratio.

The original directions of suitability, LULC score mapping, quantile classification, weighted overlay, equal interval final classification, and five sensitivity scenarios are retained. The sensitivity scenarios set DNI, LULC, Rabi rainfall, temperature, and cloudy days individually to class 1 while retaining the other factors and weights.

Two methodological choices from the supplied notebook are retained: all inputs, including LULC, use bilinear resampling before reclassification, and suitability class breaks are recalculated separately for each degradation scenario. Scenario class percentages therefore use their own score ranges. The analysis grid uses EPSG:32645 with a nominal resolution of 30 m, and area summaries use the original nominal pixel area calculation.

Outputs are written to `V2/OUTPUT`. `Solar_Irrigation_Suitability.tif` and `Solar_Irrigation_Suitability_Classified.tif` are georeferenced rasters. The other map and chart exports are display images, including the TIFF figures.

Comments, section banners, decorative symbols, and repetitive console messages have been removed. Numerical and spatial processing were compared against the supplied notebook using synthetic inputs. The original study analysis has not been rerun here, and saved notebook outputs are cleared.
