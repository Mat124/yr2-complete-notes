# Basic Quantum Mechanics

## Atomic Electron Orbital Shapes

![atomic orbital shapes](images/atomic_orbital_shapes.png)

- electron orbital names:
  - s = sharp
  - p = principal
  - d = diffuse
  - f = fundamental/fine

## Madelung's Rule

Energy ordering is from lowest n+l to highest: if n+l is the same, fill orbital with smaller n.

![madelung rule](images/madelung_rule.png)

## Pauli Exclusion Principle

- n = principal quantum number (1, 2, 3, ...)
- l = orbital angular momentum (0, 1, 2, ...)
- m<sub>l</sub> = magnetic quantum number, z component of l, |m<sub>l</sub>| <= l
- m<sub>s</sub> = spin magnetic quantum number, 1/2 or -1/2
- pauli exclusion principle: no two electrons in a given system may have all 4 numbers the same

## Hund's rule

- For a given electron config, lowest energy term has the greatest spin multiplicity
- if two or more orbitals of equal energy are available, electrons occupy them first individually, then pair up as more are added

## Orbital Occupancy of first 10 elements H to Ne

![first 10 orbital occupancy](images/orbital_occupancy_first_10.png)

## Heisenberg's Uncertainty Principle

more precisely position is know, less precisely the momentum can be known at the quantum level and vice-versa.

![heisenberg uncertainty](images/heisenberg_uncertainty.png)

for electron trapped in a 1D (just width) infinite potential well from x=0 to x=a, the uncertainty in position Δx = a. From de Broglie, p<sub>x</sub>=h/λ = ħk or -ħk where k is wave vector 2π/λ and λ=a as fixed length. Δp<sub>x</sub>=2ħk as ranges from ħk to -ħk. Therefore:

![heisenberg well ucnertainty](images/heisenberg_uncertainty_in_1d_well.png) \
h should be ħ for greater accuracy

## Valence shells

Valence shell is the outermost occupied shell of an atom

## Wavefunction

square of the wavefunction is the electron probability distribution, wavefunction is a representation of the orbital

## bonding and antibonding orbitals

wavefunction of atoms close together, the orbitals interact. Can be bonding (additive) or antibonding (subtractive)

![bonding antibonding orbitals](images/bonding_antiboding_wavefunctions.png)

![bonding antibonding diagram](images/bonding_antibonding_diagram.png)

![bonding antibonding hydrogen diagram](images/bonding_antibonding_hydrogen_diagram.png)

## Energy Bands

Example: Lithium has 1 electron in 2s orbital, so N (assumed large, 10<sup>23</sup>) electrons in N 2s orbitals. As N atoms are brought together, N energy levels formed as pauli exclusion principle. Max spread of levels when atoms spaced at inter-atomic distance a. The N energy levels form an energy band with 2N states as 2 electrons can fit in each orbital. 2s band is therefore half full.

![energy banding lithium](images/energy_banding_lithium.png)

At absolute 0K, bands are full from lowest E<sub>B</sub> to fermi level E<sub>F</sub>. Energy needed to excite electron from fermi level to vacuum (escape) is work function Φ of metal.

![fermi level banding](images/fermi_level_banding.png)

## Fermi-Dirac Function, Fermi levels, Fermi function

f(E) defines probability that a state with energy E is occupied by an electron.

![fermi-dirac function](images/fermi-dirac_equation.png)

![fermi fucntion](images/fermi_function_diff_temps.png) \
as temp increases, greater probability at higher energies and lower probability at lower energies.

## Boltzmann statistics fermi distribution approximation

assume that fermi-dirac function is equal to \
![boltzmann approximation](images/boltzmann_fermi_dirac_approx.png)

## Semiconductors

- Some free electrons, but not a lot.
- Valence band - full at 0K, bonding orbital
- conduction band - empty at 0K, antibonding orbital
- bandgap between them with energy E<sub>g</sub>
- Electrons jump from valence band to conduction band when excited, with holes moving from conduction to valence band

![Si band formation](images/si_bonding_antibonding_bands.png)

![semiconductor bands](images/semiconductor_workings_valence_conduction_bands.png)\
At 0K, electrons can't move in the VB and there are none in CB so it is an insulator. \
Above 0K, there are some electrons in the CB so some space in the VB and electrons can move in VB, so no longer an insulator.

## Crystal Structures

### Face Centred Cubic FCC

Cubic cell, atom in each corner and in centre of each face. \
Atomic Packing Factor APF = 0.74

![fcc structure](images/FCC_structure.png)

### Body Centred Cubic BCC

Cubic cell, atom in each corner and one in centre. \
Atomic Packing Factor APF = 0.68

![bcc structure](images/bcc_structure.png)

### Hexagonal Close Packed HCP

Hexagonal layers, stacks of triangles. Often two laters of ABAB... but can be 4 of ABCDABCD... \
Can be shown as full hexagons or small 4 with 4 points. \
Atomic Packing Factor APF = 0.74

![hcp strucutre](images/HCP_structure.png)

### Diamond Unit Cell DUC

Similar to FCC, but with more atoms placed equidistant from atoms in a quarter of the cube. \
Elemental semiconductors Si, Ge have this structure. \
Atomic Packing Factor APF = 0.34

![duc structure](images/DUC_strucutre.png)

### Zinc Blende Cubic Crystal Structure

Same as Diamond Unit Cell but with 2 different types of atom, example is Zinc Sulphide. \
Many compound semiconductors have this: AlAs, GaAs, GaP, GaSb, InAs, InP, InSb, ZnS, ZnTe

![zinc sulphide structure](images/zinc_sulphide_structure.png)

### Bravais Lattice Summary

![bravais lattice summary](images/bravais_lattice_summary.png)

## Crystal Structure Geometry

Miller indices - all parallel vectors have the same indices, exact length directions shown in square brackets, equivalent directions shown in angular brackets.

Calculating Planes: \
![miller planes](images/miller_planes.png)

## Intrinsic Semiconductors vs Extrinsic Semiconductors

- intrinsic - almost perfect, few/no impurities
- extrinsic - significant impurities
  - donor - donates electrons, material becomes n-type with electrons as majority carrier
  - acceptor - accepts electrons (donates holes), material becomes p-type with holes as majority carrier

## Electrons and Holes

- electrons - can be treated as free moving in CB, has effective mass m<sub>e</sub>
- holes - can be treated as free moving in VB, has effective mass m<sub>h</sub>

## Density of States DOS

Density of States g(E) or DOS(E) is such that g(E)dE is the number of states (wave-functions) in the energy interval E to E+dE. The number of states per unit volume up to E' is: \
![states per unit volume](images/dos_states_per_unit.png)

## Electrons in Intrinsic Semiconductor, Concentration of Electrons in Covalence Band CB Intrinsic Semiconductor

Concentration of electrons in CB: \
![electrons in CB](images/electrons%20in%20CB.png) \
Subbing in boltzmann approximation of f(E): \
![electrons in CB with fermi](images/electrons_in_cb_with_fermi.png) \
Splitting into n and N<sub>c</sub>: \
![electrons in CB with Nc](images/electrons_in_CB_Nc_and_n.png) \
N<sub>c</sub> is the effective density of states at the CB edge

## Holes in Intrinsic Semiconductor, Concentration of Holes in Valence Band VB Intrinsic Semiconductor

probability of electron = f(e), so probability of hole = 1 - f(e) \
Concentration of holes in VB: \
![hole concentration vb](images/holes_concentration_vb.png) \
This can be reduced to p and N<sub>v</sub>: \
![hole concentration Nv and p](images/holes_concentration_Pc_p.png) \
![hole concentration Nv](images/hole_concentration_Nv.png) \
N<sub>v</sub> is the effective density of states at the VB edge

## Mass Action Law Intrinsic Carrier Concentration

States np = n<sub>i</sub><sup>2</sup> where n<sub>i</sub> is the intrinsic carrier concentration. ONLY APPLIES IN THERMAL EQUILIBRIUM AND IN THE DARK. \
![mass action law](images/mass_action_law.png) \
np is constant as holes in valence band = electrons in conduction band, and depends on material properties N<sub>c</sub>, N<sub>v</sub> and E<sub>g</sub>. \
Can multiply out N<sub>c</sub> and N<sub>v</sub> and others to get: \
![intrinsic concentration](images/intrinsic_concentration_no_ncnv.png)

![mass action slides](images/mass_action_slides.png)

## Intrinsic Carrier Concentration vs Temperature

As temp increases, intrinsic carrier concentration also increases: \
![intrinsic concentration vs temp](images/intrinsic_concentration_vs_temperature.png)

## Fermi energy in intrinsic semiconductors fermi level instrinsic

- ![fermi energy intrinsic](images/fermi_energy_intrinsic.png) \
- E<sub>Fi</sub> = fermi energy, where f(E) = 0.5
- E<sub>v</sub> = top edge of valence band
- E<sub>c</sub> = bottom edge of conduction band
- E<sub>g</sub> = E<sub>c</sub> - E<sub>v</sub>
- k = boltzmann constant
- T = temp in kelvins
- N<sub>c</sub> = effective density of states at CB edge
- N<sub>v</sub> = effective density of states at VB edge
- if N<sub>c</sub> = N<sub>v</sub>:
  - ![fermi energy nc=nv](images/fermi_energy_nc_is_nv.png)
  - fermi energy is midpoint of the energy gap
- as ![nc nv masses](images/nc_nv_to_masses.png) we can write:
  - ![feermi energy intrinsic masses](images/fermi_energy_intrinsic_masses.png)
- multiplying out N<sub>c</sub> and N<sub>v</sub> and others:
  - ![intrinsic concentration](images/intrinsic_concentration_no_ncnv.png)