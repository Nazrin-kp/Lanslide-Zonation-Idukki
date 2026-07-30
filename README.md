# Landslide Hazard Zonation Mapping using GIS, Remote Sensing and AHP

## Overview

This project presents a **Landslide Hazard Zonation (LHZ) Map** for **Idukki District, Kerala, India** using **Geographic Information Systems (GIS)**, **Remote Sensing**, and the **Analytical Hierarchy Process (AHP)**. The objective is to identify areas with varying levels of landslide susceptibility to support disaster risk reduction and land-use planning.

The entire workflow was developed in **Python using Google Colab**, with raster processing, visualization, and weighted overlay analysis performed using open-source geospatial libraries.

---

## Study Area

- **Location:** Idukki District, Kerala, India
- **Terrain:** Mountainous region of the Western Ghats
- **Major Hazard:** Rainfall-induced landslides

---

## Methodology

The landslide susceptibility model was developed using the **Analytical Hierarchy Process (AHP)**.

### Workflow

1. DEM preprocessing
2. Terrain analysis
3. Hydrological analysis
4. NDVI generation
5. Land Use/Land Cover (LULC) processing
6. Rainfall processing
7. Raster alignment and reclassification
8. AHP weight assignment
9. Landslide Susceptibility Index (LSI) computation
10. Susceptibility classification
11. Export of final outputs

---

## Conditioning Factors

The final susceptibility model uses the following six conditioning factors:

- Slope
- Aspect
- Drainage Density
- Rainfall
- NDVI (Normalized Difference Vegetation Index)
- Land Use / Land Cover (LULC)

### Note

Lithology (Geology) was initially considered but excluded from the final model because the available geological sheet (58C13) did not provide complete spatial coverage of the study area.
---

## Data Availability

Due to GitHub file size limitations, the complete datasets used in this study are hosted separately. They are available at the following link:

**Dataset:** https://drive.google.com/drive/folders/12lpMEmCydKSURo0EAerpUobpOKccTZSm?usp=sharing

## Validation

The final landslide susceptibility map was qualitatively validated using **7 historical landslide events** extracted from the "NASA Global Landslide Catalog". Historical landslide locations were overlaid on the final susceptibility map, and raster values were sampled at each event location. **All seven documented landslide events (100%) were located within the High or Very High susceptibility zones**, demonstrating strong agreement between the AHP-based susceptibility model and historical landslide occurrences in the study area.

## Repository Structure

```text
Landslide-Hazard-Zonation/
│
├── notebooks/
│   ├── 01_DEM_Preprocessing.ipynb
│   ├── 02_Terrain_Analysis.ipynb
│   ├── 03_Hydrological_Analysis.ipynb
│   ├── 04_NDVI_Analysis.ipynb
│   ├── 05_LULC_Analysis.ipynb
│   ├── 06_Rainfall.ipynb
│   └── 07_Landslide_Hazard_Zonation_AHP.ipynb
│
├── data/
│
├── outputs/
│
├── README.md
├── requirements.txt
└── .gitignore
```

---

## Technologies Used

- Python
- Google Colab
- Rasterio
- NumPy
- Pandas
- Matplotlib
- GeoPandas
- GDAL
- GIS & Remote Sensing
- Analytical Hierarchy Process (AHP)

---

## Outputs

The project generates:

- Landslide Susceptibility Index (LSI)
- Classified Hazard Map
- Hazard Distribution Histogram
- Area Percentage Statistics
- GeoTIFF outputs
- PNG visualizations

---

## Applications

- Landslide risk assessment
- Disaster management
- Land-use planning
- Infrastructure planning
- Environmental impact assessment

---

## Future Improvements

Potential enhancements include:

- Integration of lithology with complete geological datasets
- Machine learning-based susceptibility modelling
- Validation using historical landslide inventory
- Web GIS deployment for interactive visualization

---

## Author

**Nazrin Khan**

B.Tech Civil Engineering  
Cochin University of Science and Technology (CUSAT)
