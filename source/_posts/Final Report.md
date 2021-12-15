---
title: 'Final Report'
date: 2021-12-15
comments: false
---
## Sketch Based 3D Modelling


### <span style="text-decoration:underline;">Motivation</span>

In recent years, digital painting programs like photoshop and clip studio paint  have been gaining popularity and the programs have been adding functionality to help users draw easily, for example adding perspective guidelines to help draw objects in perspective. One of the areas where I think the programs can improve is having 3d models for shading reference. Most programs do not provide this functionality or have limited functionality in this area, for example Clip studio paint provides 3d models, but the number of models are limited and there is no way to create custom models. Thus, an easy way 


### <span style="text-decoration:underline;">Aim</span>

Create a 3-D modelling interface/system that closely resembles a 2-D sketching interface. More specifically, have methods to add an object based on the input sketch and cut parts from the created object. Optionally, add options to smoothen/sharpen the model. 


### <span style="text-decoration:underline;">Summary and Uses</span>

Having a 3-D modelling interface that is close to 2-D sketching can help people get introduced to 3-D modelling without having to deal with a complicated interface. It can also help in modelling concept art, as concept art does not require a lot of detail as it is supposed to be a rough example.


### <span style="text-decoration:underline;">Related Works</span>

Sketch based modelling systems can be divided into 4 categories according to [Kazmi et al., 2014]  but I will be focussing on two of those four categories as they are the most relevant to my project.


#### <span style="text-decoration:underline;">Single-View Systems</span>

“Teddy:A skating interface for 3D free-form design”[Igarashi et al., 2006] is one of the first and the biggest single view modelling system. It pioneered the research in inflated geometrical surfaces, one of the recent papers that use inflated geometrical surfaces is “Monster Mash: A Single-View Approach to Casual 3D Modeling and Animation”[Dvorožňák et al., 2020]. While teddy is good for modelling organic models like a plush toy, it is not very useful for modelling shapes with sharp features like a cube.

In recent years, there have many papers that apply Deep learning to sketch based modelling.[Delanoy et a., 2018]


### <span style="text-decoration:underline;">Implementation Details</span>

I implemented the sketching interface in Blender for two reasons-



* Blender is free and is also used by many beginners
* Blender has an embedded Python interpreter, so you can write python scripts to utilize the inbuilt tools

For now, I have two working tools-



* Convert the user's  2-D sketch to a mesh object
  
<img src="https://youtu.be/rbyxzaf-lf4" alt="drawing" width="400"/>

* Subtract the overlapping area based on the user's sketch

 

The algorithm for the Draw method-



1. Convert GPencil object to a curve
2. Convert the curve object to a mesh
3. Remove vertices based on a threshold distance to help create faces
4. Remove extra edges and vertices 
5. Create faces 
6. Use solidify modifier to add thickness

The algorithm for the Subtract method-



1. Join the end points of the user created curve
2. Use the steps from the draw methods to create a mesh object with the same thickness 
3. Use the Boolean difference operator to subtract the original mesh from the subtraction mesh


### <span style="text-decoration:underline;">Challenges</span>



* Initially, I was trying to use a deep learning based which included training a GAN on 3D models based on [Wu et al., 2016] but I could not understand how to generalize it for free form shapes. So in order to have some results for this project, I decided to implement it in blender instead.
* The d

 

	


### <span style="text-decoration:underline;">References</span>

[Kazmi et al., 2014] I. K. Kazmi, L. You and J. J. Zhang, "A Survey of Sketch Based Modeling Systems," 2014 11th International Conference on Computer Graphics, Imaging and Visualization, 2014, pp. 27-36

[Igarashi et al., 2006]Takeo Igarashi, Satoshi Matsuoka, and Hidehiko Tanaka. 2006. Teddy: a sketching interface for 3D freeform design. In ACM SIGGRAPH 2006 Courses (SIGGRAPH '06). Association for Computing Machinery, New York, NY, USA, 11–es. DOI:[https://doi.org/10.1145/1185657.118577](https://doi.org/10.1145/1185657.118577)

[Dvorožňák et al., 2020]Marek Dvorožňák, Daniel Sýkora, Cassidy Curtis, Brian Curless, Olga Sorkine-Hornung, and David Salesin. 2020. Monster mash: a single-view approach to casual 3D modeling and animation. ACM Trans. Graph. 39, 6, Article 214 (December 2020), 12 pages. DOI:[https://doi.org/10.1145/3414685.3417805](https://doi.org/10.1145/3414685.3417805)

[Wu et al., 2016]Jiajun Wu, Chengkai Zhang, Tianfan Xue, William T. Freeman, and Joshua B. Tenenbaum. 2016. Learning a probabilistic latent space of object shapes via 3D generative-adversarial modeling. In Proceedings of the 30th International Conference on Neural Information Processing Systems (NIPS'16). Curran Associates Inc., Red Hook, NY, USA, 82–90.