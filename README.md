# Function

Calculate the PDE (Photon Detection Efficiency) with scintillator emission spectrum and SiPM absorption spectrum. The emission spectrum will be interpolated at the x value of absorption spectrum, and PDE is calculated with `numpy.trapz` or `numpy.trapezoid` (for compatibility with newer numpy versions).

## Features

- **Preset Data Selection**: Choose from built-in scintillator and SiPM data files
- **Custom File Upload**: Upload your own CSV files for analysis
- **Convolution Visualization**: View both original spectra and convolution results
- **Modern UI**: Improved interface with gradient backgrounds and intuitive controls
- **Real-time Calculation**: Python-powered calculations running in the browser using Pyodide

## Usage

1. Open `index.html` in a web browser
2. Select a scintillator preset (GAGG or BC408) or upload a custom CSV file
3. Select a SiPM preset (SensL 60035 @ 2.5V) or upload a custom CSV file
4. Click "计算并可视化" (Calculate and Visualize)
5. View the PDE result and visualization plots

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

## SiPM

[Sensl 60035](https://www.onsemi.com/pdf/datasheet/microj-series-d.pdf)

## Sample Results

- GAGG + SensL 60035 @ 2.5V: PDE ≈ 0.1977
- BC408 + SensL 60035 @ 2.5V: PDE ≈ 0.3875
