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

## Step 1: Obtain Information

The information required for constructing the models includes photogrammetry, models from other creators, satellite images, etc. It's crucial to ensure this data is comprehensive and of the highest quality to avoid errors or degraded experiences. We'll utilize two methods: obtaining images through photogrammetry and obtaining images through GIS tools.

## GIS Method

To perform this method, you'll need the following tools:

- Install [Blender](https://blender.org/) (preferably version 3.6.5).
- Install the Blender addon from the repository [BLOSM](https://github.com/vvoovv/blosm).

### About BLOSM:

BLOSM is a Blender addon that enables us to utilize APIs for creating 3D geographic or topological models. It offers advanced features such as detailed reliefs, extrusions of structures, and more. Visit the developer's page for further information.

### About Blender:

Blender is a powerful tool for editing and producing 3D models, multimedia, etc. Its versatility and practicality in editing make it ideal for processing heavy meshes. 

### Let's Get Started:

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

### Creating Our First World

![Step 1](https://github.com/jebaeros/Worlds_documentation/blob/main/gis%20method/25.png)

#### Getting the Terrain

#### Obtaining the Topological Mesh

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

#### Obtaining the Overlay

To obtain the overlay, follow these steps:

1. **Open the Window**: Usethe shortcut `N` to open the window again.
   
   ![Step 1](https://github.com/jebaeros/Worlds_documentation/blob/main/gis%20method/11.png)

2. **Navigate to Import Section**: Look for 'image overlay' in the import section.
   
   ![Step 2](https://github.com/jebaeros/Worlds_documentation/blob/main/gis%20method/18.png)

3. **Adjust Parameters**: Set the overlay source, default material, save overlay to file, and max number of tiles as per your requirements.
   
   ![Step 3](https://github.com/jebaeros/Worlds_documentation/blob/main/gis%20method/19.png)

4. **Confirmation**: Confirm the settings and you should see the overlay added to your project.
   
   ![Step 4](https://github.com/jebaeros/Worlds_documentation/blob/main/gis%20method/21.png)

### Obtaining OSM and Structures

The final step is to obtain the OSM (OpenStreetMap) data and structures. We have two options for this:

### OpenStreetMap Option

#### Steps:
1. After obtaining the mesh and its respective overlay, reopen the toolbar.
3. Select 'OpenStreetMap' in the Edit menu.
   ![Step 4](https://github.com/jebaeros/Worlds_documentation/blob/main/gis%20method/24.png)
5. Explore the different parameters and options available in the toolbar.
6. Specify the types of objects you want to import, such as rails, bodies of water, vegetation, buildings, etc.
7. Adjust the height levels to determine the size and variation in heights of the buildings.
8. **IMPORTANT**: Enable options like 'import as single object' and 'relative to initial import'. Also, define a local storage folder. Failure to do so may result in incorrect saving and future export issues in formats such as OBJ, DAE, etc.
9. You will get something like this!
![Step 4](https://github.com/jebaeros/Worlds_documentation/blob/main/gis%20method/26.png)

### Google 3D Tiles Method

To utilize the Google 3D Tiles method, follow these steps:

1. Ensure your scene is clean or clean it by selecting all elements with 'A' and then deleting them with the 'Delete' key.

2. Open the menu using the shortcut 'Ctrl + N' and search for BLOSM.

3. In the BLOSM interface, navigate to the import section and select 'Google 3D Tiles'. You should see the following interface:

   ![Step 3](https://github.com/jebaeros/Worlds_documentation/blob/main/gis%20method/27.png)

4. Before using this method, ensure you have entered the API key requested in previous steps in the preferences section. Now, **IMPORTANT**: Specify the quality of the mapping type.
Follow these steps to utilize the Google 3D Tiles method effectively and get results like this one.
 ![Step 4](https://github.com/jebaeros/Worlds_documentation/blob/main/gis%20method/28.png) 
## Agisoft Method: Creating 3D Models with Photogrammetry

### Introduction

In this section, we'll delve into the Agisoft method, a robust tool for generating 3D models through photogrammetry. Before we begin, let's ensure we meet the following minimum requirements:

- **Hardware Requirements**:
  - Processor: Quad-core or higher
  - Memory (RAM): 8 GB or more
  - Graphics Card: Dedicated GPU with at least 2 GB VRAM
  - Storage: SSD with 128 GB of free space
- **Software Requirements**:
  - Operating System: Ubuntu 18.04 LTS or higher, or Windows 10
  - Blender: Latest stable version
  - Gazebo: xxx
  - ROS: xxx
  - Agisoft: 1.17
- **Other Requirements**:
  - Internet connection for software installation
  - Up-to-date device drivers
  - Additional storage space for projects and data

### Understanding Agisoft's Functionality

Agisoft serves as a powerful ally in the realm of photogrammetry, enabling the creation of intricate 3D models from a collection of photographs. Its algorithm meticulously analyzes the spatial relationships between images, reconstructing surfaces and structures with remarkable accuracy. This functionality empowers users to capture the essence of real-world objects and environments, opening avenues for diverse applications in fields ranging from architecture to archaeology.

#### Leveraging Agisoft's Features

Upon acquiring the tool from the [Agisoft website](link), users are tasked with assembling a repository of photographs capturing the desired subject from various angles. For optimal results, these images should meet the following criteria:

1. **Quality Assurance**: Ensure the images are of high quality, free from blurriness or distortion.
2. **Metadata Enrichment**: Whenever feasible, include metadata to enhance the accuracy of spatial reconstruction.
3. **Sequential Alignment**: Capture photos in a sequential manner to facilitate the alignment process within Agisoft.
4. **Consistency in Lighting**: Maintain consistency in lighting conditions to minimize discrepancies in texture and color reproduction.

### Navigating Agisoft: Interface and Preferences

Upon launching Agisoft, users are greeted with an intuitive interface, offering a plethora of tools and options for model construction. The primary screen provides a comprehensive view of the project workspace, showcasing the imported images and the evolving 3D model.
![Agisoft Screen](https://github.com/jebaeros/Worlds_documentation/blob/main/Screenshots/1.png)
#### Exploring the Tools Section

Navigate to the "Tools" section to access a diverse array of functionalities tailored to streamline the photogrammetry workflow. Here, users can initiate critical processes such as image alignment, point cloud generation, and mesh reconstruction, each contributing to the gradual refinement of the final 3D model.
![Agisoft Screen](https://github.com/jebaeros/Worlds_documentation/blob/main/Screenshots/3.png)
### Configuring Preferences for Optimal Performance

Before embarking on the photogrammetric journey, it's prudent to configure Agisoft's preferences to align with individual workflow requirements. While these preferences may vary based on personal preference and project specifications, the following recommendations offer a solid foundation for efficient operation:
![Agisoft Screen](https://github.com/jebaeros/Worlds_documentation/blob/main/Screenshots/4.png)
1. **Language Selection**: Choose your preferred language to ensure seamless interaction with Agisoft's interface.
2. **Resource Allocation**: Allocate computational resources judiciously, striking a balance between processing power and memory utilization.
3. **Hardware Specification**: Specify the GPU and CPU dedicated to handling the intricate computations inherent in photogrammetric processing.
4. **Additional Preferences**: Customize Agisoft's settings to suit your specific workflow, accounting for factors such as file storage location and processing algorithms.

### Loading Image Folder and Initial Setup

To begin, we'll load our image folder into Agisoft by following these steps:

1. **Access the Workflow**: Navigate to the "Workflow" menu and select "Add Folder".
   
   ![Add Folder](https://github.com/jebaeros/Worlds_documentation/blob/main/Screenshots/6.png)

2. **Select Image Folder**: Choose the folder containing your images. It's essential to note that our entire workflow revolves around the "Workflow" option, as it provides a sequential guide for constructing our model.

### Understanding Single Camera vs. Dynamic Scene

Upon loading the folder, Agisoft will prompt you to choose between "Single Camera" or "Dynamic Scene". In our case, "Single Camera" is the preferred option since we're working with simplified images without dynamic effects.

After loading the images, you'll notice them displayed in the lower panel, with a preview available in the upper-left panel. This setup enables quick access to individual images and allows for easy navigation during the modeling process.

### Utilizing Markers for Improved Mapping

Markers play a crucial role in enhancing the accuracy of our photogrammetric mapping. To add a marker, follow these steps:

1. **Activate Markers**: Click on the blue flag or the penultimate option in the top toolbar to enable markers.
   
   ![Activate Markers](https://github.com/jebaeros/Worlds_documentation/blob/main/Screenshots/16.png)

2. **Add Marker**: Right-click on any image in your image bank and select "Add Marker". Ensure you input the marker's spherical, Cartesian, or other relevant coordinates for precise mapping. Note that this step may be skipped if the images contain metadata.

### Image Processing: Aligning Photos

Once markers are defined, we proceed with image processing by aligning photos. Navigate to the "Workflow" menu and select "Align Photos". You should encounter an interface similar to the following:

![Align Photos](https://github.com/jebaeros/Worlds_documentation/blob/main/Screenshots/10.png)

#### Parameter Definition:

1. **Accuracy**: Determines the precision of reference construction. Higher accuracy implies a longer processing time.
2. **Generic Preselection**: Utilizes complete AI for point selection.
3. **Reference Preselection**: Beneficial for sequentially captured images, aiding in smoother processing.
4. **Advanced Options**: Explore various advanced options such as key points, tie point limit, mask application, exclusion of stationary elements, guided image matching, and adaptive model fitting. Complete AI options are available for enhanced performance.

By carefully defining these parameters, we optimize the alignment process, paving the way for accurate and detailed 3D model reconstruction.
deberiamos obtener algo asi, donde el align destaca los principales puntos referencia:
![Align Photos](https://github.com/jebaeros/Worlds_documentation/blob/main/Screenshots/12.png)
## Building Dense Cloud

In this step, we'll construct our point cloud based on the photo alignment performed earlier. This three-dimensional point cloud provides a detailed representation of the environment, including key vertices and vectors.

### Parameters:

1. **Quality**: This parameter determines the level of detail and accuracy of the point cloud. Higher quality settings result in denser and more precise point clouds, but may also increase processing time. Provide more details.

2. **Deep Filtering**: Deep filtering helps to reduce noise and outliers in the point cloud, resulting in a cleaner and more accurate representation of the scene. Explain further.

3. **Calculate Point Colors**: Enabling this option allows Agisoft to calculate and include color information for each point in the cloud, enhancing visual realism and facilitating subsequent analysis.

4. **Calculate Point Confidence**: This parameter determines the confidence level associated with each point in the cloud, indicating the reliability of its position and attributes. More information.

![Dense Cloud Parameters](https://github.com/jebaeros/Worlds_documentation/blob/main/Screenshots/13.png)

To visualize the point cloud, follow these steps:

1. Select "Model View" in the upper panel to access the model viewing options.
   
   ![Model View](https://github.com/jebaeros/Worlds_documentation/blob/main/Screenshots/15.png)

2. Choose "Point Cloud" from the options available in the upper panel.
   
   ![Point Cloud View](https://github.com/jebaeros/Worlds_documentation/blob/main/Screenshots/16.png)

You should now be able to visualize the point cloud, which will exhibit various characteristics based on the defined parameters.

![Point Cloud Visualization](https://github.com/jebaeros/Worlds_documentation/blob/main/Screenshots/17.png)

This point cloud serves as a foundational element for further analysis, modeling, and simulation within Agisoft.







