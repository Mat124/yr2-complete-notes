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

G<sub>ph</sub> is the generation rate per unit volume caused by illumination (photogeneration). \
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

used in high-frequency applications. can be used as photodidoes under reverse bias and even respond if photon energy less thgan bandgap by jumping from edge of metal VB to semiconductor CB.

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

Illuminated so photons go through depletion layer and neutral regions. Largest current from photon absorbed in depletion layer as carriers moved by field, if absorbed in neutral then reliance on diffusion. Reverse biased pn junction to give wider depletion region. \
![phtodiode diagram](images/photodiode-diagram.png) \

## pin photodiodes or p i n photodiode or p-i-n photodiodes or pnn or p-n-n

increased deepletion region width by having lightly doped/intrinsic region between p and n regions. \
![pin photodiode](images/pin-photodiode.png)

## signal to noise ratio or responsivity and detectivity

![signal noise ratio](images/signal-nmoise-ratio.png)

## solar cells or photovoltaics

similar to photodiode, but no applied voltage and changed to most efficiently produce voltage/current: \
![solar cell](images/soalr-cell.png)
very thin n region so more absorption in depletion/p region. open circuit voltage develops between terminals as electron hole pairs are formed and drift/pushed to respective sides. \
terminals shorted: Isc flows. useful volume of solar cell: \
![solar cell vol](images/useful-volume-solar-cells.png)

electrons generated by high energy photons (high alpha) in the n-region are often lost to recombination due to high doping - significant efficiency decrease. long wavelengths also can't be absorbed and low evergy photons < Eg are lost as heat as cant be absorbed - can be 25% of energy in Si. reflection loses 10-20% of energy, but surface texturing/antireflective coating decreases reflection.

![solar cell op](images/solar-cell-op.png) \
![solar cell op2](images/solar-cell-op2.png) \
![solar cell eff](images/solar-cell-eff.png)

### fill factor

![fill factor](images/fill-factor.png)

### tandem cells multi-junction cells multiple junction cells

grow multiple np junctions with tunnel junctions between them. np juncitons have different Eg so more photons absorbed in good areas. very expensive, usually 10s of cm<sup>2</sup>: \
![tandem,, cells](images/tandem-cells.png)

## solar cells summary

![solar cells summary](images/soalr-cell-summary.png)

## LED light emitting diode

forward biased junction - injected majority carriers allowed to pass into opposite region, becoming minority carriers and so recombine rapidly. recombination releases photons equal or greater in energy to Eg of p-region.

## double heterostructure LED

two junctions with different band gaps - typical stack is np1p2. when no voltage, electrons stay in n CB and there are no holes in VB - no recombination. when forward bias, electrons move from n to p1 (which is short) and can then recombine with holes in VB. \
![led struc](images/LED-struc.png)
n has larger Eg than photons released, so not reabsorbed.

## single quantum well diode SQW diode

Thicnkess (d) of central active region reduced to get better recombination rates until quantised energy levels formed in z direction. \
![sqw](images/sqw.png) \
1D potential well in z direction, free to move in xy directions. En is the electron energy at level n: \
![sqw energy](images/sqw_energy_leveel.png)
forms 2D electron gas (2DEG) in well. density of states is constant at E1, E2, etc so large number of states are available at lowest energy. can be swamped by carrier - use multiple quantum wells, succession of SQW in series.

## LED materials and larger structure

III-V alloys: covers lower end of spectrum to green \
III-Nitrides cover green+ and UV \
![led materials](images/led-materials.png) \
use dome to prevent TIR and textured surface to prevent TIR.

## LED light emission or LED spectrum of light output or electron energy distribution

![elec energy dist](images/electron-energy-dist.png) \
![light emission spectrum](images/light-emission-spectrum.png) \
![light emsssion temp dependence](images/light-emssion-temp-dependence.png) \

## Diode lasers

particle in upper state reacts with photon matching energy seperation of levels, the particle decays and releases another photon in the same phase and frequency as incident photon - stimulated emission. \
requires population inversion - most electrons are excited, done using another optical source or by carrier injection - extreme doping so that fermi level is inside conduction band. \
This is a degenerate material, cant use boltzmann statistics: \
![degen semi](images/degernate-semicond.png) \
feedback needed to make laser - add mirrors at each end.

## laser modes

standing waves formed in lasers: \
![laser](images/laser_standing_waves.png) \
![laser](images/laser_standing_waves2.png)

## double heterostructure laser diode

![double het laser](images/double-het-laser.png)

## seperate confinement heterostrucutres SCHs diode

![schs](images/schs.png)

## vertical cavity surface emitting laser VCSEL

![vcsel](images/vcsel.png)

## diode vs laser power

![diode v laser pwoer](images/dioevlaserpwoer.png)

## Hall Effect

![hall effect](images/hall-effect.png) \
hall field E<sub>H</sub>: \
![hall field](images/hall-field.png) \
hall field diagram: \
![hall filed diagram](images/hall-field-diagram.png) \
hall coefficient R<sub>H</sub>: \
![hall coeff](images/hall-coefficiebnt.png)
hall coefficient using drift mobility: \
![hall coeff semi](images/hall-coefficient-semiconductors.png) \
hall coeff with scattering effect: \
![hall effect with scattering](images/hall%20-effect-with-scattering.png)

used to measure magnetic fields, effective use in rotating systems and contactless sensors. Useful in vehicles, phones, current sensors, etc.

## Wavefunction, Schrodinger's equation, wave particle duality principle

Describes dynamic behaviour of quantum system. \
![schrodinger](images/schrodinger-equation.png) \
![schrodigner 2](images/schrdinger2.png) \

can become time independent: \
![no time schrodinger](images/timeindependent-schrodinger.png)

## interpretation of wave function: electron momentum, wavenumber, de broglie wavelength

![wavefunction interpretation](images/wavefucntion_interpretation.png)

## electron energy and electron kinetic energy and group velocity - slope of E(k)

![electron ke](images/electron-ke.png) \
relating electron kinetic energy and velocity: \
![electron ke and v](images/velocity-and-energy.png)

## bloch theorem

periodic solids give periodic electron potentials: \
![bloch](images/bloch.png)
wavefunction contains unit cell part and planwave part - subbing bloch funciton in for unit cell function: \
![blkoch wave](images/bloch%20wave.png)

## Kronig Penney Model

![kronigpenney](images/kronig-penney.png) \
solving for wave function: \
![solveing kronig](images/solving-kronig-penney.png) \
boundary conditions for kronig-penney: \
![boundary](images/kronig-penney-boundary-cond.png) \
solving the boundary conditions to find the brillouin zone, values of k before which the periodicity starts: \
![kronig boundayr](images/kronig-solving-boundaries.png) \
plotting this for 1 brillouin zone and then limiting it to values between -1 and 1 gives allowed energy values, forming the bandgap when unfolded to more brillouin zones: \
![krong](images/bandgap-kronig.png)

## Effective mass of electon and effective mass of holes

![effective mass](images/effective-mass.png) \
effective masses affect band structure and band gaps. Also effects energy and velocity for a given wavevector: \
![kronig diff masses](images/mass-wavevector-v-velocity.png) \
Effective masses change depending on direction and material

## typical semiconductor effective masses

![semidonc masses](images/typical-semicond-masses.png) \
![semidonc](images/typical-semicond-bandfeatures.png)

## basic band theory summary: band gaps, periodicity, effective mass

![band theory summary](images/band-theory-summary.png)

## First brillouin zone: all allowed k-space fits in first brilluoin zone

![fist](images/first-brillouin-zone.png)

## Si 3D specifics, Si brillouin zone, Si first brillouin zone

![si](images/3d-si.png)

## Density of states for k-space, k-space DOS, DOS of k-space, 3D DOS, g(E)

![dos kspace](images/dos-kspace.png) \
3D DOS: \
![dos 3d](images/dos-3d.png) \
![3d dos no k](images/3d-dos-nok.png) \
2D DOS: \
![2d dos](images/2d-dos.png) \
1d DOS: \
![1d dos](images/1d-dos.png)

## converting ellipsoid mass to sphere, Mdos, Mdos-sph

![conv ellip to sph](images/converting-ellipsoid-mass-to-sphere.png) \
![dos ltt](images/dos-ltt.png)

## conductivity effective mass Mcond

![cond effective amss](images/cond-effective-mass.png)

## effective density of states, carrier concentration calculation alternatives

![carrier conc alt](images/carrier-conc-alternative.png)

## Drift and Diffusion

![drift diffusion](images/drift-diffusiobn.png) \
![total](images/total-diff-drift.png)

## Fick's Law

![fick](images/fick.png)

## Drift current

![drift current](images/drift-cuirrent.png) \
At low Efield: \
![drift curr low mob](images/drift-curr-low-mob.png)

## Mobility or drift mobility

![drift mob](images/drift-mob.png)

## Resistivity and Conductivity

![resistivity-conductobt](images/resistivity-conductivity.png)

## Einstein Relations, Einstein's relation

relates diffusion coefficient to mobility and dimensions: \
![einstein](images/einstein-relations.png) \
![einsetin](images/einstein-relations-cont.png)

## Recombination - Generation Centres (SRH centres)

![generations](images/gr-centres.png) \
use time constants and get more general result: \
![gr general stats](images/gr-general-stats.png)

## Continuity equations

![cont equations](images/cont-equations.png)

## minority carrier diffusion equations

![minority](images/minority-carrier-diff.png) \
![minortiy](images/minority-carrier-diff-cont.png)

## carrier action summary - drift, diffusion, mobility, einstein's relation, continuity, minority carrier diffusion

![carrier acc sum](images/carrier-action-sum.png)

## boltzmann transport formulation, BTE

The function f(x, v, t) describes the positions, momentum/velocity of particles at time t, i.e. how many electrons at time t are located at position x and have velocity v. Current can then be computed from: \
![boltzmann](images/boltzmann-current.png) \
![b](images/boltzmann-transport.png)

## boltzmann transport with scattering, BTE with scattering

![scattering](images/BTE-with-scattering.png) \
drift and diffusion with BTE: \
![drift diff](images/drift-diffusion-bte.png)

## drift current with BTE and displaced distribution

![drfit bte](images/drift-bte.png) \
displaced distribution: \
![dr](images/drift-bte-cont.png) \
finding flux (sum of all k-states times velocty of each state): \
![b](images/bte-flux.png) \
finding current from flux, then moving from k-space to energy-space: \
![b](images/bte-curr.png)
transport distribution function and reduced drift current from BTE: \
![btetdf](images/bte-tdf.png) \
due to df/dE, only carriers near E<sub>F</sub> contribute when using BTE

## diffusion current with BTE

start from full BTE and find flux: \
![diff](images/diffusion-curr-bte.png) \
diffusion current from flux and diffusion coefficient: \
![diff flux](images/diff-curr-flux.png) \

## Scattering rates, scattering times, relaxation rates, relaxation times

elastic, inelastic, isotropic, anisotropic: \
![scatter types](images/scattering-types.png)

## phonon scattering

phonons are lattice vibrations, move atoms in non-uniform way to strain bonds and change bandgap: \
![phons](images/acoustic-opticcal-phonons.png)

## ionized impurity scattering and screening

Brooks-Herring equation: \
![im](images/impurity-scatter.png) \
strength of screening defined by screening length L<sub>D</sub> - smaller it is, more strongly impurity is shielded and lower scattering effect.

## boundary scattering

![boundary scattering](images/bound-scatter.png)

## surface roughness scattering rate SRS

![srs](images/srs-rate.png)

## alloy scattering

occurs in compounds due to different potential variations in band: \
![alloy](images/alloy-scatter.png)

## scattering rates summary

![scater](images/scattering-rate-summary.png)

## Momentum relaxation rate

![mom](images/momentum-relax.png)

## thermoelectrics

![t](images/thermo.png) \
current from combined voltage and temperature: \
![t](images/thermo-curr.png) \
change in fermi by change in temperature: \
![diff temp](images/diff-fermi-t.png)
simplified current from voltage and temp difference with flux: \
![flux](images/thermo-curr-flux.png) \
seebeck voltage Voc and seebeck coefficient S: \
![see](images/seebeck.png) \
![see](images/seebeckcoeff.png) \
power factor, S<sup>2</sup>G: \
![power](images/power-factor.png) \
ZT figure of merit: \
![zt](images/zt.png) \
calculating ZT figure of merit: \
![calczt](images/calc-zt.png)
summary of thermoelectrics, thermoelectrics summary, k=ke+kl: \
![thermo-sum](images/thermo-sum.png)

conductivity and seebeck relation: \
![cond](images/conductivity-seebeck.png)

## MOS capacitors

MOS capacitor structure: \
![moscap](images/mos-cap.png) \
MOS off, on: \
![mos off](images/mos-off.png) \
![mos on](images/mos-on.png) \
MOS bands with no bias: \
![mos bands no bias](images/mos-bands-nobias.png) \
MOS bands with bias, surface potential, distance from instrinsic to fermi level, MOS states p-type: \
![mos be](images/mos-bending.png) \
![mos](images/mos-states.png) \
MOS charge profiles: \
![mos](images/mos-charge-profilees.png) \
MOS states n-type: \
![mos](images/mos-states-n.png) \
capacitance of MOS, MOS capactiance: \
![mops](images/mos-capacitance.png) \

MOS CV characterstics at accumulation: \
![mos acc](images/mos-acc.png) \
MOS CV characteristics at depletion: \
![mos dep](images/mos-dep.png) \
MOS CV characteristics at inversion: \
![mosinv](images/mos-inv.png) \
MOS CV summary: \
![mos](images/mos-cv-sum.png)

MOS voltage drop and MOS surface potential: \
![mos](images/MOS-surface.png) \
MOS quantum capacitance: \
![cap](images/quantum-capacitance.png)

## semiconductor growth techniques

bulk growth: \
![bulk growth](images/bulk-growth.png) \
epitaxial growth: \
![epit](images/epit-grwoth.png)
summary: \
![sum](images/growth-sum.png)

## defects in crystals

### vacancies defects, vacancy defect

Site expected to have an atom doesnt: \
![vacan](images/vanacies.png)

### Edge dislocations

![edge-dsil](images/edge-disl.png)

### Screw dislocations

![s](images/screw-dislocation.png)

### misfit dislocation and threading dislocation

![mis](images/misfit.png) \
creates lines of electrically active defecets, e.g. dopants or SRH G-R centres. Can be grown out using intermediate buffer layers to reduce strain

### surface defects

![sur](images/surface.png)

## semiconductor fabrication techniques, semiconductor device fabrication

dont have time, read the slides

## optical and xray techniques

dont have time, read the slides, small summary at **scanning techniques summary**

## electron microscopy, electron microscopes

dont have time, read the slides, small summary at **scanning techniques summary**

## STM, scanning probe, SIMS, 

dont have time, read thee slides, small summary at **scanning techniques summary**

## scanning techniques summary

![sum](images/scanning-sum.png)

## bipolar transistor design and characteristics, BJTs

basic design: \
![bjt](images/bjt_basic.png) \
bjt transport (pnp): \
![bjt](images/bjt-pnp-trans.png) \
bjt emitter current pnp: \
![ie bjt](images/ie-bjt.png) \
emitter injection efficiency and base transport factor: \
![injec](images/emitter-injection.png) \
common base current gain and current transfer ratio: \
![c](images/coimmon-base-curr-gain.png) \
base current: \
![based](images/base-curr.png) \
beta, ratio of collector to base current: \
![beta](images/beta.png)

## BJT transistor amplifier, pnp amplifier

voltage amplification, input resistance, output signal: \
![pnp amp](images/pnp-amp.png) \
full small signal input resistance: \
![small](images/small-sig-input-res.png) \
full voltage amplification: \
![samll](images/small-sig-amp.png) \
transconductance or mutual conductance gm: \
![gm](images/gm.png) \
heterostructure BJTs, HBTs: \
![hbt](images/hbt.png)

## JFETs, junction FET, junction field effect transistors

n channel JFETS structure: \
![n](images/jfet-nchan.png) \
n-channel jfet workings Vgs=0: \
![vgs0](images/jfet-vgs-0.png) \
reverse bias Vgs, if Vgs > Vp the channel is totally depleted and transistor is off except for small leakage from thermal: \
![reverse](images/reverse-bias-jfet.png) \
JFET output characteristics: Ids vs Vds, Ids vs Vgs: \
![ids](images/idsvds.png) \
![idsvgs](images/idsvgs.png) \
JFET as common source amp, transconductance gm and small signal transconductance: \
![jfet](images/jfetgm.png) \
jfet voltage gain common source amp: \
![jfetav](images/jfetav.png) \

## MESFET and MODFET

### MESFET MEtal Semiconductor FET

similar to jfet in operation: \
![mesfet](images/mesfet.png) \
mesfet equations, mesfet transconductance, mesfet current: \
![mesfet](images/mesfet-equations.png) \
mesfet critical field: \
![mesfet-crit-field](images/mesfet-crit-field.png)

### MODFET MOdulation Doped FET

used in highfrequency applications, solves problem of low mobility from high doping: \
![modet](images/modet.png) \
modfet equations, modefet characteristics: \
![modfet_eq](images/modfet_eq.png)

## enchancement mode MOSFET metaloxide semiconductor FET

enhancement mosfet structure, enchancement mode means normally off: \
![mosfet](images/mosfet-enchance-struc.png) \
mosfet Id vs Vds and Vgs: \
![moscurve](images/msoefet-curve.png) \
mosfet saturation region and transconductance: \
![mos](images/mosfetgm.png)
semi-empirical for full output - bridge linear and saturation: \
![mosfet](images/mosfet-semi.png)

## depletion mode MOSFET metaloxide semiconductor FET

depletion mosfet structure: \
![dep](images/dep-mosfet.png) \
depletion mosfet d-mode e-mode states: \
![d](images/dep-mos-modes.png) \
CMOS, complementary MOS, inverter, nMOS: \
![cmo](images/cmon.png) \
CMOS equations, figures of merit, sub-threshold swing: \
![cmos](images/cmos-eq.png) \
drain induced barrier lowering DIBL: \
![d](images/dibl.png) \
scaling issues: \
![c](images/scaling.png)

## subband quanitzation and low-dimensial channels

