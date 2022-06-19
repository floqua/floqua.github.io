---
title: "Meet the refractive index structure parameter"
sub_title: "How to describe atmospheric turbulence effects on optical waves?"
last_modified_at: 2022-06-19T14:00:00-00:00
tags: 
  - Light propagation
  - Atmosphere
  - Scintillation
---
Put a straw in a glass of water and take a close look. It appears to be bent or, even worse, broken in two. This is because of [refraction](https://en.wikipedia.org/wiki/Refraction), the physical phenomenon behind the redirection of waves (such as light) when there is a change of propagation medium (i.e. water to air in this case). Similarly, the Earth's atmosphere modifies the trajectory of light. In fact, our atmosphere is not a uniform medium since each layer of air has its own properties (pressure, temperature, density, ...). Hence, refraction occurs between the different layers, forcing the light from a star to zigzag before reaching our eyes for example. Why a zigzag and not just a curved path? Because of turbulence in the atmosphere that randomly modifies local atmospheric properties, thus randomly changing the redirections of the light. This leads to the [twinkling of stars](https://www.focals.be/2022/05/01/twinkling.html), also named scintillation.

In this post, the goal is to go further than just qualitatively describing the twinkling of stars. We want to determine quantities of interest to be able to quantify this twinkling based on atmospheric conditions. This is achieved thanks to the refractive index structure parameter, noted $C_n^2$ and introduced below.


# The refractive index as a random field
### Definition of the refractive index
The optical refractive index $n$ is a number (without unit) that describes the impact of a medium on light propagation. Each medium has its own refractive index: it is equal to $1$ for vacuum, close to $1.00027$ on average for air and approximately $1.33$ for water. In the example presented above, the direction of the light between water and air is modified due to the change of refractive index between these two media. The light bending, i.e. refraction, at the interface of two media can be computed using [Snell's law](https://en.wikipedia.org/wiki/Snell%27s_law), knowing their respective refractive indices and the angle of arrival of the light (see Figure 1).

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/refraction.png){: .align-center}
*Figure 1: Snell's law of refraction. Due to the change of refractive index between the two media, the incident light is bent in the second medium*.

Furthermore, the refractive index is also useful to determine the speed of light and the wavelength (i.e. the spatial period) of a wave in the medium. For example, the speed of light in a medium of refractive index $n$ is given by $\frac{c}{n}$, with $c$ being the speed of light in vacuum ($c=299~792~458$ m/s). 

### The refractive index of air
Often, the refractive index of air is assumed to be equal to $1$ since its first three decimals are zero. However, these decimals and the ones after matter, especially when considering atmospheric turbulence. They induce tiny changes on the refractive index that are exactly what we need to characterize the scintillation. 

An expression of the optical refractive index of air (assuming a wavelength of 500 nm, that corresponds to the cyan color) is presented below [Andrews 2005]:

$$ n(p,T) \approx 1 + 0.000079 \frac{p}{T}.$$

It involves the pressure $p$ in [hPa] and the temperature $T$ in [K] of the considered air parcel. Because of the dependency of $n$ with the pressure and the temperature, one can understand that local variations of pressure or temperature due to atmospheric turbulence will lead to local fluctuations of the refractive index.

### Turbulence and random field
Turbulence is a complex phenomenon, involving eddies in the fluid motion at several scales spanning from hundreds of meters to millimeters. As theoretical physicist and Nobel Prize winner Richard Feynman said, "turbulence is the most important unsolved problem of classical physics."

Nowadays, turbulence still remains an unsolved problem. Nevertheless, we now have capabilities to simulate fluid turbulence to a certain extent, with large eddy simulations or direct numerical simulations for example. When applied to small regions of the atmosphere, such simulations are similar to weather forecast. They start with an initial description of the atmosphere state and then predict its evolution by solving physical equations describing the motion of fluids (Navier-Stokes equations). The main difference with weather forecast is the resolution achieved, i.e. the spatial length at which meteorological quantities are simulated. This makes such simulations particularly expensive in terms of computations, making them unpractical for simulating the whole atmosphere. Moreover, this would also imply to know a complete description of the atmosphere initial state, impossible to obtain in practice.

Instead, since it is impossible to know the turbulence in a deterministic way, it is modeled statistically. In such statistical description, *the refractive index is considered as a temporal and spatial random field*. Behind these terms are hidden important concepts.

In physics, a *field* is nothing more than a generic word for describing regions of our 3D space associated with a physical quantity. We can understand it as applying a (discrete) grid over the space where each point can be referenced by its coordinates in space (usually denoted by a vector $\mathbf{r}=(x,y,z)$) and in time (at an instant $t$). Each of this point has physical quantities associated to it, such as the refractive index, the pressure, the temperature, ... For example, the refractive index field at position $\mathbf{r}$ and time $t$ can be denoted $n(\mathbf{r},t)$. This enables to describe temporal and spatial evolution of the field, as depicted in Figure 2.

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/field_illustration.png){: .align-center}
*Figure 2: illustration of a **refractive index field**, for two consecutive time instants. Colors depict refractive index values, varying in space and in time*.

Then, there are the *random variations* of this field. Think of the refractive index at a given location that can be obtained by rolling a dice. Each grid point (i.e. each point in the field) would then be associated to a dice, and a realisation of the turbulence at an instant would be modeled by rolling once all the dices. At the next instant, all dices are rerolled, giving a new realisation of the turbulence.

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/random_field_illustration.png){: .align-center}
*Figure 3: illustration of a **random refractive index field** (depicted by a "dice field"), for two consecutive time instants. Dice values depict random refractive index values, varying in space and in time*.

All in all, this gives a stochastic (i.e. random) representation of atmospheric turbulence. In practice, three differences with this simple analogy should be highlighted:

- The atmospheric refractive index field is continuous in space and time, and not discrete as the grid presented above. Furthermore, the refractive index can take continuous values, on the contrary of the dicesthat are limited to their face values of $(1;~2;~3;~4;~5;~6)$. 
- Only the refractive index fluctuations around the average are considered random. This would be equivalent to substitute the "dice field" by a mean value of $3.5$ ($=(1+2+3+4+5+6)/6$) applied everywhere and then rolling dices having face values of $(-2.5;~-1.5;~-0.5;~0.5;~1.5;~2.5)$.  The sum of the mean value $3.5$ and the fluctuations would then give the dice previous values of $(1;~2;~3;~4;~5;~6)$. Hence, the refractive index field is expressed as
$$ n(\mathbf{r},t)=n_0 + n_1(\mathbf{r},t)$$
with $n_0$ the refractive index mean and $n_1$ the fluctuations. In general, the mean $n_0$ can also vary with the field position.

- Finally, refractive index fluctuations are correlated in space and time. In our "dice field", this would mean that neighboring dices influence the value of a dice. For example, if all neighbors have large values ($5$ or $6$ for example), it is likely the dice in the middle will get a large value. Similarly, if at a given instant all dices in a region have large values, they will most likely get large values at the next instant.

Figure 4 gives a realistic simulation of a one-dimensional horizontal slice of the refractive index field $n_1(\mathbf{r},t)$. It highlights the correlation between neighboring fluctuations, i.e. when fluctuations are large at a given $x$-position, they are also large at neighboring positions.

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/synthetic_fluct.png){: .align-center}
*Figure 4: simulation of horizontal refractive index fluctuations $n_1$ as a function of the distance $x$ and for a given time $t$*.

The simulation from Figure 4 is possible thanks to the knowledge of important statistical quantities describing the refractive index fluctuations, such as the refractive index structure parameter $C_n^2$.

# The refractive index structure parameter: $C_n^2$
As mentioned previously, neighboring fluctuations are correlated. A possible tool to quantify the correlation of fluctuations is the refractive index structure function $D_n(\mathbf{\rho})$, whose definition is
$$ D_n(\mathbf{\rho})~=~ \left\langle \left(n_1(\mathbf{r}+\mathbf{\rho})-n_1(\mathbf{r})\right)^2\right\rangle,$$
with $\mathbf{\rho}$ a vector depicting the distance between two points in space, one located in $\mathbf{r}$ and the other located in $\mathbf{r}+\mathbf{\rho}$. Hence, the structure function computes the difference between neighbouring fluctuations and squares it. Since the fluctuations are random, an average over all possible realisations is made (denoted by the $\langle \cdot \rangle$ symbol) in order to obtain a deterministic function.

Assuming homogeneity and isotropy, Kolmogorov showed that the structure function depends only on the absolute distance $\rho=|\mathbf{\rho}|$ between two points and can be obtained by [Andrews 2005]:
$$ D_n(\rho)~=~ C_n^2 \rho^{2/3}.$$

This results has been derived using [dimensional analysis](https://en.wikipedia.org/wiki/Dimensional_analysis) and involves the refractive index structure parameter $C_n^2$, whose units are $m^{-2/3}$. This expression for the structure function is only valid in the inertial range, i.e. a range of spatial scales in which energy from larger eddies is assumed to be given to smaller eddies, following the Richardson's [energy cascade](https://en.wikipedia.org/wiki/Energy_cascade) theory. Mathematical transformations of $D_n(\rho)$ can also give the *Kolmogorov spectrum* that has been used to generate the fluctuations presented above.

Things are starting to get quite technical here but the key message to remember is the introduction of $C_n^2$: it is nothing more and nothing less than a statistical parameter (i.e. a number) describing how strong the fluctuations of the refractive index are. The larger the $C_n^2$, the larger the fluctuations of $n_1$. This is highlighted in Figure 5 with the same 1D simulation as in Figure 4 but with different $C_n^2$ values.

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/synthetic_fluct_Cn2.png){: .align-center}
*Figure 5: simulations of horizontal refractive index fluctuations $n_1$ as a function of the distance $x$ and for a given time $t$, with **varying $C_n^2$ values** *.

Thanks to this observation, one can understand that if $C_n^2$ is large, refractive index fluctuations will be large and hence the bending of light (i.e. refraction) following the variations of this refractive index will also increase. It will thus increase the observed twinkling phenomenon. On the contrary, low $C_n^2$ values lead to reduced twinkling.

# Variations with altitude: $C_n^2$ profiles
Hence, the refractive index structure parameter $C_n^2$ seems to be an important parameter to characterize the twinkling of stars but how can it be obtained?

Two approaches are possible: either direct measurements in the atmosphere (e.g. using balloons rising in the atmosphere and sampling $C_n^2$ values along their ascent) or physical modeling of $C_n^2$ based on other quantities (such as the pressure or the temperature). Indeed, in a general case, $C_n^2$ is not constant and varies with altitude. Astronomers are thus interested in obtaining a $C_n^2$ profile, i.e. values of $C_n^2$ as a function of the altitude $h$. Usually, turbulence is larger close to the ground and so is $C_n^2$. With increasing altitude, $C_n^2$ tends to decreases, with often a bump at the tropopause (the [tropopause](https://en.wikipedia.org/wiki/Tropopause) is an atmospheric layer between 9 to 17 km of altitude depending on the latitude in which the temperature is quite constant and at which [jet streams](https://en.wikipedia.org/wiki/Jet_stream) are found).

The most well-known $C_n^2$ profile is the Hufnagel-Valley $5/7$ (HV-5/7) model [Andrews 2005]. It is depicted in Figure 6. On the $x$-axis, $C_n^2$ is represented whereas the altitude is on the $y$-axis. One can indeed observe large $C_n^2$ values close to ground, as well as a bump at the tropopause altitude. 


![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/HV_example.png){: .align-center}
*Figure 6: Hufnagel-Valley 5/7 $C_n^2$ profile. Close to ground, $C_n^2$ is large, reaching values larger than $10^{-14}$ $m^{-2/3}$. It then decreases with increasing altitudes, with a bump at the tropopause (around the altitude of 10 km)*.

The Hufnagel-Valley model is an empirical model (i.e. based on measurements) and describes a typical average $C_n^2$ profile in the atmosphere. However, $C_n^2$ also varies in time: it is smaller during the night than during the day, and it has a seasonal dependency as well. On top of that, $C_n^2$ varies in space: it depends on the altitude as already presented but also on the locations on Earth. Finally, isolated turbulent layers can often be generated in the atmosphere, leading to local increases of $C_n^2$ that are not depicted in an average $C_n^2$ profile such as HV-5/7.


# Summary: applications of $C_n^2$ profiles
To sum up, quantifying the twinkling of stars requires to use a statistical description of the refractive index fluctuations, considering it as a spatial and temporal random field. The intensity of these fluctuations is influenced by $C_n^2$, the refractive index structure parameter. It varies with altitude, leading to $C_n^2$ profiles.

Knowledge of $C_n^2$ profiles is particularly useful in astronomy: it provides information to choose best locations to build telescopes, away from atmospheric turbulence. This is achieved by selecting sites having $C_n^2$ profiles with low $C_n^2$ values, e.g. being above the large $C_n^2$ values of the ground layer. Furthermore, instantaneous $C_n^2$ profiles give information about the location (i.e. altitude) of turbulent layers, that can then be corrected using [adaptive optics](https://www.focals.be/2022/05/04/atmospheric-challenges.html) for example. 

Similarly, $C_n^2$ profiling also helps to carry out site selection for future optical communication systems. It is also of interest for the design of such systems and to determine ideal time windows during which a successful optical communication link can be achieved (doing $C_n^2$ profile predictions).

Nevertheless, $C_n^2$ remains a statistical quantity giving on average how strong the refractive index fluctuations are. To obtain precisely the values of these fluctuations at a given instant and location, atmospheric turbulense sensing, e.g. making use of guide stars, is required and is at the hearth of adaptive optics systems.


# References
- [Andrews 2005] L. C. Andrews and R. L. Phillips, Laser Beam Propagation through
Random Media, Second Edition. SPIE Press, 2005.