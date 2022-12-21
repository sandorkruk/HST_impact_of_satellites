# Analysis on the impact of satellites on HST observations

This is a repository containing the analysis of the impact of satellites on HST observations, up-to-date by 3 October 2021.

---------------------------------------------------------------------------------------------------------------------------------------------------------------
A full list of HST observations is available from the eHST TAP (http://hst.esac.esa.int/tap-server/tap). We selected observations for the ACS/WFC and WFC3/UVIS instruments with the following ADQL queries:

## ACS/WFC:

select * 

from ehst.observation o, ehst.plane p, ehst.position pos 

where o.observation_id = p.observation_id and p.plane_id = pos.plane_id and o.collection='HST'and o.obs_type='HST Composite' and o.instrument_name='ACS/WFC' and o.exposure_duration>100 and o.intent='science' and p.data_product_type='image' and pos.fov_size>=0.045

## WFC3/UVIS:

select * 

from ehst.observation o, ehst.plane p, ehst.position pos 

where o.observation_id = p.observation_id and p.plane_id = pos.plane_id and o.collection='HST'and o.obs_type='HST Composite' and o.instrument_name=‘WFC3/UVIS' and o.exposure_duration>100 and o.intent='science' and p.data_product_type='image' and pos.fov_size>=0.045

And selected the "single observations" (members) corresponding to the composite observations.  

----------------------------------------------------------------------------------------------------------------------------------------------------------------
The list of HST observations with satellite classifications (up to 3 October 2021) is available at http:
//vospace.esac.esa.int/vospace/sh/106eaae32c5275b2a06aaf49894908ced29ccf?dl=1. The images crossed by satellites can be selected with the **flag=='satellite'** and the number of satellites is in the **sat_number** column. 

The satellite classifications are based on a binary ML classifier, based on the InceptionV3 model, trained on volunteer classifications of  satellites from https://www.zooniverse.org/projects/sandorkruk/hubble-asteroid-hunter/talk/tags/satellite and visually inspected by the authors. The HST images can be downloaded with *download_HST_images.py* code from the eHST archive.

----------------------------------------------------------------------------------------------------------------------------------------------------------------
The table containing information on current satellites in orbit *Satellites_space_track_2021.csv* is available from https://www.space-track.org/.



