---
title: "Forecasting of optical turbulence"
sub_title: "When weather forecast comes to the rescue of astronomy and optical communication"
last_modified_at: 2022-11-05T11:00:00-00:00
tags: 
  - Light propagation
  - Atmosphere
---

Optical turbulence (OT) is a generic term referring to the impacts of [atmospheric turbulence](https://www.focals.be/2022/05/04/atmospheric-challenges.html) on the propagation of optical waves in general. It is often used in both fields of astronomy and optical communication, especially when describing different quantities, tools or approaches to characterize atmospheric effects on optical waves. In this post, a general approach for forecasting OT is presented, that has many applications at astronomical and optical communication sites.

# Forecast of $C_n^2$ profiles
Atmospheric turbulence leads to fluctuations of the optical refractive index, modifying the direction of the waves. As introduced in [this post](https://www.focals.be/2022/06/19/meet-the-refractive-index-structure-parameter.html), the intensity of the refractive index fluctuations is commonly described thanks to its structure parameter, denoted $C_n^2$. The larger $C_n^2$, the larger the refractive index fluctuations, and the worse the impacts on the optical waves. Moreover, in the atmosphere, $C_n^2$ varies with the altitude $h$, leading to so-called $C_n^2$ profiles: $C_n^2(h)$.

$C_n^2$ profiles are of particular interest to characterize OT, since many other related quantities (e.g. the seeing, the Fried parameter, etc.) can be obtained mathematically from such profiles. Hence, forecasting OT often boils down to the forecast of $C_n^2$ profiles. In other words, the main goal is to estimate $C_n^2$ profiles at a given location and at particular times in the future, relying on a pre-determined approach.

# General approach for OT forecast
The first time OT forecast has been introduced is for astronomical applications, in 1986 [Coulman 1986]. Indeed, such a forecast would enable to assist and optimize the scheduling of telescope observations during the nights, e.g. by delaying observations requiring very good atmospheric conditions to periods where those conditions are forecast. Since then, many OT forecasting techniques have been explored, even though they tend to follow the general approach presented below, in Figure 1. Furthermore, this approach is now starting to be applied to optical communication sites as well, in order to identify the best locations and times to use for optical links through the atmosphere.

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/approach_simplified.png){: .align-center}  
_Figure 1: General approach to perform OT forecast and obtain $C_n^2$ profiles (Adapted from [Quatresooz 2022])._

Weather forecast, thanks to [numerical weather prediction](https://en.wikipedia.org/wiki/Numerical_weather_prediction) (NWP) simulations, is at the hearth of OT forecast. Indeed, starting from the current status of the atmosphere above a given area, one can run NWP simulations to forecast the meteorological quantities above this area in the future. As an example, the ground temperature over Europe is depicted on the left side of Figure 1, but in practice this is a real 3D grid of meteorological data describing the atmosphere status that is retrieved. Such grids often have a fixed temporal and spatial resolution, and another benefit of NWP simulations is to enhance those resolutions at the location of interest. By running these simulations, one ends up with a 3D grid of simulated and forecast meteorological quantities, as highlighted in the center of Figure 1. By using nested domains, i.e. imbricated subareas over which NWP simulations are run, the spatial resolution at which meteorological quantities are obtained can be improved, giving access to a 1 km resolution above Belgium for example.

At this stage, there is no much difference with weather forecast that have been providing, with more or less reliability, predictions of Earth's weather since several decades. However, the last step differs: based on those high-resolution simulated meteorological quantities, a $C_n^2$ model is applied to obtain a grid of predicted $C_n^2$. From such grid, a vertical slice directly above the location of interest can be extracted to get access to a $C_n^2$ vertical profile, and its time variation can be monitored. This is illustrated on the right part of Figure 1.

The key element here is the $C_n^2$ model. At this stage, it can be seen as nothing more than a "black box" taking meteorological quantities as inputs, and giving $C_n^2$ as an output. Many models actually rely on simple analytical expressions, giving for example $C_n^2$ as a function of the atltitude $h$, the pressure $p$, the temperature $T$, etc.: $C_n^2(h,p,T,...)$. Generally, those models are derived either theoretically based on the mechanics of turbulence, or from empirical measurements. More details and references about this approach can be found in [Quatresooz 2022].

As a final step, not depicted in Figure 1, validation of predicted $C_n^2$ profiles is important. This is often achieved thanks to OT measurements at the location of interest, that are then compared to the predictions. However, such measurements are costly to obtain. 

# Applications
Now that one has access to predicted $C_n^2$ profiles above a location of interest, how can they be used?

As mentioned previously, for astronomical applications, OT forecast is paramount for the flexible scheduling of astronomical observations based on OT conditions. It is also of interest for studying OT at the locations of observatories without needing costly measurement campaigns. Finally, it helps for designing adaptive optics systems, as introduced in [this post](https://www.focals.be/2022/05/04/atmospheric-challenges.html), namely by defining the system conditions of operations.

Regarding optical communication, applications are similar: OT forecast helps for the scheduling of optical links, as well as for the design of future optical communication terminals. It is also of major interest for site selection, i.e. studies of several locations to choose the one best suited for a future optical communication ground station. Since it is unpractical to obtain long-term OT measurements on multiple sites, running NWP simulations and forecasting OT is an easier solution, provided that the predictions are reliable.


# Limitations
OT forecast thanks to NWP simulations has many applications and benefits. However, it also suffers from several limitations:
- The computational power and time required to run those simulations may be quite large, especially for high-resolution simulations. A trade-off must be studied here, between the required resolution and the computational cost. There is no interest to OT forecast if, due to the computation time, forecasts are available after the times at which they are forecasting the meteorological data.
- The reliability of forecast is sometimes questionable, and is associated to the trust that can be given to weather forecast. The experience shows that forecast of small-scale weather or over long-term horizon are less reliable than forecast of large-scale atmospheric phenomena in the coming hours or days.
- Specifically to OT, the modelling of turbulence in the boundary layer, i.e. the atmospheric layer the closest to the ground, is a challenge due to its small-scale and its importance in OT effects. The development of dedicated $C_n^2$ models taking into accoung the boundary layer is a possible solution to this issue.

Despite those limitations, more research is being conducted on this topic and its future is promising. Indeed, thanks to future increases in computational power, NWP simulations will get cheaper and will enable to model small-scale phenomena with improved resolutions, increasing the reliability of forecast.


# References and further readings
- [Coulman 1986] Coulman, C., Andre, J.-C., Lacarrere, P., and Gillingham, P., “The observation, calculation, and possible forecasting of astronomical seeing,” Publications of the Astronomical Society of the Pacific 98(601), 376 (1986).
- [Quatresooz 2022] Quatresooz, F., Orban de Xivry, G., Absil, O., Vanhoenacker-Janvier, D., Oestges, C., "Challenges for optical turbulence characterization and prediction at optical communication sites," ICSO 2022.

