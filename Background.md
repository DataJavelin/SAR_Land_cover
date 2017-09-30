# Background Research on Synthetic Aperture Radar

The Sentinel 1 mission has two polar-orbiting satellites, operating day and night performing C-band synthetic aperture
 radar imaging, enabling them to acquire imagery regardless of the weather.

There are four imaging modes:
 Mode | Access Angle | Res. (Range vs Azimuth) | Swath Width | Polarisation 
--- | --- | --- | --- | ---
Strip Map | 20-45 deg. | 5 x 5 m | > 80km | HH or VV or HH+HV or VV+VH
Interferometric Wide Swath | > 25 deg. | 5 x 20 m | > 250 km | HH or VV or HH+HV or VV+VH
Extra Wide Swath | > 20deg. | 20 vs 40 m| > 400 km | HH or VV or HH+HV or VV+VH
Wave mode | 23 deg & 36.5 deg | 5 x 5m | >20 x 20 km | HH or VV

Some other key values for all modes:

**Radiometric accuracy (3 $\sigma$)** = 1dB
**Noise equivalent Sigma Zero** = -22db
**Point Target Ambiguity ratio** = -25db
**Distributed Target Ambiguity Ratio** = -22 db

IW is main mode over land. IW Normally 250 km swath at 5 by 20 m spatial resolution (single look)
IW mode captures three sub swaths using TOPS mode and a IW SLC product contains one image per sub swath (1 or 2 polarsiations).

Useful info from [https://sa.catapult.org.uk/wp-content/uploads/2016/05/Sentinel-1_Overview.pdf](https://sa.catapult.org.uk/wp-content/uploads/2016/05/Sentinel-1_Overview.pdf)

SAR measures radar backscatter $ \sigma_0$ (i.e. reflected radio pulse).

Normalised radar cross-section (backscatering coefficient) is genven by :

$\sigma_0 (\mathrm{dB}) = 10. \log_{10} (energy ratio)$
 $energy_ratio = \frac{recieved energy by sensor}{energy reflected in isotropic way}$
 Backscattered coefficient is positive if focusing of backscattered energy towards radar (i.e. diffuse surface), negative if away (i.e. smooth surface)

* Very high backscatter ($\gt -5$ dB): urban, slopes towards radar, very rough surface
* High backscatter (-10 dB t0 0 db): rough surface, dense vegetation
* Moderate (-20 to -10 dB): medium level of vegetation, agricultueral crops, moderately rough surfaces
* Low (below -20 dB): smooth surface, calm water, road, very dry terrain (e.g. sand)

Speckle noise has an exponential probability distribution
[https://earth.esa.int/documents/10174/642943/6-LTC2013-SAR-Moreira.pdf](https://earth.esa.int/documents/10174/642943/6-LTC2013-SAR-Moreira.pdf)

For physics of scattering, polarisation and speckle noise: [http://www.csre.iitb.ac.in/~avikb/GNR647/Lec_11_Speckle.pdf](http://www.csre.iitb.ac.in/~avikb/GNR647/Lec_11_Speckle.pdf)
@Abdikan:2016

## What determines Backscatter
Target parameters:
. Structure (size, orientation and distribution of scattering surfaces)
. Surface roughness (relative to wavelenght)
. Dielectric constant (moisture content)
. slope angle/orientation

Surface scattering occurs with water.
Surface (and volume if penetration) on ground with soil and rock
Volume sacttering with vvegetation (and surface)

You can also get double bounce

IN tree canapoies, primary scatterers are leaves, branches stems if size on order of wavelength or larger and orinetation similar to inciming signal
Elements smaller thatn wavelength attenuate rather backscatter

Smooth surfaces produce no depolarisation
Rough surfaces produce litte depolarisations

Multiple scattering produces strong depolarisation signals. Occurs mainly over vegetation, not open ground.
 It is very sensitive to vegetation parameters
 
 Surface roughness needs to be on order of wavelength
 
 ### Dielectic constant
 Amount of moisture content
 
 Most mateirals have values ranging from 1-100.
 
 Radar backscatter is influenced by amount of moisture in vegetation and soil, affecting absoprption and propagation of waves.
 
 Increasing moisture content reduces penetration of signal through vegeation canopy or soil.
 
 SAR double bounce scattering from flooded areas increase because of stronger amplitude of first reflection of ground
 
 
 ## Bayesian modelling of SAR
 [A Prototype Software Package to Retrieve Soil
Moisture From Sentinel-1 Data by Using a
Bayesian Multitemporal Algorithm](http://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=6515352)
This paper looks interesting. Bayesian maximumum likelihood approach to esitmate soil moisture.
 
 Model is a generative. Actual maths are in the paper [Soil moisture estimation over vegetated terrains using multitemporal remote sensing data](http://www.sciencedirect.com/science/article/pii/S0034425709003010)