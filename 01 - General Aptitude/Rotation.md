---
title: "Rotation of Shapes"
subject: "General Aptitude"
topic: "Spatial Aptitude"
source: "https://www.geeksforgeeks.org/aptitude/rotation-of-shapes/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "General Aptitude/Spatial Aptitude"
tags:
  - gate/cs
  - subject/general-aptitude
  - topic/spatial-aptitude
---


> [!abstract] Rotation of Shapes
> 
> **Subject:** `General Aptitude` &nbsp;|&nbsp; **Topic:** `Spatial Aptitude`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/aptitude/rotation-of-shapes/)

---

# Rotation of Shapes

Rotation is a geometric transformation that turns every point of a figure about a fixed point (called the center of rotation) through a given angle and direction (clockwise or counterclockwise), without changing the shape's size or internal angles. In mathematical terms, rotation is an isometry: a transformation that preserves distances and shape properties.​
![rotation_of_shapes](assets/rotation_of_shapes-afd13cd997.webp)
## **Mathematical Representation**
**1) Rotation about Origin**
> P'(x', y') = (x cosθ - y sinθ, x sinθ + y cosθ)
**2)** **Quick Rules (Standard Angles)**
| Angle | Counterclockwise | Example: (3,1) | Clockwise | Example: (3,1) |
| --- | --- | --- | --- | --- |
| 90° | (-y, x) | (-1, 3) | (y, -x) | (1, -3) |
| 180° | (-x, -y) | (-3, -1) | (-x, -y) | (-3, -1) |
| 270° | (y, -x) | (1, -3) | (-y, x) | (-1, 3) |
| 360° | (x, y) | (3, 1) | (x, y) | (3, 1) |
## Types of Rotation
**1. Based on Direction**
• Counterclockwise (Positive angle θ): Standard mathematical convention
• Clockwise (Negative angle {-θ}): Opposite to standard direction
**2. Based on Center**
**•** Origin Rotation: Center at (0,0)
• Arbitrary Point Rotation: Center at C(cx,cy)
**3. Based on Dimension**
• 2D Rotation: Plane rotation (x,y coordinates)
• 3D Rotation: Space rotation (x,y,z coordinates)
## **Clockwise & Counterclockwise Rotation**
![counterclockwise_rotation](assets/counterclockwise_rotation-68b93b46c9.webp)
**Counterclockwise Rotation** :
Rotation in the positive angle direction (standard mathematical convention) where points move leftward from the positive x-axis around the center. Every point traces a counterclockwise circular arc, preserving distance from rotation center.
**Clockwise Rotation** :
Rotation in the negative angle direction (opposite to standard convention) where points move rightward from the positive x-axis around the center. Equivalent to counterclockwise rotation by -θ.
## **Origin Rotation & Arbitrary Point Rotation**
**Origin Rotation** : Rotation about the fixed point (0,0) using simple coordinate transformation rules. Every point rotates around the origin maintaining constant distance from (0,0).
**Arbitrary Point Rotation** : Rotation about any point C(cx,cy) (not origin) requires 3-step process:
(1) Translate so C becomes origin
(2) Rotate about new origin
(3) Translate back to original position.
All points maintain same distance from C after rotation.
> Step 1: Translate: P(x,y) → P1 (x-cx, y-cy)
>
> Step 2: Rotate: P1 → P2 (x1cosθ - y1sinθ, x1sinθ + y1cosθ)
>
> Step 3: Translate back: P2 → P' (x2 + cx, y2 + cy)
**Example:** Rectangle Rotation 90° Counterclockwise about C(2, 2)
Original Rectangle ABCD: A(1, 1), B(4, 1), C(2, 2), D(2, 4) rotated 90° Counterclockwise about center C(2, 2)
Solution :-
> **Step 1**: Translate C(2,2) → Origin
>
> A(1,1) → A₁(1-2,1-2) = (-1,-1)
>
> B(4,1) → B₁(4-2,1-2) = (2,-1)
>
> D(2,4) → D₁(2-2,4-2) = (0,2)
>
> **Step 2**: 90° CCW Rotation [(-y,x) Rule]
>
> A₁(-1,-1) → A₂(1,-1)
>
> B₁(2,-1) → B₂(1,2)
>
> D₁(0,2) → D₂(-2,0)
>
> **Step 3**: Translate Back C(2,2)
>
> A₂(1,-1) → A'(1+2,-1+2) = (3,1)
>
> B₂(1,2) → B'(1+2,2+2) = (3,4)
>
> D₂(-2,0) → D'(-2+2,0+2) = (0,2)
>
> **Final Answer**: A'(3,1), B'(3,4), D'(0,2)
## 2D **&** 3D Rotation
![2d_rotation](assets/2d_rotation-3862f9f1c7.webp)
**2D Rotation :** It transforms points in a plane (x,y coordinates) around a fixed center by angle θ. Points move along circular arcs maintaining constant distance from rotation center.
2D Rotation Matrix about Origin:
>
$$
\begin{bmatrix} x' \\ y' \end{bmatrix} = \begin{bmatrix} \cos \theta & -\sin \theta \\ \sin \theta & \cos \theta \end{bmatrix} \begin{bmatrix} x \\ y \end{bmatrix}
$$
**3D Rotation :** It transforms points in space (x,y,z coordinates) around a fixed axis (X, Y, or Z) by angle θ.
Homogeneous Coordinates (3×3 for composition):
>
$$
\begin{bmatrix} x' \\ y' \\ 1 \end{bmatrix} = \begin{bmatrix} \cos \theta & -\sin \theta & 0 \\ \sin \theta & \cos \theta & 0 \\ 0 & 0 & 1 \end{bmatrix} \begin{bmatrix} x \\ y \\ 1 \end{bmatrix}
$$
## Rotation of Shape - Solved Question and Answers
**Question 1** : Point P(3,−2) is rotated 90° counterclockwise about the origin. Find the coordinates of P′ .
**Solution :**
> For 90° CounterClockWise about origin, use rule: (x , y) → (−y , x)
>
> **P**(3 , −2) → **P**′ (−(−2) , 3) = (2,3)
**Question 2:** Point A(5,7) is rotated 180° about the origin. Find the coordinates of A′.
**Solution :**
> For 180° (same for Clockwise/Counterclockwise): (x,y) → (−x,−y).​
>
> A(5 , 7) → A′(−5 , −7)
>
> **Answer:**  A′(−5 , −7)
**Question 3:** The given figure is rotated 90° counterclockwise about the black dot (which acts as the center of rotation). Which of the following options correctly represents the rotated figure?
![rotation1](assets/rotation1-d1b0e30950.jpg)
Question 3
**Solution:**
> - During a 90° counterclockwise rotation, the black dot remains fixed as the center of rotation.
> - All parts of the figure move along circular paths, maintaining their distances and orientation.
> - Only **Option (C)** shows the correct position and orientation after this rotation.
### Realated Articles
> - [Assembling](https://www.geeksforgeeks.org/aptitude/assembling-aptitude/)
> - [Grouping](https://www.geeksforgeeks.org/aptitude/grouping-of-images/)
> - [Paper Folding](https://www.geeksforgeeks.org/ssc-banking/non-verbal-reasoning-paper-folding/)
> - [Cutting](https://www.geeksforgeeks.org/ssc-banking/non-verbal-reasoning-paper-cutting/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/aptitude/rotation-of-shapes/)

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
> - [[Scaling]]
> - [[Translation]]
> - [[Adjectives]]
> - [[Alphanumeric Series]]
> - [[Analogy]]
