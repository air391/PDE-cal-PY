# Function

Calculate the PDE (Photon Detection Efficiency) with scintillator emission spectrum and SiPM absorption spectrum. The emission spectrum will be interpolated at the x value of absorption spectrum, and PDE is calculated with `numpy.trapz` or `numpy.trapezoid` (for compatibility with newer numpy versions).

## Features

- **JSON-based Preset Configuration**: Presets are defined in `presets.json` - add new CSV files by simply updating this file
- **Preset Data Selection**: Choose from built-in scintillator and SiPM data files loaded dynamically from JSON
- **Custom File Upload**: Upload your own CSV files for analysis
- **Interactive Plotly Visualization**: Web-optimized charts with proper Chinese character support
- **Convolution Visualization**: View both original spectra and convolution results in dual-panel layout
- **Modern UI**: Improved interface with gradient backgrounds and intuitive controls
- **Real-time Calculation**: Python-powered calculations running in the browser using Pyodide

## Usage

1. Open `index.html` in a web browser
2. Wait for the preset configuration to load from `presets.json`
3. Select a scintillator preset (GAGG or BC408) or upload a custom CSV file
4. Select a SiPM preset (SensL 60035 @ 2.5V) or upload a custom CSV file
5. Click "计算并可视化" (Calculate and Visualize)
6. View the PDE result and interactive Plotly visualization

## Adding New Presets

To add new CSV data files:

1. Place your CSV file in the appropriate directory (`Scin/` or `SiPM/`)
2. Edit `presets.json` to add the new preset:

```json
{
  "scintillators": [
    {
      "id": "NEW_SCIN",
      "name": "Display Name",
      "description": "Description of the scintillator",
      "file": "Scin/new_file.csv"
    }
  ]
}
```

No HTML code changes required!

## CSV Format

CSV files should contain two columns: wavelength (nm) and intensity/efficiency:
```
wavelength, intensity
462.22, 0.0012402
464.98, 0.0028274
...
```

# Data

## Scin

[GAGG](https://www.scintillator-crylink.cn/wp-content/uploads/Ce-GAGG-%E9%97%AA%E7%83%81%E6%99%B6%E4%BD%93%E4%BA%A7%E5%93%81%E5%86%8C-%E5%8D%97%E4%BA%AC%E5%85%89%E5%AE%9D%E5%85%89%E7%94%B5-CRYLINK.pdf)

[BC408](https://luxiumsolutions.com/sites/default/files/2023-08/146337_Luxium_SGC%20BC400%20404%20408%20412%20416_FIN.pdf)

[CLYC](https://link.springer.com/article/10.1007/s41365-017-0342-4#Fig2)

## SiPM

[Sensl 60035](https://www.onsemi.com/pdf/datasheet/microj-series-d.pdf)

[Hamamatsu S13360-6050VE](https://www.hamamatsu.com.cn/content/dam/hamamatsu-photonics/sites/documents/99_SALES_LIBRARY/ssd/s13360-2050ve_etc_kapd1053e.pdf)

## Sample Results

- GAGG + SensL 60035 @ 2.5V: PDE ≈ 0.1977
- BC408 + SensL 60035 @ 2.5V: PDE ≈ 0.3875

## Technology Stack

- **Plotly.js**: Interactive, web-optimized plotting with full Chinese character support
- **Pyodide**: Python runtime in the browser for numerical calculations
- **JSON Configuration**: Easy preset management without code changes
