# Introduction

For our project, we chose to model a skipping stone in the hopes of answering the question: What is the best angle at which to throw a skipping stone in order to have both the most skips and the furthest distance travelled? We chose this topic because skipping stones is something that everyone has experience with and memories of, yet we rarely think about how it is possible for a rock to skip across water. It is something we were really curious about, and additionally wanted to understand how to be successful in getting the most skips out of a single throw. To do this, we are creating a model based on a paper discussing the idealized physics of a skipping stone. This paper also offers its own results into the number of skips that can be obtained from any given stone tilt which agree very closely with real life observations.

Scientific Model

	We assume an ideal skipping stone: a uniform thickness h=1cm, a circular face with a radius R = 5cm, and a reasonable mass density of ??=2.5 g/cm^3. We then have a stone mass determined by the equation

m_s=?_s pR^2 h

	This stone is thrown horizontally outward and experiences forces exerted on it by gravity and air resistance a_d, so the stone’s acceleration in each the x and y directions are

a_x=-a_(d_x )

a_y=-a_(d_y )-g

	The stone strikes the water at an angle ??, and with a tilt ?? relative to the surface of the water. Once it hits the water, it feels a force normal to its surface (that is, at an angle ??+90). When the water pushes at this angle, the direction of the stone’s velocity is changed until its remaining velocity is in the direction of ??. This is what allows the stone to skip: it slides in the direction of its tilt and parallel to the water instead of plunging into it, so the stone is no longer subject to the normal forces exerted by the water.

	The resulting velocity of the exiting velocity in the x direction is

v_(x out)=|v_in |cos(-ß+a)cosa

In the y direction, which is also dampened by gravity, the exiting velocity is

v_(y out)=|v_in |cos(-ß+a)sinav(1-2Rgsina/?(|v_in |cos(-ß+a)sina)?^2 )

Numerical Model

	The stone’s velocity through the air (i.e. for y>0) is computed using Euler’s method:

v_x (t+dt)=v_y (t)+a_x dt

v_y (t+dt)=v_y (t)+a_y dt

	For the instant that it touches the water (i.e. when the height switches from positive to negative), it’s y-position is set to 0 and its new velocities are given by the above equations for exiting velocity. This yields the following stone trajectories for different cases:

In the case where the tilt of the stone alpha is set to 0.3 radians and a velocity of 10m/s horizontally, the stone skips 9 times:
