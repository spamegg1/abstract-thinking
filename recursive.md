# Recursive thinking

![broccoli](images/broccoli.png)

## recursive computations

This explanation is from [Big Java: Early Objects 7ed](https://www.wiley.com/en-us/Big+Java%3A+Early+Objects%2C+7th+Edition-p-9781119499091) by Cay Horstmann. A few changes were made.

A recursive computation solves a problem by using the solution to a simpler version of the problem, to solve the original problem.

For example, if we look at a triangle made from shapes such as this one:

```java
[]
[][]
[][][]
```

We’d like to compute the area of the triangle assuming each square has area 1. The purpose of this example is to explain the concept of recursion by walking through an example.

If the width of the triangle is 1, then the triangle consists of a single square, and the area is 1.

To deal with the general case, consider this picture:

```java
[]
[][]
[][][]
[][][][]
```

Suppose we knew the area of the upper triangle with width 3. Then we could easily compute the area of the larger traingle as:
`smallerTriangleArea` + `width`.

How can we get the area of the smaller triangle?

```java
[]
[][]
[][][]
```

Similar to before, if we knew the area of the smaller triangle with width 2, then we could easily compute the area of the triangle with width 3 as:
`smallerTriangleArea` + `width`.

```java
[]
[][]
+
[][][]
=
[]
[][]
[][][]
```

Now we can complete a recursive computation for getting the area of any given triangle:

1. if width is equal to 1, the area of this triangle is 1
2. otherwise, the smaller triangle is the triangle with width equal to this traingle's width - 1
3. and the area of this triangle is equal to the area of the smaller triangle plus the width of this triangle.

or, in pseudocode:

```java
if this.width == 1 { area = 1 }
else {
  smallerTraingle = Triangle(width = this.width - 1)
  area = smallerTriangle.getArea() + this.width
}
```

The computation: `smallerTriangleArea` + `width` will repeat itself until the area of the triangle is 1, at which point all the computaitons will be computed like so:

```java
[]
+
[][]
=
[]
[][]
+
[][][]
=
[]
[][]
[][][]
+
[][][][]
=
[]
[][]
[][][]
[][][][]
```

This solution has 1 remarkable quality. To solve the area problem for a triangle of a given width, we use the fact that we can solve the same problem for a triangle of lesser width. This is called a _recursive_ solution because the same computation recurs, i.e. repeats itself.

You only need to figure out how to combine the solution to a simpler version of the problem, in this case the area of the smaller triangle, with the extra input of your problem, in this case the width, to find a solution to your problem, the area of the triangle with the wider base.

### the mental model for coming up with recursive solutions

The steps to follow when coming up with a recursive solution are the following.

1. Consider various ways to simplify the inputs, e.g. the area of the smaller triangle
2. Combine solutions with simpler inputs into a solution for the original problem, e.g. `smallerTriangleArea` + `width`
3. Find solutions to the simplest inputs, e.g. `if (width == 1) { area = 1 }`
4. Implement the solution by combining the simple cases, and the simplification followed by combination step. e.g.

```java
if this.width == 1 { area = 1 }
else {
  smallerTriangle = Triangle(width = this.width - 1)
  area = smallerTriangle.getArea() + this.width
}
```

## Work in progress

[Back to Elements](README.md#recursive-thinking)
