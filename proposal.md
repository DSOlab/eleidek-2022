1 Excellence, State-of-the-art and Objectives
==============================================================================

1.1 Introduction
=================
Geodesy has greatly advanced since the introduction of artificial, Earth 
orbiting satellites. A new era has emerged, where satellite-based data dominate 
the field, providing results for a wide range of geodesy-related fields,
including but not limited to positioning, reference frames, altimetry and 
gravity field determination. Exploitation of satellite-based observations 
though, is inherently coupled with the complex problem of orbit determination.

Orbit determination offers unprecedented insight in the field of geodesy. Its 
contribution can be broadly grouped in a twofold role:
  1. As a product (i.e. tabulated satellite coordinates and/or velocity) it is 
  needed for most spaced-based applications. Knowledge of satellite position 
  (or state) is a prerequisite for most applications and in general dictates 
  the quality of the application’s outcome. It should be noted that despite 
  the extended demand for accurate satellite coordinates in recent years 
  (mainly due to GNSS), the product list is by no means exhausted here; several
  other estimates constitute orbit determination products, as are e.g. earth 
  orientation parameters, crucial for reference frame studies.

  2. As a field of study, it enables the testing, validation and improvement 
  of models and theoretical aspects for various scientific disciplines, geodesy 
  being the first and foremost beneficiary.

In this project, the second point above is targeted, i.e. the orbit 
determination methodology, as a means to deliver products of geodetic quality.

Given the composition of the research team and the available resources at hand, 
we strongly believe the proposal’s aims will be accomplished within the 
requested period of 24 months. The research team has an extensive, solid 
background and expertise on space geodesy and especially the analysis of 
satellite-based observations. It possesses knowledge of state-of-the-art 
methodologies on data processing and is actively involved in applications of 
space-geodetic techniques demanding the outmost precision.

1.2 Relevance with the selected Scientific Area
===============================================

1.3 Proposal objectives and necessity/challenges
================================================

The current proposal's objective is the design and implementation of a 
state-of-the-art, open-source and free software module to perform precise orbit 
determination and positioning using the Doppler Orbitography and 
Radiopositioning Integrated by Satellite (DORIS) satellite system.

Within the framework of the project, three satellites will be targeted, namely 
 * the Joint Altimetry Satellite Oceanography Network–3 (Jason-3),
 * the Sentinel-3A and
 * the Hai Yang 2C (HY-2C)
satellites.

Via the resulting software, NTUA will be able to provide:
  * Precise orbit products for the selected satellite missions,
  * High quality position estimates for the DORIS-system ground segment 
    (beacons)
  * Estimates for a number of parameters of geodetic and/or atmospheric 
    interest

1.3.1 Jason-3
=============

Jason-3 is a satellite mission that supports scientific, commercial and practical 
applications related to sea level rise, ocean circulation, and climate change. 
It is an international cooperative mission in which NOAA is partnering with 
the Centre National d'Etudes Spatiales (CNES, France’s governmental space 
agency), European Organisation for the Exploitation of Meteorological 
Satellites (EUMETSAT), and National Aeronautics and Space Administration (NASA) [1].

1.3.2 Sentinel-3A
=================

Sentinel-3A is a European Space Agency Earth observation satellite dedicated 
to oceanography. It will provide, ocean, inland sea and coastal zone colour 
measurements, sea surface temperature measurements and sea surface topography 
measurements (altimetry) including an along track SAR capability [2].

1.3.3 Hai Yang 2C
=================

The Hai Yang 2C is developed and operated by China. It's mission is to monitor 
and investigate the marine environment, and obtain marine dynamic environmental 
parameters including sea surface wind, wave height, sea surface height, etc. 
HY-2C could directly provide measured data for early warning of disastrous sea 
conditions and provide services for marine disaster prevention and mitigation, 
marine rights maintenance, marine resource development, marine environmental 
protection and marine scientific research [3], [4].

1.3.4
=====

The objectives of the targeted satellite missions can only be achieved in the 
precense of high quality space vehicle orbits. Measurements performed by their 
onboard instruments can only be used in high precision applications, if the 
satellite's position is known to a required accuracy. Hence, the neccesity of 
precise orbit determination is profound, inherent to the mission's success.

Among other instruments, the payload of the satellites includes DORIS 
receivers to enable precise orbit determination. However, only a few Analysis 
Centers worldwide can process observations of this system. Acoording to the 
International DORIS Service (IDS), the last contribution of the Service to the 
latest International Terrestrial Refernce Frame (ITRF2020, [5]) included 
analysis results from no more than four Analysis Centers ([6]), each one using 
their own, in-house software package.

This scarcity of both Analysis Centers and respective software (In comparisson, 
for the other two prominent space-based orbit determination techniques, the 
International GNSS service includes tweleve Analysis Centers [7] and the 
International ILRS Service includes seven core and a number of Associate 
Analysis Centers [8]) 

Indicative fields should include:
    • Relevance with the selected Scientific Area
    • Proposal objectives and necessity/challenges
    • State-of-the-art & Innovation
    • Scientific and/or social impact 

2 Methodology and Implementation
==============================================================================
Indicative fields should include:
    • Research Methodology
    • Work Plan
    • Research Team

2.1 Research Methodology

References
==============================================================================
[1] "Jason-3 Satellite - Mission" (https://www.nesdis.noaa.gov/jason-3/mission.html). 
    Retrieved 10 October 2022.
[2] "Sentinel - Mission Objectives" (https://sentinels.copernicus.eu/web/sentinel/missions/sentinel-3/mission-objectives) 
    Retrieved 10 October 2022.
[3] "China launches ocean monitoring satellite", Spaceflight Now, October 10, 2022
[4] "National Satellite Ocean Application Service, HY-2C" (http://www.nsoas.org.cn/eng/item/253.html), Retrieved 10 October 2022.
[5] "The International Terrestrial reference Frame: an update", Z. Altamimi, Fifteenth Meeting of the International Committee on Global Navigation Satellite Systems (ICG), 2021
[6] "The international DORIS service contribution to ITRF2020", G. Moreaux, F. G. Lemoine, H. Capdeville, M. Otten, P. Štěpánek, J. Saunier, P. Ferrage, Advances in Space Research, 2022
[7] "Analysis Center Coordinator, IGS Analysis Centers", https://igs.org/acc/, Retrieved 10 October 2022.
[8] "ILRS Analysis Centers", https://ilrs.gsfc.nasa.gov/science/analysisCenters/index.html, Retrieved 10 October 2022.
