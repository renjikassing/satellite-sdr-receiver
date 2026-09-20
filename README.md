# Satellite SDR Receiver
A V-Dipole antenna tuned to receive 137 MHz satellite signals, paired with an SDR to process them.

## Hardware
* Two copper rods, 54.5 cm long, 3mm outer diameter, 0.25mm wall thickness
* RTL-SDR; NooElec NESDR Smartee V2
* NooElec SAWbird+ NOAA, saw filter + LNA
* NooElec Flamingo+ FM Notch Filter
* Two SMA male-to-male barrel jacks
* 50-ohm SMA female panel mount connector
* RG-58, 7mm ferrite chokes
* 3D-printed stand, PLA
* Fasteners to secure rods to stand
* Laser-cut tripod, 3mm plywood

## Photos


## Design
### Antenna elements
* The copper rods are 54.5 cm long, which is a quarter-wavelength at 137 MHZ.
* The 120 degree angle of the rods creates a wide radiation pattern allowing reception from front to back, ideal for a satellite passover. It also gives the antenna a 50-ohm impedance at resonance.
* The rods are soldered to the panel mount connector with 2-inch stranded wire to allow for frequent transport and reduce the risk of electrical connection breakage.
### RF Chain
* The RF chain was designed to reduce interference. The FM notch filter is placed closest to the feedpoint, removing strong FM signals, then is followed by the SAWbird+ to increase gain and further dampen unwanted signals.
* The RG-58 is run perpendicularly to the rod plane for >2 ft to prevent unintended coupling with the antenna. Ferrite chokes were placed on the RG-58 to further reduce common-mode current.
### Stand and Tripod
* The stand is modular to allow for easy transport and removal of the antenna elements. It strictly holds the rods at 120 degrees.
* The entire assembly is roughly 2.5 feet tall, taller than a quarter-wavelength, to reduce the risk of the antenna elements  interacting with the ground. This size still permits portability.

## Workflow
1. The rods are fastened into the stand's top piece with clamps and fasteners. The panel mount connector is positioned in the central hole.
2. The stand's top piece slots into the middle piece, then the middle piece into the tripod with dovetail mounts.
3. The Flamingo+ is attached to the panel mount connector with a male-to-male jack.
4. The SAWbird+ is attached to the Flamingo+ with a male-to-male jack.
5. The RG-58 is connected to the SAWbird+ through the tripod's center hole and strapped to its central piece.
6. Ferrite chokes are added adjacent to the SAWbird+ feedpoint.
7. The RG-58 is screwed into the RTL-SDR, which is plugged into a laptop.
8. Place the antenna away from metal objects, ideally at least 7 feet away, with a clear sightline of the sky. Move the laptop as far as practically possible.
9. Aim the antenna's apex directly North or South, and ensure the rods' plane is parallel with the ground.
10. Use SDR software to listen for signals, or SatDump to track satellites and process signals.

## Signal
My antenna received a signal consistent with an ORBCOMM passover at 137.8 MHz, as seen next to the DC spike. The waterfall demonstrates the signal's Doppler-shifting as the satellite moved.
<p align="center">
  <img src="images/orbcomm.png" width="500">
</p>

## Future Improvements
1. The antenna should be used in a less RF-dense environment, as this antenna was operated in a busy part of New York City. Such an environment inevitably suffers from RF interference.
2. The antenna should be taller, as my best testing location is surrounded by metal that is likely detuning it, including rebar within the terrace, metal on the tables, and metal railings.
