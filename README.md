# Analysis on the impact of satellites on HST observations

This is a repository containing the analysis of the impact of satellites on HST observations, up-to-date by 3 October 2021.

---------------------------------------------------------------------------------------------------------------------------------------------------------------
A full list of HST observations is available from the eHST TAP server (http://hst.esac.esa.int/tap-server/tap). We selected individual exposures with the ACS/WFC and WFC3/UVIS instruments, taken and release publicly between 22 March 2002 and 3 October 2021 (for ACS/WFC) and between 25 June 2009 and 3 October 2021 (for WFC3/UVIS). 

We processed the individual images by adding the two ACS/WFC (WFC3/UVIS, respectively) apertures side-by-side, without correcting for geometric distortions and without the gap between the two detectors (hence why the satellite trails can appear discontinuous in the images). The full list of HST observations used in this study is available at: https://doi.org/10.5281/zenodo.7474191 (the images crossed by satellites are flagged with  **'satellite'** and the number of satellites is in the **no_sats** column). 

![Hubble_sat](https://user-images.githubusercontent.com/9132229/222450533-2b03b710-615d-4475-9ba4-93444a7c2707.jpg=250x250)


The satellite classifications are based on a binary ML classifier, based on the InceptionV3 model, trained on volunteer classifications of  satellites from https://www.zooniverse.org/projects/sandorkruk/hubble-asteroid-hunter/talk/tags/satellite and visually inspected by the authors. The images were rescaled from 4,096 × 4,096 pixels to 600 × 600 pixels before being fed to the ML classifier.

----------------------------------------------------------------------------------------------------------------------------------------------------------------




