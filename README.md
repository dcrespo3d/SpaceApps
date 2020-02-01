# SpaceApps

These demos have been developed for the 2018 International NASA Space Apps Challenge.

There are four demos here:

* [Seasons](https://dcrespo3d.github.io/SpaceApps/seasons/index.html)
* [Stable Orbits](https://dcrespo3d.github.io/SpaceApps/orbital/stable01.html)
* [Unstable Orbits 1](https://dcrespo3d.github.io/SpaceApps/orbital/unstable01.html)
* [Unstable Orbits 2](https://dcrespo3d.github.io/SpaceApps/orbital/unstable02.html)

***

Seasons
-------

The first demo, "Seasons", represents the earth from the point of view of the sun, as it rotates around it, and also over itself. When completing full rotation around the sun, (this) earth completes 12 rotations around itself, so this is not a "real" demo, but the axis of inclination of the earth self-rotation is correct. So the inclination of the earth as viewed from the sun is visible, and the north hemisphere is more tilted towards the south in boreal summer, and more tilted towards the north in boreal winter. The demo starts in boreal summer.

***

Orbits
------

In the next three demos, Orbits, there are four bodies:

* one central star (0 - sun)
* a near body (1 - mercury)
* a intermediate body (2 - venus)
* a far body (3 - earth)

The gravitatory interactions are calculated every frame, and the resulting forces are used to recalculate the velocity of the bodies, which ultimately affects their position.

All pairs of interactions are calculated:
* 0 - 1 (sun - mercury)
* 0 - 2 (sun - venus)
* 0 - 3 (sun - earth)
* 1 - 2 (mercury - venus)
* 1 - 3 (mercury - earth)
* 2 - 3 (venus - earth)

The "stable orbits" demo features an stable configuration.

The other "unstable orbits" modifies relative masses and initial position, so after some time one of the bodies is ejected from the system, and close encounters create orbital perturbations.

Components: Body System and Orbital Trail
-----------

The [body system component](./js/bodysystem.js) calculates gravitatory interactions between pairs of bodies, calculating forces. Forces produce accelerations on bodies which are summed on every body. The acceleration on a body modifies its velocity, and the velocity modifies its position. Everything is calculated every frame.

The [orbital trail component](./js/trail.js) calculates and draws an orbital trail which vanishes as it gets older. It differs from a typical trail from game engines, so that a regular trail vanishes with trail length, but this orbital trail vanishes with the trail angle. The idea is that the trail vanishes (approximately) after one rotation of the orbit, independently of the proximity of the orbiting body to the central body. Due to its angular approach, it works correcly even for highly elliptical orbits.

***

A-Frame
-------

These demos have been developed with [A-Frame](https://aframe.io/), a Virtual Reality framework initially developed by Mozilla.
