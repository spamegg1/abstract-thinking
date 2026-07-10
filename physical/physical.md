# Physical world

Many abstract ideas in math + CS come from physical reality and nature.

Here is a [survey article](https://doi.org/10.34133/research.0442)
of nature-inspired computing.

Here is a [wonderful site](https://natureofcode.com) with many
examples of math + CS ideas found in or inspired by nature.

## Examples

|     Abstract version| ↔ |Physical version                        |
|--------------------:|:-:|:---------------------------------------|
|addition, subtraction| ↔ |putting things together, removing things|
|       transformation| ↔ |bending / stretching / shifting objects |
|         modus ponens| ↔ |cause and effect                        |
| traits, polymorphism| ↔ |genetics                                |
|            recursion| ↔ |plants, shells, other life forms        |
|software architecture| ↔ |physical architecture                   |
|      neural networks| ↔ |human brain                             |
|    OS task switching| ↔ |multi-tasking of the human brain        |

## Example: seashells and cellular automata

Some life forms like seashells exhibit interesting patterns:

![textile](../images/Textile_cone.JPG)

(Image credit: Copyright (c) 2005 Richard Ling, used under
[CC3.0 license](https://creativecommons.org/licenses/by-sa/3.0/deed.en))

This kind of phenomenon can happen in real life due to some simple physics and chemistry
of the molecules that create the pigmentations, in addition to the information
stored in the genetics of the life form for various reasons (like camouflage).

We can abstract away the mechanism that generates these patterns.

1. We can first simplify it:
    - assume there are only 2 colors, and
    - assume it's all on a grid.

2. We can imagine some simple rules that determine the colors of a square on the next row,
  based on the square on the current row, and two of its surrounding squares (left+right).
  For example, if it's `WHITE WHITE WHITE` then the next square in the middle
  could also be `WHITE`:

    ||left|mid|right|
    |:-:|:-:|:-:|:-:|
    |current|WHITE|WHITE|WHITE|
    |next|???|WHITE|???|

    Based on this idea, there would have to be 8 rules.

3. By looking at the seashell we can get some inspiration and play around with some rules.
  As a result, this is the pattern that's generated
  (with the 8 rules depicted at the bottom of the image):

    ![rule30](../images/Cellular_Automata_running_Wolfram-rule-30.svg.png)

    (Image credit: [Nonenmac](https://en.wikipedia.org/wiki/User:Nonenmac)
    at [English Wikipedia](https://en.wikipedia.org/wiki/),
    used under [CC3.0 license](https://creativecommons.org/licenses/by-sa/3.0/deed.en))

This type of idea can be taken much further to give rise to cellular automata.
It gets extremely deep: this simple discrete model of computation is shown to be
Turing complete, i.e. capable of emulating any arbitrary computation!

## Exercise: create abstract ideas from physical things

### Rolling a 4-sided die

Consider a 4-sided die, where I marked the four corners with numbers
(we could have also marked the four faces instead):

![tet-01](../images/tet-01.png)

Now think about rolling this die. It will land in some way on one of its four faces.

For simplicity, let's assume that it lands in the same "pose" (called a *symmetry*),
except the faces and corners might have been switched around in some way
(otherwise there are infinitely many possibilities). For example:

![tet-09](../images/tet-09.png)

What kinds of things can happen to the positions of the four corners
as a result of rolling the die and having it land in different ways?

#### Orientation

First notice that since this is a solid physical object,
certain configurations are not possible. For example:

![tet-imp](../images/tet-imp.png)

Here 2 and 3 switched places while keeping the rest of the die intact,
which would be equivalent to bending or twisting it somehow.
This is not possible for a hard solid object just by rolling it.
(In other words, rolling a die *preserves its orientation*.)

Keeping this in mind, we can draw all the possibilities. There are 12 of them:

![tet-all](../images/tet-all.png)

But this is not the abstract idea I want you to come up with!

#### Exercise: abstracting the die rolls

1. How (in the physical sense) can you move the die between these three states:

    ![tet-01-02-03](../images/tet-01-02-03.png)

    Can you come up with an abstract version of these movements?
    How would you describe them? Symbols? Figures? Notation?
    Are there relations between them? Can one be described in terms of another?

2. How can you move the die between these three states:

    ![tet-04-05-06](../images/tet-04-05-06.png)

    Is there a similarity between this and how you can move between the previous 3?

3. Think similarly to 1-2 for the other states:

    These three:

    ![tet-07-08-09](../images/tet-07-08-09.png)

    And these three:

    ![tet-10-11-12](../images/tet-10-11-12.png)

4. Can you think of a way to "combine" the moves from 1 with the moves from 2 or 3?
  Are there any relations between combinations? What can you say about them?

5. How to move (in the physical sense) between these two?

    ![tet-12-34](../images/tet-12-34.png)

    Can you come up with an abstract version of this movement?

6. How to move between these two?

    ![tet-13-24](../images/tet-13-24.png)

    Is there a similarity between this and the previous?

7. Think similarly to 5-6 to move between these two:

    ![tet-14-23](../images/tet-14-23.png)

8. Can you now list all 12 moves, using your descriptions?
  Each one of the 12 moves should start from the initial die position:

    ![tet-01](../images/tet-01.png)

  and end with one of the 12 positions (including the initial itself).

#### Solution

1. We can move by a rotation around the vertical axis:

    ![tet-rot](../images/tet-rot.png)

    Such a rotation leaves the "top of the pyramid" unmoved and just rotate "the base".

    These rotations can be 120° (to move from the 1st to the 2nd,
    or from the 2nd to the 3rd, or from the 3rd to the 1st),
    240° (1st -> 3rd, 2nd -> 1st, 3rd -> 2nd).
    If the rotation is 360° then it does not change anything.

    Abstractly we can use algebraic notation.
    Let's give the rotation some name.
    It fixes the point 4, so maybe call it $r_4$.
    This is a 120° counter-clockwise rotation.

    Then the 240° rotation is the same as $r_4$ applied twice in a row!
    There are many ways to represent this. We could use a string $r_4r_4$
    where the rotations are applied left-to-right, or right-to-left if we choose.
    Or we can think of "applying rotations in a row" as "multiplication",
    so it could be notated as $r_4^2$.

    Symbolically we can also think of it as "function application" so it's right-to-left:

    ![tet-fun-1](../images/tet-fun-1.png)

    ![tet-fun-2](../images/tet-fun-2.png)

    Then applying $r_4$ three times in a row gets us back to the same state,
    in other words it does nothing. It's like 0 in addition or 1 in multiplication.
    This is called an "identity" element. Let's call this move $I$.
    Then algebraically $r_4^3 = I$. We could say that $r_4$ "has degree 3".

    Warning! This "multiplication" notation needs some care, because it won't be
    the same as the usual multiplication of numbers. Order matters!
    Normally $2 \times 3 = 3 \times 2$ but if we get different kinds of rotations
    then they may not work like this. Applying one rotation first, then another second
    may not be the same as the other way around.
    In other words they might not be *commutative*.

2. Similarly we can think of a rotation $r_3$ such that $r_3^3 = I$.
3. Similarly we can think of rotations $r_1$ and $r_2$.
4. If we apply $r_1$ then $r_2$ here's what happens:

    ![tet-r1-r2](../images/tet-r1-r2.png)

    Notice that applying $r_1$ and then $r_2$, is the same as just applying $r_4$.
    Weird! So if we use the right-to-left algebraic notation: $r_2r_1 = r_4$.

    You can play around with many combinations for fun.
    Try to find other "algebraic laws" like this!
    There are way too many of them, I don't expect you to write them all down.
    [Here is a list](https://proofwiki.org/wiki/Alternating_Group_on_4_Letters)
    in case you are curious (although they use different notation).

5. This can be done by a 180° rotation around an axis like this:

    ![tet-rot-180](../images/tet-rot-180.png)

    Such a rotation swaps 1 with 2, and swaps 3 with 4.
    Since this is a 180° rotation, applying it twice does nothing.
    So, if we call it $r_{12,34}$, then $r_{12,34}^2 = I$. So it has order two.

6. You can find a similar axis with a 180° rotation that swaps 1-3 and 2-4.
7. You can find a similar axis with a 180° rotation that swaps 1-4 and 2-3.
8. Let's start by listing all 12 that we have:
  $I, r_1, r_1^2, r_2, r_2^2, r_3, r_3^2, r_4, r_4^2, r_{12,34}, r_{13,24}, r_{14,23}$.

  Normally we would have to be careful that there isn't some subtle relation between
  these that causes a repetition, in other words we'd have to make sure that
  these moves are all different from each other. But let's not worry about that for now.

  Here is ONE WAY to describe the 12 moves (there are many other, equivalent ways).
  If we number all the states like this

  ![tet-all-num](../images/tet-all-num.png)

  then:

  1. $I$ moves `1.` to `1.`

      ![tet-id](../images/tet-id.png)

  2. $r_1$ moves `1.` to `7.`

      ![tet-r1](../images/tet-r1.png)

  3. $r_2$ moves `1.` to `6.`

      ![tet-r2](../images/tet-r2.png)

  4. $r_3$ moves `1.` to `8.`

      ![tet-r3](../images/tet-r3.png)

  5. $r_4$ moves `1.` to `2.`

      ![tet-r4](../images/tet-r4.png)

  6. $r_1^2$ moves `1.` to `4.`

      ![tet-r1sq](../images/tet-r1sq.png)

  7. $r_2^2$ moves `1.` to `11.`

      ![tet-r2sq](../images/tet-r2sq.png)

  8. $r_3^2$ moves `1.` to `10.`

      ![tet-r3sq](../images/tet-r3sq.png)

  9. $r_4^2$ moves `1.` to `3.`

      ![tet-r4sq](../images/tet-r4sq.png)

  10. $r_{12,34}$ moves `1.` to `5.`

      ![tet-r1234](../images/tet-r1234.png)

  11. $r_{13,24}$ moves `1.` to `9.`

      ![tet-r1324](../images/tet-r1324.png)

  12. $r_{14,23}$ moves `1.` to `12.`

      ![tet-r1423](../images/tet-r1423.png)

## Exercises: find physical analogies that correspond to abstract ideas

Here we are looking for *just analogies.*
Not physical phenomena that perfectly correspond to the ideas.
Can you think of a physical analogy to these ideas?
There are many possibilities. Try to think of a verb for each one, if possible.

### Exercise 1

Consider working through a list of numbers and adding them up, or multiplying them:

```py
[1, 2, 3, 4, 5, 6, 7, 8, 9]
   [3, 3, 4, 5, 6, 7, 8, 9]
      [6, 4, 5, 6, 7, 8, 9]
        [10, 5, 6, 7, 8, 9]
           [15, 6, 7, 8, 9]
              [21, 7, 8, 9]
                 [28, 8, 9]
                    [36, 9]
                        45
```

### Exercise 2

Consider a list that contains other lists, and converting them all into a single list.
For example, turning this:

```py
             8
      4      9
   2  5     10  12
1, 3, 6, 7, 11, 13
```

![list-of-lists](../images/list-of-lists.png)

into this:

```py
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13]
```

### Exercise 3

In two or three dimensional Cartesian coordinate systems, points like $(x, y)$
or $(x, y, z)$ can be converted to lower dimensional versions:

![proj-2d](../images/proj-2d.png)

![proj-3d](../images/proj-3d.png)

The same abstract idea works more generally in higher dimensions too.

### Solutions

Obviously there is no right or wrong answer here.
If you found other analogies, great!

1. Folding: think of it like folding a long piece of paper little by little in stages.
  Another good one is "snowballing" or "avalanche"! 😄
2. Flattening: like pushing it down to the ground or taking the air out of it.
3. Projecting: like how light can be projected onto walls or screens.

[Back to our senses and the physical world](README.md)
