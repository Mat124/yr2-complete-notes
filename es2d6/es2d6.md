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

Materials considered intrinsic if n<sub>i</sub> >> doping concentration.

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

## Doping N-Type

Add impurities with larger amount of valence electrons than original material to produce "free electrons", e.g. adding Sb to Si crystal as Sb has 5 valence electrons and Si has 4. \
![doping si sb](images/doping_si_sb.png)

Si doped with As: \
![si as doping](images/si_doped_with_As.png)

## Doping P-Type

Add impurities with less valence electrons than original to add "holes". e.g. adding B to Si as B has 3 valence electrons and Si has 4. \
![doping si b](images/doping_si_b.png)

Si doped with B: \
![si doped with B](images/si_doped_with_B.png)

## Binding energy

Binding energy of donor carrier (swap Me for Mh for holes) in material (orbits around donor atom until this energy met):\
![si bidning energy](images/si_binding_energy.png)

## Majority Carrier and Majority Carrier Concentration in Doped Semiconductors

Electrons and Holes are carriers of charge. Whichever carrier is present in the largest number is the majority carrier: **Holes in p-type, electrons in n-type**. The other is the minority carrier.

![ntype ptype band diagrams](images/ntype_ptype_band_diagrams.png)

N<sub>D</sub> = electron donors, N<sub>A</sub> = electron acceptors
![majority carrier concentration](images/carrier_concentration_in_doped.png)

If |N<sub>D</sub> - N<sub>A</sub>| ~ n<sub>i</sub><sup>2</sup>, then: \
N-type: ![ntype low doping](images/n-type+low_doping.png) \
P-type: ![ptype low doping](images/ptype_low_doping.png)

## Majority carrier concentration in Doped Semiconductors Against Temperature 1/T

![doped semicond carrier conc vs temp](images/carrier_concentration_doped_vs_temp.png)

## Degenerate Semiconductors

If doping very high (10<sup>19</sup>cm<sup>-3</sup>+ in Si), can no longer use Boltzmann statistics and must use full Fermi-Dirac Equation as fermi level may lie within CB or VB. Therefore, np=n<sub>i</sub><sup>2</sup>, n=N<sub>d</sub> and p=N<sub>a</sub> are not valid.

## Compound Semiconductors III-V Semiconductors 3-5 Semiconductors

Have group III (3 electrons in valence) and group V (5 electrons in valence) in a unit cell bonded, most likely in zinc blende crystal structure. Acts as 'intrinsic'. Doped: \
N-type by replacing V atoms with VI atoms (as VI is more similar to V than III) \
P-type by replacing III atoms with II atoms (as II is more similar to III than V) \
Doping with IV is ambiguous as could replace V or III, unknown doping outcome.

## Typically Semiconductor Properties Si SiC Ge GaN GaAs InGaAs InAs InSb

![semicond properties](images/semiconductor_properties.png)

## Semiconductor uses with different band gaps

### Wide band gap uses E<sub>g</sub> > 2.5eV

typical semiconductors: SiC, GaN, InGaN \
electronic uses: high power/temp electronics as more stable: electric vehicles, grid power, radar, high voltage switching
optical (III-V) uses: white light and UV light sources: LEDs and lasers

### Intermediate band gap uses 2.5eV > E<sub>g</sub> > 0.6eV

Typical semiconductors: Si, Ge, GaAs, GaP, InP, InGaAs \
electronic uses: all modern electronics (transistors, diodes, etc)
optical (III-V) uses: visible/high IR LEDs, lasers, detectors and solar cells

### Low band gap uses 0.6eV > E<sub>g</sub>

Typical semiconductors: Sn (alpha), GaSb, InAs, InSb \
electronic uses: magnetic sensors, high frequency electronics
optical (III-V) uses: mid IR LEDs, lasers, detectors

## Electric Current Density J<sub>x</sub> and Drift Velocity v<sub>dx</sub> (classical)

![electirc current density](images/electric_current_Density.png) \
![drift velocity](images/drift_velocity.png) \
![combined](images/electric_current_and_Drift_velocity.png)

Using v=u+at for electrons and u=0 due to scattering: \
![vdx with v=u+at](images/vdx_with_vuat.png)

Mean free time (relaxation time) is time between collisions, so: \
![mean free time and vdx](images/mean_free_time_t_ti.png)

Drift mobility u<sub>d</sub> is a constant of proportionality, can be subbed into v<sub>dx</sub> and J<sub>x</sub>: \
![drift mobiliuty jx and vdx](images/drift_mobility_in_jx_vdx.png)

Electrons and holes have individual mobilities: \
![electron drift](images/electron_drift_mobility.png) \
![hole drift mobility](images/hole_drift_mobility.png)

visual of why Ex causes current to flow (it effectively causes the bands to bend, band bending):\
![band bending](images/band_bending_Ex.png)

conduction current or total current density J can be split into electron and holes: \
![current denisty vde vdh](images/current_density_vde_vdh.png) \
![cuirrent density coinductivity](images/current_density_with_conductivity.png)

This assumed: relaxation time independent of electric field, all electrons have same mass, avg velocity of any 1 electron = avg of all electron velocties. \
Reasonable assumption for metals/large semiconductors. Doesnt work for small devices with small number of carriers/short distances for electrons to travel, high electric fields so saturation velocity reached, high doping so mass not the same for all electron/hole concentrations.

## Drift mobility temperature dependance

![drift mobility temp](images/drift_mobility_temp_dependence.png)\
see lattice impurity scattering and lattice vibration scattering for why the below graph occurs: \
![drift mobility vs temp](images/temp_vs_drift_mobility.png)

## Thermal Velocity

![thermal velocity](images/thermal_velocity.png)

Typically thermal velocity >>> drift velocities in metals: semiconductors allow for drift velocities comparable to thermal velocities.

![thermal velcoity proportional ot t](images/thermal%20velocity%20proportional%20to%20T.png)

## Scattering Processes

### Matthiessen's Rule

Scaterring occurs due to thermal lattice vibrations, impurities and crystal grain boundaries (from impurities/imperfect growth). Matthiessen's Rule gives total scattering probability and total drift mobility. \
![mattheissens rule](images/mattheiessens_rule.png)

### Lattice Vibration Scattering (classical)

![mean free time lattice](images/mean_free_time_lattice_vibrations.png) \
S = cross-sectional area of the scatterer \
V<sub>th</sub> = thermal velocity of carrier \
N<sub>s</sub> = number of scatterers per unit volume (m<sup>-3</sup>) \
![scattering lattice](images/scattering_lattice.png) \
a = amplitude of the atomic vibrations about the equilibrium, a<sup>2</sup> is proportional to temp T \
S = pi*a<sup>2</sup>

![lattice drift mobility](images/lattice_drift_mobility.png)

### Lattice Impurity Scattering Impurities Scattering

![scattering impurities](images/scattering_ionized_impurities.png)
![scattering impirities 2](images/scattering_impurities.png)

## Recombination Processes

Free electron finds an incomplete bond, moves from CB to VB. At above 0K thermal excitation constantly moves electrons from VB to CB, and in equilibrium electrons must move from CB to VB at same rate. Excess energy from recombination lost as photon.\
![wave vectors energy](images/wave_vectors_energy.png) \
k = wavevector, 'direction' of wave. Momentum must be conserved, so when electron moved from CB to VB must keep the same k. \
![direct indirect bandgap](images/direct_bandgap_indirect_bandgap.png) \
Left: direct bandgap, electrons in base of CB have same k as holes in top of VB. \
Right: indirect bandgap, electrons in base of CB have different k to holes in top of VB.

summary (no details): \
![summary](images/recomb_process_summary.png)

### Radiative Recombination

Needs direct bandgap, electrons move direct from bottom of CB to top of VB and keep the same k.

### Shockley-Read-Hall Recombination SRH Recombination

Electrons moves (is captured by) from CB to a SRH recombination centre between the CB and VB, and then the SRH centre captures a hole from VB and electron moves to VB. Accommodates momentum mismatch by absorption/emission of phonons (lattice vibrations). SRH centres are impurities or crystal defects, so have different bandgaps to rest of material. \
![srh centre](images/srh_centre_recombination.png)

Trapping: Similar to SRH, trapping centre takes in electron from CB and holds it, then releases it back to CB when excited. \
![trapping centre](images/trapping_centre.png)

![srh recombination materials](images/SRH_recombination_materials.png)

### Augur recombination

Electron and hole have different k and recombine, energy from different k's is transferred to another electron which has an opposite change in k to the recombining electron. Energy is slowly lost by thermalisation. \
![augur recomb](images/augur_recomb.png)

## Minority Carrier Lifetime

Rate of recombination of excess carriers is dependent on density of carriers, giving exponential behaviour of minority carrier lifetime. \
![recomb summary](images/recomb_summary.png)

### Transient photoconductivity

G<sub>ph</sub> is the generation rate per unit volume caused by illumination. \
![transient photo](images/transient_photocond.png)

### Radiative recombination rate low level injection

![readiative recomb rate](images/radiateve_recomb_rate.png) \
In thermal equilibrium np = n<sub>i</sub><sup>2</sup>, so Re=Gth and net rate is 0.

For doped semiconductors (swap n and p to get p-type): \
![radiateive recomb rate](images/radiative_recomb_rate.png) \
minority carrier lifetime inversely proportional to doping concentration

### Shockley-Read-Hall recombination rate SRH recombination rate low level injection

![srh net rate](images/srh_net_recomb_rate.png) \
Et is SRH energy, Nt is number of SRH centres \
Rate maxed for Et=Ei, mid-gap energies are most effective, assume this is true: \
![srh ei=et rate](images/srh_rate_ei_is_et.png) \

For doped semiconductors (swap n and p to get p-type): \
![doped srh rate](images/doped_srh_rate.png) \
n<sub>i</sub> is removed from bottom as n<sub>i</sub> << p/n in doped materials \
minority carrier lifetime inversely proportional to SRH centre concentration

### Augur recomb rate low level injection

![augur rate](images/augur_recomb_rate.png) \

for doped semiconductors (swap n and p to get p-type): \
![augur doped rate](images/augur_doped_rate.png) \
minority carrier lifetime inversely proportional to doping concentration squared

## High level injection recombination rate for radiative, SRH, Augur

![high injection rates](images/high_injection_recomb_rates.png)

## Ideal Diodes

Formed from pn junction of differently doped materials. \
Ideal Diode under forward bias, see depletion layer and pn junction for why: \
![ideal diode bias](images/ideal_diode_forward_bias.png) \
Ideal Diode under reverse bias: \
![ideal diode revrse](images/ideal_diode_reverse_bias.png)

## Depletion Layer

With no external voltage, pn junctions will form a depletion layer where holes and electrons recombine as they thermally diffuse between the materials. \
![depletion layer](images/depletion_layer.png) \
This causes the depletion layer to become charged - excess positive ions on the n-type side as electrons are removed and excess negative ions on the p-type side as holes are removed. This causes a barrier potential to be formed until equilibrium is reached - stops more movement of electrons and holes when no external voltage. \
![depletion charge](images/depletion_layer_charge.png) \
This is barrier potential or built in voltage: \
![bi voltage](images/built_in_voltage.png)

Thickness (W or Wo) dependant on doping, depletion layer lies majority inside lower doped side of junction. \
Assuming symmetrical doping, depletion layer thickness under no external voltage: \
![depletion layer thicc](images/depletion_layer_thiccnes.png) \
Under external voltage (forward is positive): \
![layer thicc with voltage](images/depletion_thicc_voltageapplied.png)

Capacitance of depletion layer or depletion layer capacitance: \
![layer cap](images/capactiance_depletion_layer.png)

## PN junction band diagram

![pn junc band diagram](images/pn_junc_badn_diagram.png) \
As connected the fermi levels must the same, so bands bend to accomodate this.

## diffusion limited ideal diode under forward voltage bias

![ideal diode forward voltage](images/ideal_diode_forwardvoltage.png) \
Voltage mostly dropped across depletion layer as neutral regions have high carrier concentrations. Reduces the Vbi, so more carriers diffuse - more current. Amount of new carriers: \
![new carriers](images/new_carriers_in_neurtral_diodes.png) \
![excess carriers](images/excess_carrier_density_depletion.png) \
![excess carrier cont](images/excess_carrier_cont.png) \
Swap h for e and p for n to get p-type side excess electron density. Sum of Jhole + Jelec is constant, as current must be constant throughout the diode. \
![total current density](images/total_current_density_ideal_diode.png) \
for given diode at given temp, only change is due to voltage change. \
For larger V, so 1 << exp(eV/kt): \
![ideal diode large v](images/ideal_diode_diffusion_highV.png)

## diffusion limited ideal diode reverse bias

![reverse bias](images/reverse_bias_ideal_diode.png) \
If V is negative (reverse bias), then right side of equation tends to -1, and J tends to -Js.

## diffusion capacitance ideal diodes

When forward bias, minority carrriers are injected into neutral regions. They take some time to combine, giving extra diffusion capacitance. \
![diff cap](images/diffusion_cap.png) \
Under forward bias, diffusion capacitance is typically in the nF range and is much larger than depletion capacitance.

## Dynamic resistance or differential resistance

![dynamic resis](images/dynamic_resistance.png)

## non-ideal diodes or real diodes

### short diodes

length of p-type l<sub>p</sub> and n-type l<sub>n</sub> regions are shorter than the diffusion lengths of carriers Le and Lh. \
![short diode](images/short_diode_minority_diffusion.png) \
at distance from depletion region x'=0 the carrier conc is the same and must be 0 when x'=l<sub>p or n</sub>, so linear change as few carriers lost to recombination due to neutral region << diffusion length. \
Current density (swap p and n, h and e for p-region): \
![short current](images/short_diode_current_density.png)

## recombination in the depletion layer or depletion layer recombination

Some carriers recombine in the depletion layer and are replenished by external current. \
![depletion layer recomb](images/depletion_layer_recomb.png) \
![depletion layer recomb cont](images/depletion_layer_recomb_cont.png) \
More rigorous analysis (actual equation): \
![dep layer ecomb](images/dep_layer_recomb.png)

## generation in depletion layer - reverse bias

Reverse bias causes wider depletion layer. In addition, thermal generation of electron-hole pairs can occur in the depletion layer: \
![dep layer generation](images/depletion_layer_generation.png)

## characteristics of diodes: IV I-V characteristics

![iv diode](images/IV-diodes.png) \
![iv and temp current diode](images/temp_current_diode.png)

## diode summary

![diode summary](images/diode_summary.png)

## diode breakdown - avalanche breakdown

electric filed over depletion layer large enough that electron gain kinetic energy to break a bond, forming another electron-hole pair. \
![avalanceh mult](images/avalanceh_multiplier.png) \
breakdown voltage: \
![breakdown voltage avalanche](images/breakdown_voltage_avalancghe.png) \

## zener diode - zener breakdown

heavily doped pn junction - apply reverse bias and Ec on one side may be lower than Ev on other side. If gap between p and n materials is small enough, electrons then tunnel from one to the other: \
![zener diode current density](images/zener_diode_current_density.png)

## Schottky diodes

metal joined to semiconductor. electrons in semiconductor move to metal as there are higher energy VB states they can easily get to. electrons accumulate on metal-semiconductor edge, giving electron depletion region of width W containing positively charged donors and no free electrons. \
![schottky bands](images/schjottky_bands.png)

no external voltage: \
![schottky no voltage](images/schottky-no-voltage.png)

forward bias: \
![schottky dforwad bias](images/schottky-forward-bias.png)

reverse bias: \
![schottky reverse bias](images/schottky-reverse-bias.png)

used in high-frequency applications.

### ohmic contacts

if metal has smaller work function than semiconductor, no barrier is formed and no restriction to flow current. \
![ohmic contact](images/homic-contact.png)

## photodetectors or photodetection

photon with energy > Eg absorbed, so electron moves from VB to CB. high energy photons make electrons move to high levels of CB which lose energy through phonons until within 3kT/2 of band edge. \
alpha is the absorption coefficient. if photon energy = Eg, alpha is low as low amounts of electrons at VB edge and low amount of free states in CB. \
if photon energy > Eg, alpha is higher as more electrons that can be moved to CB and more states in CB that electron could be moved to. \
![absoption coeeffficient](images/absoption%20coefficient.png)

## optical absorption beer-lambert law

![beer lambert](images/beer-lambert.png)

## photoconductor

single material, like resistor. incident light causes generation (photogeneration): \
![photo conductor](images/photoconductor.png) \
![phopto cond cont](images/photocond-cont.png)

## photodiodes