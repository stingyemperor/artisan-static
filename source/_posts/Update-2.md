---
title: 'Update-2'
date: 2021-11-18
comments: false
---
### Summary of Work

I was having trouble going from sketches to 3-D models since there are many variables to consider. So I have been working on a simpler case of 3-D reconstruction from images, since there is a lot of study material available for that particular problem. I have been working with 3D GAN’s to generate 3-D models. The 3-D GAN is based on the paper “Learning a Probabilistic Latent Space of Object Shapes via 3D Generative-Adversarial Model”. Some generated airplane voxel models are shown below.



<img src="https://raw.githubusercontent.com/stingyemperor/artisan-static/master/source/_posts/images/air.PNG" alt="drawing" width="400"/>


<img src="https://raw.githubusercontent.com/stingyemperor/artisan-static/master/source/_posts/images/air2.PNG" alt="drawing" width="400"/>



### Challenges

The biggest challenge I have been facing is modelling free form shapes. The GAN I am currently working on requires pre-existing 3-D models to train on, and thus the scope of shapes it can output is limited. Also, the learning times for the models are very long, so I need to find a way to make my code run faster. But the information available for models working on free form shapes is very limited, and the code available is tricky to work through.


### Plan of Completion

The work to complete the project can be divided into three parts-



1. Making the user interface for the project to allow drawing and editing of shapes. I have not yet started working on this, but since there are many implementations available online, I do not think it should be too difficult
2. Working on making a GAN model that can make normal maps or some other representation of 3-D data in a fast an accurate fashion. This is by far the hardest portion of the project and there are hardly  any tutorials available online.
3. Rendering the 3-D model. This portion of the project is pretty straightforward as there are many implementations available online. 
