---
layout: project
title: Torque Wrench Optimization
description: Mechanics of Materials Final Project
technologies: [Solidworks, ANSYS]
image: /assets/images/RW deflection.png
---

For my final project in Mechanics of Materials I was tasked with optimizing a custom design for a torque wrench. This includes material selection, geometry optimization, strain gauge specification, and FEM (ANSYS) with custom boundary condition setups to iterate and optimize.

For my final design, I ultimately settled on a stainless steel 304 1/4 hard alloy with the following material properties and dimensions.

![Shaded rendering of earlier version]({{ "/assets/images/RW material properties.png" | relative_url }}){: .inline-image-r style="width: 450px"}



![Photo of old radio]({{ "/assets/images/RW drawing.png" | relative_url }}){: .inline-image style="width: 450px"}

In my FEM anlysis in ANSYS, an important stage was to properly reflect the real usage of a torque wrench by accurately setting up boundary conditions. This meant first applying a zero displacement condition to the four faces of the wrench drive, and secondly applying a force to the load point of the wrench on the far end. This force is applied in the direction normal to the drive and parallel with the end face as depicted.



![Photo of old radio]({{ "/assets/images/RW displacement setup.png" | relative_url }}){: .inline-image-l style="width: 1000px"}

![Photo of old radio]({{ "/assets/images/RW force setup.png" | relative_url }}){: .inline-image-l style="width: 1000px"}

Below are images of the normal strain contours in the strain gauge direction from my finalized FEM analysis, and a contour plot of maximum principal stress.

![Photo of old radio]({{ "/assets/images/RW normal strain.png" | relative_url }}){: .inline-image-l style="width: 1000px"}
![Photo of old radio]({{ "/assets/images/RW max principlal stress.png" | relative_url }}){: .inline-image-l style="width: 1000px"}

<div style="clear: both;"></div>