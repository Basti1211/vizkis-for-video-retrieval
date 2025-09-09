# Evaluating Keyframe Layouts for Visual Known-Item Search in Homogeneous Collections

This repository contains the code and resources for the submission **"Evaluating Keyframe Layouts for Visual Known-Item Search in Homogeneous Collections"**.  

- The folder **`application/`** contains the fully Dockerized study application.  
- The folder **`grids/`** contains pre-computed layouts for all *(collection, layout)* pairs.  

<div align="center">
  <img width="100%" alt="Visual Known-Item Search Task example" src="example_kis.gif">
</div>

---

## Setup

The application is fully Dockerized to provide a ready-to-use study environment. To get started:

1. [Download and install Docker](https://www.docker.com/products/docker-desktop/).  
2. Start Docker.  
3. Clone this repository.  
4. Open a terminal and navigate to the **`application/`** folder.  
5. Build and start the application:  
   ```bash
   docker compose up --build
6. Once running, the application will be available at  [http://localhost:5173/](http://localhost:5173/).
7. All collected data (scroll data, target overlays, and submissions) will be stored in **`backend/CollectedData/`**.

## Config
The configuration of which (collection,method) pair will be loaded is determined by a latin-square randomization strategy. A exemplary latin-square configuration is stored at **`application/backend/configLatinSquare.csv`**. Each row corresponds to one user, and each column is a (collection, method) pair. The latin square file is CSV with the first value being number of images per row (4,8) and the second the desired ordering. Datasets are shifted for each user to test all datasets for each configuration.

Possible ordering values:
- `d` : default folder ordering (rank-based)
- `sp` : side-panel (otherwise same as `d`)
- `mc` : middle column first (otherwise same as `d`)
- `ss` : self-sorting
- `lab` : LAB color self-sorting
- `group` : group by video

## Evaluation

All user interactions are automatically logged in **`backend/CollectedData/`**. To analyze the data, we provide an example Jupyter notebook **`read_logging_data.ipynb`**.

## Pre-Computed Grids

We provide pre-computed grids in **`grids/`** folder. In total, we employed 35 collections and 7 layouts, leading to 245 (collection,layout) pairs. For reproducibility, we share the exact arrangement of images on the grid. We share the .txt files necessary to reproduce the grids and provide .png thumbnails of the grids.


