---
## STL
An STL (Stereo Lithography) file is a triangular representation of a 3-dimensional surface geometry. The surface is broken down into a series of small triangles (facets or faces).  Each facet is described by a perpendicular direction (the normal) and three points representing the vertices (corners) of the triangle.

![Facet, vertex and normal](https://developers.formide.com/#/docs/katana/img/Facet_vertex_normal.png)

This data is used by the slicing algorithm in katana to determine the cross sections (2d layers) of the 3-dimensional shape to be printed by a 3d printer.

---
### How does STL Work?

An STL file consists of a list of facet data.  Each facet is uniquely identified by a unit normal and  three vertices.  The normal and each vertex are specified by three coordinates each, so there is a total of 12 numbers stored for each facet.

The STL standard includes two data formats, ASCII and binary.

---
### ASCII format

The ASCII format is primary intended for testing new CAD interfaces.  The larger size of its files makes it impractical for general use.

The syntax for an ASCII STL file is as follows:
```
    solid name
        facet normal n_i n_j n_k
            vertex v_1,i v_1,j v_1,k
            vertex v_2,i v_2,j v_2,k
            vertex v_3,i v_3,j v_3,k
        end facet
        ...
    end solid          
```

Note: A vertex normal can have a negative coordinate, a vertex not (i.e. The 3d model can have facets facing the negative parts of the x,y, and z axes. But the model itself must lie in the all-positive octant.  In other words, all vertex coordinates must be positive-define (nonnegative and nonzero) numbers).

---
### Binary format

The binary format uses the IEEE integer and floating point numerical representation.
The header record consists of 84 bytes, the first eighty are used for information about the file, author's name and other miscellaneous comments, the last 4 bytes represent the number of triangular facets.  Next, for each facet, 50 bytes are used to represent the x, y and z components of the normal to the facets, then the x, y and z coordinates of each vertex of the triangle. 4 bytes are used for each coordinate, resulting is 48 bytes per facet.  The last two bytes are not used.

---
### Facet Orientation

The facets define the surface of a 3-dimensional object. As such, each facet is part of the boundary between the interior and the exterior of the object.  The orientation of the facets  is specified redundantly in two ways which must be consistent.  First, the direction of the normal is outward. Second, the vertices are listed in counterclockwise order when looking at the object from the outside (right-hand rule).

---
### Vertex-to-vertex rule

Each triangle must share two vertices with each of its adjacent triangles.  In other words, a vertex of one triangle cannot lie on the side of another.   
