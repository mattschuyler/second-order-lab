# Second-Order Lab

Interactive teaching tool for ENEB 302 (Analog Circuits), second-order transients.
A single self-contained `index.html`. Open it in a browser, no build step.

Live copy: https://claude.ai/artifact/PTM7Q55DfW74XcntHRGmai

## Tabs

- **Circuit explorer**: the six circuits from the lecture slides (series RLC natural
  response, parallel RLC step, the slide-28 initial-condition example, two-capacitor,
  two-inductor, sinusoidal source). Sliders for every R, L, C and source value.
  Shows the time response (complete, forced and natural parts, envelope, initial slope),
  the roots in the s-plane with a root locus, the Bode plot of H(jω), and a live
  worked solution that follows the slide algorithm step by step.
- **Poles & damping**: drag a pole in the s-plane and see the step response, overshoot,
  rise time and settling time change.
- **Where the energy goes**: series RLC energy split between C, L and R, with an
  animated mass-spring-damper analogy.
- **Damping quiz**: random series and parallel RLC circuits; pick the damping case and
  see the working.

## How it solves

Each circuit is written as a 2-state system `x' = A x + b u`, `y = c·x`. The solver
(`solve2`) finds the characteristic equation, classifies the damping case, computes
the particular solution from H(0) or H(jω), and fits A and B to `y(0+)` and `y'(0+)`,
the same way the slides do. All preset answers match the worked examples in the slides.

## Run locally

```
python -m http.server 8765 --directory .
```
