# ResultThree
_Utilities for animating [Modelica](https://modelica.org/) results in [three.js](https://threejs.org/)_

3D animation is an essential tool for developing and debugging physical systems because it allows developers to use their highly-trained eyes and experience of the physical world to look for modeling errors.
Yet animation is overlooked by many Modelica tools; they may have a basic capability but most of their development/UX effort is elsewhere.
The problem is twofold: experienced developers work on the needs of experienced users, and of the resources gap between solo/small team Modelica users and corporate / university research groups.
[Modelica By Example](https://mbe.modelica.university/) is a great resource, but only because Dr. Tiller decided to create it; it was not 'needed' or produced by any of the leading Modelica organizations, by those who determine tool development priorities.

I have been frustrated in making animations for the [MonthlyMechanisms](/tags/monthly-mechanism), dealing either with OMEdit's [inability](https://github.com/OpenModelica/OpenModelica/issues/9503) to display STLs and save animations ([this was recorded by screencap](https://mechanomy.com/posts/220701_tensegrityTable/#simulation-results)) or the [DLR's poor rendering](https://mechanomy.com/posts/230116_viseHammer/#results) rendering.
Other people have this problem [as](https://stackoverflow.com/questions/76051951/modelica-4-0-0-multibody-animation-how-to-read-stl-files) [well](https://stackoverflow.com/questions/74119665/cant-use-custom-3d-model-for-visualization/74149149).

What do *you* want in a Modelica animation tool?

My initial design is bare-bones: a post-simulation script taking the model and result files, producing an animation according to parameters.
Rigid bodies will use the same shape= field to specify the shape, though allowing more advanced files like glTF.
Initially, it will be restricted to models contained in a single file, as parsing a modelica package tree is tedious.
Animation will be performed by three.js, with an optional output of the three.js scene JSON.
The basic workflow will be an MIT-licensed Julia package, email me for translations into other languages.

## How you can help:
* what Modelica tool and scripting language do you prefer to use?
* what systems are you modeling, can you send me an example link?
* and, because the wheels need to turn, is your use commercial?
Please leave comments on [GitHub](https://github.com/mechanomy/ResultThree/discussions/1).

## Existing work:
* I wrote an [module](https://github.com/JuliaIO/MAT.jl/pull/181) for MAT.jl to read Modelica v4 .mat files
* [MeshCat.jl](https://docs.juliahub.com/MeshCat/CZdjb/0.11.1/) - focused on creating Three.js viewers from Julia processes
* [Modia3D](https://modiasim.github.io/Modia3D.jl/stable/tutorial/GettingStarted.html#.-Pendulum-with-Animation) - not there yet, cannot handle kinematic loops
* ?

