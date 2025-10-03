# Impact-of-Urbanization-on-Different-Land-Cover-Classes
Investigated Delhi’s rapid, unplanned urbanization, where growth has not translated into improved quality of life using remote sensing and GIS tools to support sustainable urban planning.

---

##  1. Introduction  

Urbanization is one of the most significant drivers of environmental and socio-economic change globally.  
In **Delhi**, India’s capital and a rapidly growing megacity, the impacts of urban expansion are particularly visible.  

This repository documents a **Google Earth Engine (GEE) project** analyzing **land cover transformations in Delhi between 2022 and 2023 using Sentinel-2 imagery**.  

The workflow includes:  
- Land use/land cover (LULC) classification with Random Forest  
- Accuracy assessment (confusion matrix, overall accuracy, kappa)  
- Change detection (2022 vs 2023)  
- Area statistics for each class  

---

##  2. Research Motivation  

Delhi has undergone dramatic transformation:  
- **Population Growth** → Migration-driven increase in population density  
- **Built-Up Expansion** → Conversion of green/agricultural land into concrete infrastructure  
- **Environmental Challenges** → Declining vegetation cover, shrinking water bodies, worsening air quality  

Understanding these changes is critical for sustainable development and urban planning.  

---

##  3. Objectives  

1. **Characterize Urban Expansion**  
   - Map and classify urban, vegetation, water, forest, and bareland  

2. **Assess Environmental Impacts**  
   - Quantify vegetation reduction, water shrinkage, and bareland change  

3. **Perform Change Detection**  
   - Detect pixel-level changes between 2022 and 2023  

4. **Support Planning**  
   - Provide evidence-based insights for policymakers  

---

##  4. Data & Tools  

**Data Sources**  
- **Sentinel-2 Surface Reflectance (S2_SR)** – 10m resolution, cloud-masked  
- **Delhi NCR Shapefile** – Imported as GEE asset for study boundary  

**Tools**  
- **Google Earth Engine (JavaScript API)**  
- Random Forest Classifier (built-in GEE ML library)  

---

##  5. Methodology  

The pipeline is divided into **13 parts** :  

1. **Define ROI (Delhi NCR)** – Import shapefile into GEE assets  
2. **Import Sentinel-2 Dataset** – Acquire S2_SR imagery  
3. **Cloud Masking** – Remove clouds & cirrus using QA60 band  
4. **Filter 2023 Imagery** – Median composite (Jan–Dec 2023)  
5. **Filter 2022 Imagery** – Median composite (Jan–Dec 2022)  
6. **Visualization** – Add composites to the map (true color: B4, B3, B2)  
7. **Training Data Merge** – Urban, Water, Vegetation, Forest, Bareland samples  
8. **Train-Test Split** – 80% training, 20% testing  
9. **Classifier Training** – Random Forest with 50 trees  
10. **Classification** – Generate 2022 & 2023 land cover maps  
11. **Accuracy Assessment** – Confusion matrix, OA, Kappa  
12. **Change Detection** – Pixel-wise comparison of 2022 vs 2023  
13. **Area Estimation** – Compute area (m²) of each land cover class  

---

##  6. Literature Review  

- **Random Forest (RF)** widely applied in remote sensing due to robustness against noise  
- **Delhi-focused studies** highlight urban sprawl, shrinking wetlands, and vegetation loss  
- **Global context**: urban expansion linked with biodiversity loss, heat island effects, and socio-economic disparities  

---

##  7. Significance  

This project demonstrates how **Google Earth Engine + Machine Learning** can:  
- Rapidly classify LULC using free satellite data  
- Quantify environmental change with high accuracy  
- Provide actionable insights for sustainable city planning  

---


