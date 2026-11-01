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

The analysis grid uses EPSG:32645 with a nominal resolution of 30 m, and area summaries use the original nominal pixel area calculation.
