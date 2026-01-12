# Marine Energy and Offshore Wind Farm Assessment - Brazil

This Jupyter Notebook provides a comprehensive analysis of oceanographic conditions for offshore wind farm site assessment in Brazilian coastal waters.

## 📚 Course Information
**Institution:** École des Ponts  
**Project:** Marine Energy 2025-2026  
**Region:** Brazil (6°S to 2°S, 38°W to 34°W)

## 🎯 Learning Objectives

- Analyze oceanographic data from Copernicus Marine Service
- Understand major current systems (Brazil Current and Equatorial currents)
- Assess sediment transport processes and scour hazards
- Evaluate offshore wind farm site suitability
- Visualize ocean dynamics through animations and plots

## 🔧 Prerequisites

- Python 3.8 or higher
- Jupyter Notebook or JupyterLab
- Required Python packages (see Installation section)

## 📦 Installation

### **Step 1: Clone this repository**
Download and install [Git for Windows](https://git-scm.com/install/windows)
```bash
git clone https://github.com/Pablo.Tassi/Marine-Energy-Brazil.git
cd Marine-Energy-Brazil
```

### **Step 2: Install Mamba (recommended)**

**Miniforge (includes Mamba)** - Recommended:
1. Download Miniforge from: https://github.com/conda-forge/miniforge
2. Install following the instructions for your operating system
3. Mamba will be available by default


### **Step 3: Install the Copernicus Marine Toolbox**

1. Open the *Miniforge Prompt* to create a new environment (could be anything, but let's call it `copernicusmarine`) and install the Copernicus Marine Toolbox from conda-forge:
```bash
mamba create --name copernicusmarine conda-forge::copernicusmarine --yes
```
2. Activate the newly created environment (called `copernicusmarine`) to use the Toolbox
```bash
mamba activate copernicusmarine
```

### **Step 4: Install additional required packages**
```bash
mamba install -c conda-forge numpy pandas xarray matplotlib cartopy cmocean scipy imageio netCDF4
```

Or install everything in one command:
```bash
mamba install -c conda-forge copernicusmarine numpy pandas xarray matplotlib cartopy cmocean scipy imageio netCDF4
```

### **Step 5: Verify installation**
```bash
copernicusmarine --version
```

### **Step 6: Configure your credentials**
Run this command once to save your credentials:
```bash
copernicusmarine login
```
Enter your Copernicus Marine username and password when prompted: create a free Copernicus Marine account at: https://data.marine.copernicus.eu/register

### **Step 7: Upgrade the Toolbox**
To get the latest version of the Copernicus Marine Toolbox as installed in the previous step and considering an environment whose name is `copernicusmarine`, then run the following command:
```bash
mamba update --name copernicusmarine copernicusmarine --yes
```

## 🚀 Usage

1. **Open the notebook in VS Code or Jupyter:**
   ```bash
   jupyter notebook JN_MarineEnergy_Brazil.ipynb
   ```
   Or open directly in VS Code with Jupyter extension

2. **Run cells sequentially** - Each section builds on previous analyses

3. **Generated outputs:**
   - Plots saved in `img/` folder
   - Animations saved in `img/animations/` folder

## 📖 Notebook Structure

| Section | Content |
|---------|---------|
| **1. Introduction** | Regional oceanography and current systems |
| **2. Setup** | Python modules and data loading |
| **3. Study Area** | Bathymetry, geography, and domain overview |
| **4. Temporal Variability** | Time series analysis of ocean variables |
| **5. Animations** | Dynamic visualizations (SSH, currents, waves, SPM) |
| **6. Ocean Currents** | Surface and vertical current structure |
| **7. Wave Climate** | Wave statistics and energy potential |
| **8. Sediment Transport** | Shields parameter, bedload transport, scour assessment |
| **9. OWF Assessment** | Offshore wind farm hazard mapping and site selection |
| **10. Exercises** | Student activities and questions |
| **11. Conclusion** | Summary of key findings |
| **12. References** | Scientific literature and data sources |

## 🎨 Key Features

- **Interactive visualizations** using Matplotlib and Cartopy
- **Geospatial analysis** with proper map projections
- **Sediment transport physics** including Shields parameter calculations
- **Hazard assessment** for offshore wind farm installation
- **Animated GIFs** showing temporal evolution of ocean conditions

## 🌊 Main Findings

- **Brazil Current** (south/southeast): Western boundary current with moderate to high energy
- **Equatorial Current System** (north): Complex multi-scale current patterns
- **Recommended OWF site**: Brazilian continental shelf (37.0-35.5°W, 3.5-5.0°S)
  - Low scour risk (bed shear stress < 0.5 Pa)
  - Manageable wave conditions
  - Away from strong current zones

## 📊 Data Sources

All data accessed from the Copernicus Marine Service:
- **Global Ocean Physics Analysis and Forecast** (GLOBAL_ANALYSISFORECAST_PHY_001_024)
- **Global Ocean Waves Analysis and Forecast** (GLOBAL_ANALYSISFORECAST_WAV_001_027)
- **Global Ocean Colour** (OCEANCOLOUR_GLO_BGC_L4_NRT_009_102)

## 📝 License

This material is provided for **educational purposes only**.

## 👥 Authors

Pablo Tassi - Marine Energy Project - Course 2025-2026

## 📧 Contact

For questions or issues, please contact <pablo.tassi@enpc.fr> or create GitHub issues

---

**Note:** This notebook requires access to Copernicus Marine Service data. Students must register and download datasets independently.
