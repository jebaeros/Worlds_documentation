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

## Mesh Construction

With the developed point cloud, we must now generate the mesh that will serve for the subsequent export of our file in the required format, as a point cloud alone cannot provide the visual or collision aspects necessary for our model. Let's return to *Workflow* -> *Build Mesh*.

The main parameters are:

- **Quality**: This parameter determines the level of detail and density of the polygonal mesh. Higher quality results in greater definition and density of the mesh.

- **Deep Filtering**: Helps refine the mesh by reducing noise and outliers, resulting in a cleaner and more accurate representation of the environment.

- **Calculate Point Colors**: Enabling this option allows the software to calculate and apply color information to the mesh, enhancing visual realism.

- **Calculate Point Confidence**: This parameter determines the confidence level associated with each point in the mesh, indicating the reliability of its geometry and attributes.

![Mesh Parameters](https://github.com/jebaeros/Worlds_documentation/blob/main/Screenshots/18.png)

After completing this step, we will obtain a result like this:

![Mesh Visualization](https://github.com/jebaeros/Worlds_documentation/blob/main/Screenshots/19.png)

It's important to note that higher quality settings will result in a mesh with greater definition and polygonal density. Remember to visualize the mesh by following the same steps used to view the point cloud: select "Model View" in the upper panel and choose "Mesh" from the available options.
## Texture Construction

Finally, it is indispensable to construct the texture, as this will add more life and definition to our model. Meshes often distort texture images and may obscure colors, hence the importance of this step.

The parameters for texture construction are as follows:

1. **Texture Type**: Specify the type of texture to be applied to the mesh, such as diffuse, specular, or normal maps.

2. **Source Data**: Choose the source data from which the texture will be generated, such as color images or grayscale maps.

3. **Mapping Mode**: Determine how the texture will be mapped onto the mesh, whether using UV mapping, spherical mapping, or other techniques.

4. **Blending Mode**: Define the blending mode for combining multiple textures or layers, such as additive blending, alpha blending, or overlay blending.

5. **Texture Size/Count**: Set the resolution and number of textures to be applied to the mesh, considering factors like memory usage and rendering performance.

6. **Advanced Settings**: Explore additional options for texture generation and manipulation, such as filtering, compression, or seam removal.

After configuring these parameters, return to the upper panel and select the visualization of the mesh with texture applied.

![Mesh with Texture](https://github.com/jebaeros/Worlds_documentation/blob/main/Screenshots/16.png).

ya con esto en mente contamos con nuestro modelo 3d de nuestro entorno, ahora vienen las operaciones de refinado donde se sugiere que se evalue el caso particular y las necesidades de cada modelo para aplicar cambios ya que cualquier modificacion es irreversible, por lo cual se sugiere guardar en este punto.
si retornamos al apartado de tools, veremos una ventana de la siguiente forma:
## Texture Construction

Finally, it is indispensable to construct the texture, as this will add more life and definition to our model. Meshes often distort texture images and may obscure colors, hence the importance of this step.

The parameters for texture construction are as follows:

1. **Texture Type**: Specify the type of texture to be applied to the mesh, such as diffuse, specular, or normal maps.

2. **Source Data**: Choose the source data from which the texture will be generated, such as color images or grayscale maps.

3. **Mapping Mode**: Determine how the texture will be mapped onto the mesh, whether using UV mapping, spherical mapping, or other techniques.

4. **Blending Mode**: Define the blending mode for combining multiple textures or layers, such as additive blending, alpha blending, or overlay blending.

5. **Texture Size/Count**: Set the resolution and number of textures to be applied to the mesh, considering factors like memory usage and rendering performance.

6. **Advanced Settings**: Explore additional options for texture generation and manipulation, such as filtering, compression, or seam removal.

After configuring these parameters, return to the upper panel and select the visualization of the mesh with texture applied.

![Mesh with Texture](https://github.com/jebaeros/Worlds_documentation/blob/main/Screenshots/19.png)
Where modifications can be made to the elements we have generated, such as point clouds, meshes, or textures. In this case, it is advisable to refine the meshes because there is often a lot of noise or unwanted elements in our mesh that can hinder further processing.

Additionally, we have operations not only for meshes but also for other generated elements. However, it is worth noting that modifying any element implies replicating all the processes that follow the modified element, as it changes its composition and shape.

![Mesh with Texture](https://github.com/jebaeros/Worlds_documentation/blob/main/Screenshots/20.png)

The panel will show us options like this for meshes, where I suggest exploring the Agisoft manual for the various refining and editing options.

### Parameters:

1. **Refine Mesh**: Refines the mesh by optimizing its topology and reducing noise.
2. **Decimate Mesh**: Reduces the polygon count of the mesh while preserving its overall shape.
3. **Smooth Mesh**: Applies smoothing algorithms to the mesh surface, reducing roughness.
4. **Close Holes**: Automatically fills holes in the mesh geometry.
5. **Colorize Vertices**: Assigns colors to vertices based on texture or other attributes.
6. **Resize Texture**: Adjusts the resolution or dimensions of the texture applied to the mesh.
7. **Remove Lighting**: Removes lighting effects from the mesh, allowing for better visualization.
8. **Generate Mask**: Creates a mask for specific areas of the mesh.
9. **View Mesh Statistics**: Displays statistical information about the mesh, such as vertex count and surface area.
10. **View Mesh UV**: Visualizes the UV mapping of the mesh.
11. **Measure Area and Volume**: Calculates the surface area and volume of the mesh.

Once this is completed, we will export our model in formats such as .obj, .ae, and .stl for simulation:

1. Go to **File** -> **Export**.

![Exporting Model](https://github.com/jebaeros/Worlds_documentation/blob/main/Screenshots/22.png)

This will generate a folder containing metadata, .mtl, and mesh files along with the texture.
## Postprocessing with MeshLab

So far, we have covered three fundamental steps in environment construction: obtaining information, processing information, and converting the file to the desired format. Now, we will perform the postprocessing of our model using MeshLab. You can find more information about this tool [here](https://www.meshlab.net).

### Requirements:

- **Operating System**: MeshLab is compatible with Windows, macOS, and Linux.
- **Hardware**: Ensure your system meets the minimum requirements for running MeshLab effectively. Complete the hardware requirements.

### Functionality of MeshLab:

MeshLab is a powerful open-source tool for processing and editing 3D triangular meshes. Its capabilities include mesh cleaning, repairing, smoothing, simplification, and more.

### Getting Started:

Let's begin the postprocessing process:

1. **Open MeshLab**: Upon opening MeshLab, you should see the main interface. Navigate to the main panel and go to `File` -> `Import Mesh`. Locate the folder where you downloaded your mesh and select the mesh file.

   ![meshlab](https://github.com/jebaeros/Worlds_documentation/blob/main/meshlab/1.png)

2. **Model Navigation**: After importing the model, you should see something similar to this – your 3D model with a sphere or wheel axis that allows you to navigate and visualize your model.

   ![meshlab](https://github.com/jebaeros/Worlds_documentation/blob/main/meshlab/2.png)

3. **Lighting and Shading Options**: In the lower right panel, you should be able to see the lighting and shading options. These options modify the textures and how you view the mesh. 

   - **Light Vertices**: Illuminates vertices of the mesh.
   - **Light Faces**: Illuminates faces of the mesh.
   - **Light Both**: Illuminates both vertices and faces of the mesh.
   - **Flat Shading**: Applies flat shading to the mesh.
   - **Smooth Shading**: Applies smooth shading to the mesh.

   ![meshlab](https://github.com/jebaeros/Worlds_documentation/blob/main/meshlab/3.png)

4. **Toolbar Exploration**: Explore the toolbar located at the top, which contains various options for mesh processing and editing. Each function has its purpose. 

   ![meshlab](https://github.com/jebaeros/Worlds_documentation/blob/main/meshlab/4.png)

5. **Render Options**: In the toolbar, you will find the "Render" option, which includes various rendering options. Enumerate and describe each one.

   - **Shaders**: Selects different shading modes for the mesh.
   - **Background Grid**: Toggles the visibility of the background grid.
   - **Show Axis**: Displays the reference axis in the scene.
   - **Show Box Corners**: Displays the bounding box corners.
   - **Show Current Mesh**: Highlights the current mesh.
   - **Show Camera**: Displays the camera in the scene.
   - **Show Normal**: Visualizes the normals of the mesh.
   - **Show UV Tex Param**: Displays UV texture parameterization.
   - **Show Vertex Quality Histogram**: Shows a histogram of vertex quality.
   - **Show Face Quality Histogram**: Shows a histogram of face quality.
   - **Show Quality Contour**: Displays quality contours on the mesh.
   - **Show Curvature**: Visualizes curvature information.
   - **Show Labels**: Displays labels on mesh elements.
   - **Rasters-to-geometry reprojection**: Converts rasters to geometry.
   - **Enable shadow mapping**: Enables shadow mapping for the scene.
   - **Enable Screen Space Ambient Occlusion**: Applies ambient occlusion to the scene.

   ![meshlab](https://github.com/jebaeros/Worlds_documentation/blob/main/meshlab/5.png)

6. **View Options**: Similarly, the "View" option in the toolbar contains various viewing options. Enumerate and describe each one.

   - **FullScreen**: Switches to full-screen mode.
   - **Show Layer Dialog**: Displays the layer dialog for managing layers.
   - **Show Current Raster Mode**: Shows the current raster mode.
   - **Show Trackball**: Displays the trackball for navigation.
   - **Reset Trackball**: Resets the trackball orientation.
   - **Toggle Orthographic Camera**: Switches between orthographic and perspective cameras.
   - **Show Info Panel**: Displays the information panel.
   - **ToolBars**: Toggles the visibility of toolbars.
   - **Alt+Return**: Toggles full-screen mode.
   - **Ctrl+L**: Locks the current view.
   - **Shift+R**: Resets the camera view.
   - **Shift+H**: Hides the selected elements.
   - **Ctrl+H**: Hides unselected elements.

   ![meshlab](https://github.com/jebaeros/Worlds_documentation/blob/main/meshlab/6.png)

7. **Window Options**: The "Window" option in the toolbar contains various window management options. Enumerate and describe each one.

   - **Close All Windows**: Closes all open windows.
   - **Tile**: Arranges windows in a tiled layout.
   - **Cascade**: Cascades windows.
   - **Next**: Switches to the next window.
   - **Split current view**: Splits the current view.
   - **Close current view**: Closes the current view.
   - **Link Viewers**: Links multiple viewers together.
   - **View from**: Sets the view from a specific perspective.
   - **Trackball step**: Specifies the trackball step.
   - **Read camera settings from file**: Reads camera settings from a file.
   - **Save camera settings to file**: Saves camera settings to a file.
   - **View from Mesh Camera**: Sets the view from the mesh camera.
   - **View from Raster Camera**: Sets the view from the raster camera.
   - **Ctrl+)**: Sets the view from the raster camera.
   - **Copy camera settings to clipboard**: Copies camera settings to the clipboard.
   - **Paste clipboard to camera settings**: Pastes clipboard to camera settings.
   - **1.Project**: Specifies project settings.

   ![meshlab](https://github.com/jebaeros/Worlds_documentation/blob/main/meshlab/7.png)

8. **Tools Options**: Lastly, the "Tools" option in the toolbar contains various mesh processing tools. Enumerate and describe each one.

   - **Apply filter**: Applies a filter to the mesh.
   - **Show current filter script**: Displays the current filter script.
   - **Selection**: Allows selection of mesh elements.
   - **Cleaning and Repairing**: Tools for cleaning and repairing mesh errors.
   - **Create New Mesh Layer**: Creates a new mesh layer.
   - **Remeshing, Simplification and Reconstruction**: Tools for remeshing, simplification, and reconstruction.
   - **Polygonal and Quad Mesh**: Tools for generating polygonal and quad meshes.
   - **Color Creation and Processing**: Tools for creating and processing colors on the mesh.
   - **Smoothing, Fairing and Deformation**: Tools for smoothing, fairing, and deforming the mesh.
   - **Quality Measure and Computations**: Tools for measuring quality and computing mesh properties.
   - **Normals, Curvatures and Orientation**: Tools for calculating normals, curvatures, and orientation of the mesh.
   - **Mesh Layer**: Options for managing mesh layers.
   - **Raster Layer**: Options for managing raster layers.
   - **Range Map**: Tools for handling range maps.
   - **Point Set**: Options for managing point sets.
   - **Sampling**: Tools for sampling mesh data.
   - **Texture**: Tools for texture mapping.
   - **Camera**: Tools for managing camera settings.
   - **Other**: Miscellaneous tools.

   ![meshlab](https://github.com/jebaeros/Worlds_documentation/blob/main/meshlab/8.png)
9. **Main Options**:
   - **Merge Close Vertices**: Merges vertices that are close to each other.
   - **Merge Wedge Texture Coord**: Merges texture coordinates for wedged faces.
   - **Remove Duplicate Faces**: Deletes duplicate faces from the mesh.
   - **Remove Duplicate Vertices**: Removes duplicate vertices from the mesh.
   - **Remove Isolated Folded Faces by Edge Flip**: Removes isolated folded faces by flipping edges.
   - **Remove Isolated Pieces (wrt Diameter)**: Deletes isolated mesh pieces based on diameter.
   - **Remove Isolated Pieces (wrt Face Num.)**: Deletes isolated mesh pieces based on face count.
   - **Remove T-Vertices**: Eliminates T-vertices from the mesh.
   - **Remove Unreferenced Vertices**: Deletes vertices that are not referenced by any faces.
   - **Remove Vertices wrt Quality**: Removes vertices based on quality criteria.
   - **Remove Zero Area Faces**: Deletes faces with zero area.
   - **Repair Non-Manifold Edges**: Fixes non-manifold edges in the mesh.
   - **Repair Non-Manifold Vertices by Splitting**: Repairs non-manifold vertices by splitting.
   - **Select Self-Intersecting Faces**: Highlights self-intersecting faces in the mesh.
   - **Snap Mismatched Borders**: Aligns mismatched borders by snapping.

   ![clean and repairing](https://github.com/jebaeros/Worlds_documentation/blob/main/meshlab/9.png)

10. **Remeshing, Simplification, and Reconstruction**:
    - **Alpha Complex/Shape**: 
        - Enumerate and describe the function.
    - **Alpha Wrap**: 
        - Enumerate and describe the function.
    - **Build a Polyline from Selected Edges**: 
        - Enumerate and describe the function.
    - **Close Holes**: 
        - Enumerate and describe the function.
    - **Convex Hull**: 
        - Enumerate and describe the function.
    - **Create Solid Wireframe**: 
        - Enumerate and describe the function.
    - **Cubic Stylization**: 
        - Enumerate and describe the function.
    - **Curvature Flipping Optimization**: 
        - Enumerate and describe the function.
    - **Cut Mesh along Crease Edges**: 
        - Enumerate and describe the function.
    - **Generate Scalar Harmonic Field**: 
        - Enumerate and describe the function.
    - **Global Align Meshes**: 
        - Enumerate and describe the function.
    - **ICP Between Meshes**: 
        - Enumerate and describe the function.
    - **Iso Parametrization Build Atlased Mesh**: 
        - Enumerate and describe the function.
    - **Iso Parametrization Remeshing**: 
        - Enumerate and describe the function.
    - **Iso Parametrization Transfer between Meshes**: 
        - Enumerate and describe the function.
    - **Iso Parametrization: Main**: 
        - Enumerate and describe the function.
    - **Make Mesh Developable**: 
        - Enumerate and describe the function.
    - **Marching Cubes (APSS)**: 
        - Enumerate and describe the function.
    - **Marching Cubes (RIMLS)**: 
        - Enumerate and describe the function.
    - **Mesh Boolean: Difference**: 
        - Enumerate and describe the function.
    - **Mesh Boolean: Intersection**: 
        - Enumerate and describe the function.
    - **Mesh Boolean: Symmetric Difference (XOR)**: 
        - Enumerate and describe the function.
    - **Mesh Boolean: Union**: 
        - Enumerate and describe the function.
    - **Planar Flipping Optimization**: 
        - Enumerate and describe the function.
    - **Points Cloud Movement**: 
        - Enumerate and describe the function.
    - **Refine User-Defined**: 
        - Enumerate and describe the function.
    - **Remeshing: Isotropic Explicit Remeshing**: 
        - Enumerate and describe the function.
    - **Select Crease Edges**: 
        - Enumerate and describe the function.
    - **Simplification: Clustering Decimation**: 
        - Enumerate and describe the function.
    - **Simplification: Edge Collapse for Marching Cube meshes**: 
        - Enumerate and describe the function.
    - **Simplification: Quadric Edge Collapse Decimation**: 
        - Enumerate and describe the function.
    - **Simplification: Quadric Edge Collapse Decimation (with texture)**: 
        - Enumerate and describe the function.
    - **Subdivision Surfaces: Butterfly Subdivision**: 
        - Enumerate and describe the function.
    - **Subdivision Surfaces: Catmull-Clark**: 
        - Enumerate and describe the function.
    - **Subdivision Surfaces: Doo Sabin**: 
        - Enumerate and describe the function.
    - **Subdivision Surfaces: LS3 Loop**: 
        - Enumerate and describe the function.
    - **Subdivision Surfaces: Loop**: 
        - Enumerate and describe the function.
    - **Subdivision Surfaces: Midpoint**: 
        - Enumerate and describe the function.
    - **Surface Reconstruction: Ball Pivoting**: 
        - Enumerate and describe the function.
    - **Surface Reconstruction: Screened Poisson**: 
        - Enumerate and describe the function.
    - **Surface Reconstruction: VCG**: 
        - Enumerate and describe the function.
    - **Tri to Quad by 4-8 Subdivision**: 
        - Enumerate and describe the function.
    - **Tri to Quad by Smart Triangle Pairing**: 
        - Enumerate and describe the function.
    - **Turn into Quad-Dominant mesh**: 
        - Enumerate and describe the function.
    - **Turn into a Pure-Triangular mesh**: 
        - Enumerate and describe the function.
    - **Uniform Mesh Resampling**: 
        - Enumerate and describe the function.
    - **Vertex Attribute Seam Voronoi Filtering**: 
        - Enumerate and describe the function.

   ![remeshing, simplification, and reconstruction](https://github.com/jebaeros/Worlds_documentation/blob/main/meshlab/10.png)

When you finish editing your model, remember to export the file to a different folder or subfolder within your working directory to avoid conflicts with previous files.

## Collision Model Definition Using Instant Meshes

In this phase, we will define collisions for our model or environment. For this purpose, we'll utilize Instant Meshes, a powerful tool known for its capability to edit heavy models and simplify meshes without compromising their main characteristics and shapes.

### What is Instant Meshes?

Instant Meshes is a software tool designed for mesh processing and editing. It allows users to manipulate 3D models efficiently, particularly focusing on mesh simplification and remeshing tasks. Instant Meshes is widely used in various industries such as game development, 3D animation, and architectural visualization.

### Requirements for Instant Meshes:
- Operating System: Windows, macOS, Linux
- Processor: Intel Core i5 or equivalent
- RAM: 8 GB minimum
- Graphics Card: OpenGL 3.3 compatible
- Disk Space: 500 MB for installation

### Getting Started with Instant Meshes:

1. Open Instant Meshes and you'll be greeted with the following interface:
   ![instantmesh](https://github.com/jebaeros/Worlds_documentation/blob/main/instantmeshes/1.png)

2. Explore the menu options which include:
   - **Open mesh:** Allows you to import a mesh file.
   - **Advanced settings:** Provides additional configuration options for remeshing.
   - **Remesh as Quads:** Specifies the remeshing mode.
   - **Configuration details:** Displays detailed settings for the remeshing process.
   - **Extrinsic:** Adjusts mesh alignment.
   - **Align to boundaries:** Aligns mesh to boundaries.
   - **Sharp creases:** Preserves sharp creases in the mesh.
   - **Target vertex count:** Sets the desired number of vertices.
   - **Orientation field/Position field:** Tools for modifying mesh orientation and position.
   - **Solve:** Initiates the remeshing process.
   - **Export mesh:** Allows you to save the edited mesh.

   ![instantmesh](https://github.com/jebaeros/Worlds_documentation/blob/main/instantmeshes/2.png)

3. The advanced options panel includes the following functions:
   - **Current state:** Indicates the current status of the mesh.
   - **Reset/Load/Save:** Operations for resetting, loading, and saving mesh configurations.
   - **Visualize:** Visualization options for the mesh.
   - **Hierarchy level:** Adjusts the mesh hierarchy.
   - **Automatic:** Enables automatic settings.
   - **Crease angle:** Defines the angle for preserving sharp edges.
   - **Render layers:** Options for rendering mesh layers.
   - **Input mesh:** Specifies the input mesh file.
   - **Face IDs/Vertex IDs:** Displays identification information for mesh elements.
   - **Orientation field/Position field:** Tools for manipulating mesh orientation and position.
   - **Output mesh:** Indicates the output mesh file.

   ![instantmesh](https://github.com/jebaeros/Worlds_documentation/blob/main/instantmeshes/4.png)

4. After importing the model, ensure to view it from the top without textures:
   ![instantmesh](https://github.com/jebaeros/Worlds_documentation/blob/main/instantmeshes/3.png)

5. Finally, after editing the mesh using the above options, navigate to the ### Export Options:

- **Mesh settings:** This section allows you to configure various mesh properties before exporting. You can adjust parameters such as mesh density, smoothing iterations, and other mesh-related settings.

- **Pure quad mesh:** Specifies whether the exported mesh should consist of pure quadrilateral elements.

- **Smoothing iterations:** Determines the number of iterations applied to smooth the mesh surface during export.

- **Actions:** Provides additional actions you can perform before exporting the mesh. This may include extracting a specific part of the mesh or showing the output mesh.

- **Extract mesh:** This action allows you to extract a specific portion of the mesh before exporting it. It's useful for isolating certain parts of the model for export.

- **Show output:** Displays the output mesh in the preview window to ensure that the exported mesh appears as expected.

- **Save:** Initiates the export process and saves the edited mesh to the specified file location. You can choose the file format and adjust export settings as needed before saving.
   ![instantmesh](https://github.com/jebaeros/Worlds_documentation/blob/main/instantmeshes/5.png)





