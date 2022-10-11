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
space-geodetic techniques demanding the utmost precision.

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
presence of high quality space vehicle orbits. Measurements performed by their 
onboard instruments can only be used in high precision applications, if the 
satellite's position is known to a required accuracy. Hence, the necessity of 
precise orbit determination is profound, inherent to the mission's success.

Among other instruments, the payload of the satellites includes DORIS 
receivers to enable precise orbit determination. However, only a few Analysis 
Centers worldwide can process observations of this system. According to the 
International DORIS Service (IDS), the last contribution of the Service to the 
latest International Terrestrial Reference Frame (ITRF2020, [5]) included 
analysis results from no more than four Analysis Centers ([6]), each one using 
their own, in-house software package.

This scarcity of both Analysis Centers and respective software (In comparison, 
for the other two prominent space-based orbit determination techniques, the 
International GNSS service includes twelve Analysis Centers [7] and the 
International ILRS Service includes seven core and a number of Associate 
Analysis Centers [8]) underlines the need for high-caliber scientific teams 
targeting this challenging technique, thus further strengthening its contribution 
to both earth-based (e.g. the ITRF realizations) and space-based (e.g. orbits) 
products.

On the other hand, this scarcity is also a proof of concept for the challenges 
posed in performing high quality analysis using the DORIS system. Processing 
system observations requires expertise in various multi-disciplinary fields 
(e.g. astrodynamics, geodesy, atmospheric physics, etc), claiming optimal 
decisions between models and methodologies, design and implementation, in an 
ever-upgrading field. Precise orbit determination and positioning constitutes 
one of the most complex and demanding problems in Satellite Geodesy, one that 
is always evolving due to its multi-disciplinary nature and the ever-growing 
disposal of satellite missions and data.

1.4 State-of-the-art & Innovation
=================================

Currently, only four such software packages exist ([6]) worldwide, but are 
neither open source, nor free. The objective of the proposed project is to 
design and implement an orbit determination and positioning software tool using 
DORIS data, introducing on the way novel approaches, and validating state-of-the-art 
methodologies. We aim at a robust methodology providing quality satellite 
state estimates, one though that can be efficient enough to be implemented for 
near-real time applications. Hence, algorithmic design and implementation, as 
well as efficiency and resource awareness are all topics to be considered. 

We expect that the outcome of the project will be an innovative, state-of-the-art 
software package, open and free to the scientific community.

Guidelines set by the IDS act as the de-facto standard for orbit determination
via DORIS. We will try to comply with this set of recommendations as close as 
possible, deviating when needed to check and validate alternate or novel 
processing approaches. Specific points of novelty, will be:

  * use of RINEX-only observation files ([12]) (as opposed to the widely used, 
    older doris2.2 format). Allow parsing of near real-time RINEX data parsing.

  * use of measured satellite attitude (quaternion-based) determination (as 
    opposed to the common attitude-law approach). According to [9], using 
    measured satellite attitude (satellite body orientation in the quaternion 
    form and solar panel angles) instead of nominal attitude results in 
    slightly better Precise Orbit Determination results

  * full compliance with the IERS2010 ([13]) models for transformation between 
    celestial and terrestrial reference frames, including the 2006/2000A 
    precession/nutation models and new mean pole model ([11])

  * use of the latest EIGEN time-variable gravity (TVG) models RL04 ([14]) and 
    respective dealiasing products

  * use of the newest FES2014/FES2014b ([15]) ocean tide models

  * use modern design patterns and implementation details, including template 
    metaprogramming and compile-time mathematical functions (e.g. [16]). Note 
    that most relevant software packages have to be complant with legacy code, 
    written deceads ago, thus prohibiting use of modern programming approaches

  * use of a modern, widely used and user-friendly distribution and dissemination 
    approach. Enable software distribution via Docker ([17]), instead of the 
    cumbersome approach of source-code release and building.

1.5 Scientific and social impact
================================

We expect that the results of this proposal will have a strong effect, first 
and foremost in the scientific community.

The results and outcomes of the project will enhance our knowledge on Satellite 
Geodesy, Earth and Atmospheric Physics and Orbit Determination/Astrodynamics. 
Applying state-of-the-art methodologies and novel approaches will greatly enhance 
the collective knowledge and provide crucial feedback and conclusions. It will 
reveal drawbacks and limitations and act as a validation platform for the most 
modern modeling approaches and theories.

Additionally, the community will be provided with a state-of-the-art, free and 
open software, a fact expected to drive interest and attention to one of the 
most prominent and robust space-geodetic techniques. Scarcity of such a tool is 
on of the basic reasons why the system has a more limited user community (as 
e.g. compared to GPS/GNSS) even though it's application range and accuracy is 
on the same level.

Via the software tool that will be developed, DSO will be able to contribute 
to the IDS, thus in turn strengthening the Service's contribution to a series 
of products vital to the scientific community (e.g. realization of ITRF, Earth 
attitude, etc). IDS products, as all collective space-geodetic services e.g. 
the IGS and ILRS, are based on an accumulation of individual Analysis Centers 
results; hence the Service is in search of top-quality scientific contributors.

DSO itself will also largely benefit from contributing to such a high-caliber 
Service. IDS is a collective organization of a series of elite institutions, 
such as the National Centre for Space Studies (CNES), Goddard Space Flight 
Center (NASA/GSFC), European Space Operations Centre (ESA/ESOC) and Jet Propulsion 
Laboratory (NASA/JPL). Cooperation and collaboration with such renowned 
institutions will hugely benefit both the personnel involved (research team) and 
the NTUA/DSO, gaining unprecedented expertise on the subject.

2 Methodology and Implementation
==============================================================================

2.1 Research Methodology
========================

Core software development will be performed using the C++ programming language, 
taking advantage of its speed and versatility. Various minor, peripheral parts 
of the package will be developed using Python, allowing development speed and 
ease of use (for end users).

As a first step to tackling the challenges posed in the proposal, the research 
team will first evaluate and refactor current software tools already designed 
and developed throughout the previous years (e.g. [18]) and investigate current 
state-of-the-art models and algorithms to be implemented and incorporated in the 
software.

Throughout the first year, the research team will design and develop software 
to handle the complicated modeling of orbital mechanics for Low Earth Orbiting 
(LEO) satellites. Fundamental forces acting on earth orbiting bodies will be 
treated using robust, elaborate, state-of-the-art models, describing and 
compensating for their effects (e.g. atmospheric drag, solar radiation pressure, 
etc).

Reference frames and time systems (scales), play a major role in the modeling of 
orbital dynamics. Special care will be taken, to implement the most recent 
earth attitude models, as described by the International Earth Rotation Service 
(IERS Standards 2010, [13]). Displacement of reference points (on the Earth's 
crust) and loading effects (ocean, sold-earth, atmospheric) will be curated using 
the most recent standards.

Integrators are of fundamental importance in orbit determination, since they 
allow the (numerical) solution of the equations of motion, accounting for 
perturbation effects. This system of Ordinary Differential Equations, called 
the variational equations, plays a crucial role in both the quality and the 
efficiency of the orbit determination process. We will focus on designing and 
implementing a multistep integrator, using the Adams-Bashforth-Moulton, 
Predict–Evaluate–Correct–Evaluate (PECE) algorithm (e.g. [21]).

DORIS system observables (observation equations) will be formulated using the 
DORIS RINEX format/data files, and following the rigorous approach described in 
[19]. Novel approaches will be introduced here, estimating the relative frequency 
offsets using second degree polynomials with process noise.

Once these components are in place and tested, the research team will implement 
satellite-specific models and parts of the software for the targeted satellites. 
Attitude determination will be performed using measured data via the quaternion 
approach when available (at least for Jason-3). If no such data is published, 
the so called satellite-specific "attitude law" will be implemented to model 
rigid body rotations. Satellite-specific macromodels ([20]) will be used to 
compute surface area and on-board phase center eccentricities.

Using the above satellite-specific approach, part of the forces acting on the 
space vehicle will be refined, using an elaborate modeling of the satellite 
geometry, attitude and design characteristics. Most notably, drag forces and 
solar radiation pressure effects will be modeled using this satellite-specific 
approach.

Parameter estimation will be performed via the (Extended) Kalman Filter algorithm 
[21]. All parameters describing the satellite state, the orbit and force model 
dynamics (e.g. atmospheric drag and solar radiation pressure coefficients) and 
beacon-specific frequency/clock parameters will be estimated, using a sophisticated 
stochastic approach. Model and observation noise characteristics and their 
impact on the methodology and respective results will be thoroughly tested.

Lastly, the research team will incorporate the estimation of Earth Orientation 
parameters (Earth rotation axis pole coordinates and Length of Day) [23] 
within the analysis process at the level of geodetic precision.

2.2.1 Brief outline of the overall work plan
============================================

During the first three months (WP1), the research team will evaluate and refactor 
current, already available software developed during the last years within the 
host institute (e.g. [24] and [25]). This will act as a starting ground for further 
development.

In WP2, the fundamental parts of the software suite will be designed and developed; 
all core parts (including orbit dynamics, reference frames, force modelling and 
integration) of the analysis tools will be implemented in this nine month 
span. Depending on the needs, new source code will be written from scratch, or 
evaluated source code (from WP1) will be adopted and upgraded to meet state-of-the-art 
standards.

Once the core parts of the software are ready, the research team will start the 
development of satellite-specific components, including attitude determination 
and space vehicle macromodels, as well as refinement of the force model to take 
into account indivudual satellite geometry (WP3). It is expected that a three-month 
period of development will be enough for each case. 

Shortly after a working version of the software for the first satellite (Jason-3), 
has been reached, the evaluation process will take place, along with the 
processing of older (than current), "historic" data (WP4) to obtain results for 
orbit determination, positioning and other parameters of interest. Bug-fixes and 
software refinements are expected to take place within this period, which will 
last untill the end of the project.

Once the bulk of the processing results from WP4 is ready, the research team 
will move on to evaluate and validate the estimated parameters and hence the 
overall software efficiency (WP5). Position estimates of ground stations in the 
vicinity of Greece will be accumulated and analyzed to estimate crustal behaviour 
(a task demanding results of utmost accuracy) and compared to times series derived 
from GNSS analysis (e.g. [26]). Orbital parameters will be validated using the 
IDS published results (sp3c orbits).

2.2.2 Description of each Work Package
======================================

WP Number 1, Objectives:
  Evaluation and validation of already developed software tools by the host 
  institution (e.g. [24] and [25]). Setting of standards, design patterns and 
  development and algorithmic guidelines to be followed later on. Gaining a 
  clear view on the starting ground and further development needs of the 
  core parts of the software. Refactor existing source code to comply to the 
  proposal's needs.

WP Number 3, Objectives:
  Upgrade the core software to meet the demands and accuracy of Precise Orbit
  Determination and Positioning, by implementing individual satellite attitude 
  model, design geometry and macromodels. Derive a state-of-the-art DORIS 
  processing software suite.

Description of the Work:
  Implement space-vehicle attitude determination (either quaternion based if 
  possible or using phase law). Implement satellite-specific geometrical design 
  (e.g. vehicle-fixed reference frame), on-board phase center offset and 
  macromodels. Use the the aforementioned tools to refine satellite force 
  modeling (e.g. computation of projected areas for drag and radiation) and 
  observation modeling (e.g.reduction of observation vectors to receiver 
  phase center). Release software beta versions once satellite-specific modeling 
  is through for each individual satellite.

WP Number 5, Objectives:
  Evaluation and validation of results obtained by the software developed, using 
  products of the utmost quality. Identification of deficiencies and further fine 
  tuning; derive proposals for further enhancements and methodology/algorithmic 
  enhancements. Determination of mismodeling effects or non-mitigated error sources 
  and recommend specific patterns or study areas for their curation.

Description of the Work:
  Stack position estimates derived from the processing of data performed in 
  WP4, to get time-series for DORIS network beacons, in and/or around Greece. 
  Analyze the time-series to derive crustal dynamics (tectonic velocity and 
  harmonics signals if any) on each point and compare with results for GPS/GNSS 
  colocated sites.
  Ritrieve IDS published orbits (in Sp3c format) and compare with the estimates 
  obtained by the processing in WP4. Compare estimated Earth Orietation parameters 
  to the ones published by the IERS.


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
[9] "Impact of nominal and measured satellite attitude on SLR- and DORIS-derived orbits of Jason satellites and altimetry results", S. Rudenko, J. Zeitlhöfler, M. Bloßfeld and D. Dettmering, Ocean Surface Topography Science Team Meeting (OSTST) 2019, 21-25 October 2019, Chicago, Illinois, United States of America
[10] "DORIS results on Precise Orbit Determination and on geocenter and scale solutions from CNES/CLS IDS Analysis Center contribution to the ITRF2020", H. Capdeville, J-M. Lemoine, A. Mezerette and G. Moreaux, EGU21-5384, G2 - Reference Frames and Geodetic Observing Systems, G2.4 - Precise Orbit Determination for Geodesy and Earth Science
[11] "IDS Recommendations and suggestions for ITRF 2020 reprocessing", International DORIS Service, https://ids-doris.org/images/IDS_RecommendationsITRF2020_04.02.2020.pdf,  Retrieved 10 October 2022.
[12] "RINEX DORIS 3.0 (Issue 1.7)", CNES & IDS, ftp://ftp.ids-doris.org/pub/ids/data/RINEX_DORIS.pdf, Retrieved 10 October 2022.
[13] "IERS Conventions (2010)", G. Petit and B. Luzum (eds.), International Earth Rotation and Reference Systems Service (IERS), IERS Technical Note No. 36, 2010 
[14] "CNES/GRGS RL04 Earth gravity field models, from GRACE and SLR data. GFZ Data Services", Lemoine J-M.l, Biancale R., Reinquin F., Bourgogne S., Gégout P. (2019), https://doi.org/10.5880/ICGEM.2019.010
[15] "FES2014 global ocean tide atlas: design and performance", F. H. Lyard, D. J. Allain, M. Cancet, L. Carrère, and N. Picot, Ocean Sci., 17, 615–649, https://doi.org/10.5194/os-17-615-2021, 2021
[16] "More constexpr for <cmath> and <complex>", E. J. Rosten,  O. J. Rosten, Programming Language C++, Library Working Group, 2019 (available at https://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1383r0.pdf)
[17] Docker, https://www.docker.com/
[18] "Designing a DORIS processing software for orbit determination and estimation of geodetic parameters", X. Papanikolaou, M. Tsakiri, S. Nahmani and A. Pollet, Reference Frames for Applications in Geosciences (REFAG), Thessaloniki-Greece, 2022
[19] "Precise orbit determination and station position estimation using DORIS RINEX data", J.-M. Lemoine, H. Capdeville, L. Soudarin, Advances in Space Research 58 (2016) 2677–2690
[20] "DORIS satellites models implemented in POE processing", L. Cerri, A. Couhert, P. Ferrage, CNES & IDS, 2022
[21] "Implementation of Gauss-Jackson Integration for Orbit Propagation", M. M. Berry and L. M. Healy, The Journal of the Astronautical Sciences, Vol. 52, No. 3, July–September 2004
[22] "Real-time orbit determination of Low Earth orbit satellite based on RINEX/DORIS 3.0 phase data and spaceborne GPS data", C. Zhou, S. Zhong, B. Peng, J. Ou, J. Zhang, R. Chen, Advances in Space Research, Volume 66, Issue 7, 2020
[23] "Estimation of the Length of Day (LOD) from DORIS observations", P. Štěpánek, U. Hugentobler, M. Buday, V. Filler, Advances in Space Research 62 (2018) 370–382
[24] "Development of an in-house DORIS processing software", X. Papanikolaou, V. Zacharis, M. Tsichlaki, S. Nahmani, A.Pollet, M. Tsakiri, J. Galanis, IDS Analysis Center Workshop, Venice-Italy, 2022
[25] "Validating DORIS meteo data", V. Zacharis, M. Tsichlaki, X. Papanikolaou, M. Tsakiri, IDS Analysis Center Workshop, Venice-Italy, 2022 
[26] "Routine Analysis of all available GNSS Stations in Greece: Processing Scheme and Dissemination of Products and Data", X. Papanikolaou, D. Anastasiou, A. Marinou, V. Zacharis, D. Paradissis, EGU General Assembly Conference, 2015
