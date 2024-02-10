# Methodology for Development and Creation of Simulation Environments

## Introduction

The purpose of this document is to provide a comprehensive guide to various methods, strategies, and alternatives for developing realistic simulation environments. We'll cover how to create, optimize, manipulate, and manage these environments effectively.

## Emphasis on Gazebo Simulation Environment

It's essential to clarify that this document primarily focuses on worlds developed for the Gazebo simulation environment. However, it's worth noting that the generated models or meshes can be modified to suit other needs as well.

For more information about the repositories associated with our methods, you can visit the [GAZEBO](https://github.com/gazebosim) and [ROS]() repositories.

## Workflow Outline

The following workflow presents the sequence in which the proposed method should be developed:

![Workflow Outline](https://github.com/jebaeros/Worlds_documentation/raw/main/metodology.png)

Following this workflow sequence, we'll explore different options and alternatives for developing the solution environment and the tools required.

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

### Step 1: Obtain Information

The information required for constructing the models includes photogrammetry, models from other creators, satellite images, etc. It's crucial to ensure this data is comprehensive and of the highest quality to avoid errors or degraded experiences. We'll utilize two methods: obtaining images through photogrammetry and obtaining images through GIS tools.

#### GIS Method

To perform this method, you'll need the following tools:

- Install [Blender](https://blender.org/) (preferably version 3.6.5).
- Install the Blender addon from the repository [BLOSM](https://github.com/vvoovv/blosm).

##### About BLOSM:

BLOSM is a Blender addon that enables us to utilize APIs for creating 3D geographic or topological models. It offers advanced features such as detailed reliefs, extrusions of structures, and more. Visit the developer's page for further information.

##### About Blender:

Blender is a powerful tool for editing and producing 3D models, multimedia, etc. Its versatility and practicality in editing make it ideal for processing heavy meshes. 

#### Let's Get Started:

1. **Download the BLOSM addon**.
   
2. **Open Blender**.
   
   ![Step 2](https://github.com/jebaeros/Worlds_documentation/blob/main/gis%20method/1.png)

3. Navigate to the **Edit** section and select **Preferences**.
   
   ![Step 4](https://github.com/jebaeros/Worlds_documentation/blob/main/gis%20method/3.png)

4. Go to the **Add-ons** section.
   
   ![Step 5](https://github.com/jebaeros/Worlds_documentation/blob/main/gis%20method/4.png)

5. Click on **Install** to add the addon and navigate to the downloaded .zip file.
   
   ![Step 6](https://github.com/jebaeros/Worlds_documentation/blob/main/gis%20method/5.png)

6. Search for 'BLOSM' again in the addons and activate the addon by clicking on 'import-export:blosm'.
   
   ![Step 7](https://github.com/jebaeros/Worlds_documentation/blob/main/gis%20method/7.png)

7. **Activate API Keys**: Once BLOSM is downloaded, activate the API keys by clicking on 'Get it!' next to each space.

## Creating Our First World

![Step 1](https://github.com/jebaeros/Worlds_documentation/blob/main/gis%20method/25.png)

### Getting the Terrain

### Obtaining the Topological Mesh

To obtain the topological mesh of our study section, follow these steps:

1. **Open BLOSM**: Use the shortcut `N` to open the BLOSM addon.
   
   ![Step 1](https://github.com/jebaeros/Worlds_documentation/blob/main/gis%20method/11.png)

2. **Set Import Section to Terrain**: Change the import section to "terrain" in the BLOSM interface.
   
   ![Step 2](https://github.com/jebaeros/Worlds_documentation/blob/main/gis%20method/12.png)

3. **Update Coordinates**: Click 'select' to update the coordinates of the study section.
   
   ![Step 3](https://github.com/jebaeros/Worlds_documentation/blob/main/gis%20method/13.png)

4. **Select Study Area**: Choose the area of interest using the magnifying glass or 'show selection rectangle' option.
   
   ![Step 4](https://github.com/jebaeros/Worlds_documentation/blob/main/gis%20method/14.png)

   Import the selected study area to obtain the terrain mesh.

### Obtaining the Overlay

To obtain the overlay, follow these steps:

1. **Open the Window**: Usethe shortcut `N` to open the window again.
   
   ![Step 1](https://github.com/jebaeros/Worlds_documentation/blob/main/gis%20method/11.png)

2. **Navigate to Import Section**: Look for 'image overlay' in the import section.
   
   ![Step 2](https://github.com/jebaeros/Worlds_documentation/blob/main/gis%20method/18.png)

3. **Adjust Parameters**: Set the overlay source, default material, save overlay to file, and max number of tiles as per your requirements.
   
   ![Step 3](https://github.com/jebaeros/Worlds_documentation/blob/main/gis%20method/19.png)

4. **Confirmation**: Confirm the settings and you should see the overlay added to your project.
   
   ![Step 4](https://github.com/jebaeros/Worlds_documentation/blob/main/gis%20method/21.png)

## Obtaining OSM and Structures

The final step is to obtain the OSM (OpenStreetMap) data and structures. We have two options for this:

1. **OpenStreetMap Functionality**:
   - OpenStreetMap provides versatile and user-friendly functions for selecting the type of mapping required.
   - For more information, you can visit [OpenStreetMap](https://github.com/openstreetmap/).
   
2. **Google 3D Tiles API**:
   - Google 3D Tiles is a powerful paid tool that allows you to obtain high-quality 3D models with textures of structures and buildings.
   - It utilizes photogrammetry present in Google's database to provide detailed 3D models.
   - However, it comes with high requirements for downloading, processing, and modifying these meshes.

### OpenStreetMap Option

#### Steps:
1. After obtaining the mesh and its respective overlay, reopen the toolbar.
3. Select 'OpenStreetMap' in the Edit menu.
   ![Step 4](https://github.com/jebaeros/Worlds_documentation/blob/main/gis%20method/24.png)
5. Explore the different parameters and options available in the toolbar.
6. Specify the types of objects you want to import, such as rails, bodies of water, vegetation, buildings, etc.
7. Adjust the height levels to determine the size and variation in heights of the buildings.
8. **IMPORTANT**: Enable options like 'import as single object' and 'relative to initial import'. Also, define a local storage folder. Failure to do so may result in incorrect saving and future export issues in formats such as OBJ, DAE, etc.
9. you will get something like this!
![Step 4](https://github.com/jebaeros/Worlds_documentation/blob/main/gis%20method/26.png)

AHORA EL SIGUIENTE METODO ES El google 3d tiles, para ello repetiremos los pasos hechos de la siguiente forma:
1. procura tener tu escena limpia, o limpiala con a y luego suprimir
2. posterior a ello abre el menu con el atajo control n y busca blosm
3. luego de ello ve a la seccion de import y selecciona google 3d tiles, deberias ver esta interfaz
4. donde para hacer uso de este metodo debe haber ingresado la clave api que se solicito en pasos anteriores en la seccion de preferencias, ahora IMPORTANTE: debemos indicar la calidad del tipo mapeado 



