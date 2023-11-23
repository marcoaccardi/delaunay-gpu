# Delaunay triangulation on GPU
a shader implementation of delaunay triangulation

## Graphics Algorithms Collection

This repository contains a set of tools for graphical computations and visualizations, specifically focusing on triangulation and Voronoi diagrams. These tools are designed for use with Max/MSP Jitter, a visual programming language for music and multimedia.

## Files Description

1. **delaunay.jxs**
   - **Type**: Jitter Shader
   - **Description**: This shader is intended for Delaunay triangulation, a method for creating a mesh of triangles from a given set of points. It's useful in various computer graphics applications.

**Vertex Program**:
Input: Takes in vertex positions (vec3) and color (vec4).

Processing: It appears to transform the vertex positions and pass them along with color information to the next stage in the pipeline.

Purpose: Typically, vertex shaders process each vertex's position and other attributes before passing them to the geometry shader.

**Geometry Program**:
Input and Output Types: It's configured to take 'lines_adjacency' as input and output 'triangle_strip'. This suggests complex operations on the vertex data, suitable for generating a mesh of triangles.

Texture and Buffer: Uses a 2D texture (middleTex0) and a buffer (posBuff), possibly to store and retrieve intermediate data needed for triangulation.

Main Function: It seems to be responsible for the actual computation of Delaunay triangulation, calculating positions based on texture lookups and buffer data.

**Fragment Program**:
Color Processing: Processes color data, likely determining the final color of each pixel in the rendered triangles.
Final Output: Outputs color data, which is a standard operation in fragment shaders to determine the color of individual pixels on the screen.

2. **fastVoronoi.jxs**
   - **Type**: Jitter Shader
   - **Description**: This shader implements a fast Voronoi diagram algorithm. Voronoi diagrams are used for partitioning a plane based on distances to a set of points, finding applications in graphics, geospatial mapping, and more.

Shader Structure: Similar to the Delaunay shader, it has Vertex, Geometry, and Fragment programs, indicating a standard rendering pipeline.

**Vertex Program**:
Input: Takes vertex positions, instance positions, and color.
Operations: Transforms vertex positions, possibly for instanced rendering, and passes additional data (like instance ID) to the next stage.

**Geometry Program**:
Input and Output Types: Configured differently from the Delaunay shader, suggesting a different approach to processing the vertex data.
Unique Operations: Appears to handle the generation of Voronoi cells, calculating distances and directions based on vertex positions.

**Fragment Program**:
Data Processing: Takes in the processed data (like distances and directions) and determines the final color output for each pixel.

Voronoi Diagram Rendering: The color output likely represents the different regions of the Voronoi diagram.

3. **triangulation.maxpat**
   - **Type**: Max Patch
   - **Description**: This Max patch likely utilizes the shaders provided in the other files for performing triangulation tasks. It's a visual program that showcases the application of the Delaunay and Voronoi algorithms in a practical setting.

## Usage

To use these shaders and the patch, you should have Max/MSP Jitter installed on your computer. Load the shaders into your Jitter projects to apply the Delaunay triangulation and Voronoi algorithms. The Max patch can be opened directly in Max/MSP for an interactive experience with these algorithms.

## Requirements

- Max/MSP Jitter

## Contributing

Contributions to this project are welcome. Please ensure that any enhancements or bug fixes are compatible with the latest version of Max/MSP Jitter.

@credits Matteo Marson
