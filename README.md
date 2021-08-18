# Triangle Strip

This repository provides an easy to use python function that generates a
(not guaranteed optimal) triangle strip out of a set of
connected triangles.

This can be especially useful for converting regular triangle based meshes
into a triangle strip based one. Such a version can then be used inside
a geometry shader.

If you got any improvements for the module feel free to raise an issue or
contact me.

## Example
Just call the `find_strip` function with a list of triangles:
```python
icosahedron_triangles = [[0, 1, 2],
                         [3, 1, 0],
                         [4, 1, 3],
                         [5, 1, 4],
                         [2, 1, 5],
                         [6, 7, 8],
                         [8, 7, 9],
                         [9, 7, 10],
                         [10, 7, 11],
                         [11, 7, 6],
                         [0, 2, 6],
                         [2, 5, 11],
                         [5, 4, 10],
                         [4, 3, 9],
                         [3, 0, 8],
                         [8, 0, 6],
                         [9, 3, 8],
                         [10, 4, 9],
                         [11, 5, 10],
                         [6, 2, 11]]

print("Trying to find a triangle strip representation of an icosahedron")
triangle_strip = find_strip(icosahedron_triangles)
print("Triangle strip:", triangle_strip)
print("Length of the triangle strip:", len(triangle_strip))

```
A triangle is just a list of three elements that are comparable and represent
the vertices of that triangle. This could either be an integer describing the
vertex id (as in the case of this example) or a custom object that is comparable
and contains the position of that vertex.

## License
This code is licensed under The Unlicense. More information can be found in the
`LICENSE` file in this repository.
