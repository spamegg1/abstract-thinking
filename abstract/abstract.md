# Abstraction

## Many meanings of abstraction

1. Generalization
2. Hiding details (design vs. implementation)
3. Making things unreal, imaginary by removing context and application
4. Recognizing common patterns and turning them into building blocks

There are probably many more! But we'll stick to these.
These four have some similarities and common aspects,
but we won't split them further into even smaller ideas (it gets *too abstract*).

## Generalization and Specialization

- Universal and existential quantification.
- Parametrization.
- Contextual generalization (connection to implicits.)
- Abstraction and reification.

### An example of generalization: surface area

- Surface area in the naive, physical sense:
  - how much water does it take to fill some flat surface container (of unit height)?

Start simple:

- squares: $A = s \times s$,

Then generalize to:

- rectangles: $A = w \times h$,
- triangles: $A = w \times h / 2$,
- regular polygons: add up the triangles,
- irregular polygons (break up into regular polygons, triangulation),
- areas under arbitrary *continuous* curves of a single variable over *an interval*:
  - add up areas of rectangles over the interval, take limit: Riemann integral
- *piecewise continuous* curves over *an interval,*
- *"integrable" curves* over *an interval*,
- *integrable curves* over *the partitioning of an interval by a function of bounded variation,*
- *integrable curves* over *measurable sets*: Lebesgue integral,
- multi-variable version of this,
- the $p$-adic numbers instead of $\mathbb{R}$,
- an integral over a *locally compact topological group* with a *left-invariant Haar measure*:
  - abstract harmonic analysis!

## Hiding details

TODO

### An example of detail hiding

TODO

## Removing context and application

![abstraction-hierarchy](../images/abstraction.png)

- Start with real-world, often physical, observations of objects.
- Remove "special properties" (or "context") from the real world:
  - If you are looking at a picture with three different lions, remove their differences,
  - and then remove their "animalness", etc.
  - this is called making it "context-free".
- Look for:
  - relations between them,
  - operations that act on them,
  - properties they might have.
  - This is the most difficult part and cannot be taught completely.
- Now see if the objects can be replaced with others.
  - Do the properties / relations still hold?
- Now see if the operations could be replaced with others:
  - Do they still work?

### An example of context removal

TODO

## Recognizing patterns and turning them into building blocks

TODO

### An example of creating building blocks

TODO

## Complex example with many meanings of abstraction together

TODO

[Back to the abstract stuff](README.md)
