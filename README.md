# Function

Calculate the PDE with scintillator emission spectrum and SiPM absorption spectrum. The emission spectrum will be interpolated at the x value of absorption spectrum, and PDE is calculated with `numpy.trapz`

# Data

## Scin

[GAGG](https://www.scintillator-crylink.cn/wp-content/uploads/Ce-GAGG-%E9%97%AA%E7%83%81%E6%99%B6%E4%BD%93%E4%BA%A7%E5%93%81%E5%86%8C-%E5%8D%97%E4%BA%AC%E5%85%89%E5%AE%9D%E5%85%89%E7%94%B5-CRYLINK.pdf)

[BC408](https://luxiumsolutions.com/sites/default/files/2023-08/146337_Luxium_SGC%20BC400%20404%20408%20412%20416_FIN.pdf)

## SiPM

[Sensl 60035](https://www.onsemi.com/pdf/datasheet/microj-series-d.pdf)
