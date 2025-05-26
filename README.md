# Freshwater Cultural Ecosystem Services – Large Scale Modelling Framework

This repository implements a framework for large-scale modelling of freshwater Cultural Ecosystem Services (CES), structured around four main Python scripts and supported by key data files.

---

## Developed by

- **Francesc Comalada** (Main developer, ICRA) – [fcomalada@icra.cat](mailto:fcomalada@icra.cat)  
- **Vicenç Acuña** (Supervision, ICRA)  
- **Xavier Garcia** (Supervision, ICRA)  

Please contact us if you have questions or suggestions: fcomalada@icra.cat

---

## Repository Structure

### `coordinates/` – Bounding Box Input

Contains an example Excel file (`Bounding_box_example.xlsx`) defining bounding boxes along a river. Each row should contain:

- `sw_lat`: southwest latitude  
- `sw_lon`: southwest longitude  
- `ne_lat`: northeast latitude  
- `ne_lon`: northeast longitude  

### `model_path/` – Pre-trained CES Classifier

Includes a ResNet152 `.pth` file trained to classify images into five CES categories.

### `scripts/` – Core Components

Four Jupyter notebooks performing the full modelling pipeline (described below).

---

## How to Use the Framework (in Visual Studio Code)

1. Install [Visual Studio Code](https://code.visualstudio.com/)  
2. Download the folder `CES Modelling` from this repository  
3. Open it in VS Code via `File > Open Folder`  
4. Navigate to `/notebooks/AI_Model.ipynb` and open it  
5. Install [Python 3.10.3](https://www.python.org/downloads/release/python-3103/)  
6. In VS Code, click `Select Kernel > Python Environments...`, and choose `.venv (Python 3.10.3)`  
7. Run the notebooks inside `scripts/` sequentially  

---

## Script Descriptions

### `01_Photo_extraction.ipynb`

- Downloads geolocated Flickr photos using bounding box and time filters.

### `02_AI_Model.ipynb`

- Classifies images into CES categories using a pre-trained ResNet152 CNN.
- Achieves ~91% classification accuracy.

### `03_Metadata_retrival.ipynb`

- Extracts and structures metadata (timestamp, user ID, geolocation, etc.) from classified images.

### `04_CES_Modelling.ipynb`

- Builds predictive models (XGBoost) linking CES presence to predictors like NDVI, population density, naturalness, and river order.
- Includes residual analysis, spatial autocorrelation (Moran's I), and interpolation, and mapping.

---

## Data Handling

- Place photos inside a folder (e.g., `photos_example`)  
- The model will sort them into subfolders by predicted CES category  
- Use relative paths within the main `CES Modelling` directory  

---

## Supplementary Data

This repository includes a GeoPackage of CES images from the Iberian Peninsula, used in the original publication.

This repository contains six raster layers highlighting areas with high visitation rates but low population density, derived from crowdsourced data.

This repository includes the row code of the Resnet-152 model (for replication) (freshCES-net.ipynb

This repository includes the photo ID used for model training and each photo's category (Training_CES_photos.xlsx)


---

## Citation

If you use this tool, please cite it as appropriate (publication pending). Your acknowledgement supports ongoing research.

---

## License

Distributed for academic and non-commercial use.

---

## Thank You

We hope this tool supports your research. For any feedback or issues, feel free to open an issue or email us.
