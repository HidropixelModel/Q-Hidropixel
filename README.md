# Q-Hidropixel (Version 4.0.2)

## Overview

**Q-Hidropixel** is a plugin of the pixel-based distributed rainfall-runoff hydrological model for QGIS. It estimates the runoff travel time to the outlet for each pixel of the watershed's Digital Elevation Model (DEM). Subsequently, it calculates the excess rainfall at each pixel using the *Curve Number* method from the *Natural Resources Conservation Service* (NRCS-CN).

Finally, the watershed's final hydrograph is obtained by overlaying the hydrographs generated individually for each pixel. The version presented is the **Hidropixel - Distributed Linear Reservoirs (DLR)**, where the final hydrograph is attenuated due to the presence of linear reservoirs associated with each pixel of the DEM.

The plugin facilitates the application of the model in hydrological studies by integrating tools to configure, execute, and analyze hydrological simulations directly within a Geographic Information System (GIS).

## Authors

* João Vitor Dias da Silva Lima
* Dário Macedo Lima
* Adriano Rolim da Paz

---

## System Requirements

### Operating System
* **Windows**: The current version is exclusive to the Windows operating system.
* **macOS**: A compatible version is currently under development.

### Regional Settings
* **Decimal Separator**: The operating system must be configured to use the **dot (.)** as the decimal separator, not the comma. Using a comma will cause errors during model simulations.

### Dependencies
The plugin uses packages native to QGIS, primarily:
* **GDAL**: Essential for reading TIFF files and converting them into compatible raster formats.
* **Numpy**: Fundamental for array-based operations and pixel-by-pixel calculations.
* **Matplotlib**: Used for plotting specific Q-Hidropixel results.

### Compatibility with QGIS# Q-Hidropixel (Version 4.0.2)

* It is recommended to install Q-Hidropixel on QGIS version **3.28.0 (Firenze)** or later. Older versions may limit the plugin's functionality.

### Hardware Requirements 

| Component | Minimum | Recommended |
| :--- | :--- | :--- |
| **Processor** | Core i3 2.7Ghz or similar | Core i7 3.5Ghz or similar |
| **RAM** | 2 GB | 8 GB or more |
| **Hard Drive** | 500 GB SATA or similar | 128 GB SSD or 500 GB SATA |
| **Video Memory** | 1 GB | 2 GB or more |
| **OS** | Windows 7-11 | Windows 7-11 |

---
## Installation

As of version 4.0.2, Q-Hidropixel is not available in the official QGIS plugin repository. Installation differs from standard plugins and must be done manually via a ZIP file.

1.  **Download**: Obtain the `hidropixel.zip` file for the desired version (LTR - Long Term Release or LV - Last Version). You can donwload this repository and change the file name to 'hidropixel.zip'.
2.  **In QGIS**:
    * Go to the **Plugins** menu > **Manage and Install Plugins**.
    * Select the **Install from ZIP** tab.
    * Click the button to select the downloaded `hidropixel.zip` file.
    * Click **Install Plugin**.
3.  **Access**: After installation, Q-Hidropixel will appear in the "Plugins" menu or toolbar.

> **Update Note**: To install a new version, you must first uninstall the previous version of Q-Hidropixel via the QGIS plugin manager or by manually deleting the folder in the active profile directory.

---

## Main Functionalities

The initial menu presents three main modules:

### 1. Flow Travel Time
Determines the time required for water to flow from each pixel to the watershed outlet, considering different flow types:
* **Sheet Flow** 
* **Shallow Concentrated Flow**
* **Channel Flow**
It uses an adapted version of the velocity method (NRCS, 2004) based on Manning's equation.

### 2. Excess Rainfall
Performs spatial interpolation of precipitation and applies the **Curve Number (CN)** method from the *Natural Resources Conservation Service* (NRCS-CN) to calculate the fraction of rainfall that becomes surface runoff, considering soil characteristics and land use. It generates maps for total rainfall, initial abstraction, and maximum potential retention.

### 3. Flow Routing
Propagates the flow along the watershed and calculates the final hydrograph at the outlet by aggregating the individual contributions of each pixel. It employs a Distributed Linear Reservoir (DLR) approach to represent storage effects.

## 4. Input data

The main datasets required by Q-Hidropixel include:

- Watershed delineation raster
- Digital Elevation Model (DEM)
- Flow direction raster
- Drainage network raster
- Flow accumulation (drainage area)
- Land use / land cover map
- Curve Number (CN) data
- Rainfall data (point-based or spatially distributed)

All raster datasets must share:
- The same coordinate reference system
- The same spatial resolution
- The same geographic extent

---

## Documentation

Complete documentation, including:
- Detailed algorithm descriptions
- Parameter definitions for each module
- Data preparation guidelines
- Interpretation of results

is available in the **[Q-Hidropixel User Manual (PDF)](https://github.com/HidropixelModel/Q-Hidropixel/tree/f7d881e0eb9cd99719aef649f9daa69884c4ed77/docs)**.

---

## References

* ILLINOIS DRAINAGE GUIDE. QGIS download & installation guide. University of Illinois Urbana-Champaign, 2022.
* Lima, D.M. "Abordagens distribuídas para simulação do escoamento superficial baseadas no modelo digital de elevação". Master's Dissertation - UFPB, 2021.
* Lima, D.M., da Paz, A.R., Xuan, Y. et al. Incorporating spatial variability in surface runoff modeling with new DEM-based distributed approaches. Comput Geosci 28, 1331-1348 (2024).
* Pereira, A. B. S., et al. Avaliação de Modelos Hidrológicos e Hidrodinâmicos Distribuídos Empregados em Bacia de Médio Porte e Dados Diários. In XVII SRHNe.
* Veeck, S. et al. "Scale dynamics of the HIDROPIXEL high-resolution DEM-based distributed hydrologic modeling approach". Environmental Modelling & Software, Vol. 127, 2020. k# Q-Hidropixel (Version 4.0.2)You can donwload this repository and change its name to 'hidropixel.zip'

---

## License

See the `LICENSE` file for license information.

---

## Citation

If you use Q-Hidropixel in academic work, please refer to:
`Lima, J.V.D.S. ; SILVA, P. A. M. ; BARREIRO, B. M. ; LIMA, D. M. ; PAZ, A. R. ; ALLASIA, DANIEL G. . Hidropixel-plugin: desenvolvimento, ferramentas e aplicação da integração de um modelo hidrológico distribuído ao QGIS. In: XXVI Simpósio Brasileiro de Recursos Hídricos, 2025, Vitória. Anais do XXVI SBRH. Vitória: ABRHidro, 2025.`
