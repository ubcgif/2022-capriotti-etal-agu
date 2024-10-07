# Linking open source tools for geophysical simulation and inversion in rugged topographies

_Joseph Capriotti, Johnathan Kuttai, Dominique Fournier and Lindsey J. Heagy_

![thumbnail](./abstract/thumbnail.png)

## Summary 

Real world collection of geophysical data is rarely done in the absence of topographic effects, and incorporating topography into our interpretations, through forward simulations and inversions, requires us to represent the continuous surface with a discretized earth model. Designing meshes that take topography into account is often a challenge because we need to accurately model the topography (where we often take our measurements), and accurately represent the geophysical method. Meshes can be structured, semi-structured or unstructured. The simplest approaches use structured meshes made of rectangular prisms. This can lead to issues near the surface due to the pixelated representation of topography if our observation is near the edge of a surface cell. Simple approaches also require fine discretization of the subsurface with large numbers of cells to accurately represent rugged topographies. Semi-structured meshes, such as quadtree and octree meshes, can be locally refined near the surface without a large increase in the total number of cells but still use a pixelated representation of topography. Unstructured meshes made of arbitrary tetrahedral or curvilinear cells can follow topography closely with a smaller number of cells, but these types of meshes are generally difficult to create and visualize. We use a combination of open source tools and demonstrate our workflow for designing meshes with a rugged topography, and apply these methods to a DC resistivity inversion. We make use of the Discretize package to design rectilinear, octree, and curvilinear meshes using built-in tools. We integrate gmsh into the workflow to create tetrahedral meshes that follow topography which are then imported into Discretize. Discretize, which is built upon the open source Numpy and Scipy packages, defines finite volume numerical partial differential operators for each mesh. SimPEG then uses these abstract operators to set up and solve the DC resistivity forward and inverse operations in a manner that allows us to easily interchange each type of mesh within the framework. All of these mesh types are representable in Pyvista, which we use to visualize recovered inversion models. We make these workflows available through the SimPEG organization as examples for others to build off and generalize to their own problems.

## Citation 

