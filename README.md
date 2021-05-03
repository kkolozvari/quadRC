# quadRC
3-D finite element model for planar RC elements

[K. Kolozvari](mailto:kkolozvari@fullerton.edu), CSU Fullerton<br/>
M.F. Gullu, Harran University<br/>
K. Orakcal, Bogazici University<br/>

quadRC element will be publicly available in fall 2021.

## Description

The quadRC element (Figure 1b) is a three-dimensional four-node element with 24 DOFs for nonlinear analysis of planar reinforced concrete (RC) elements. The element in-plane behavior is described with two translational and one rotational (drilling) DOFs defined at each node of the element (Figure 1c) and is governed with a four-node bilinear finite element formulation (Figure 1d). The four in-plane DOFs that represent the drilling rotations normal to the plane of the element are presently implemented as “dummy” DOFs and are assigned infinitesimal stiffness values; i.e., the drilling DOFs are ignored in the present model element formulation. Material behavior at each integration point is described with the Fixed-Strut-Angle-Model (FSAM; Figure 1e). Out-of-plane behavior of the proposed model is simulated with a four-node elastic thin-plate finite element formulation based on the Mindlin-Reissner plate theory corresponding to one translational and two rotational DOFs (Figure 1f-g) at each node.

![quadRC](https://user-images.githubusercontent.com/53920372/116842793-a1058300-ab92-11eb-94e9-2a76c2b4f7d9.PNG)
**Figure 1. Model formulation: a) Wall segment, b) 3D four-node quadRC element, c) element in-plane DOFs, d) in-plane parent element, and e) 2D constitutive model for reinforced concrete (FSAM), f) element out-of-plane DOFs, g) plate moments**

### quadRC Input
```markdown
element quadRC eleTag iNode jNode kNode lNode thick matTag <-thickMod tMod> <-Poisson Nu> <-Density Dens>
```

| parameter | description |
|----------|------------|
| eleTag | unique element tag|
| iNode jNode kNode lNode | tags of element nodes defined in counterclockwise direction|
| thick | element thicknesses|
| matTag | material tag of nDmaterial FSAM |
| tMod | thickness modifier for out-of-plane bending behavior (optional; default - 0.63, which is equivalent to 25% of uncracked stiffness) |
| Nu | Poisson ratio for out-of-plane bending (optional; default = 0.25) |
| Dens | Density (optional, default = 0.0)|

### Recorders

In preparation

### OpenSeesPy Documentation
   
In preparation
   
## Example

In preparation 

## References

K. Kolozvari, M. F. Gullu, K. Orakcal (2021, in print). "Finite Element Modeling of Reinforced Concrete Walls under Uni- and Multi-directional Loading using OpenSees", Bulletin of Earthquake Engineering.
