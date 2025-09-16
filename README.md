# Hablab

Hablab is a research tool developed by **ARC Marine Ltd.** to analyse habitat space within a 3D structure and enable ecological research using characteristic metrics for the structure.<br>
It is released as freeware for **non-commercial academic and research use**.

## Installation

To download Hablab, go to the [Releases](https://github.com/Kyle-ARCMarine/hablab/releases) page of this repository and navigate to the latest release.
- On Windows, download the latest version of the Hablab installer (`.exe`).
- On Mac, download the latest version of the Hablab installer (`.dmg`).

Once downloaded, run the installer and follow on-screen instructions.

**System requirements:**
- Windows 10/11
- macOS 10.9+

## Usage

The installed Hablab application can now be launched from the search bar.

### Parameters

- The mesh file must first be loaded; this is done using the "Browse" feature, with `.stl`, `.obj`, and `.ply` as the primary mesh formats supported.
- The units that the mesh is created with must be set for use in results. This is set to metres by default.
- The resolution at which the structure is to be analysed must then be defined.
- The structure type must be defined as a "Sample" or "Structure".
  - A "Sample" is accessible only through the upper surface, as it is defined as a cut-out sample of a larger structure.
  - A "Structure" is accessible from all sides aside from below, as it is defined as a stand-alone structure.
- You may choose to calculate for an accessing diameter, as defined by [paper link].
- You may choose to calculate for a full access class, as defined by [paper link].
- If "Calculate for an accessing diameter" is toggled, an input table for access classes will be available for user inputs.
  - Access class minimum refers to the diameter at which "Accessible volume" is calculated to be accessible for.
  - Access class maximum refers to the diameter at which "Accessible refuge volume" is calculated to be inaccessible for.
  - "Prey" and "Predator" names can be assigned to access class minima and maxima for a more meaningful output page.
  - If "Calculate for a full access class" is not toggled, the "Access class maximum" column will not be utilised for calculations.
- If "Skip to Results" is toggled, then previously calculated results for a given mesh will be used to accelerate the calculation of results (if available).

### Results

- Structure Summary
  - The structure dimensions in the given unit are listed under "Dimensions".
  - The structure footprint area, calculated using the Hablab script and including all interstitial space determined to be part of the structure, is listed under "Footprint Area".
  - The total volume of the structure, calculated using the Hablab script and including all interstitial space determined to be part of the structure, is listed under "Total Surveyed Volume".
  - The "View Structure" button loads a 3D view of the input mesh.
- Analysis Summary
  - The mesh unit, resolution, and structure type as defined by the user are listed here.
- Interstitial Space Summary
  - Total accessible volume, or the total space within the structure accessible from the exterior, is listed as V<sub>int</sub>.
  - Total accessible void percentage is calculated, dividing V<sub>int</sub> by the total surveyed volume.
  - An output table with access classes is made available, specifying "Prey" and "Predator" as per the input table.
  - Accessible volume, or AV, refers to the volume accessible to the access class minimum.
  - Accessible refuge volume, or ARV, refers to the volume accessible to the access class minimum and free from the access class maximum.
- Figure Display
  - All figures produced by Hablab for the structure can be selected for viewing.
  - Graphs can be viewed individually using the Pop Out Graph button.
- Log Output
  - Process outputs throughout the running of the script are logged here.
  - Runtimes of processes, including the full script runtime, are also logged.

### Graphs

- "Accessible volume" plots the AV against the accessing diameter.
- "Accessible volume per accessible space" plots the AV as a fraction of total accessible volume against the accessing diameter.
- "Accessible volume per footprint" plots the AV divided by the footprint area against the accessing diameter.
- "Accessible volume per total space" plots the AV as a fraction of total surveyed volume against the accessing diameter.
- "Accessible refuge volume" plots the ARV against the access class minimum, using various ratios between access class maximum and minimum.
- "Accessible volume per exact accessing diameter" plots the negative of the gradient of AV against the accessing diameter.
- "Mean accessing diameter over structure height" plots the mean accessing diameter against the height above the base of the structure.
- "Mean accessing diameter over structure depth range" plots the mean accessing diameter against the depth below the wrapped surface of the structure.