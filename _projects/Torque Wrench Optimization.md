---
layout: project
title: Torque Wrench Optimization
description: Mechanics of Materials Final Project
technologies: [Solidworks, ANSYS]
image: /assets/images/RW deflection.png
---

For my final project in Mechanics of Materials I was tasked with optimizing a custom design for a non-racheting, 3/8 inch drive torque wrench rated for 600 in-lbf. This includes material selection, geometry optimization, strain gauge specification, and FEM (ANSYS) with custom boundary condition setups to iterate and optimize.

For my final design, I ultimately settled on a stainless steel 440 tempered alloy with the following material properties and dimensions.

![Shaded rendering of earlier version]({{ "/assets/images/RW better material properties.png" | relative_url }}){: .inline-image-r style="width: 450px"}

![Photo of old radio]({{ "/assets/images/RW drawing.png" | relative_url }}){: .inline-image style="width: 450px"}

The key dimensions here include the diamter of the rod (0.55"), the total length of the wrench (16"), the distance from the center of the drive to the end of the wrench (15"), and the dimensions of the drive (.375" square with flats of height 0.4"). The key material properties for the selected stainless alloy are yield strength (261 ksi), Poisson's ratio (0.275), and tensile strength (268 ksi).

In my FEM analysis in ANSYS, an important stage was to properly reflect the real usage of a torque wrench by accurately setting up boundary conditions. This meant first applying a zero displacement condition to the four faces of the wrench drive, and secondly applying a force to the load point of the wrench on the far end. This force is applied in the direction normal to the drive and parallel with the end face in the y direction as depicted.

This applied force corresponds with the required torque rating for the wrench of 600 in-lbf. To back out the correct force application from the desired moment about the drive, this rating goal of 600 in-lbf was divided by 15, the distance from the end of the wrench to the center of the drive, to result in a force of 40 lbf.

![Photo of old radio]({{ "/assets/images/RW displacement setup.png" | relative_url }}){: .inline-image-l style="width: 1000px"}

![Photo of old radio]({{ "/assets/images/RW force setup.png" | relative_url }}){: .inline-image-l style="width: 1000px"}

Below are images of the normal strain contours in the strain gauge direction from my finalized FEM analysis, and a contour plot of maximum principal stress.

![Photo of old radio]({{ "/assets/images/RW normal strain.png" | relative_url }}){: .inline-image-l style="width: 1000px"}
![Photo of old radio]({{ "/assets/images/RW max principlal stress.png" | relative_url }}){: .inline-image-l style="width: 1000px"}

The above plots indicate a maximum principal stress of 91308 psi, and a normal strain in the strain gauge direction of 0.0019313 in/in. These are just a couple of key solutions to retreive from the structural ANSYS setup. The primary three results to investigate are the maximum normal stress throughout the wrench, the load point deflection, and the strain at the strain gauge location, which will be discussed more in the following section. Those results are respectively shown below.

![Photo of old radio]({{ "/assets/images/RW max normal stress real.png" | relative_url }}){: .inline-image-l style="width: 1000px"}
![Photo of old radio]({{ "/assets/images/RW deflection.png" | relative_url }}){: .inline-image-l style="width: 1000px"}

The maximum normal stress found in the ANSYS results was a stress of 67,943 psi in the Z Axis at the tensile loading point of the wrench drive geometry. This stress concenration forms at the contact point between the drive and the wrench geometry itself, which is why there is a significant spike up from the ~30,000 psi stress near the gauge location, which more accurately reflects my hand caculations. Still, given this true stress at the drive, there is a safety factor of 3.85 against yielding, which will comfortably avoid failure of the wrench, and also encompasses small changes in the mesh used in the FEM model. At the load point, the wrench will deflect 0.403".

The design of the strain gauge itself is a very important consideration in this process as it is the primary driving force behind successful operation of the torque wrench and its sensitivity. To accurately understand what the strain is at the given parameterized location of 1 inch from the drive, I first set up a coordinate system at this location. This system allowed me to probe the strain in the gauge direction at the location of the strain gauge that will be seeing the most strain. For this design, I've chosen a half bridge with a bridge factor of 0.5 at the 1" distance from the center of the drive. Assumptions were confirmed with the FEA model, and one gauge will be in tension while the other is in compression under the specified loading. The torque wrench sensitivity calculations are as follows: (Gauge Factor)x(Strain At Gauge)x(Bridge Factor) = (2)(1.7e3)(.5) = 1.7. This satisfies the requirements of the design.

![Photo of old radio]({{ "/assets/images/RW strain probe.png" | relative_url }}){: .inline-image-l style="width: 1000px"}
![Photo of old radio]({{ "/assets/images/RW strain probe coordinate.png" | relative_url }}){: .inline-image-l style="width: 500px"}
![Photo of old radio]({{ "/assets/images/RW strain probe results.png" | relative_url }}){: .inline-image-l style="width: 400px"}

<div style="clear: both;"></div>