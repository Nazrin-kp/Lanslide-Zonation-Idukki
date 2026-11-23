<img width="657" height="639" alt="Screenshot 2026-11-23 at 3 01 06 PM" src="https://github.com/user-attachments/assets/276232c0-a8f9-4fcb-be08-2c634a7b7caf" /># Landslide Hazard Zonation Mapping using GIS, Remote Sensing and AHP

## Overview

This project presents a **Landslide Susceptibility (Hazard Zonation) Map** for **Idukki District, Kerala, India** using **Geographic Information Systems (GIS)**, **Remote Sensing** and the **Analytical Hierarchy Process (AHP)**. The objective is to identify areas with different levels of landslide susceptibility to support disaster risk reduction and land use planning.

The map is validated against **2,185 mapped landslides** from the 2018 Kerala monsoon (AUC = 0.74).

The entire workflow was developed in **Python using Google Colab**, with raster processing, visualization and weighted overlay analysis performed using open source geospatial libraries.

<p align="center">
  <img src="<img width="657" height="639" alt="Screenshot 2026-11-23 at 3 01 06 PM" src="https://github.com/user-attachments/assets/cb060564-63e8-4169-ac77-28d82bd7acb7" />
">
</p>

---

## Study Area

- **Location:** Idukki District, Kerala, India
- **Terrain:** Mountainous region of the Western Ghats
- **Major Hazard:** Rainfall induced landslides

---

## Methodology

The susceptibility model was developed using the **Analytical Hierarchy Process (AHP)**.

### Workflow

1. DEM preprocessing
2. Terrain analysis (slope and aspect)
3. Hydrological analysis (drainage density)
4. NDVI generation
5. Land Use / Land Cover (LULC) processing
6. Rainfall processing
7. Raster alignment and reclassification
8. AHP weight assignment (consistency ratio 0.012, below the 0.10 limit)
9. Landslide Susceptibility Index (LSI) computation
10. Susceptibility classification (five classes using quantile breaks, 20% of the district each)
11. Validation against the 2018 Kerala landslide inventory
12. Export of final outputs

---

## Conditioning Factors

The final susceptibility model uses six conditioning factors:

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

Due to GitHub file size limitations, the datasets used in this study are hosted separately:

**Dataset:** https://drive.google.com/drive/folders/12lpMEmCydKSURo0EAerpUobpOKccTZSm?usp=sharing

The landslide inventory used for validation is available from DANS:

van Westen, C.J. (2020). *Landslide inventory of the 2018 monsoon rainfall in Kerala, India.* DANS. https://doi.org/10.17026/DANS-X6C-Y7X2 (CC BY 4.0). See also Hao et al. (2020), *Earth System Science Data*, 12, 2899.

---

## Validation

The map was validated against **2,185 landslides** from the 2018 Kerala monsoon inventory (van Westen, 2020), using the AUC (area under the ROC curve) and the frequency ratio (FR).

| Class | Landslides (%) | Area (%) | Frequency Ratio |
|---|---|---|---|
| Very Low | 3.6 | 20 | 0.18 |
| Low | 7.2 | 20 | 0.36 |
| Moderate | 13.9 | 20 | 0.70 |
| High | 25.4 | 20 | 1.27 |
| Very High | 49.9 | 20 | 2.49 |

- **AUC = 0.738**, which is acceptable discrimination.
- The Very High class covers 20% of the area and contains about 50% of the landslides. High and Very High together cover 40% of the area and contain about 75% of the landslides.
- A frequency ratio above 1 means more landslides than expected by chance.

<p align="center">
  <img src="AHP_validation.png" width="85%" alt="ROC curve and frequency ratio by class">
</p>

An earlier check with only 7 events from the NASA Global Landslide Catalog gave an AUC of about 0.56, close to chance. It was too small to be reliable, so it was replaced by the full inventory validation above.

### Limitations

- The inventory covers a single event (2018).
- Many landslides are cut slope and road failures, so part of the pattern may reflect human disturbance.
- NDVI (2024) and land cover (2021) are from after 2018.
- Non landslide points are random pixels, not confirmed stable ground.
- Soil depth, curvature and complete lithology are not included.

---

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
│   ├── 09_Final_Model_v2.ipynb
│   ├── 10_AHP_Validation_only.ipynb
│   └── old/   (earlier versions, kept for reference)
│
├── data/
├── outputs/
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
- SciPy
- scikit-learn
- GIS and Remote Sensing
- Analytical Hierarchy Process (AHP)

---

## Outputs

The project generates:

- Landslide Susceptibility Index (LSI)
- Classified susceptibility map
- Area percentage statistics
- Validation results (AUC and frequency ratio)
- GeoTIFF outputs
- PNG visualizations

---

## Applications

- Preliminary landslide susceptibility screening
- Support for disaster management and land use planning
- Starting point for infrastructure and environmental planning

*This map is indicative and is not a substitute for site level geotechnical investigation.*

---

## Future Improvements

- Compare AHP with a Random Forest model using spatial cross validation
- Add curvature, soil depth, distance to roads and streams
- Integrate lithology with complete geological datasets
- Web GIS deployment for interactive visualization

---

## Author

**Nazrin Khan P**

B.Tech Civil Engineering
Cochin University of Science and Technology (CUSAT)
