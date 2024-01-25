# Abstraction

## Generalization and Specialization

- Universal and existential quantification.
- Parametrization.
- Contextual generalization (connection to implicits.)
- Abstraction and reification.

## How to generalize: thinking abstractly

![abstraction-hierarchy](images/abstraction.png)

- Here, we can add logic as an external meta-abstraction that applies to ALL of these.
  - With arrows pointing from Logic to each one.

- Start with real-world, often physical, observations of objects,
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

## An example

- Surface area in the naive, physical sense:
  - how much water does it take to fill some flat surface?

Then generalize to:

- squares: $A = s \times s$,
- rectangles: $A = w \times h$,
- triangles: $A = w \times h / 2$,
- regular polygons: add up the triangles,
- irregular polygons,
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

## Work in progress!

[Back to Elements](README.md#abstraction)