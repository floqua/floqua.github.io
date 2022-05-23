---
title: "Introduction to optical communication for space applications"
sub_title: "Using light to communicate through space..."
last_modified_at: 2022-05-23T14:00:00-00:00
tags: 
  - Light propagation
  - Free space optical communications
---

**..-.  ...  ---**? Do you remember once using a flashlight to send Morse code to a friend? Then both of you were using a form of optical wireless communication. Now imagine doing it so fast that your eyes cannot see the flashlight blinking anymore, transmitting more data that your brain would never be able to process, over distances that cannot be travelled in a lifetime. THIS is real optical wireless communication.

# Optical wireless communications
Optical Wireless Communication (OWC) refers to the use of light to convey an information signal wirelessly, i.e. without needing a support (e.g. an optical fiber) to guide the signal. Usually, such communications are performed through vacuum, air or even water, making use of visible, infrared or ultravioled light. 

Figure 1 depicts the electromagnetic (EM) spectrum: the visible light region is highlighted and corresponds to the light that can be seen by the human eye. Its wavelength, i.e. the spatial period of the EM wave, is between 380 to 750 nanometers (1 nm = 10<sup>-9</sup> m). Next to the visible region are the ultraviolet and infrared regions, also of interest for optical communication. Increasing the wavelength to the order of centimeters, meters, or even more leads to region of the radio waves that is where most wireless communication devices currently operate (this is the case of mobile phones for example). Making use of visible light to communicate can thus simply be seen as modifying the operating wavelength of today's devices. In practice, things are not so simple and completely different technologies must be used.

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/EM_spectrum.png){: .align-center}
<p class="text-center">Figure 1: Electromagnetic spectrum.</p>

The acronym OWC can designate communication systems having completely different ranges: it includes indoor (short-range) systems such as Li-Fi (a technology using light to provide network and mobile communications in similar applications as Wi-Fi) or chip-to-chip communications (communications at the scale of an electronic device to transfer information between neighboring chip without needing wired connections). It also includes outdoor (long-range) applications that are referred to as Free Space Optical (FSO) communications. This is the case of terrestrial links (e.g. vehicle-to-vehicle communications, [backhaul](https://en.wikipedia.org/wiki/Backhaul_(telecommunications)) links), Earth-to-space links and space links. A possible classification of OWC systems is presented in Figure 2. In the following, focus will be given to FSO communications. 

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/OWC_classification.png){: .align-center}
<p class="text-center">Figure 2: Classification of optical wireless communication systems.</p>

# Free space optical communications
The use of FSO communications is mainly driven by its advantages with respect to classical radiofrequency (RF) communications, including:
- A large modulation bandwidth: optical frequencies are in the order of hundreds of THz, offering larger modulation bandwidths than RF systems. The larger the modulation bandwidth, the more data can be transmitted per second, hence increasing the data rate;
- A narrow beam divergence and a high directivity, given the smaller wavelength of optical waves;
- An unlicensed spectrum, thanks to the high directivity of optical beams. For classical RF communications, licensing is required to avoid interference when using the same frequencies since RF waves tends to propagate in all directions;
- An increased security: signal interception is made difficult by the high directivity;
- Reduced power consumption, weight and size of the systems compared to RF terminals. This is especially of interest for space applications.

The high directivity, as presented above, is seen as an advantage. However, it is also an important challenge regarding the acquisition, tracking and pointing of optical systems that must be sufficiently accurate. Think about a laser pointer that you want to steer from the ground towards a moving satellite located at hundreds of kilometers of altitude. Not an easy task right?

Nevertheless, based on these advantages, FSO communications for space applications are getting interest, for space links and for Earth-space links.


### Space links
**Inter-satellite links:** optical links are used as relay between low Earth orbit (LEO) satellites and geosynchronous (GEO) satellites that then convey the information back to Earth. This is the case of the *European Data Relay Satellite* ([EDRS](https://artes.esa.int/european-data-relay-satellite-system-edrs-overview)) constellation of the European Space Agency (ESA), of which [two satellites are already operational](https://eoportal.org/web/eoportal/satellite-missions/content/-/article/edrs) so far (May 2022). Other examples include the future *Laser Communications Relay Demonstration* ([LCRD](https://www.nasa.gov/mission_pages/tdm/lcrd/index.html)) from the National Aeronautics and Space Administration (NASA) or the *Laser Utilizing Communication System* ([LUCAS](https://www.satnavi.jaxa.jp/ja/project/lucas/)) from the Japanese Space Agency (JAXA).

**Deep space link:** future exploration of the solar system will be in high definition thanks to the increased data rate offered by optical communications. For example, NASA is currently working on the *Deep Space Optical Communications* ([DSOC](https://www.nasa.gov/mission_pages/tdm/dsoc/index.html)) demonstration, to be part of the [Psyche mission](https://en.wikipedia.org/wiki/Psyche_(spacecraft)) scheduled for launch in summer 2022.

Even though it is not a deep space link in the strict sense, the *Lunar Laser Communication Demonstration* ([LLCD](https://www.nasa.gov/directorates/heo/scan/opticalcommunications/llcd/)) from NASA is also worth mentioning. In October 2013, the first optical link between a spacecraft orbiting the Moon and a ground station on Earth has been achieved. This corresponds to a distance of 385 000 kilometers and is thus the longest optical link achieved to date (May 2022). However, it may not hold this record for long since new Moon-to-Earth optical links are scheduled for [Artemis II](https://www.nasa.gov/specials/artemis/), i.e. the NASA mission that plans to bring astronauts back to the Moon. Indeed, the [Orion spacecraft](https://www.nasa.gov/exploration/systems/orion/index.html) will be equipped by an optical communications terminal named *Orion Artemis II Optical Communications System* ([O2O](https://esc.gsfc.nasa.gov/projects/LEMNOS?tab=overview)).

### Earth-space links
Space links are useful to forward and relay data in space. However, at some point, a link from Earth or back to Earth is always needed. Such ground-to-satellite links are named *feeder links* and can be of two types: 
- *uplink*: when data is sent from Earth to a satellite or a spacecraft;
- *downlink*: when data is sent from space to Earth.

Ground-to-satellite optical communications are particularly challenging because of the Earth's atmosphere, especially because of clouds and atmospheric turbulence.

**Clouds:** nothing can be done against them. Clouds absorb optical wavelengths more than RF waves, hence they have a greater impact on optical communications. Think about clouds blocking the light from the sun such that it is not visible anymore. Two potential solutions to mitigate cloud blockage of optical communication are being explored.

The first solution is simple: it consists in delaying the optical communication to a time when there is no cloud anymore. Weather forecast can be of interest to determine beforehand the time windows that can be used for optical links.

The second solution is to use site diversity: instead of having a single optical ground station to communicate with a satellite, several ground stations located at different locations can be used. The locations are chosen to have *uncorrelated* atmospheres such that it is unlikely that clouds will prevent communication with all ground stations at the same time. Nevertheless, this solution requires all ground stations to be connected together. Based on measurements or atmospheric simulations, maps depicting ideal locations for building future optical ground stations are currently being studied. 

**Atmospheric turbulence:** even under a clear sky (i.e. without cloud), atmospheric turbulence damages the received and emitted optical waves. One possible solution is to use adaptive optics to correct the distortions introduced by the turbulence, as briefly introduced in this post about [atmospheric challenges for astronomy](https://www.focals.be/2022/05/04/atmospheric-challenges.html).

Current research trends on this topic also include the prediction of atmospheric turbulence using numerical weather prediction simulations, just as clouds could be predicted to block optical communication links at a given time.


Despite these challenges, demonstrations of ground-to-satellite optical communications have been performed in recent years [Toyoshima 2021].

# References and further readings:
- [Toyoshima 2021]: M. Toyoshima, "Recent Trends in Space Laser Communications for Small Satellites and Constellations," in _Journal of Lightwave Technology_, vol. 39, no. 3, pp. 693-699, 1 Feb.1, 2021, doi: 10.1109/JLT.2020.3009505.
- NASA optical communications: 
[https://www.nasa.gov/directorates/heo/scan/opticalcommunications](https://www.nasa.gov/directorates/heo/scan/opticalcommunications)
- Free space optical communications: [https://en.wikipedia.org/wiki/Free-space_optical_communication](https://en.wikipedia.org/wiki/Free-space_optical_communication)
