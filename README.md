# Methodology of development and creation of simulation environments.
## Introduction
the purpose of this document is to provide you with the different methods, strategies and alternatives regarding the development of realistic simulation environments and how to create, optimize, manipulate and manage them.
## Slope
it should be clarified that this document emphasizes the worlds developed for the gazebo simulation environment, but this does not mean that the generated models or meshes cannot be modified according to other needs.
you can find more information about the repositories for which we have developed the methods here :
[GAZEBO](https://github.com/gazebosim) and [ROS]()
## Get it started
the following workflow outline presents the order and structure in which the method proposed here should be developed.
![Workflow Outline](https://github.com/jebaeros/Worlds_documentation/raw/main/metodology.png)
following the workflow sequence, we will show the different options and alternatives for the development of the solution environment and the required tools.
### System Requirements

#### Hardware:

- **Processor**: Quad-core or higher
- **Memory (RAM)**: 8 GB or more
- **Graphics Card**: Dedicated GPU with at least 2 GB VRAM
- **Storage**: SSD with 128 GB of free space

#### Software:

- **Operating System**: Ubuntu 18.04 LTS or higher, or Windows 10
- **Blender**: Latest stable version
- **Gazebo**: xxx
- **ROS**: xxx
- **Agisoft**: 1.17

#### Other Requirements:

- Internet connection for software installation
- Up-to-date device drivers
- Additional storage space for projects and data

### Step 1: Get the Information

The information pertains to all the necessary data for constructing the models that will be integrated into our world. This can include photogrammetry, models from other creators, satellite images, etc. This information will serve as the starting point for developing our environments and it is required to be as comprehensive as possible and of the highest quality. Corrupt or inaccurately measured data could result in inefficient or incomplete meshes that may lead to errors or degrade the experience.

For this project, we will be employing two methods: obtaining images through photogrammetry and obtaining images through GIS tools.

#### GIS method
To perform this method, you must make use of the following tools:

- Install [Blender](https://blender.org/) here, preferably version 3.6.5.
- Install the Blender addon from the repository [BLOSM](https://github.com/vvoovv/blosm).
#### About BLOSM:

BLOSM is a Blender addon that enables us to utilize APIs for the creation of 3D geographic or topological models. With BLOSM, we can create detailed reliefs and capture various details, curvatures, and characteristics of a study area. Additionally, BLOSM allows us to generate extrusions of structures or buildings present in the images obtained through specialized algorithms for detection and interpretation. For more information, visit the developer's page.


#### About Blender:

Blender is a powerful tool for editing and producing 3D models, multimedia, and more. Its versatility and practicality in editing make it ideal for processing heavy meshes, where other editing software may struggle. Blender offers a wide range of features and capabilities, including:
- **Modeling**: Create complex 3D models with ease.
- **Animation**: Bring your models to life with sophisticated animation tools.
- **Rendering**: Produce high-quality renders of your scenes.
- **Simulation**: Simulate various phenomena such as physics, fluids, and particles.
- **Compositing**: Combine multiple layers and effects to create stunning visuals.
- **Scripting**: Customize and automate tasks with Python scripting.



