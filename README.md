unity-triangulation2D
=====================

Delaunay Triangulation and Ruppert's Delaunay Refinement Algorithm in Unity.
![drawing](https://raw.githubusercontent.com/mattatz/unity-triangulation2D/master/Captures/drawing.gif)

Input contour points for [planar straight-line graph](https://en.wikipedia.org/wiki/Planar_straight-line_graph)
![input](https://raw.githubusercontent.com/mattatz/unity-triangulation2D/master/Captures/input.png)

Delaunay Triangulation
![triangulation](https://raw.githubusercontent.com/mattatz/unity-triangulation2D/master/Captures/delaunay_triangulation.png)

Mesh Refinement with minimum angle α(22.5)
![refinement](https://raw.githubusercontent.com/mattatz/unity-triangulation2D/master/Captures/mesh_refinement.png)

## Usage

```cs
// input points for a polygon2D contor
List<Vector2> points = new List<Vector2>();

// Add Vector2 to points
points.Add(new Vector2(-2.5f, -2.5f));
points.Add(new Vector2(2.5f, -2.5f));
points.Add(new Vector2(4.5f, 2.5f));
points.Add(new Vector2(0.5f, 4.5f));
points.Add(new Vector2(-3.5f, 2.5f));

// construct Polygon2D 
Polygon2D polygon = Polygon2D.Contour(points.ToArray());

// construct Triangulation2D with Polygon2D and threshold angle (18f ~ 27f recommended)
Triangulation2D triangulation = new Triangulation2D(polygon, 22.5f);

// build a mesh from triangles in a Triangulation2D instance
Mesh mesh = triangulation.Build();
// GetComponent<MeshFilter>().sharedMesh = mesh;
```

## Demo

![demo](https://raw.githubusercontent.com/mattatz/unity-triangulation2D/master/Captures/demo.gif)

## Sources

- Ruppert's algorithm - https://en.wikipedia.org/wiki/Ruppert%27s_algorithm

- Ruppert's Delaunay Refinement Algorithm - https://www.cs.cmu.edu/~quake/tripaper/triangle3.html

- Chapter 7.pdf - http://www.ti.inf.ethz.ch/ew/Lehre/CG13/lecture/Chapter%207.pdf
