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

## 📦 Installation on Windows

### Method 1: Using Anaconda/Mamba (Recommended)

Anaconda is **highly recommended for Windows users** as it handles complex dependencies (especially cartopy) much better than pip.

#### Step 1: Download and Install Anaconda
1. Visit [https://www.anaconda.com/download](https://www.anaconda.com/download)
2. Download the Windows installer (64-bit recommended)
3. Run the installer:
   - ✅ Check "Add Anaconda to my PATH environment variable" (optional but helpful)
   - ✅ Check "Register Anaconda as my default Python"
4. Complete the installation

#### Step 2: Open Anaconda Prompt
- Search for "Anaconda Prompt" in the Start menu
- Right-click and select "Run as administrator" (recommended)

#### Step 3: Create a new environment
```bash
conda create -n copernicus_env python=3.12 -y
```

Type `y` to proceed if prompted.

#### Step 4: Activate the environment
```bash
conda activate copernicus_env
```

Your prompt should now show `(copernicus_env)`.

#### Step 5: Install conda packages
```bash
conda install -c conda-forge numpy pandas xarray matplotlib cartopy netCDF4 jupyter ipykernel scipy -y
```

This may take a few minutes. Conda will handle all dependencies automatically.

#### Step 6: Install Copernicus Marine Toolbox
```bash
pip install copernicusmarine
```

**📌 Note:** We use `pip` here because `copernicusmarine` is **not available in conda/conda-forge** repositories - it's only distributed through PyPI. This is perfectly normal and safe: conda and pip work together seamlessly in conda environments. Best practice is to install conda packages first (Step 5), then pip packages (Step 6) to avoid dependency conflicts.

#### Step 7: Register the Jupyter kernel
```bash
python -m ipykernel install --user --name=copernicus_env --display-name="Python (Copernicus Marine)"
```

#### Step 8: Verify installation
```bash
copernicusmarine --version
```

You should see the version displayed.

### Step 9: Configure your credentials
Run this command once to save your credentials (see procedure below):
```bash
copernicusmarine login
```

#### Step 10: Launch Jupyter
You can launch Jupyter from the Anaconda Prompt:
```bash
jupyter notebook
```

Or use VS Code with the notebook and select the **"Python (Copernicus Marine)"** kernel.

#### Step 11: Upgrade the Toolbox
To get the latest version of the Copernicus Marine Toolbox as installed in the previous step and considering an environment whose name is `copernicusmarine`, then run the following command:
```bash
mamba update --name copernicusmarine copernicusmarine --yes
```

#### 🚀 Optional: Use Mamba for faster installations

For future package installations, you can use Mamba (5-10x faster than conda):
```bash
conda install -c conda-forge mamba -y
```

Then use `mamba` instead of `conda`:
```bash
mamba install -c conda-forge <package_name>
```

---

### Method 2: Using Command Prompt with pip (Not Recommended)

**⚠️ Warning:** This method may encounter issues with cartopy installation on Windows. Use Anaconda (Method 1) unless you have specific reasons to use pip.

#### Step 1: Open Command Prompt
- Press `Win + R`
- Type `cmd` and press Enter

#### Step 2: Navigate to your project directory
```cmd
cd /d D:\path\to\your\course\TD
```

**Note:** Replace `D:\path\to\your\course\TD` with your actual path. The `/d` flag allows changing drives.

#### Step 3: Create a virtual environment
```cmd
python -m venv venv_copernicus
```

If this fails, try:
```cmd
py -m venv venv_copernicus
```

#### Step 4: Activate the virtual environment
```cmd
venv_copernicus\Scripts\activate
```

After activation, your prompt should show `(venv_copernicus)` at the beginning.

#### Step 5: Upgrade pip
```cmd
python -m pip install --upgrade pip
```

#### Step 6: Install Copernicus Marine Toolbox
```cmd
pip install copernicusmarine
```

#### Step 7: Install additional required packages
```cmd
pip install numpy pandas xarray matplotlib cartopy netCDF4 jupyter ipykernel scipy
```

**Note:** Installing `cartopy` on Windows via pip often fails. If you encounter errors, you may need to install from pre-built wheels or switch to Anaconda.

#### Step 8: Register the Jupyter kernel
```cmd
python -m ipykernel install --user --name=venv_copernicus --display-name="Python (Copernicus Marine)"
```

#### Step 9: Verify installation
```cmd
copernicusmarine --version
```

---

### Method 3: Using PowerShell with pip (Not Recommended)

**⚠️ Warning:** This method may encounter issues with cartopy installation on Windows. Use Anaconda (Method 1) for best results.

#### Step 1: Open PowerShell
- Press `Win + X`
- Select "Windows PowerShell" or "Terminal"

#### Step 2: Set execution policy (if needed)
If you encounter an execution policy error, run:
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

Type `Y` and press Enter to confirm.

#### Step 3: Navigate to your project directory
```powershell
cd D:\path\to\your\course\TD
```

#### Step 4: Create a virtual environment
```powershell
python -m venv venv_copernicus
```

#### Step 5: Activate the virtual environment
```powershell
.\venv_copernicus\Scripts\Activate.ps1
```

#### Step 6: Upgrade pip
```powershell
python -m pip install --upgrade pip
```

#### Step 7: Install Copernicus Marine Toolbox
```powershell
pip install copernicusmarine
```

#### Step 8: Install additional required packages
```powershell
pip install numpy pandas xarray matplotlib cartopy netCDF4 jupyter ipykernel scipy
```

#### Step 9: Register the Jupyter kernel
```powershell
python -m ipykernel install --user --name=venv_copernicus --display-name="Python (Copernicus Marine)"
```

#### Step 10: Verify installation
```powershell
copernicusmarine --version
```

---

## 🔑 Copernicus Marine Service Registration

To download data, you need a free Copernicus Marine Service account.

### Registration Steps:

1. **Visit the registration page:**  
   [https://data.marine.copernicus.eu/register](https://data.marine.copernicus.eu/register)

2. **Fill in the registration form:**
   - Email address
   - Password
   - First and last name
   - Country
   - Organization type (Academic/Research for students)

3. **Verify your email:**  
   Check your inbox for a verification email and click the confirmation link.

4. **Save your credentials securely:**  
   You'll need your username and password for data access.

### Important Notes:
- Registration is **completely free**
- Academic users get **unlimited access** to most datasets
- Keep your credentials confidential
- **Do not share your credentials** in notebooks or code repositories

---

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
