<!---
{
  "id": "9c17f900-f66c-44e6-9761-fcfba8a2f87d",
  "depends_on": [],
  "author": "Stephan Bökelmann",
  "first_used": "2025-04-11",
  "keywords": ["vector potential", "electromagnetism", "EM waves", "Maxwell equations"]
}
--->

# Introduction to Vector Potential for Electromagnetic Waves

> In this exercise you will learn how electromagnetic waves can be described not only by electric and magnetic fields, but also by a helper concept called the vector potential. Furthermore we will explore how this idea helps us understand light and radio waves more easily.

### Introduction

Electromagnetic waves, like light and radio waves, are all around us. These waves are made of electric fields and magnetic fields. Usually, in school, we learn about these fields directly, but there's another way to look at them: using something called a **vector potential**.

A **vector potential**, often written as **A**, is like a hidden map that helps us calculate both the electric and magnetic fields. Just like how the slope of a hill tells you how fast you're going downhill, the vector potential helps describe how the fields are changing. While this might sound abstract, it’s a powerful way to work with electromagnetic waves — especially when doing calculations.

For example, the magnetic field **B** can be found from **A** using a special kind of derivative called the **curl**:

```latex
\vec{B} = \nabla \times \vec{A}
```

That squiggly "∇×" means we're finding how the vector potential twists or curls in space.

Why do we care? Sometimes it’s easier to find the vector potential first and then calculate the fields, especially in complicated situations. And in advanced physics, like quantum mechanics and relativity, the vector potential is actually more fundamental than the electric and magnetic fields themselves - which was shown by the Aharonov-Bohm effect in 1959!

Let’s walk through some simple steps to understand how it works, starting with drawing fields and working out examples.

### Further Readings and Other Sources

- [Khan Academy: Electromagnetic Waves and Fields](https://www.khanacademy.org/science/physics/light-waves)
- [MIT OpenCourseWare on Vector Potential (Video)](https://ocw.mit.edu/courses/8-02sc-physics-ii-electricity-and-magnetism-fall-2010/resources/lecture-22-vector-potential/)
- [HyperPhysics – Vector Potential](http://hyperphysics.phy-astr.gsu.edu/hbase/magnetic/vector.html)

---

## Tasks

### Task 1: Visualizing the Magnetic Field and the Vector Potential

1. Draw a straight wire with a current going upwards.
2. Around this wire, draw circular magnetic field lines around the wire.
3. Now, draw arrows that point along those circles. These arrows represent the vector potential **A**.
4. Use the formula `\vec{B} = \nabla \times \vec{A}` to explain how the circular **A** leads to circular **B**.
Hint: You can think of the vector potential arrows as flowing water in a whirlpool — the twist of that flow is the magnetic field.


- Assume the vector potential \( \vec{A} \) points tangentially around the wire (like a whirlpool), and its magnitude depends on the distance from the wire.
- In cylindrical coordinates (\( r, \theta, z \)), this might look like:

```latex
\vec{A} = A_\theta(r) \hat{\theta}
```

- The curl of \( \vec{A} \) in cylindrical coordinates gives the magnetic field:

```latex
\vec{B} = \nabla \times \vec{A} = \left( \frac{1}{r} \frac{\partial (r A_\theta)}{\partial r} \right) \hat{z}
```

- Suppose \( A_\theta(r) = \frac{k}{r} \), then:

```latex
\frac{\partial}{\partial r} (r A_\theta) = \frac{\partial}{\partial r} (r \cdot \frac{k}{r}) = \frac{\partial}{\partial r} (k) = 0
```

- This would mean no magnetic field (\( \vec{B} = 0 \)), so instead pick a function like \( A_\theta = kr \), then:

```latex
r A_\theta = kr^2 \Rightarrow \frac{\partial}{\partial r}(r A_\theta) = \frac{\partial}{\partial r}(kr^2) = 2kr
```

- Then:

```latex
\vec{B} = \frac{1}{r} (2kr) = 2k \Rightarrow \vec{B} = 2k \hat{z}
```

- This shows a uniform magnetic field pointing upward along the wire — matching what we observe around a current-carrying wire!

### Task 2: Deriving the Magnetic Field from a Simple Vector Potential (Step-by-Step)

We are given a vector potential:

```latex
\vec{A} = (-y, x, 0)
```

This means:
- The x-component of **A** is **−y**
- The y-component of **A** is **x**
- The z-component of **A** is **0**

To find the magnetic field **B**, we take the **curl** of **A**:

```latex
\vec{B} = \nabla \times \vec{A}
```

Now we compute this using the curl formula in Cartesian coordinates:

```latex
\nabla \times \vec{A} = 
\left( \frac{\partial A_z}{\partial y} - \frac{\partial A_y}{\partial z},\ 
       \frac{\partial A_x}{\partial z} - \frac{\partial A_z}{\partial x},\ 
       \frac{\partial A_y}{\partial x} - \frac{\partial A_x}{\partial y} \right)
```

Let’s plug in each component of **A**:

- \( A_x = -y \)
- \( A_y = x \)
- \( A_z = 0 \)

Now evaluate each partial derivative:

1. **x-component of B**:
```latex
\frac{\partial A_z}{\partial y} = \frac{\partial 0}{\partial y} = 0 \\
\frac{\partial A_y}{\partial z} = \frac{\partial x}{\partial z} = 0 \\
\Rightarrow B_x = 0 - 0 = 0
```

2. **y-component of B**:
```latex
\frac{\partial A_x}{\partial z} = \frac{\partial (-y)}{\partial z} = 0 \\
\frac{\partial A_z}{\partial x} = \frac{\partial 0}{\partial x} = 0 \\
\Rightarrow B_y = 0 - 0 = 0
```

3. **z-component of B**:
```latex
\frac{\partial A_y}{\partial x} = \frac{\partial x}{\partial x} = 1 \\
\frac{\partial A_x}{\partial y} = \frac{\partial (-y)}{\partial y} = -1 \\
\Rightarrow B_z = 1 - (-1) = 2
```

Putting it all together:

```latex
\vec{B} = (0, 0, 2)
```

**Conclusion:**  
The magnetic field is a constant vector pointing in the z-direction with magnitude 2. So, even though **A** varies with x and y, the resulting **B** is a uniform field pointing straight out of the page.


### Task 3: Relating Electric Field to the Vector Potential (Step-by-Step)

Sometimes, instead of coming from charges, electric fields are created when the vector potential changes over time.

The mathematical relationship is:

```latex
\vec{E} = -\frac{\partial \vec{A}}{\partial t}
```

This means:
- The electric field **E** is the **negative rate of change** of the vector potential **A** over time.
- If **A** increases or decreases, **E** appears in the opposite direction.


Let’s say the vector potential depends on time like this:

```latex
\vec{A}(t) = (0, A_0 \cos(\omega t), 0)
```

Which means:
- There is no x-component or z-component of **A**.
- The y-component oscillates back and forth with cosine over time.

Now calculate **E** by taking the time derivative:

1. Take the partial derivative of **A** with respect to time:

```latex
\frac{\partial \vec{A}}{\partial t} = \left( 0, -A_0 \omega \sin(\omega t), 0 \right)
```

2. Apply the negative sign from the formula:

```latex
\vec{E}(t) = -\frac{\partial \vec{A}}{\partial t} = \left( 0, \omega A_0 \sin(\omega t), 0 \right)
```

So the electric field is:

```latex
\vec{E}(t) = (0, \omega A_0 \sin(\omega t), 0)
```

#### Interpretation:

- The electric field oscillates over time in the y-direction, just like **A**, but shifted to a sine wave instead of a cosine.
- If you were to plot both, you’d see **A** lagging behind **E** by a quarter cycle.
- This type of behavior is common in **electromagnetic waves**, where **A**, **E**, and **B** are all linked and oscillate together.

Try sketching both **A** and **E** on the same time axis to visualize how one creates the other!

---

## Questions

1. Why do scientists use the vector potential instead of always using electric and magnetic fields directly?
2. What does the curl of a vector tell us in physical terms?
3. If the vector potential was zero, what could you say about the magnetic field?
4. Can you think of a situation where calculating the vector potential is easier than finding **B** directly?

---

## Advice

Understanding the vector potential takes time, especially because it's not something we see directly in nature. But just like gravity can be described by a potential energy field, magnetism can be described by a vector potential. Stick with the diagrams — they help a lot! If you find yourself confused, go back to drawing the fields and ask yourself: what is twisting, and what is flowing? This sheet connects nicely with the sheet on [magnetic field lines from currents](#) and [electromagnetic waves as solutions to Maxwell's equations](#). Keep exploring, and remember: even the most advanced ideas in physics start with a picture and a question!

