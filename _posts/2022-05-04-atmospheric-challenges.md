---
title: "Atmospheric challenges for astronomy"
sub_title: "How to tackle atmospheric turbulence and absorption?"
last_modified_at: 2022-05-04T18:00:00-00:00
tags: 
  - Atmosphere
  - Scintillation
  - Adaptive optics
  - Space telescope
---

<img src="image.jpg" class="align-left" alt="">
<img src="image.jpg" class="align-center" alt="">
<img src="image.jpg" class="align-right" alt="">

In their fascinating quest of observing the universe, astronomers are facing gargantuan challenges such as the *faintness* of distant objects, the *blindness* arising from absorption in nebulae (i.e. gas clouds) or even *light pollution* from human activities. And one of the biggest of these challenges is also the closest to us: the Earth's atmosphere and its associated *blurriness*.


# Atmospheric turbulence
Turbulences in the Earth's atmosphere are associated to local fluctuations of physical quantities such as the pressure, the temperature and the humidity. In turn, their variations lead to fluctuations of the refractive index, inducing scintillation on the received light. Scintillation is defined as temporal and spatial variations of the received intensity of a wave owing to turbulence in the propagation medium. This is the physical phenomenon behind the [twinkling of stars](https://www.focals.be/2022/05/01/twinkling.html).

Hence, atmospheric turbulence is responsible for blurring images of space objects, limiting the achievable resolution of optical telescope. Luckily, astronomers found creative solutions to avoid or reduce these damages.


## First solution: gain altitude

As far back as 1703, Sir Isaac Newton had recognized that telescopes “cannot be so formed as to take away that confusion of the rays which arise from the tremors of the atmosphere. The only remedy is a most serene and quiet air, such as may perhaps be found on the tops of the highest mountains above the grosser clouds” [Duffner 2009].

The solution is thus to build observatories and telescopes at high altitude, on mountain tops for example. At these locations, the air is thinner. The propagation path through the atmosphere is also reduced, and so is the scintillation. Other motivations to build telescopes at high altitudes are related to the lower cloud coverage and the reduced light pollution (away from cities).

In 2010, **Astronomy magazine** published a map showing the locations of main optical telescopes (Fig. 2). Most of them are indeed located at high altitudes, for example in La Palma (altitude: 2400 m), on the top of the Mauna Kea (altitude: 4200 m) or in Chile (altitude: above 2000 m, up to 5600 m).

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/map_optical_telescopes.png){: .align-center}
*Figure 1: locations of main optical telescopes in the world (Source: Astronomy Magazine, Volume 18, Issue 11, November 2010. Retrieved from [universe-review.ca](https://universe-review.ca/R08-11-instruments.htm))*.

### Space telescopes
Pushing this idea of gaining altitude to its limit, one ends up with *space telescopes*. Despite their increased costs and the difficulties of maintenance, space telescopes are ideal solutions to avoid scintillation, atmospheric absorption (see below) and light pollution. In space, stars are not twinkling since their light did not propagate through the turbulent Earth's atmosphere.

The first successful space telescope is the American Orbiting Astronomical Observatory OAO 2, launched in 1968. Since then, many more have been launched, a complete list being available on this [Wikipedia page](https://en.wikipedia.org/wiki/List_of_space_telescopes).

The most well-known space telescope is probably the *Hubble Space Telescope* (HST), launched in 1990 and still operational at this date of writing. It is orbiting the Earth at 540 km of altitude, with a period of 95 minutes. Between 1993 and 2009, it has been serviced 5 times using the space shuttles. It is looking in the near-infrared and at visible and ultraviolet light.

Its successor in the infrared is also well-known: the James Webb Space Telescope (JWST). Launched successfully in December 2021, it is expected to produce its first science images in summer 2022.


## Second solution: adaptive optics
Alternatively to space telescopes, improvements on ground telescopes can be made in order to correct partially for optical turbulence. This is achieved thanks to *adaptive optics*.

Its underlying principle is to (mechanically) compensate the wavefront distortions prior to imaging, using for example a deformable mirror.  This is illustrated in Figure 2: the perturbed light from a star is reflected by a mirror in such a way that atmospheric turbulent effects are corrected (i.e. going from a distorted wavefront to a plane wavefront). In order to determine how to deform the mirror, the light wavefront is analyzed and commands are then applied to the deformable mirror. It is thus a closed-loop system working at a rate of a few kilohertz. Ideally, the final image should be free from atmospheric abberations.

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/ao_illustration.PNG){: .align-center}
*Figure 2: illustration of adaptive optics (Source: [Badkoubeh 2017])*.

Adaptive optics is similar to **equalization** in radio frequency (RF) communications. It requires two important steps: acquiring information about the atmospheric damages on the light and correcting for these using the deformable mirror. Sometimes, reference stars sufficiently bright and close to the target of interest can be used to acquire the information about the atmospheric turbulence. However, better approaches making use of laser guide stars (LGS) have been developed.

Laser guide stars are artificial stars created by focussing a laser emitted from the ground. The laser can be focussed at a desired altitude, relying either on Rayleigh scattering (focus between 10 to 20 km of altitude) or on the Sodium emission (focus between 90 to 95 km of altitude). More details can be found in [Duffner 2009].

In a way, laser guide stars are similar to **pilots** used for channel estimation in RF communications. They are also expected to be help for ground-to-satellite optical communications, namely for uplink, i.e. communication links from the ground to the satellite.

# Atmospheric absorption
Aside from atmospheric turbulence, the atmosphere is also responsible for absorbing light at particular wavelengths, making observations in X-rays, ultraviolet light and part of infrared light impossible. This is illustrated in Figure 3. This absorption comes from the different gases present in the atmosphere, such as water vapor and carbon dioxide that are mostly responsible for the absorption in the infrared.

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/atmospheric_absorption.png){: .align-center}
*Figure 3: illustration of Earth's atmospheric opacity (Source: NASA, retrieved from [Wikipedia](https://en.wikipedia.org/wiki/James_Webb_Space_Telescope#/media/File:Atmospheric_electromagnetic_opacity.svg))*.

Atmospheric absorption can hardly be avoided. As for atmospheric turbulence, space telescopes are a potential solution, with for example the JWST that is looking in the infrared.

# Summary
In summary, the Earth's atmosphere is responsible for the twinkling of stars and the absorption of light. These effects make the work of astronomers more difficult, leading to the development of several solutions such as space telescopes or adaptive optics.

Similarly, ground-to-satellite optical communications also have to tackle these challenges, urging for alternative solutions: space optical terminals won't solve the problem of sending information back to Earth, and considered optical terminal locations may not be on mountain tops. Adaptive optics is a promising solution for downlink (i.e. from satellite to ground) communications but will need to be adapted for uplink (i.e. from ground to satellite) communications.

# References
- [Duffner 2009]: Duffner, R., "The Adaptive Optics Revolution: A History", University of New Mexico Press, 2009.
- [Badkoubeh 2017]: Badkoubeh, A., Zhu, G., & Beguenane, R., "Open-Loop Adaptive Optics with Closed-Loop Control of Deformable Mirror".
