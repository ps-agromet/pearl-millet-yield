# Data

All rasters and shapefiles are in geographic coordinates (WGS 84, EPSG:4326), except `shape/Jodhpur_block`, which uses WGS 84 India NSF LCC.

| Folder / file | Content | Source | Licence |
|---|---|---|---|
| `weather/<DISTRICT>.csv` | Daily solar radiation, Tmax, Tmin, RH, wind speed at 2 m, corrected rainfall, 1990–2022, at each district centroid | [NASA POWER](https://power.larc.nasa.gov/) (MERRA-2 / CERES), daily, native resolution | Free to use; NASA asks for acknowledgement |
| `weather_aquacrop/<DISTRICT>.txt` | Day, Month, Year, Tmin, Tmax, rainfall, ET0 (FAO-56), in AquaCrop format | Made from `weather/` by `notebooks/01_ET0_calculation.ipynb` | as above |
| `soil/Rajasthan_<property>_<depth>_mean.tif` | Properties: bulk density (`bod`), CEC, coarse fragments (`cfvo`), clay, nitrogen, organic carbon density (`ocd`), pH (`phh2o`), sand, silt, SOC, and WRB soil class. Depths: 0–5, 5–15, 15–30, 30–60, 60–100, 100–200 cm | [SoilGrids 2.0](https://soilgrids.org) (ISRIC), clipped to Rajasthan | CC BY 4.0 |
| `soil/Rajasthan_wp_*`, `soil/Rajasthan_airdry_*` | Water content at wilting point and air-dry (m³ m⁻³) | Derived layers. 
| `location data/Rajasthan.shp` | 33 district boundaries (STATE_NAME, DISTRICT) | Subset of an all-India district shapefile. 
| `location data/location.csv` | District centroids used to download NASA POWER data | Derived from `Rajasthan.shp` | — |
| `location data/Rajasthan_PM_{mean,CV,weather}.shp` | District mean yield, CV and seasonal weather by sowing date | Output of `notebooks/04_district_mean_cv.ipynb` | — |
| `shape/` | Rajasthan (with centroids), Jodhpur district, Jodhpur blocks, map extract | 
| `observed_yield/Report_DES.xls` | District-wise pearl millet area, production, yield | Directorate of Economics & Statistics (DES), Govt. of India. | Government open data |
| `observed_yield/benchmark_yield_rajasthan_dashboard_pm.csv` | District yield, area, production, 1966 onwards | 
| `observed_yield/baselineYield.xlsx` | Baseline yields |

District names follow the shapefile spelling (for example `JAISELMER`, `PRATAPGARH1`). Weather file names must match these names exactly.

Soil rasters have no nodata value set. Pixels outside Rajasthan are stored as 0.
