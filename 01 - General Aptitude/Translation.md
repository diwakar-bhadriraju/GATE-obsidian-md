---
title: "Translation of Shapes"
subject: "General Aptitude"
topic: "Spatial Aptitude"
source: "https://www.geeksforgeeks.org/aptitude/translation-of-shapes/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "General Aptitude/Spatial Aptitude"
tags:
  - gate/cs
  - subject/general-aptitude
  - topic/spatial-aptitude
---


> [!abstract] Translation of Shapes
> 
> **Subject:** `General Aptitude` &nbsp;|&nbsp; **Topic:** `Spatial Aptitude`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/aptitude/translation-of-shapes/)

---

# Translation of Shapes

Translation is a geometric transformation that moves every point of a figure by the same distance in the same direction, without changing the shape's size, orientation, or internal angles. In mathematical terms, a translation is an isometry: a transformation that preserves distances and shape properties.
> When you translate a shape, you are essentially "sliding" it to a new position on the coordinate plane. Every point on the original figure (called the pre-image) shifts by identical amounts in the horizontal and vertical directions to produce the new figure (called the image).
![translation_of_shapes_one](assets/translation_of_shapes_one-de5b4af993.webp)
**Mathematical Representation**
For a translation in 2D space, if a point P has coordinates (**x** , **y**), and we translate it by a vector **v**=(**t**x** ,**t**y**), the new coordinates P′ will be:
>
$$
P' = (x + t_x, y + t_y)
$$
Where:
- tx = horizontal displacement (positive = right, negative = left)
- ty = vertical displacement (positive = up, negative = down)
## Types of Translation
Translation means sliding a figure from one position to another without rotating, flipping, or resizing it. The shape and orientation remain the same.
![translation_of_shapes_two](assets/translation_of_shapes_two-f4db0be6ed.webp)
**1) Horizontal Translation (Along X-axis)**
A translation where only the x-coordinates change: v = (tx,0)
> **Example:** Move point P(3, 4) by 5 units to the right.
>
> **P** ′= (3+5,4+0) = (8,4)
**2) Vertical Translation (Along Y-axis)**
A translation where only the y-coordinates change: v = (0,ty)
> **Example:** Move point Q(2, 3) by 4 units upward.
>
> **Q** ′= (2+0,3+4) = (2,7)
**3) Combined Translation (Both Horizontal and Vertical)**
A translation with both x and y components: **v**=(**t**x**,**t**y**) where both tx ≠ 0 and ty ≠ 0.
> **Example:** Move point R(1, 1) by 3 units right and 2 units down.
>
> **R** ′ = (1+3,1−2) = (4,−1)
## **Properties of Translation**
**1. Congruence Preservation**​
Translation produces a figure that is congruent to the original. This means:
- Side lengths are preserved
- Angles are preserved
- Area and perimeter remain unchanged
**2. Isometry**​
Translation is an isometry transformation, which means:
- Distance between any two points is preserved
- The shape maintains its exact form
**3. Vector Addition Property**​
If you translate a shape by vector v1 = (a,b) and then by vector v2 = (c,d), it's equivalent to translating by the single vector v1+v2 = (a+c,b+d).
**4. Inverse Translation**
For any translation by vector **v**, there exists an inverse translation by vector (−**v)** that returns the shape to its original position.
**5. No Fixed Points**​
Unlike rotation (which has a center) or reflection (which has an axis of symmetry), translation has no fixed points , every point in the plane moves.
## Translating a Rectangle
**Problem Statement**
Consider a rectangle ABCD with vertices at: A(2,3) , B(6,3) , C(6,5) , D(2,5) . Translate this rectangle by the vector v = (3,2) (3 units to the right and 2 units upward).
Solution :
> Apply the translation formula to each vertex:
>
> **For vertex A(2, 3):**
>
> A′ = (2+3,3+2) = (5,5)
>
> **For vertex B(6, 3):**
>
> B′ = (6+3,3+2) = (9,5)
>
> **For vertex C(6, 5):**
>
> C′ = (6+3,5+2) = (9,7)
>
> **For vertex D(2, 5):**
>
> D′ = (2+3,5+2) = (5,7)
>
> ![translation_of_a_rectangle_by_vector_v_3_2_](assets/translation_of_a_rectangle_by_vector_v_3-fb52d157ce.webp)
>
> The translated rectangle A'B'C'D' has vertices at (5, 5), (9, 5), (9, 7), and (5, 7), respectively. The shape maintains its original dimensions (width = 4 units, height = 2 units) and orientation.
## Translation of Shapes - Solved Questions and Answers
**Question 1** : Which of the following statements accurately describes the properties of translations of shapes?
**(A)** Translations preserve the angles of geometric figures
**(B)** Translations change the area of the shape
**(C)** Translations can rotate the shape
**(D)** Translations increase the size of the shape
> According to fundamental properties of translation
>
> Translation is an isometric transformation, so all metric properties (distances, angles, area) are preserved. Only the position changes.
>
> So, (A) is the correct option
**Question 2** : Triangle ABC has vertices A(1, 2), B(4, 2), and C(2, 5). Translate it by vector v = (−2,3). What are the coordinates of the image triangle A'B'C'?
**Solution :**
> For each vertex, apply: (x′,y′) = (x+tx , y+ty) where v = (−2,3)
>
> For A(1, 2): **A**′ = (1+(−2),2+3) = (−1,5)
>
> For B(4, 2): B′ = (4+(−2),2+3) = (2,5)
>
> For C(2, 5): C′ = (2+(−2),5+3) = (0,8)
>
> Verification:
>
> - Distance AB = √(4−1)2 + (2−2)2 = 3 units
> - Distance A'B' = √(2−(−1))2+(5−5)2 = 3 units
> - Distances are preserved, confirming this is a valid translation.
**Question 3 :** Shape X is shown on a coordinate grid. Shape Y appears to be a translation of Shape X. Which column vector BEST describes the translation from X to Y?
**Solution :**
> A point on X is at (3, 4) and the corresponding point on Y is at (7, 1).
>
> Translation vector = (Final position) - (Initial position)​
>
> v = (7−3,1−4) = (4,−3)
>
> This means:
>
> - 4 units to the RIGHT (positive x)
> - 3 units DOWN (negative y)
**Question 4 :** A shape is translated by 4 units to the right and 3 units upward. Which of the following is NOT a property of the translated shape compared to the original ?
**(A)** Congruent to the original shape
**(B)** Same perimeter as the original
**(C)** Same orientation as the original
**(D)** Same distance from the origin
**Solution :**
> Since the shape moves, its distance from the origin changes. This is the ONLY property among the options that is NOT preserved by translation. So , (D) is the correct option.
### Related Articles:
> - [Spatial Aptitude](https://www.geeksforgeeks.org/aptitude/spatial-aptitude/)
> - [Mirroring](https://www.geeksforgeeks.org/ssc-banking/concept-of-mirror-image-non-verbal-reasoning/)
> - [Paper Folding](https://www.geeksforgeeks.org/ssc-banking/non-verbal-reasoning-paper-folding/)
> - [Cutting](https://www.geeksforgeeks.org/ssc-banking/non-verbal-reasoning-paper-cutting/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/aptitude/translation-of-shapes/)

## GATE CS

- Subject: General Aptitude
- Topic: Spatial Aptitude

> [!note] Related notes
>
> - [[Assembling]]
> - [[Cutting]]
> - [[Grouping]]
> - [[Mirroring]]
> - [[Paper Folding]]
> - [[Rotation]]
> - [[Scaling]]
> - [[Adjectives]]
> - [[Alphanumeric Series]]
> - [[Analogy]]
