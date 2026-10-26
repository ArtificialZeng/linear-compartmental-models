# Linear compartmental model utilities

Python utilities for constructing linear compartmental models and their
input-output coefficient maps, with configurable input, output and leak
locations. This repository is linked from the [2025 Huneke–Keen REU
report](https://artsci.tamu.edu/mathematics/_files/_docs/reu/results/2025/huneke-keen-report.pdf).

The original programs are:

- [linear_compartmental_models.py](linear_compartmental_models.py): an
  interactive builder with catenary, directed-cycle and mammillary templates,
  and manual directed-edge entry for other graphs. It displays the state-space
  matrix, input-output equations, coefficient map and Jacobian information.
- [linear_compartmental_model_data_gather_template.py](linear_compartmental_model_data_gather_template.py):
  an editable batch template that exports model configurations, matrices,
  coefficient maps, and SIAN/Julia equations to an Excel workbook.

## Optional exact verification notes

Self-contained additions use the same state-space and coefficient-map
conventions and run independently of the interactive programs:

- [Two-leak directed-cycle fibers](verification/cycle-global-fibers/README.md):
  explicit inverse branches, generic complex degree `p! (n-p)!`, and an exact
  root-interval criterion counting strictly positive parameter vectors.
- [Arbitrary-leak retained-root tree sensors](verification/tree-sensor-linkages/README.md):
  the maximum number q of vertex-disjoint observation-to-leak paths gives
  generic rank `2n-2+q`, ambiguity dimension `L-q`, and the complete local
  placement criterion `q=L`. This extends the two-leak corollary below.
- [Two-leak bidirected-tree sensors](verification/tree-two-leak-sensors/README.md):
  a criterion for one additional calibrated output to restore generic local
  identifiability while retaining the root input and output. The two relevant
  tree paths must share an edge.

Each directory contains its assumptions, sources, proof, two independently
implemented checkers and exact computational receipts. Its README gives
commands to run from that directory. The checkers print new receipts by default
and leave the archived evidence available for comparison.

The all-size claims depend on the written arguments and their cited
dependencies; finite computations support those arguments. The mathematical
scope received separate AI checks. External human confirmation and priority
remain pending. The tree result concerns generic local identifiability, and
the cycle result distinguishes complex degree from positive fiber counts.

The newly contributed verification material is MIT licensed under the license
included in each verification directory.
