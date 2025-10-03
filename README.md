# Solar Concentrated Power System CVAE Data Compression and Prediction Dataset


This dataset contains comprehensive simulation data for solar energy optimization research, specifically focusing on heliostat aiming strategies for concentrated solar power (CSP) systems. The dataset includes both raw simulation data and CVAE-encoded representations for machine learning applications.

## Dataset Structure

### Training Data (`Training_Data_Unified/`)

The unified training dataset contains **1,200 simulation cases** covering diverse operational conditions:

- **Case Range**: `simulation_case_001` to `simulation_case_1200`
- **Conditions**: Various Cloud conditions, DNI levels, azimuth angles, and elevation angles
- **Heliostat Configurations**: 271 heliostats with different aiming strategies

#### Data Files per Case

Each simulation case contains multiple CSV files:

1. **Performance Summary** (`param_perf-summary_*.csv`):
   - Direct Normal Irradiation (DNI) values
   - Solar azimuth and elevation angles
   - Plant cost and efficiency metrics
   - Power output statistics

2. **Flux Data** (`param_flux-data_Receiver 1_*.csv`):
   - Receiver flux intensity maps (25×13 )
   - Maximum, minimum, and average flux values
   - Spatial flux distribution data

### CVAE-Encoded Data (`encoded_flux_data_merged.h5`)

The dataset includes CVAE-encoded representations for efficient machine learning:

- **Latent Vectors**: Compressed flux representations (4-dimensional latent space)
- **Original Flux**: Full-resolution flux maps for reconstruction validation
- **Reconstructed Flux**: CVAE-decoded flux maps
- **Conditional Data**: Aiming heights, sun positions, DNI values, and cloud parameters

## Technical Specifications

### System Parameters

- **Heliostat Count**: 271 mirrors
- **Aiming Height Range**: 170° - 190° (discrete levels)
- **DNI Range**: Variable (typically 800-1000 W/m²)
- **Solar Position**: Azimuth 0-360°, Elevation 0-90°

### Data Format

- **Raw Data**: CSV files with comma-separated values
- **Encoded Data**: HDF5 format for efficient storage and access
- **Units**: Flux in kW/m², angles in degrees, power in kW



## Usage Notes

- The dataset is designed for training predictive models and MPC controllers
- CVAE-encoded data provides efficient representation for real-time applications
- Raw simulation data enables detailed analysis and model validation
- All data is generated using validated SolarPilot simulation software

## Citation

If you use this dataset in your research, please cite the associated publication on solar energy optimization and heliostat control strategies.
