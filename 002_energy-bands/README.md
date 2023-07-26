Author: **Ang Chen** | Email: chenang@outlook.com | Date: 07-30-2023 | Online monthly meeting @BIT

# Contents
- [Contents](#contents)
- [Energy bands](#energy-bands)
  - [Hydrogen atom](#hydrogen-atom)
  - [Periodic potential](#periodic-potential)
    - [Nyquist–Shannon sampling theorem](#nyquist–shannon-sampling-theorem)
    - [Brillouin Zone](#brillouin-zone)
  - [Silicon](#silicon)
  - [Graphene](#graphene)
- [References](#references)

# Energy bands 

Energy bands of a solid describe the range of energy levels that electrons may have within it, as well as the ranges of energy that they may not have (called band gaps or forbidden bands).
To derive those bands and band gaps, we need solve the Shr&ouml;dinger equation:

$$\tag{1}
i\hbar\frac{\partial}{\partial t}\Psi(\textbf{r}, t) =
-\frac{\hbar}{2m} \nabla^2 \Psi(\textbf{r}, t) + V(\textbf{r}, t)\Psi(\textbf{r}, t),
$$

where $\Psi(\textbf{r}, t)$ is the wave function of the electron, $V(\textbf{r}, t)$ is the potential energy of the electron, and $m$ is the mass of the electron.

For energy bands calculations, we only consider the case that the potential $V$ is *independent of $t$*. Then with the separation of variables $\Psi(\textbf{r}, t) = \psi(\textbf{r})f(t)$ and some algebra, we can get $\Psi(\textbf{r}, t) = \psi(\textbf{r})e^{-iEt/\hbar}$ with $E$ the state energy and the time-independent Shr&ouml;dinger equation:

$$\tag{2}
-\frac{\hbar}{2m} \nabla^2\psi(\textbf{r}) + V(\textbf{r})\psi(\textbf{r}) = E \psi(\textbf{r}).
$$

We can go no further with it until the potential $V(\textbf{r})$ is specified. Next consider the following three cases:

- Hydrogen atom: solved in an exact closed form, with Coulomb potential $V(\textbf{r}) = -\frac{e^2}{4\pi\epsilon_0}\frac{1}{r}$.
- Silicon: the most important semiconductor, with 3D periodic potential $V(\textbf{r}) = V(\textbf{r}+\textbf{R})$.
- Graphene: the most important 2D material, with 2D periodic potential $V\left(\textbf{r}_\parallel\right) = V\left(\textbf{r}_\parallel+\textbf{R}_\parallel\right)$.

## Hydrogen atom

For an hydrogen atom, the potential is $V(\textbf{r}) = -\frac{e^2}{4\pi\epsilon_0}\frac{1}{r}$, which is a function only of $r$. In that case, it's natural to adopt spherical coordinates $(r, \theta, \phi)$, and the Laplacian operator takes the form:

$$\tag{3}
\nabla^2 = \frac{1}{r^2}\frac{\partial}{\partial r}\left(r^2\frac{\partial}{\partial r}\right) + \frac{1}{r^2\sin\theta}\frac{\partial}{\partial \theta}\left(\sin\theta\frac{\partial}{\partial \theta}\right) + \frac{1}{r^2\sin^2\theta}\frac{\partial^2}{\partial \phi^2}.
$$

And we can separate the variables $\psi(r, \theta, \phi) = R(r)Y(\theta, \phi)$, resulting in two equations:

$$
\tag{4a} \frac{1}{R}\frac{d}{dr}\left(r^2\frac{dR}{dr}\right) + \frac{2mr^2}{\hbar^2}\left[\frac{e^2}{4\pi\epsilon_0}\frac{1}{r} + E\right] = l(l+1),
$$
and
$$
\tag{4b} \frac{1}{Y}\left[\frac{1}{\sin\theta}\frac{\partial}{\partial \theta}\left(\sin\theta\frac{\partial Y}{\partial \theta}\right) + \frac{1}{\sin^2\theta}\frac{\partial^2 Y}{\partial \phi^2}\right] = -l(l+1).
$$


## Periodic potential

![Physics and Coding Synergy: Here we use a picture of fractal to imply such ethereal synergy.](../figs/Brillouin_Zone.svg "physics and coding synergy")

### Nyquist–Shannon sampling theorem

Here are two expressions of the Nyquist-Shannon sampling theorem to enhance everyone's understanding of the theorem:

**Theorem** — *If a function $x(t)$ contains no frequencies higher than $B$ hertz, then it can be completely determined from its ordinates at a sequence of points spaced less than $1/(2B)$ seconds apart.* 

or 

**Theorem** — *If a system uniformly samples an analog signal at a rate that exceeds the signal’s highest frequency by at least a factor of two, the original analog signal can be perfectly recovered from the discrete values produced by sampling.*


### Brillouin Zone

## Silicon

## Graphene


# References

1. https://www.wikipedia.org
2. David J. Griffiths. *Introduction to Quantum Mechnics*. Prentice Hall, NJ, 1995.
