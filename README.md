# Delaunay triangulation on GPU
a shader implementation of delaunay triangulation
## About the algorithms

This repository is about computing Delaunay triangulation in the GPU. 
Assumption: the Voronoi diagram and Delaunay triangulation are mathematically dual structures in computational geometry, meaning they are closely related and can be derived from one another.

Voronoi Diagram: A Voronoi diagram partitions a plane with n points (seeds, sites) into convex polygons such that each polygon contains exactly one generating point and every point in a given polygon is closer to its generating point than to any other. These polygons are called Voronoi cells.

Delaunay Triangulation: Delaunay triangulation for a set of points in a plane gives a triangulation such that no point is inside the circumcircle of any triangle. Delaunay triangles maximize the minimum angle compared to any other triangulation of the points.

The Relationship:
- If you take the circumcenters of the Delaunay triangles in a Delaunay triangulation, these points will be the vertices of the Voronoi cells in the corresponding Voronoi diagram.
- Conversely, if you connect the points (seeds) of neighboring Voronoi cells, you obtain the edges of the Delaunay triangulation.
- This implies that if you have computed one structure, you can derive the other without additional point location or distance calculation, just by connecting points or calculating circumcenters accordingly.


## Usage

To use these shaders and the patch, you should have Max/MSP Jitter installed on your computer. Load the shaders into your Jitter projects to apply the Delaunay triangulation and Voronoi algorithms. The Max patch can be opened directly in Max/MSP for an interactive experience with these algorithms.

## Requirements

- Max/MSP Jitter

## Contributing

Contributions to this project are welcome. Please ensure that any enhancements or bug fixes are compatible with the latest version of Max/MSP Jitter.

Many thanks to Matteo Marson for the help!
