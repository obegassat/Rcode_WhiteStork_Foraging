# Rcode_WhiteStork_Foraging
R scripts used for movement ecology analysis on white storks (Ciconia ciconia). This repository includes data processing, visualization, and statistical analysis code.
The scripts focus on behavioural classification, environmental data processing, and statistical analyses.

## 📂 Repository Structure  

### Behavioural Analysis  
- **`Model_bhvClassif_rabc.Rmd`** → Builds and evaluates a behavioural classification model based on acceleration data (not provided).  

### Environmental Data Processing  
- **`SPEIcalculation.Rmd`** → Computes the Standardized Precipitation-Evapotranspiration Index (SPEI) for two french stations to assess environmental conditions affecting storks foraging behaviour.  

### Statistical Analysis  
 **`Statistical_analyses_WhiteStork_space_use.Rmd`** → Mixed models to test which factors influence home range size, daily distance from the nest, mean daily Overall Dynamic Body Acceleration (ODBA), and monthly proportion on walk behavior of white storks from two french marshes.

### Dataset
**`matrice_ciccic_2025all.csv`** → Filtered and aggregated data matrix used for the statistical models.

Variables
device: GPS device ID
id_30: 30-day period ID (1st or 2nd part of the rearing period)
Deviceyear: concatenation of the device ID and the study year
num_unique: unique no. per Deviceyear
ID: shorter ID, concatenation of num_unique, the two last number of the year and the period number (1 or 2)
YEAR: study year
POP1: French administrative department code of the bird (44: Loire site, 17: Gironde site)
POP: same as for POP, except that 44 is replaced by 1 and 17 is replaced by 2.
SEXE: sex of the individuals
PRODUCTION_envol: number of fledglings
START: start date of the recordings used in the analyses
END: end date of the recordings used in the analyses
ECLO: hatching date
ENVOL:  fledging date
PERIOD: 1st or 2nd 30-day period of the chick rearing
CHICKAGE: 0 when in the 1st period, 1 when in the 2nd period of chick rearing
n_all_bhv: number of GPS locations (all behaviours)
days_available: number of days with valid GPS locations
n_foraging: number of GPS locations classified as "foraging" ("walking")
ratio_foraging_all: ratio between n_foraging/ n_all_behaviours
HRker95_allhadjust: Home range size calculated using Kernel density estimator (95%) using adjusted h
HRker95_foragingHref: Home range size calculated using Kernel density estimator (95%) using h-ref
Hrker_foraging_hadjust: Home range size only based on foraging locations, calculated using Kernel density estimator (95%) using adjusted h
Mean_nest_dist: distances between the nest and each foraging location were calculated for each individual-period using the R package ‘geosphere’ (Hijmans et al. 2022), and averaged for each day to obtain mean daily distance.
prop_for_month: the proportion of foraging activity calculated by dividing the number of walking locations by the total number of GPS locations for each 30-day period.
ODBA.mG.: daily mean Overall Dynamic Body Acceleration was calculated first by summing the absolute dynamic acceleration across the three spatial axes for each 10 s sequence, and then by averaging these values across all sequences recorded within the day (Qasem et al. 2012). Daily mean ODBA was then averaged for each 30-day rearing period.
daily_mean_ODBA: same as ODBA.mG. but in G 
SPEI_har_pond: the standardized precipitation-evapotranspiration index (SPEI). This index was calculated using the functions spei and hargreaves (modified form of the Hargreave’s equation; Droogers and Allen 2002) from the ‘SPEI’ package (Beguería et al. 2014, Beguería and Vicente-Serrano 2023). It was computed on a monthly basis, incorporating data from the two preceding months, to reflect time-integrated drought conditions experienced by breeding storks.  It was then weighted for each individual 30-day period based on the proportion of days from each overlapping month that fell within the period.

## 🚀 How to Use  
If you use this code in your research, please cite this repository and the corresponding publication (doi: 10.1002/jav.03504).
