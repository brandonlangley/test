<a id="topofdoc">&nbsp;</a>

### Table Of Contents
- [root](#root_anchor)
    - [arc](#arc)
        - [geometry](#arcgeometry)
            - [materials](#arcgeometrymaterials)
            - [blends](#arcgeometryblends)
            - [surfaces](#arcgeometrysurfaces)
            - [reactor](#arcgeometryreactor)
        - [calculations](#arccalculations)
            - [mcc3](#arccalculationsmcc3)
            - [dif3d](#arccalculationsdif3d)
    - [lumped_element_external_list](#lumped_element_external_list)
        - [afrac](#lumped_element_external_listafrac)
- [Referenced Choice Lists](#referenced_choice_lists)

---

### <a id="root_anchor">&nbsp;</a>[/](#root_anchor)
Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
[arc](#arc)|SubObject|0 or 1|||Input definition for ARC codes
[lumped_element_external_list](#lumped_element_external_list)|SubObject|0 or 1|||Description of a list of isotopes in a new lumped element

---

### <a id="arc">&nbsp;</a>[/](#root_anchor)[arc](#arc)
#### Input definition for ARC codes

##### How Many: 0 or 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
[geometry](#arcgeometry)|SubObject|1|||[required] Description of the core model
[calculations](#arccalculations)|SubObject|0 or 1|||Description of the list of calculations

---

### <a id="arcgeometry">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)
#### [required] Description of the core model

##### How Many: 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
[materials](#arcgeometrymaterials)|SubObject|1|||[required] List of materials
[blends](#arcgeometryblends)|SubObject|0 or 1|||List of mixtures of materials
[surfaces](#arcgeometrysurfaces)|SubObject|1|||[required] List of surfaces used for geometry description
[reactor](#arcgeometryreactor)|SubObject|0 or 1|||[required] Description of the core with lattice of assemblies

---

### <a id="arcgeometrymaterials">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[materials](#arcgeometrymaterials)
#### [required] List of materials

##### How Many: 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
[material](#arcgeometrymaterialsmaterial)|SubObject|1 or more|||[required] Material definition

---

### <a id="arcgeometrymaterialsmaterial">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[materials](#arcgeometrymaterials)/[material](#arcgeometrymaterialsmaterial)
#### [required] Material definition

##### How Many: 1 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arcgeometrymaterialsmaterialid">&nbsp;</a>|Tag|1|String||
wdensity<a id="arcgeometrymaterialsmaterialwdensity">&nbsp;</a>|KeyedValue|0 or 1|Real|__Range__<br>[0.0,+INF)|Weight density of material [g/cm3]
adensity<a id="arcgeometrymaterialsmaterialadensity">&nbsp;</a>|KeyedValue|0 or 1|Real|__Range__<br>[0.0,+INF)|Atom density of material [at/barn-cm]
temp<a id="arcgeometrymaterialsmaterialtemp">&nbsp;</a>|KeyedValue|1|Real|__Range__<br>[0.0,+INF)|[required] Temperature [Kelvin]
[wfracs](#arcgeometrymaterialsmaterialwfracs)|SubObject|0 or 1|||Isotopic composition defined as weight fractions
[adens](#arcgeometrymaterialsmaterialadens)|SubObject|0 or 1|||Isotopic composition defined as atom densities
[afracs](#arcgeometrymaterialsmaterialafracs)|SubObject|0 or 1|||Isotopic composition defined as atom fractions
[wdens](#arcgeometrymaterialsmaterialwdens)|SubObject|0 or 1|||Isotopic composition defined as weight densities
[aform](#arcgeometrymaterialsmaterialaform)|SubObject|0 or more|||Isotopic composition defined as atom formulas
[lumped_element_aden](#arcgeometrymaterialsmateriallumped_element_aden)|TaggedValue|0 or more|||Atom density of lumped element specified in calculations/mcc3

---

### <a id="arcgeometrymaterialsmaterialwfracs">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[materials](#arcgeometrymaterials)/[material](#arcgeometrymaterialsmaterial)/[wfracs](#arcgeometrymaterialsmaterialwfracs)
#### Isotopic composition defined as weight fractions

##### How Many: 0 or 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
[wfrac](#arcgeometrymaterialsmaterialwfracswfrac)|TaggedValue|1 or more|||

---

### <a id="arcgeometrymaterialsmaterialwfracswfrac">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[materials](#arcgeometrymaterials)/[material](#arcgeometrymaterialsmaterial)/[wfracs](#arcgeometrymaterialsmaterialwfracs)/[wfrac](#arcgeometrymaterialsmaterialwfracswfrac)
##### How Many: 1 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arcgeometrymaterialsmaterialwfracswfracid">&nbsp;</a>|Tag|1|String|__Choices__<br>REF:[CompNames](#ref-compnames)<br>REF:[NuclideIds](#ref-nuclideids)<br>|
value<a id="arcgeometrymaterialsmaterialwfracswfracvalue">&nbsp;</a>|Value|1|Real|__Range__<br>[0.0,1.0]|

---

### <a id="arcgeometrymaterialsmaterialadens">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[materials](#arcgeometrymaterials)/[material](#arcgeometrymaterialsmaterial)/[adens](#arcgeometrymaterialsmaterialadens)
#### Isotopic composition defined as atom densities

##### How Many: 0 or 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
[aden](#arcgeometrymaterialsmaterialadensaden)|TaggedValue|1 or more|||

---

### <a id="arcgeometrymaterialsmaterialadensaden">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[materials](#arcgeometrymaterials)/[material](#arcgeometrymaterialsmaterial)/[adens](#arcgeometrymaterialsmaterialadens)/[aden](#arcgeometrymaterialsmaterialadensaden)
##### How Many: 1 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arcgeometrymaterialsmaterialadensadenid">&nbsp;</a>|Tag|1|String|__Choices__<br>REF:[CompNames](#ref-compnames)<br>REF:[NuclideIds](#ref-nuclideids)<br>|
value<a id="arcgeometrymaterialsmaterialadensadenvalue">&nbsp;</a>|Value|1|Real|__Range__<br>[0.0,+INF)|

---

### <a id="arcgeometrymaterialsmaterialafracs">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[materials](#arcgeometrymaterials)/[material](#arcgeometrymaterialsmaterial)/[afracs](#arcgeometrymaterialsmaterialafracs)
#### Isotopic composition defined as atom fractions

##### How Many: 0 or 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
[afrac](#arcgeometrymaterialsmaterialafracsafrac)|TaggedValue|1 or more|||

---

### <a id="arcgeometrymaterialsmaterialafracsafrac">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[materials](#arcgeometrymaterials)/[material](#arcgeometrymaterialsmaterial)/[afracs](#arcgeometrymaterialsmaterialafracs)/[afrac](#arcgeometrymaterialsmaterialafracsafrac)
##### How Many: 1 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arcgeometrymaterialsmaterialafracsafracid">&nbsp;</a>|Tag|1|String|__Choices__<br>REF:[CompNames](#ref-compnames)<br>REF:[NuclideIds](#ref-nuclideids)<br>|
value<a id="arcgeometrymaterialsmaterialafracsafracvalue">&nbsp;</a>|Value|1|Real|__Range__<br>[0.0,1.0]|

---

### <a id="arcgeometrymaterialsmaterialwdens">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[materials](#arcgeometrymaterials)/[material](#arcgeometrymaterialsmaterial)/[wdens](#arcgeometrymaterialsmaterialwdens)
#### Isotopic composition defined as weight densities

##### How Many: 0 or 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
[wden](#arcgeometrymaterialsmaterialwdenswden)|TaggedValue|1 or more|||

---

### <a id="arcgeometrymaterialsmaterialwdenswden">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[materials](#arcgeometrymaterials)/[material](#arcgeometrymaterialsmaterial)/[wdens](#arcgeometrymaterialsmaterialwdens)/[wden](#arcgeometrymaterialsmaterialwdenswden)
##### How Many: 1 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arcgeometrymaterialsmaterialwdenswdenid">&nbsp;</a>|Tag|1|String|__Choices__<br>REF:[CompNames](#ref-compnames)<br>REF:[NuclideIds](#ref-nuclideids)<br>|
value<a id="arcgeometrymaterialsmaterialwdenswdenvalue">&nbsp;</a>|Value|1|Real|__Range__<br>[0.0,+INF)|

---

### <a id="arcgeometrymaterialsmaterialaform">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[materials](#arcgeometrymaterials)/[material](#arcgeometrymaterialsmaterial)/[aform](#arcgeometrymaterialsmaterialaform)
#### Isotopic composition defined as atom formulas

##### How Many: 0 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arcgeometrymaterialsmaterialaformid">&nbsp;</a>|Tag|1|Integer|__Range__<br>[1,+INF)|
[afrac](#arcgeometrymaterialsmaterialaformafrac)|TaggedValue|1 or more|||

---

### <a id="arcgeometrymaterialsmaterialaformafrac">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[materials](#arcgeometrymaterials)/[material](#arcgeometrymaterialsmaterial)/[aform](#arcgeometrymaterialsmaterialaform)/[afrac](#arcgeometrymaterialsmaterialaformafrac)
##### How Many: 1 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arcgeometrymaterialsmaterialaformafracid">&nbsp;</a>|Tag|1|String|__Choices__<br>REF:[CompNames](#ref-compnames)<br>REF:[NuclideIds](#ref-nuclideids)<br>|
value<a id="arcgeometrymaterialsmaterialaformafracvalue">&nbsp;</a>|Value|1|Real|__Range__<br>[0.0,1.0]|

---

### <a id="arcgeometrymaterialsmateriallumped_element_aden">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[materials](#arcgeometrymaterials)/[material](#arcgeometrymaterialsmaterial)/[lumped_element_aden](#arcgeometrymaterialsmateriallumped_element_aden)
#### Atom density of lumped element specified in calculations/mcc3

##### How Many: 0 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arcgeometrymaterialsmateriallumped_element_adenid">&nbsp;</a>|Tag|1|String|__InputKeys__<br>[lumped_element_text_file id](#arccalculationsmcc3lumped_element_text_fileid)<br>|
value<a id="arcgeometrymaterialsmateriallumped_element_adenvalue">&nbsp;</a>|Value|1|Real|__Range__<br>(0.0,+INF)|

---

### <a id="arcgeometryblends">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[blends](#arcgeometryblends)
#### List of mixtures of materials

##### How Many: 0 or 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
[blend](#arcgeometryblendsblend)|SubObject|1 or more|||[required] Mixtures definition

---

### <a id="arcgeometryblendsblend">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[blends](#arcgeometryblends)/[blend](#arcgeometryblendsblend)
#### [required] Mixtures definition

##### How Many: 1 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arcgeometryblendsblendid">&nbsp;</a>|Tag|1|String||
[volf](#arcgeometryblendsblendvolf)|TaggedValue|1 or more|||[required] Volume fraction of materials

---

### <a id="arcgeometryblendsblendvolf">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[blends](#arcgeometryblends)/[blend](#arcgeometryblendsblend)/[volf](#arcgeometryblendsblendvolf)
#### [required] Volume fraction of materials

##### How Many: 1 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arcgeometryblendsblendvolfid">&nbsp;</a>|Tag|1|String|__InputKeys__<br>[material id](#arcgeometrymaterialsmaterialid)<br>|
value<a id="arcgeometryblendsblendvolfvalue">&nbsp;</a>|Value|1|Real|__Range__<br>[0.0,1.0]|

---

### <a id="arcgeometrysurfaces">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[surfaces](#arcgeometrysurfaces)
#### [required] List of surfaces used for geometry description

##### How Many: 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
[cylinder](#arcgeometrysurfacescylinder)|SubObject|0 or more|||Cylinder definition
[plane](#arcgeometrysurfacesplane)|SubObject|0 or more|||Plane definition
[hexagon](#arcgeometrysurfaceshexagon)|SubObject|0 or more|||Hexagon definition
[square](#arcgeometrysurfacessquare)|SubObject|0 or more|||Square definition

---

### <a id="arcgeometrysurfacescylinder">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[surfaces](#arcgeometrysurfaces)/[cylinder](#arcgeometrysurfacescylinder)
#### Cylinder definition

##### How Many: 0 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arcgeometrysurfacescylinderid">&nbsp;</a>|Tag|1|String||
axis<a id="arcgeometrysurfacescylinderaxis">&nbsp;</a>|KeyedValue|1|String|__Choices__<br>z<br>|
radius<a id="arcgeometrysurfacescylinderradius">&nbsp;</a>|KeyedValue|1|Real|__Range__<br>(0.0,+INF)|

---

### <a id="arcgeometrysurfacesplane">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[surfaces](#arcgeometrysurfaces)/[plane](#arcgeometrysurfacesplane)
#### Plane definition

##### How Many: 0 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arcgeometrysurfacesplaneid">&nbsp;</a>|Tag|1|String||
x<a id="arcgeometrysurfacesplanex">&nbsp;</a>|KeyedValue|0 or 1|Real|__Range__<br>(0.0,+INF)|
y<a id="arcgeometrysurfacesplaney">&nbsp;</a>|KeyedValue|0 or 1|Real|__Range__<br>(0.0,+INF)|
z<a id="arcgeometrysurfacesplanez">&nbsp;</a>|KeyedValue|0 or 1|Real|__Range__<br>[0.0,+INF)|

---

### <a id="arcgeometrysurfaceshexagon">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[surfaces](#arcgeometrysurfaces)/[hexagon](#arcgeometrysurfaceshexagon)
#### Hexagon definition

##### How Many: 0 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arcgeometrysurfaceshexagonid">&nbsp;</a>|Tag|1|String||
orientation<a id="arcgeometrysurfaceshexagonorientation">&nbsp;</a>|KeyedValue|1|String|__Choices__<br>y<br>|
normal<a id="arcgeometrysurfaceshexagonnormal">&nbsp;</a>|KeyedValue|1|String|__Choices__<br>z<br>|
pitch<a id="arcgeometrysurfaceshexagonpitch">&nbsp;</a>|KeyedValue|0 or 1|Real|__Range__<br>(0.0,+INF)|
radius<a id="arcgeometrysurfaceshexagonradius">&nbsp;</a>|KeyedValue|0 or 1|Real|__Range__<br>(0.0,+INF)|

---

### <a id="arcgeometrysurfacessquare">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[surfaces](#arcgeometrysurfaces)/[square](#arcgeometrysurfacessquare)
#### Square definition

##### How Many: 0 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arcgeometrysurfacessquareid">&nbsp;</a>|Tag|1|String||
axis<a id="arcgeometrysurfacessquareaxis">&nbsp;</a>|KeyedValue|2|String|__Choices__<br>x<br>y<br>|
side_length<a id="arcgeometrysurfacessquareside_length">&nbsp;</a>|KeyedValue|1|Real|__Range__<br>(0.0,+INF)|

---

### <a id="arcgeometryreactor">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[reactor](#arcgeometryreactor)
#### [required] Description of the core with lattice of assemblies

##### How Many: 0 or 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
[reactor_hex_lattice](#arcgeometryreactorreactor_hex_lattice)|SubObject|0 or 1|||Hexagonal lattice definition within a reactor
[reactor_square_lattice](#arcgeometryreactorreactor_square_lattice)|SubObject|0 or 1|||Square lattice definition within a reactor
lower_axial_surf<a id="arcgeometryreactorlower_axial_surf">&nbsp;</a>|KeyedValue|0 or 1|String|__InputKeys__<br>[plane id](#arcgeometrysurfacesplaneid)<br>|Lower axial surface of the core - must be a plane with z = 0
upper_axial_surf<a id="arcgeometryreactorupper_axial_surf">&nbsp;</a>|KeyedValue|0 or 1|String|__InputKeys__<br>[plane id](#arcgeometrysurfacesplaneid)<br>|Upper axial surface of the core
lower_boundary_condition<a id="arcgeometryreactorlower_boundary_condition">&nbsp;</a>|KeyedValue|0 or 1|String|__Choices__<br>vacuum<br>reflective<br>extrapolated<br>|Boundary condition on the lower axial surface
upper_boundary_condition<a id="arcgeometryreactorupper_boundary_condition">&nbsp;</a>|KeyedValue|0 or 1|String|__Choices__<br>vacuum<br>reflective<br>extrapolated<br>|Boundary condition on the upper axial surface
[assembly](#arcgeometryreactorassembly)|SubObject|1 or more|||[required] Assembly definition

---

### <a id="arcgeometryreactorreactor_hex_lattice">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[reactor](#arcgeometryreactor)/[reactor_hex_lattice](#arcgeometryreactorreactor_hex_lattice)
#### Hexagonal lattice definition within a reactor

##### How Many: 0 or 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
assembly_surf<a id="arcgeometryreactorreactor_hex_latticeassembly_surf">&nbsp;</a>|KeyedValue|1|String|__InputKeys__<br>[hexagon id](#arcgeometrysurfaceshexagonid)<br>|
num_ring<a id="arcgeometryreactorreactor_hex_latticenum_ring">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[1,+INF)|
fill<a id="arcgeometryreactorreactor_hex_latticefill">&nbsp;</a>|Array of Size<br>[num_ring](#arcgeometryreactorreactor_hex_latticenum_ring)|1|String|__InputKeys__<br>[assembly id](#arcgeometryreactorassemblyid)<br>|
[replace_ring](#arcgeometryreactorreactor_hex_latticereplace_ring)|TaggedValue|0 to [num_ring](#arcgeometryreactorreactor_hex_latticenum_ring)|||Replace a full ring with list of assemblies
[replace](#arcgeometryreactorreactor_hex_latticereplace)|SubObject|0 or more|||Replace one element of a ring

---

### <a id="arcgeometryreactorreactor_hex_latticereplace_ring">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[reactor](#arcgeometryreactor)/[reactor_hex_lattice](#arcgeometryreactorreactor_hex_lattice)/[replace_ring](#arcgeometryreactorreactor_hex_latticereplace_ring)
#### Replace a full ring with list of assemblies

##### How Many: 0 to [num_ring](#arcgeometryreactorreactor_hex_latticenum_ring)

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arcgeometryreactorreactor_hex_latticereplace_ringid">&nbsp;</a>|Tag|1|Integer|__Range__<br>[2,[num_ring](#arcgeometryreactorreactor_hex_latticenum_ring)]|
value<a id="arcgeometryreactorreactor_hex_latticereplace_ringvalue">&nbsp;</a>|Value|6 or more|String|__Choices__<br>null<br><br>__InputKeys__<br>[assembly id](#arcgeometryreactorassemblyid)<br>|

---

### <a id="arcgeometryreactorreactor_hex_latticereplace">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[reactor](#arcgeometryreactor)/[reactor_hex_lattice](#arcgeometryreactorreactor_hex_lattice)/[replace](#arcgeometryreactorreactor_hex_latticereplace)
#### Replace one element of a ring

##### How Many: 0 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
ring<a id="arcgeometryreactorreactor_hex_latticereplacering">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[2,[num_ring](#arcgeometryreactorreactor_hex_latticenum_ring)]|
index<a id="arcgeometryreactorreactor_hex_latticereplaceindex">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[1,+INF)|
name<a id="arcgeometryreactorreactor_hex_latticereplacename">&nbsp;</a>|KeyedValue|1|String|__Choices__<br>null<br><br>__InputKeys__<br>[assembly id](#arcgeometryreactorassemblyid)<br>|

---

### <a id="arcgeometryreactorreactor_square_lattice">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[reactor](#arcgeometryreactor)/[reactor_square_lattice](#arcgeometryreactorreactor_square_lattice)
#### Square lattice definition within a reactor

##### How Many: 0 or 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
assembly_surf<a id="arcgeometryreactorreactor_square_latticeassembly_surf">&nbsp;</a>|KeyedValue|1|String|__InputKeys__<br>[square id](#arcgeometrysurfacessquareid)<br>|
num_ring<a id="arcgeometryreactorreactor_square_latticenum_ring">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[1,+INF)|
fill<a id="arcgeometryreactorreactor_square_latticefill">&nbsp;</a>|Array of Size<br>[num_ring](#arcgeometryreactorreactor_square_latticenum_ring)|1|String|__InputKeys__<br>[assembly id](#arcgeometryreactorassemblyid)<br>|
[replace_ring](#arcgeometryreactorreactor_square_latticereplace_ring)|TaggedValue|0 to [num_ring](#arcgeometryreactorreactor_square_latticenum_ring)|||Replace a full ring with list of assemblies
[replace](#arcgeometryreactorreactor_square_latticereplace)|SubObject|0 or more|||Replace one element of a ring

---

### <a id="arcgeometryreactorreactor_square_latticereplace_ring">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[reactor](#arcgeometryreactor)/[reactor_square_lattice](#arcgeometryreactorreactor_square_lattice)/[replace_ring](#arcgeometryreactorreactor_square_latticereplace_ring)
#### Replace a full ring with list of assemblies

##### How Many: 0 to [num_ring](#arcgeometryreactorreactor_square_latticenum_ring)

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arcgeometryreactorreactor_square_latticereplace_ringid">&nbsp;</a>|Tag|1|Integer|__Range__<br>[2,[num_ring](#arcgeometryreactorreactor_square_latticenum_ring)]|
value<a id="arcgeometryreactorreactor_square_latticereplace_ringvalue">&nbsp;</a>|Value|6 or more|String|__Choices__<br>null<br><br>__InputKeys__<br>[assembly id](#arcgeometryreactorassemblyid)<br>|

---

### <a id="arcgeometryreactorreactor_square_latticereplace">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[reactor](#arcgeometryreactor)/[reactor_square_lattice](#arcgeometryreactorreactor_square_lattice)/[replace](#arcgeometryreactorreactor_square_latticereplace)
#### Replace one element of a ring

##### How Many: 0 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
ring<a id="arcgeometryreactorreactor_square_latticereplacering">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[2,[num_ring](#arcgeometryreactorreactor_square_latticenum_ring)]|
index<a id="arcgeometryreactorreactor_square_latticereplaceindex">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[1,+INF)|
name<a id="arcgeometryreactorreactor_square_latticereplacename">&nbsp;</a>|KeyedValue|1|String|__Choices__<br>null<br><br>__InputKeys__<br>[assembly id](#arcgeometryreactorassemblyid)<br>|

---

### <a id="arcgeometryreactorassembly">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[reactor](#arcgeometryreactor)/[assembly](#arcgeometryreactorassembly)
#### [required] Assembly definition

##### How Many: 1 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arcgeometryreactorassemblyid">&nbsp;</a>|Tag|1|String||
[sub_assembly](#arcgeometryreactorassemblysub_assembly)|SubObject|1 or more|||[required] Sub-assembly definition

---

### <a id="arcgeometryreactorassemblysub_assembly">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[reactor](#arcgeometryreactor)/[assembly](#arcgeometryreactorassembly)/[sub_assembly](#arcgeometryreactorassemblysub_assembly)
#### [required] Sub-assembly definition

##### How Many: 1 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arcgeometryreactorassemblysub_assemblyid">&nbsp;</a>|Tag|1|String|__InputKeys__<br>[cell associated_sub_assembly](#arccalculationsmcc3cellassociated_sub_assembly)<br>[cell other_sub_assembly_using_XS](#arccalculationsmcc3cellother_sub_assembly_using_xs)<br>|
lower_axial_surf<a id="arcgeometryreactorassemblysub_assemblylower_axial_surf">&nbsp;</a>|KeyedValue|0 or 1|String|__InputKeys__<br>[plane id](#arcgeometrysurfacesplaneid)<br>|Lower axial surface of the sub-assembly
upper_axial_surf<a id="arcgeometryreactorassemblysub_assemblyupper_axial_surf">&nbsp;</a>|KeyedValue|0 or 1|String|__InputKeys__<br>[plane id](#arcgeometrysurfacesplaneid)<br>|Upper axial surface of the sub-assembly
material<a id="arcgeometryreactorassemblysub_assemblymaterial">&nbsp;</a>|KeyedValue|0 or 1|String|__InputKeys__<br>[material id](#arcgeometrymaterialsmaterialid)<br>[blend id](#arcgeometryblendsblendid)<br>|Homogenized material defining the sub-assembly
[hex_lattice](#arcgeometryreactorassemblysub_assemblyhex_lattice)|SubObject|0 or 1|||Hexagonal lattice and pins definition within a sub-assembly
[square_lattice](#arcgeometryreactorassemblysub_assemblysquare_lattice)|SubObject|0 or 1|||Square lattice and pins definition within a sub-assembly
[radial_region](#arcgeometryreactorassemblysub_assemblyradial_region)|SubObject|0 or more|||Radial region definition as a radial layer within a sub-assembly

---

### <a id="arcgeometryreactorassemblysub_assemblyhex_lattice">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[reactor](#arcgeometryreactor)/[assembly](#arcgeometryreactorassembly)/[sub_assembly](#arcgeometryreactorassemblysub_assembly)/[hex_lattice](#arcgeometryreactorassemblysub_assemblyhex_lattice)
#### Hexagonal lattice and pins definition within a sub-assembly

##### How Many: 0 or 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
pitch<a id="arcgeometryreactorassemblysub_assemblyhex_latticepitch">&nbsp;</a>|KeyedValue|1|Real|__Range__<br>(0.0,+INF)|
num_ring<a id="arcgeometryreactorassemblysub_assemblyhex_latticenum_ring">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[1,+INF)|
outer<a id="arcgeometryreactorassemblysub_assemblyhex_latticeouter">&nbsp;</a>|KeyedValue|1|String|__InputKeys__<br>[material id](#arcgeometrymaterialsmaterialid)<br>[blend id](#arcgeometryblendsblendid)<br>|
fill<a id="arcgeometryreactorassemblysub_assemblyhex_latticefill">&nbsp;</a>|Array of Size<br>[num_ring](#arcgeometryreactorassemblysub_assemblyhex_latticenum_ring)|1|String|__InputKeys__<br>[pin id](#arcgeometryreactorassemblysub_assemblyhex_latticepinid)<br>|
[replace_ring](#arcgeometryreactorassemblysub_assemblyhex_latticereplace_ring)|TaggedValue|0 to [num_ring](#arcgeometryreactorassemblysub_assemblyhex_latticenum_ring)|||Replace a full ring with list of pins
[replace](#arcgeometryreactorassemblysub_assemblyhex_latticereplace)|SubObject|0 or more|||Replace one element of a ring
[pin](#arcgeometryreactorassemblysub_assemblyhex_latticepin)|SubObject|1 or more|||Pin definition - a pin is made of sub-pins and wire wrap

---

### <a id="arcgeometryreactorassemblysub_assemblyhex_latticereplace_ring">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[reactor](#arcgeometryreactor)/[assembly](#arcgeometryreactorassembly)/[sub_assembly](#arcgeometryreactorassemblysub_assembly)/[hex_lattice](#arcgeometryreactorassemblysub_assemblyhex_lattice)/[replace_ring](#arcgeometryreactorassemblysub_assemblyhex_latticereplace_ring)
#### Replace a full ring with list of pins

##### How Many: 0 to [num_ring](#arcgeometryreactorassemblysub_assemblyhex_latticenum_ring)

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arcgeometryreactorassemblysub_assemblyhex_latticereplace_ringid">&nbsp;</a>|Tag|1|Integer|__Range__<br>[2,[num_ring](#arcgeometryreactorassemblysub_assemblyhex_latticenum_ring)]|
value<a id="arcgeometryreactorassemblysub_assemblyhex_latticereplace_ringvalue">&nbsp;</a>|Value|6 or more|String|__Choices__<br>null<br><br>__InputKeys__<br>[pin id](#arcgeometryreactorassemblysub_assemblyhex_latticepinid)<br>|

---

### <a id="arcgeometryreactorassemblysub_assemblyhex_latticereplace">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[reactor](#arcgeometryreactor)/[assembly](#arcgeometryreactorassembly)/[sub_assembly](#arcgeometryreactorassemblysub_assembly)/[hex_lattice](#arcgeometryreactorassemblysub_assemblyhex_lattice)/[replace](#arcgeometryreactorassemblysub_assemblyhex_latticereplace)
#### Replace one element of a ring

##### How Many: 0 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
ring<a id="arcgeometryreactorassemblysub_assemblyhex_latticereplacering">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[2,[num_ring](#arcgeometryreactorassemblysub_assemblyhex_latticenum_ring)]|
index<a id="arcgeometryreactorassemblysub_assemblyhex_latticereplaceindex">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[1,+INF)|
name<a id="arcgeometryreactorassemblysub_assemblyhex_latticereplacename">&nbsp;</a>|KeyedValue|1|String|__Choices__<br>null<br><br>__InputKeys__<br>[pin id](#arcgeometryreactorassemblysub_assemblyhex_latticepinid)<br>|

---

### <a id="arcgeometryreactorassemblysub_assemblyhex_latticepin">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[reactor](#arcgeometryreactor)/[assembly](#arcgeometryreactorassembly)/[sub_assembly](#arcgeometryreactorassemblysub_assembly)/[hex_lattice](#arcgeometryreactorassemblysub_assemblyhex_lattice)/[pin](#arcgeometryreactorassemblysub_assemblyhex_latticepin)
#### Pin definition - a pin is made of sub-pins and wire wrap

##### How Many: 1 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arcgeometryreactorassemblysub_assemblyhex_latticepinid">&nbsp;</a>|Tag|1|String||
[sub_pin](#arcgeometryreactorassemblysub_assemblyhex_latticepinsub_pin)|SubObject|1 or more|||Sub-pin definition as a cylindrical layer within a pin
[wire_wrap](#arcgeometryreactorassemblysub_assemblyhex_latticepinwire_wrap)|SubObject|0 or 1|||Wire-wrap definition

---

### <a id="arcgeometryreactorassemblysub_assemblyhex_latticepinsub_pin">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[reactor](#arcgeometryreactor)/[assembly](#arcgeometryreactorassembly)/[sub_assembly](#arcgeometryreactorassemblysub_assembly)/[hex_lattice](#arcgeometryreactorassemblysub_assemblyhex_lattice)/[pin](#arcgeometryreactorassemblysub_assemblyhex_latticepin)/[sub_pin](#arcgeometryreactorassemblysub_assemblyhex_latticepinsub_pin)
#### Sub-pin definition as a cylindrical layer within a pin

##### How Many: 1 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
material<a id="arcgeometryreactorassemblysub_assemblyhex_latticepinsub_pinmaterial">&nbsp;</a>|KeyedValue|1|String|__InputKeys__<br>[material id](#arcgeometrymaterialsmaterialid)<br>[blend id](#arcgeometryblendsblendid)<br>|
inner_surf<a id="arcgeometryreactorassemblysub_assemblyhex_latticepinsub_pininner_surf">&nbsp;</a>|KeyedValue|0 or 1|String|__InputKeys__<br>[cylinder id](#arcgeometrysurfacescylinderid)<br>|
outer_surf<a id="arcgeometryreactorassemblysub_assemblyhex_latticepinsub_pinouter_surf">&nbsp;</a>|KeyedValue|1|String|__InputKeys__<br>[cylinder id](#arcgeometrysurfacescylinderid)<br>|

---

### <a id="arcgeometryreactorassemblysub_assemblyhex_latticepinwire_wrap">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[reactor](#arcgeometryreactor)/[assembly](#arcgeometryreactorassembly)/[sub_assembly](#arcgeometryreactorassemblysub_assembly)/[hex_lattice](#arcgeometryreactorassemblysub_assemblyhex_lattice)/[pin](#arcgeometryreactorassemblysub_assemblyhex_latticepin)/[wire_wrap](#arcgeometryreactorassemblysub_assemblyhex_latticepinwire_wrap)
#### Wire-wrap definition

##### How Many: 0 or 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
diameter<a id="arcgeometryreactorassemblysub_assemblyhex_latticepinwire_wrapdiameter">&nbsp;</a>|KeyedValue|1|Real|__Range__<br>(0.0,+INF)|
path<a id="arcgeometryreactorassemblysub_assemblyhex_latticepinwire_wrappath">&nbsp;</a>|KeyedValue|1|Real|__Range__<br>(0.0,+INF)|
material<a id="arcgeometryreactorassemblysub_assemblyhex_latticepinwire_wrapmaterial">&nbsp;</a>|KeyedValue|1|String|__InputKeys__<br>[material id](#arcgeometrymaterialsmaterialid)<br>[blend id](#arcgeometryblendsblendid)<br>|

---

### <a id="arcgeometryreactorassemblysub_assemblysquare_lattice">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[reactor](#arcgeometryreactor)/[assembly](#arcgeometryreactorassembly)/[sub_assembly](#arcgeometryreactorassemblysub_assembly)/[square_lattice](#arcgeometryreactorassemblysub_assemblysquare_lattice)
#### Square lattice and pins definition within a sub-assembly

##### How Many: 0 or 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
pitch<a id="arcgeometryreactorassemblysub_assemblysquare_latticepitch">&nbsp;</a>|KeyedValue|1|Real|__Range__<br>(0.0,+INF)|
num_ring<a id="arcgeometryreactorassemblysub_assemblysquare_latticenum_ring">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[1,+INF)|
outer<a id="arcgeometryreactorassemblysub_assemblysquare_latticeouter">&nbsp;</a>|KeyedValue|1|String|__InputKeys__<br>[material id](#arcgeometrymaterialsmaterialid)<br>[blend id](#arcgeometryblendsblendid)<br>|
fill<a id="arcgeometryreactorassemblysub_assemblysquare_latticefill">&nbsp;</a>|Array of Size<br>[num_ring](#arcgeometryreactorassemblysub_assemblysquare_latticenum_ring)|1|String|__InputKeys__<br>[pin id](#arcgeometryreactorassemblysub_assemblysquare_latticepinid)<br>|
[replace_ring](#arcgeometryreactorassemblysub_assemblysquare_latticereplace_ring)|TaggedValue|0 to [num_ring](#arcgeometryreactorassemblysub_assemblysquare_latticenum_ring)|||Replace a full ring with list of pins
[replace](#arcgeometryreactorassemblysub_assemblysquare_latticereplace)|SubObject|0 or more|||Replace one element of a ring
[pin](#arcgeometryreactorassemblysub_assemblysquare_latticepin)|SubObject|1 or more|||Pin definition - a pin is made of sub-pins

---

### <a id="arcgeometryreactorassemblysub_assemblysquare_latticereplace_ring">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[reactor](#arcgeometryreactor)/[assembly](#arcgeometryreactorassembly)/[sub_assembly](#arcgeometryreactorassemblysub_assembly)/[square_lattice](#arcgeometryreactorassemblysub_assemblysquare_lattice)/[replace_ring](#arcgeometryreactorassemblysub_assemblysquare_latticereplace_ring)
#### Replace a full ring with list of pins

##### How Many: 0 to [num_ring](#arcgeometryreactorassemblysub_assemblysquare_latticenum_ring)

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arcgeometryreactorassemblysub_assemblysquare_latticereplace_ringid">&nbsp;</a>|Tag|1|Integer|__Range__<br>[2,[num_ring](#arcgeometryreactorassemblysub_assemblysquare_latticenum_ring)]|
value<a id="arcgeometryreactorassemblysub_assemblysquare_latticereplace_ringvalue">&nbsp;</a>|Value|6 or more|String|__Choices__<br>null<br><br>__InputKeys__<br>[pin id](#arcgeometryreactorassemblysub_assemblysquare_latticepinid)<br>|

---

### <a id="arcgeometryreactorassemblysub_assemblysquare_latticereplace">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[reactor](#arcgeometryreactor)/[assembly](#arcgeometryreactorassembly)/[sub_assembly](#arcgeometryreactorassemblysub_assembly)/[square_lattice](#arcgeometryreactorassemblysub_assemblysquare_lattice)/[replace](#arcgeometryreactorassemblysub_assemblysquare_latticereplace)
#### Replace one element of a ring

##### How Many: 0 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
ring<a id="arcgeometryreactorassemblysub_assemblysquare_latticereplacering">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[2,[num_ring](#arcgeometryreactorassemblysub_assemblysquare_latticenum_ring)]|
index<a id="arcgeometryreactorassemblysub_assemblysquare_latticereplaceindex">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[1,+INF)|
name<a id="arcgeometryreactorassemblysub_assemblysquare_latticereplacename">&nbsp;</a>|KeyedValue|1|String|__Choices__<br>null<br><br>__InputKeys__<br>[pin id](#arcgeometryreactorassemblysub_assemblysquare_latticepinid)<br>|

---

### <a id="arcgeometryreactorassemblysub_assemblysquare_latticepin">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[reactor](#arcgeometryreactor)/[assembly](#arcgeometryreactorassembly)/[sub_assembly](#arcgeometryreactorassemblysub_assembly)/[square_lattice](#arcgeometryreactorassemblysub_assemblysquare_lattice)/[pin](#arcgeometryreactorassemblysub_assemblysquare_latticepin)
#### Pin definition - a pin is made of sub-pins

##### How Many: 1 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arcgeometryreactorassemblysub_assemblysquare_latticepinid">&nbsp;</a>|Tag|1|String||
[sub_pin](#arcgeometryreactorassemblysub_assemblysquare_latticepinsub_pin)|SubObject|1 or more|||Sub-pin definition as a cylindrical layer within a pin

---

### <a id="arcgeometryreactorassemblysub_assemblysquare_latticepinsub_pin">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[reactor](#arcgeometryreactor)/[assembly](#arcgeometryreactorassembly)/[sub_assembly](#arcgeometryreactorassemblysub_assembly)/[square_lattice](#arcgeometryreactorassemblysub_assemblysquare_lattice)/[pin](#arcgeometryreactorassemblysub_assemblysquare_latticepin)/[sub_pin](#arcgeometryreactorassemblysub_assemblysquare_latticepinsub_pin)
#### Sub-pin definition as a cylindrical layer within a pin

##### How Many: 1 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
material<a id="arcgeometryreactorassemblysub_assemblysquare_latticepinsub_pinmaterial">&nbsp;</a>|KeyedValue|1|String|__InputKeys__<br>[material id](#arcgeometrymaterialsmaterialid)<br>[blend id](#arcgeometryblendsblendid)<br>|
inner_surf<a id="arcgeometryreactorassemblysub_assemblysquare_latticepinsub_pininner_surf">&nbsp;</a>|KeyedValue|0 or 1|String|__InputKeys__<br>[cylinder id](#arcgeometrysurfacescylinderid)<br>|
outer_surf<a id="arcgeometryreactorassemblysub_assemblysquare_latticepinsub_pinouter_surf">&nbsp;</a>|KeyedValue|1|String|__InputKeys__<br>[cylinder id](#arcgeometrysurfacescylinderid)<br>|

---

### <a id="arcgeometryreactorassemblysub_assemblyradial_region">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[geometry](#arcgeometry)/[reactor](#arcgeometryreactor)/[assembly](#arcgeometryreactorassembly)/[sub_assembly](#arcgeometryreactorassemblysub_assembly)/[radial_region](#arcgeometryreactorassemblysub_assemblyradial_region)
#### Radial region definition as a radial layer within a sub-assembly

##### How Many: 0 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arcgeometryreactorassemblysub_assemblyradial_regionid">&nbsp;</a>|Tag|1|String||
material<a id="arcgeometryreactorassemblysub_assemblyradial_regionmaterial">&nbsp;</a>|KeyedValue|1|String|__InputKeys__<br>[material id](#arcgeometrymaterialsmaterialid)<br>[blend id](#arcgeometryblendsblendid)<br>|
inner_surf<a id="arcgeometryreactorassemblysub_assemblyradial_regioninner_surf">&nbsp;</a>|KeyedValue|0 or 1|String|__InputKeys__<br>[cylinder id](#arcgeometrysurfacescylinderid)<br>[hexagon id](#arcgeometrysurfaceshexagonid)<br>[square id](#arcgeometrysurfacessquareid)<br>|
outer_surf<a id="arcgeometryreactorassemblysub_assemblyradial_regionouter_surf">&nbsp;</a>|KeyedValue|1|String|__InputKeys__<br>[cylinder id](#arcgeometrysurfacescylinderid)<br>[hexagon id](#arcgeometrysurfaceshexagonid)<br>[square id](#arcgeometrysurfacessquareid)<br>|

---

### <a id="arccalculations">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)
#### Description of the list of calculations

##### How Many: 0 or 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
num_cpu_max<a id="arccalculationsnum_cpu_max">&nbsp;</a>|KeyedValue|0 or 1|Integer|__Range__<br>[1,+INF)|Maximum number of CPUs used for parallelized calculations
[mcc3](#arccalculationsmcc3)|SubObject|0 or 1|||Description for MCC3 (+ Twodant or Partisn) calculations
[dif3d](#arccalculationsdif3d)|SubObject|0 or 1|||Description for DIF3D (+ REBUS and PERSENT) calculations

---

### <a id="arccalculationsmcc3">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[mcc3](#arccalculationsmcc3)
#### Description for MCC3 (+ Twodant or Partisn) calculations

##### How Many: 0 or 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
xslib<a id="arccalculationsmcc3xslib">&nbsp;</a>|KeyedValue|1|String|__Choices__<br>endf6.0<br>endf7.0<br>endf7.1<br>|[required] Nuclear data library version
egroupname<a id="arccalculationsmcc3egroupname">&nbsp;</a>|KeyedValue|0 or 1|String|__Choices__<br>anl33<br>anl70<br>anl230<br>anl1041<br>anl2082<br>|Energy group structure (final condensation)
egroupvals<a id="arccalculationsmcc3egroupvals">&nbsp;</a>|Array of Size<br>1 or more<br>Increasing Values|0 or 1|Real|__Range__<br>(0.0,+INF)|Customized energy group structure
scattering_order<a id="arccalculationsmcc3scattering_order">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[0,+INF)|[required] Scattering order
inelastic_treatment<a id="arccalculationsmcc3inelastic_treatment">&nbsp;</a>|KeyedValue|0 or 1|String|__Choices__<br>approximate<br>rigorous<br>|Type of inelastic treatment - approximate or rigorous
force_mixture_calc<a id="arccalculationsmcc3force_mixture_calc">&nbsp;</a>|KeyedValue|0 or 1|String|__Choices__<br>true<br>false<br>|Option that forces 0-D calculations on all cells
[cell](#arccalculationsmcc3cell)|SubObject|1 or more|||[required] Definition of a new cell - each sub-assembly must be specified in a cell
[rzmflx_code_options](#arccalculationsmcc3rzmflx_code_options)|SubObject|0 or 1|||Description of the 2-D geometry and code options
[lumped_element_text_file](#arccalculationsmcc3lumped_element_text_file)|TaggedValue|0 or more|||Link to text file containing description of a lumped element

---

### <a id="arccalculationsmcc3cell">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[mcc3](#arccalculationsmcc3)/[cell](#arccalculationsmcc3cell)
#### [required] Definition of a new cell - each sub-assembly must be specified in a cell

##### How Many: 1 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arccalculationsmcc3cellid">&nbsp;</a>|Tag|1|String|__Choices__<br>a<br>b<br>c<br>d<br>e<br>f<br>g<br>h<br>i<br>j<br>k<br>l<br>m<br>n<br>o<br>p<br>q<br>r<br>s<br>t<br>u<br>v<br>w<br>x<br>y<br>z<br>|
associated_sub_assembly<a id="arccalculationsmcc3cellassociated_sub_assembly">&nbsp;</a>|KeyedValue|1|String|__InputKeys__<br>[sub_assembly id](#arcgeometryreactorassemblysub_assemblyid)<br>[sub_assembly id](#arcgeometryreactorassemblysub_assemblyid)<br>|[required] Sub-assembly which composition is used for cell calculation
other_sub_assembly_using_XS<a id="arccalculationsmcc3cellother_sub_assembly_using_xs">&nbsp;</a>|Array of Size<br>1 or more|0 or 1|String|__InputKeys__<br>[sub_assembly id](#arcgeometryreactorassemblysub_assemblyid)<br>[sub_assembly id](#arcgeometryreactorassemblysub_assemblyid)<br>|List of sub-assemblies that will use the cross-sections generated with this cell 
buckling_search<a id="arccalculationsmcc3cellbuckling_search">&nbsp;</a>|KeyedValue|0 or 1|String|__Choices__<br>true<br>false<br>|Buckling search for fissile regions
external_source<a id="arccalculationsmcc3cellexternal_source">&nbsp;</a>|KeyedValue|0 or 1|String|__InputKeys__<br>[cell id](#arccalculationsmcc3cellid)<br>|Another cell's ID which neutron leakage is used as external source for a non-fissile cell
[hete_cell_options](#arccalculationsmcc3cellhete_cell_options)|SubObject|0 or 1|||Description of the 1-D geometry used for heterogeneous XS treatment

---

### <a id="arccalculationsmcc3cellhete_cell_options">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[mcc3](#arccalculationsmcc3)/[cell](#arccalculationsmcc3cell)/[hete_cell_options](#arccalculationsmcc3cellhete_cell_options)
#### Description of the 1-D geometry used for heterogeneous XS treatment

##### How Many: 0 or 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
geometry_type<a id="arccalculationsmcc3cellhete_cell_optionsgeometry_type">&nbsp;</a>|KeyedValue|1|String|__Choices__<br>cylinder<br>slab<br>|[required] Type of 1-D geometry
max_mesh_size<a id="arccalculationsmcc3cellhete_cell_optionsmax_mesh_size">&nbsp;</a>|KeyedValue|1|Real|__Range__<br>(0.0,+INF)|[required] Number in meters of the maximum 1d mesh size
boundary_condition<a id="arccalculationsmcc3cellhete_cell_optionsboundary_condition">&nbsp;</a>|KeyedValue|0 or 1|String|__Choices__<br>reflective<br>periodic<br>|
external_composition<a id="arccalculationsmcc3cellhete_cell_optionsexternal_composition">&nbsp;</a>|KeyedValue|0 or 1|String|__InputKeys__<br>[cell id](#arccalculationsmcc3cellid)<br>|Another cell's ID which fissile composition is used as surrounding material (required for non-fissile cell)
r_location<a id="arccalculationsmcc3cellhete_cell_optionsr_location">&nbsp;</a>|Array of Size<br>2 or more|1|String|__InputKeys__<br>[plane id](#arcgeometrysurfacesplaneid)<br>[cylinder id](#arcgeometrysurfacescylinderid)<br>|[required] Surface boundaries of the different areas
r_composition<a id="arccalculationsmcc3cellhete_cell_optionsr_composition">&nbsp;</a>|Array of Size<br>2 or more|1|String|__InputKeys__<br>[material id](#arcgeometrymaterialsmaterialid)<br>|[required] Material in each area defined by r_location

---

### <a id="arccalculationsmcc3rzmflx_code_options">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[mcc3](#arccalculationsmcc3)/[rzmflx_code_options](#arccalculationsmcc3rzmflx_code_options)
#### Description of the 2-D geometry and code options

##### How Many: 0 or 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
bottom_boundary_condition<a id="arccalculationsmcc3rzmflx_code_optionsbottom_boundary_condition">&nbsp;</a>|KeyedValue|0 or 1|String|__Choices__<br>vacuum<br>reflective<br>|
top_boundary_condition<a id="arccalculationsmcc3rzmflx_code_optionstop_boundary_condition">&nbsp;</a>|KeyedValue|0 or 1|String|__Choices__<br>vacuum<br>reflective<br>|
right_boundary_condition<a id="arccalculationsmcc3rzmflx_code_optionsright_boundary_condition">&nbsp;</a>|KeyedValue|0 or 1|String|__Choices__<br>vacuum<br>reflective<br>|
left_boundary_condition<a id="arccalculationsmcc3rzmflx_code_optionsleft_boundary_condition">&nbsp;</a>|KeyedValue|0 or 1|String|__Choices__<br>vacuum<br>reflective<br>|
code<a id="arccalculationsmcc3rzmflx_code_optionscode">&nbsp;</a>|KeyedValue|1|String|__Choices__<br>twodant<br>partisn<br>|
egroupname<a id="arccalculationsmcc3rzmflx_code_optionsegroupname">&nbsp;</a>|KeyedValue|1|String|__Choices__<br>anl33<br>anl70<br>anl230<br>anl1041<br>anl2082<br>|[required] Energy group structure (used for 2-D calculation)
R_boundaries<a id="arccalculationsmcc3rzmflx_code_optionsr_boundaries">&nbsp;</a>|Array of Size<br>1 or more|0 or 1|String|__InputKeys__<br>[cylinder id](#arcgeometrysurfacescylinderid)<br>|[required for RZ geometry]
R_nodes_distance<a id="arccalculationsmcc3rzmflx_code_optionsr_nodes_distance">&nbsp;</a>|KeyedValue|0 or 1|Real|__Range__<br>(0.0,+INF)|[required for RZ geometry]
Z_boundaries<a id="arccalculationsmcc3rzmflx_code_optionsz_boundaries">&nbsp;</a>|Array of Size<br>1 or more|0 or 1|String|__InputKeys__<br>[plane id](#arcgeometrysurfacesplaneid)<br>|[required for RZ geometry]
Z_nodes_distance<a id="arccalculationsmcc3rzmflx_code_optionsz_nodes_distance">&nbsp;</a>|KeyedValue|0 or 1|Real|__Range__<br>(0.0,+INF)|[required for RZ geometry]
X_boundaries<a id="arccalculationsmcc3rzmflx_code_optionsx_boundaries">&nbsp;</a>|Array of Size<br>1 or more|0 or 1|String|__InputKeys__<br>[plane id](#arcgeometrysurfacesplaneid)<br>|[required for XY geometry]
X_nodes_distance<a id="arccalculationsmcc3rzmflx_code_optionsx_nodes_distance">&nbsp;</a>|KeyedValue|0 or 1|Real|__Range__<br>(0.0,+INF)|[required for XY geometry]
Y_boundaries<a id="arccalculationsmcc3rzmflx_code_optionsy_boundaries">&nbsp;</a>|Array of Size<br>1 or more|0 or 1|String|__InputKeys__<br>[plane id](#arcgeometrysurfacesplaneid)<br>|[required for XY geometry]
Y_nodes_distance<a id="arccalculationsmcc3rzmflx_code_optionsy_nodes_distance">&nbsp;</a>|KeyedValue|0 or 1|Real|__Range__<br>(0.0,+INF)|[required for XY geometry]
SN_angular_order<a id="arccalculationsmcc3rzmflx_code_optionssn_angular_order">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>(0,+INF)|
core_2d_geometry<a id="arccalculationsmcc3rzmflx_code_optionscore_2d_geometry">&nbsp;</a>|Array of Size<br>1 or more|1|String|__InputKeys__<br>[cell id](#arccalculationsmcc3cellid)<br>|[required] list of MCC3 cell IDs in each area defined with R/Z/X/Y boundaries

---

### <a id="arccalculationsmcc3lumped_element_text_file">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[mcc3](#arccalculationsmcc3)/[lumped_element_text_file](#arccalculationsmcc3lumped_element_text_file)
#### Link to text file containing description of a lumped element

##### How Many: 0 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arccalculationsmcc3lumped_element_text_fileid">&nbsp;</a>|Tag|1|String||
value<a id="arccalculationsmcc3lumped_element_text_filevalue">&nbsp;</a>|Value|1|String||

---

### <a id="arccalculationsdif3d">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[dif3d](#arccalculationsdif3d)
#### Description for DIF3D (+ REBUS and PERSENT) calculations

##### How Many: 0 or 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
power<a id="arccalculationsdif3dpower">&nbsp;</a>|KeyedValue|1|Real|__Range__<br>(0.0,+INF)|[required] Neutron power of the full-core [W]
run_dif3d<a id="arccalculationsdif3drun_dif3d">&nbsp;</a>|KeyedValue|0 or 1|String|__Choices__<br>true<br>false<br>|Option to skip DIF3D stand-alone calculation
geometry_type<a id="arccalculationsdif3dgeometry_type">&nbsp;</a>|KeyedValue|1|String|__Choices__<br>hexagonal_full_core<br>hexagonal_sixth_core<br>hexagonal_third_core<br>hexagonal_infinite_lattice<br>triangular_full_core<br>cartesian_full_core<br>cartesian_half_core<br>cartesian_fourth_core<br>cartesian_infinite_lattice<br>|[required] Type of geometry modelled and symmetry specification
isotxs<a id="arccalculationsdif3disotxs">&nbsp;</a>|KeyedValue|0 or 1|String||Link to multi-group XS data
max_axial_mesh_size<a id="arccalculationsdif3dmax_axial_mesh_size">&nbsp;</a>|KeyedValue|0 or 1|Real|__Range__<br>(0.0,+INF)|[required for Hex-Z or XYZ geometries]
max_radial_mesh_size<a id="arccalculationsdif3dmax_radial_mesh_size">&nbsp;</a>|KeyedValue|0 or 1|Real|__Range__<br>(0.0,+INF)|[required for XY or XYZ geometries]
[num_axial_burnup_zones](#arccalculationsdif3dnum_axial_burnup_zones)|TaggedValue|0 or more|||Axial subdivision of a sub-assembly (useful if contains depleted materials)
[variant_options](#arccalculationsdif3dvariant_options)|SubObject|0 or 1|||Options for VARIANT solver of DIF3D
[dif_fd_options](#arccalculationsdif3ddif_fd_options)|SubObject|0 or 1|||Options for Finite Difference solver of DIF3D
[dif_nod_options](#arccalculationsdif3ddif_nod_options)|SubObject|0 or 1|||Options for Nodal solver of DIF3D
[rebus](#arccalculationsdif3drebus)|SubObject|0 or 1|||Description REBUS calculations
[persent](#arccalculationsdif3dpersent)|SubObject|0 or 1|||Description for PERSENT calculations

---

### <a id="arccalculationsdif3dnum_axial_burnup_zones">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[dif3d](#arccalculationsdif3d)/[num_axial_burnup_zones](#arccalculationsdif3dnum_axial_burnup_zones)
#### Axial subdivision of a sub-assembly (useful if contains depleted materials)

##### How Many: 0 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arccalculationsdif3dnum_axial_burnup_zonesid">&nbsp;</a>|Tag|1|String|__InputKeys__<br>[sub_assembly id](#arcgeometryreactorassemblysub_assemblyid)<br>[sub_assembly id](#arcgeometryreactorassemblysub_assemblyid)<br>|
value<a id="arccalculationsdif3dnum_axial_burnup_zonesvalue">&nbsp;</a>|Value|1|Integer|__Range__<br>[2,+INF)|

---

### <a id="arccalculationsdif3dvariant_options">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[dif3d](#arccalculationsdif3d)/[variant_options](#arccalculationsdif3dvariant_options)
#### Options for VARIANT solver of DIF3D

##### How Many: 0 or 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
polynomial_approx_source<a id="arccalculationsdif3dvariant_optionspolynomial_approx_source">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[1,[polynomial_approx_fluxes](#arccalculationsdif3dvariant_optionspolynomial_approx_fluxes)]|
polynomial_approx_fluxes<a id="arccalculationsdif3dvariant_optionspolynomial_approx_fluxes">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[1,12]|
polynomial_approx_leakages<a id="arccalculationsdif3dvariant_optionspolynomial_approx_leakages">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[0,[polynomial_approx_fluxes](#arccalculationsdif3dvariant_optionspolynomial_approx_fluxes)]|
angular_approx<a id="arccalculationsdif3dvariant_optionsangular_approx">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[1,60]|
anisotropic_scattering_approx<a id="arccalculationsdif3dvariant_optionsanisotropic_scattering_approx">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[0,[scattering_order](#arccalculationsmcc3scattering_order)]|
omega_acceleration<a id="arccalculationsdif3dvariant_optionsomega_acceleration">&nbsp;</a>|KeyedValue|0 or 1|String|__Choices__<br>true<br>false<br>|

---

### <a id="arccalculationsdif3ddif_fd_options">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[dif3d](#arccalculationsdif3d)/[dif_fd_options](#arccalculationsdif3ddif_fd_options)
#### Options for Finite Difference solver of DIF3D

##### How Many: 0 or 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
hex_triangular_subdivision<a id="arccalculationsdif3ddif_fd_optionshex_triangular_subdivision">&nbsp;</a>|KeyedValue|0 or 1|Integer|__Range__<br>[0,+INF)|

---

### <a id="arccalculationsdif3ddif_nod_options">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[dif3d](#arccalculationsdif3d)/[dif_nod_options](#arccalculationsdif3ddif_nod_options)
#### Options for Nodal solver of DIF3D

##### How Many: 0 or 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
coarse_mesh_rebalance<a id="arccalculationsdif3ddif_nod_optionscoarse_mesh_rebalance">&nbsp;</a>|KeyedValue|1|String|__Choices__<br>true<br>false<br>|

---

### <a id="arccalculationsdif3drebus">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[dif3d](#arccalculationsdif3d)/[rebus](#arccalculationsdif3drebus)
#### Description REBUS calculations

##### How Many: 0 or 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
cycle_length<a id="arccalculationsdif3drebuscycle_length">&nbsp;</a>|KeyedValue|0 or 1|Real|__Range__<br>(0.0,+INF)|Cycle length specification
num_subintervals<a id="arccalculationsdif3drebusnum_subintervals">&nbsp;</a>|KeyedValue|0 or 1|Integer|__Range__<br>[1,+INF)|Number of subintervals per cycle
subinterval_length<a id="arccalculationsdif3drebussubinterval_length">&nbsp;</a>|Array of Size<br>1 or more|0 or 1|Real|__Range__<br>(0.0,+INF)|List of subinterval lengths per cycle
num_cycles<a id="arccalculationsdif3drebusnum_cycles">&nbsp;</a>|KeyedValue|0 or 1|Integer|__Range__<br>[1,+INF)|Number of cycle - non-equilibrium problems only
shutdown_time_between_cycle<a id="arccalculationsdif3drebusshutdown_time_between_cycle">&nbsp;</a>|KeyedValue|0 or 1|Real|__Range__<br>[0.0,+INF)|Shutdown time between each cycle - non-equilibrium problems only
xs_update_at_each_timestep<a id="arccalculationsdif3drebusxs_update_at_each_timestep">&nbsp;</a>|KeyedValue|0 or 1|String|__Choices__<br>true<br>false<br>|Option to re-calculate XS at each timestep - non-equilibrium problems only
[equilibrium_search](#arccalculationsdif3drebusequilibrium_search)|SubObject|0 or 1|||Options for equilibrium problems
[decay_chain](#arccalculationsdif3drebusdecay_chain)|SubObject|1|||[required] Decay chain description

---

### <a id="arccalculationsdif3drebusequilibrium_search">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[dif3d](#arccalculationsdif3d)/[rebus](#arccalculationsdif3drebus)/[equilibrium_search](#arccalculationsdif3drebusequilibrium_search)
#### Options for equilibrium problems

##### How Many: 0 or 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
keff_target<a id="arccalculationsdif3drebusequilibrium_searchkeff_target">&nbsp;</a>|KeyedValue|1|Real|__Range__<br>(0.0,+INF)|[required] Minimum value of k-effective targeted
enrich_high<a id="arccalculationsdif3drebusequilibrium_searchenrich_high">&nbsp;</a>|KeyedValue|1|Real|__Range__<br>(0.0,1.0)|[required] Upper range of fissile enrichment for the search
enrich_low<a id="arccalculationsdif3drebusequilibrium_searchenrich_low">&nbsp;</a>|KeyedValue|1|Real|__Range__<br>(0.0,1.0)|[required] Lower range of enrichment for the search
frac_cycle_keff_target_met<a id="arccalculationsdif3drebusequilibrium_searchfrac_cycle_keff_target_met">&nbsp;</a>|KeyedValue|1|Real|__Range__<br>(0.0,1.0]|[required] Fraction of the cycle where k-effective target must be met
MCC3_XS_iterations<a id="arccalculationsdif3drebusequilibrium_searchmcc3_xs_iterations">&nbsp;</a>|KeyedValue|0 or 1|Integer|__Range__<br>[0,2]|Number of MCC3/REBUS iterations requested to converge on XS at BOEC
[external_feed](#arccalculationsdif3drebusequilibrium_searchexternal_feed)|SubObject|1 or more|||[required] External feed isotopic description
[reprocessing](#arccalculationsdif3drebusequilibrium_searchreprocessing)|SubObject|0 or more|||Reprocessing strategy description
[path](#arccalculationsdif3drebusequilibrium_searchpath)|SubObject|1 or more|||[required] Reactor charge/discharge specification for every sub-assembly containing fissile elements

---

### <a id="arccalculationsdif3drebusequilibrium_searchexternal_feed">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[dif3d](#arccalculationsdif3d)/[rebus](#arccalculationsdif3drebus)/[equilibrium_search](#arccalculationsdif3drebusequilibrium_search)/[external_feed](#arccalculationsdif3drebusequilibrium_searchexternal_feed)
#### [required] External feed isotopic description

##### How Many: 1 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arccalculationsdif3drebusequilibrium_searchexternal_feedid">&nbsp;</a>|Tag|1|String||
[afracs](#arccalculationsdif3drebusequilibrium_searchexternal_feedafracs)|SubObject|1|||
total_volume<a id="arccalculationsdif3drebusequilibrium_searchexternal_feedtotal_volume">&nbsp;</a>|KeyedValue|0 or 1|Real|__Range__<br>(0.0,+INF)|Total volume in reserve for the external feed

---

### <a id="arccalculationsdif3drebusequilibrium_searchexternal_feedafracs">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[dif3d](#arccalculationsdif3d)/[rebus](#arccalculationsdif3drebus)/[equilibrium_search](#arccalculationsdif3drebusequilibrium_search)/[external_feed](#arccalculationsdif3drebusequilibrium_searchexternal_feed)/[afracs](#arccalculationsdif3drebusequilibrium_searchexternal_feedafracs)
##### How Many: 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
[afrac](#arccalculationsdif3drebusequilibrium_searchexternal_feedafracsafrac)|TaggedValue|1 or more|||

---

### <a id="arccalculationsdif3drebusequilibrium_searchexternal_feedafracsafrac">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[dif3d](#arccalculationsdif3d)/[rebus](#arccalculationsdif3drebus)/[equilibrium_search](#arccalculationsdif3drebusequilibrium_search)/[external_feed](#arccalculationsdif3drebusequilibrium_searchexternal_feed)/[afracs](#arccalculationsdif3drebusequilibrium_searchexternal_feedafracs)/[afrac](#arccalculationsdif3drebusequilibrium_searchexternal_feedafracsafrac)
##### How Many: 1 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arccalculationsdif3drebusequilibrium_searchexternal_feedafracsafracid">&nbsp;</a>|Tag|1|String|__InputKeys__<br>[decay_chain list_isotopes](#arccalculationsdif3drebusdecay_chainlist_isotopes)<br>[decay_chain list_lumped_elements](#arccalculationsdif3drebusdecay_chainlist_lumped_elements)<br>|
value<a id="arccalculationsdif3drebusequilibrium_searchexternal_feedafracsafracvalue">&nbsp;</a>|Value|1|Real|__Range__<br>[0.0,1.0]|

---

### <a id="arccalculationsdif3drebusequilibrium_searchreprocessing">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[dif3d](#arccalculationsdif3d)/[rebus](#arccalculationsdif3drebus)/[equilibrium_search](#arccalculationsdif3drebusequilibrium_search)/[reprocessing](#arccalculationsdif3drebusequilibrium_searchreprocessing)
#### Reprocessing strategy description

##### How Many: 0 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arccalculationsdif3drebusequilibrium_searchreprocessingid">&nbsp;</a>|Tag|1|String||
reprocessing_time<a id="arccalculationsdif3drebusequilibrium_searchreprocessingreprocessing_time">&nbsp;</a>|KeyedValue|0 or 1|Real|__Range__<br>[0.0,+INF)|
storage_time<a id="arccalculationsdif3drebusequilibrium_searchreprocessingstorage_time">&nbsp;</a>|KeyedValue|0 or 1|Real|__Range__<br>[0.0,+INF)|
[recovery_frac_enrich](#arccalculationsdif3drebusequilibrium_searchreprocessingrecovery_frac_enrich)|TaggedValue|1 or more|||[required] Fraction of isotope recovered and defined as enrich material
[recovery_frac_other](#arccalculationsdif3drebusequilibrium_searchreprocessingrecovery_frac_other)|TaggedValue|0 or more|||Fraction of isotope recovered and defined as other material

---

### <a id="arccalculationsdif3drebusequilibrium_searchreprocessingrecovery_frac_enrich">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[dif3d](#arccalculationsdif3d)/[rebus](#arccalculationsdif3drebus)/[equilibrium_search](#arccalculationsdif3drebusequilibrium_search)/[reprocessing](#arccalculationsdif3drebusequilibrium_searchreprocessing)/[recovery_frac_enrich](#arccalculationsdif3drebusequilibrium_searchreprocessingrecovery_frac_enrich)
#### [required] Fraction of isotope recovered and defined as enrich material

##### How Many: 1 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arccalculationsdif3drebusequilibrium_searchreprocessingrecovery_frac_enrichid">&nbsp;</a>|Tag|1|String|__InputKeys__<br>[decay_chain list_isotopes](#arccalculationsdif3drebusdecay_chainlist_isotopes)<br>|
value<a id="arccalculationsdif3drebusequilibrium_searchreprocessingrecovery_frac_enrichvalue">&nbsp;</a>|Value|1|Real|__Range__<br>[0.0,1.0]|

---

### <a id="arccalculationsdif3drebusequilibrium_searchreprocessingrecovery_frac_other">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[dif3d](#arccalculationsdif3d)/[rebus](#arccalculationsdif3drebus)/[equilibrium_search](#arccalculationsdif3drebusequilibrium_search)/[reprocessing](#arccalculationsdif3drebusequilibrium_searchreprocessing)/[recovery_frac_other](#arccalculationsdif3drebusequilibrium_searchreprocessingrecovery_frac_other)
#### Fraction of isotope recovered and defined as other material

##### How Many: 0 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arccalculationsdif3drebusequilibrium_searchreprocessingrecovery_frac_otherid">&nbsp;</a>|Tag|1|String|__InputKeys__<br>[decay_chain list_isotopes](#arccalculationsdif3drebusdecay_chainlist_isotopes)<br>[decay_chain list_lumped_elements](#arccalculationsdif3drebusdecay_chainlist_lumped_elements)<br>|
value<a id="arccalculationsdif3drebusequilibrium_searchreprocessingrecovery_frac_othervalue">&nbsp;</a>|Value|1|Real|__Range__<br>[0.0,1.0]|

---

### <a id="arccalculationsdif3drebusequilibrium_searchpath">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[dif3d](#arccalculationsdif3d)/[rebus](#arccalculationsdif3drebus)/[equilibrium_search](#arccalculationsdif3drebusequilibrium_search)/[path](#arccalculationsdif3drebusequilibrium_searchpath)
#### [required] Reactor charge/discharge specification for every sub-assembly containing fissile elements

##### How Many: 1 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arccalculationsdif3drebusequilibrium_searchpathid">&nbsp;</a>|Tag|1|String|__InputKeys__<br>[sub_assembly id](#arcgeometryreactorassemblysub_assemblyid)<br>[sub_assembly id](#arcgeometryreactorassemblysub_assemblyid)<br>|
fabr_mat_wdens<a id="arccalculationsdif3drebusequilibrium_searchpathfabr_mat_wdens">&nbsp;</a>|KeyedValue|1|Real|__Range__<br>(0.0,+INF)|[required] Weight density of the heavy nuclei fabricated material
num_batches<a id="arccalculationsdif3drebusequilibrium_searchpathnum_batches">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[1,+INF)|[required] Number of batches in core for the sub-assembly before discharge
fabrication_time<a id="arccalculationsdif3drebusequilibrium_searchpathfabrication_time">&nbsp;</a>|KeyedValue|0 or 1|Real|__Range__<br>[0.0,+INF)|
enrich_modif_fact<a id="arccalculationsdif3drebusequilibrium_searchpathenrich_modif_fact">&nbsp;</a>|KeyedValue|1|Real|__Range__<br>[0.0,1.0]|[required] Factor modifying the enrichment in one path relative to another
feeds_enrich<a id="arccalculationsdif3drebusequilibrium_searchpathfeeds_enrich">&nbsp;</a>|Array of Size<br>1 or more|1|String|__InputKeys__<br>[reprocessing id](#arccalculationsdif3drebusequilibrium_searchreprocessingid)<br>[external_feed id](#arccalculationsdif3drebusequilibrium_searchexternal_feedid)<br>|[required] List of preferred feeds (by preference order) for the enriched material
feeds_other<a id="arccalculationsdif3drebusequilibrium_searchpathfeeds_other">&nbsp;</a>|Array of Size<br>1 or more|0 or 1|String|__InputKeys__<br>[reprocessing id](#arccalculationsdif3drebusequilibrium_searchreprocessingid)<br>[external_feed id](#arccalculationsdif3drebusequilibrium_searchexternal_feedid)<br>|List of preferred feeds (by preference order) for the other material

---

### <a id="arccalculationsdif3drebusdecay_chain">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[dif3d](#arccalculationsdif3d)/[rebus](#arccalculationsdif3drebus)/[decay_chain](#arccalculationsdif3drebusdecay_chain)
#### [required] Decay chain description

##### How Many: 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
list_isotopes<a id="arccalculationsdif3drebusdecay_chainlist_isotopes">&nbsp;</a>|Array of Size<br>1 or more|1|String|__Choices__<br>REF:[CompNames](#ref-compnames)<br>REF:[NuclideIds](#ref-nuclideids)<br>|[required] List of all isotopes part of the decay chain (heavy nuclei and fission products if explicitly defined)
list_lumped_elements<a id="arccalculationsdif3drebusdecay_chainlist_lumped_elements">&nbsp;</a>|Array of Size<br>1 or more|0 or 1|String|__InputKeys__<br>[lumped_element_text_file id](#arccalculationsmcc3lumped_element_text_fileid)<br>|List of all lumped elements part of the decay chain
list_&nbsp;_elements<a id="arccalculationsdif3drebusdecay_chainlist_&nbsp;_elements">&nbsp;</a>|Array of Size<br>1 or more|0 or 1|String||List of all &nbsp; elements part of the decay chain
text_file<a id="arccalculationsdif3drebusdecay_chaintext_file">&nbsp;</a>|KeyedValue|1|String||[required] Path to decay chain file that provides the decay chain in REBUS-3 format

---

### <a id="arccalculationsdif3dpersent">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[dif3d](#arccalculationsdif3d)/[persent](#arccalculationsdif3dpersent)
#### Description for PERSENT calculations

##### How Many: 0 or 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
rebus_output_file<a id="arccalculationsdif3dpersentrebus_output_file">&nbsp;</a>|KeyedValue|0 or 1|String||Path to REBUS output file - allows to skip REBUS calculation
dif3d_refcalc_depsteps<a id="arccalculationsdif3dpersentdif3d_refcalc_depsteps">&nbsp;</a>|Array of Size<br>1 or more|0 or 1|Integer|__Range__<br>[0,99]|List of depletion steps to run preliminary stand-alone reference DIF3D calculations to provide flux files to speed-up recuring PERSENT calculations
[variant_options](#arccalculationsdif3dpersentvariant_options)|SubObject|0 or 1|||[required if not specified in DIF3D block] Description of VARIANT options
[pert_calc](#arccalculationsdif3dpersentpert_calc)|SubObject|0 or more|||Description of Perturbation calculation
[sens_calc](#arccalculationsdif3dpersentsens_calc)|SubObject|0 or more|||Description of Sensitivity calculation

---

### <a id="arccalculationsdif3dpersentvariant_options">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[dif3d](#arccalculationsdif3d)/[persent](#arccalculationsdif3dpersent)/[variant_options](#arccalculationsdif3dpersentvariant_options)
#### [required if not specified in DIF3D block] Description of VARIANT options

##### How Many: 0 or 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
polynomial_approx_source<a id="arccalculationsdif3dpersentvariant_optionspolynomial_approx_source">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[1,[polynomial_approx_fluxes](#arccalculationsdif3dpersentvariant_optionspolynomial_approx_fluxes)]|
polynomial_approx_fluxes<a id="arccalculationsdif3dpersentvariant_optionspolynomial_approx_fluxes">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[1,12]|
polynomial_approx_leakages<a id="arccalculationsdif3dpersentvariant_optionspolynomial_approx_leakages">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[0,[polynomial_approx_fluxes](#arccalculationsdif3dpersentvariant_optionspolynomial_approx_fluxes)]|
angular_approx<a id="arccalculationsdif3dpersentvariant_optionsangular_approx">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[1,60]|
anisotropic_scattering_approx<a id="arccalculationsdif3dpersentvariant_optionsanisotropic_scattering_approx">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[0,[scattering_order](#arccalculationsmcc3scattering_order)]|
omega_acceleration<a id="arccalculationsdif3dpersentvariant_optionsomega_acceleration">&nbsp;</a>|KeyedValue|0 or 1|String|__Choices__<br>true<br>false<br>|

---

### <a id="arccalculationsdif3dpersentpert_calc">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[dif3d](#arccalculationsdif3d)/[persent](#arccalculationsdif3dpersent)/[pert_calc](#arccalculationsdif3dpersentpert_calc)
#### Description of Perturbation calculation

##### How Many: 0 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arccalculationsdif3dpersentpert_calcid">&nbsp;</a>|Tag|1|String|__Choices__<br>a<br>b<br>c<br>d<br>e<br>f<br>g<br>h<br>i<br>j<br>k<br>m<br>n<br>o<br>p<br>q<br>t<br>u<br>v<br>w<br>x<br>y<br>z<br>|
depletion_step<a id="arccalculationsdif3dpersentpert_calcdepletion_step">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[0,+INF)|[required] Time step number of the REBUS depletion calculation
xs_updated<a id="arccalculationsdif3dpersentpert_calcxs_updated">&nbsp;</a>|KeyedValue|1|String|__Choices__<br>true<br>false<br>|[required] Indicate whether cross-sections will be recalculated for the perturbed state and for the reference state of depletion_step>0
pert_type<a id="arccalculationsdif3dpersentpert_calcpert_type">&nbsp;</a>|KeyedValue|1|String|__Choices__<br>keff<br>lambda_beta<br>|
[material_perturbation](#arccalculationsdif3dpersentpert_calcmaterial_perturbation)|SubObject|0 or more|||Description of the type of perturbation on a material
[surface_perturbation](#arccalculationsdif3dpersentpert_calcsurface_perturbation)|TaggedValue|0 or more|||Description of a perturbation on a surface
pert_option<a id="arccalculationsdif3dpersentpert_calcpert_option">&nbsp;</a>|KeyedValue|0 or 1|String|__Choices__<br>first_order_pertubation_theory<br>general_perturbation_theory<br>direct<br>|[required for keff problem]

---

### <a id="arccalculationsdif3dpersentpert_calcmaterial_perturbation">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[dif3d](#arccalculationsdif3d)/[persent](#arccalculationsdif3dpersent)/[pert_calc](#arccalculationsdif3dpersentpert_calc)/[material_perturbation](#arccalculationsdif3dpersentpert_calcmaterial_perturbation)
#### Description of the type of perturbation on a material

##### How Many: 0 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arccalculationsdif3dpersentpert_calcmaterial_perturbationid">&nbsp;</a>|Tag|1|String|__InputKeys__<br>[material id](#arcgeometrymaterialsmaterialid)<br>|
list_isotopes_perturbed<a id="arccalculationsdif3dpersentpert_calcmaterial_perturbationlist_isotopes_perturbed">&nbsp;</a>|Array of Size<br>1 or more|1|String|__Choices__<br>all_from_material<br>REF:[CompNames](#ref-compnames)<br>REF:[NuclideIds](#ref-nuclideids)<br><br>__InputKeys__<br>[lumped_element_text_file id](#arccalculationsmcc3lumped_element_text_fileid)<br>|
density_perturbation_factor<a id="arccalculationsdif3dpersentpert_calcmaterial_perturbationdensity_perturbation_factor">&nbsp;</a>|KeyedValue|0 or 1|Real|__Range__<br>(0.0,+INF)|
new_temp<a id="arccalculationsdif3dpersentpert_calcmaterial_perturbationnew_temp">&nbsp;</a>|KeyedValue|0 or 1|Real|__Range__<br>(0.0,+INF)|

---

### <a id="arccalculationsdif3dpersentpert_calcsurface_perturbation">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[dif3d](#arccalculationsdif3d)/[persent](#arccalculationsdif3dpersent)/[pert_calc](#arccalculationsdif3dpersentpert_calc)/[surface_perturbation](#arccalculationsdif3dpersentpert_calcsurface_perturbation)
#### Description of a perturbation on a surface

##### How Many: 0 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arccalculationsdif3dpersentpert_calcsurface_perturbationid">&nbsp;</a>|Tag|1|String|__InputKeys__<br>[hexagon id](#arcgeometrysurfaceshexagonid)<br>[square id](#arcgeometrysurfacessquareid)<br>[cylinder id](#arcgeometrysurfacescylinderid)<br>[plane id](#arcgeometrysurfacesplaneid)<br>|
value<a id="arccalculationsdif3dpersentpert_calcsurface_perturbationvalue">&nbsp;</a>|Value|1|String|__InputKeys__<br>[hexagon id](#arcgeometrysurfaceshexagonid)<br>[square id](#arcgeometrysurfacessquareid)<br>[cylinder id](#arcgeometrysurfacescylinderid)<br>[plane id](#arcgeometrysurfacesplaneid)<br>|

---

### <a id="arccalculationsdif3dpersentsens_calc">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[dif3d](#arccalculationsdif3d)/[persent](#arccalculationsdif3dpersent)/[sens_calc](#arccalculationsdif3dpersentsens_calc)
#### Description of Sensitivity calculation

##### How Many: 0 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arccalculationsdif3dpersentsens_calcid">&nbsp;</a>|Tag|1|String|__Choices__<br>a<br>b<br>c<br>d<br>e<br>f<br>g<br>h<br>i<br>j<br>k<br>m<br>n<br>o<br>p<br>q<br>t<br>u<br>v<br>w<br>x<br>y<br>z<br>|
depletion_step<a id="arccalculationsdif3dpersentsens_calcdepletion_step">&nbsp;</a>|KeyedValue|1|Integer|__Range__<br>[0,+INF)|[required] Time step number of the REBUS depletion calculation
xs_updated<a id="arccalculationsdif3dpersentsens_calcxs_updated">&nbsp;</a>|KeyedValue|1|String|__Choices__<br>true<br>false<br>|[required] Indicate whether cross-sections will be recalculated for the perturbed state and for the reference state of depletion_step>0
sensitivity_factor<a id="arccalculationsdif3dpersentsens_calcsensitivity_factor">&nbsp;</a>|KeyedValue|1|Real|__Range__<br>(0.0,+INF)|[required] Factor by which the cross-sections are perturbed for the sensitivity analysis
sens_type<a id="arccalculationsdif3dpersentsens_calcsens_type">&nbsp;</a>|KeyedValue|1|String|__Choices__<br>keff<br>beta<br>lambda<br>|
sensitivity_regions<a id="arccalculationsdif3dpersentsens_calcsensitivity_regions">&nbsp;</a>|Array of Size<br>1 or more|1|String|__InputKeys__<br>[cell id](#arccalculationsmcc3cellid)<br>|[required] List of XS cells on which the sensitivities are calculated
list_isotopes<a id="arccalculationsdif3dpersentsens_calclist_isotopes">&nbsp;</a>|Array of Size<br>1 or more|1|String|__Choices__<br>all_from_sensitivity_regions<br>REF:[CompNames](#ref-compnames)<br>REF:[NuclideIds](#ref-nuclideids)<br><br>__InputKeys__<br>[lumped_element_text_file id](#arccalculationsmcc3lumped_element_text_fileid)<br>|[required] List of isotopes on which the sensitivities are calculated
list_reactions<a id="arccalculationsdif3dpersentsens_calclist_reactions">&nbsp;</a>|Array of Size<br>1 or more|1|String|__Choices__<br>fission<br>chi<br>capture<br>elastic<br>inelastic<br>nu<br>n2n<br>p1elastic<br>|[required] List of reactions on which the sensitivities are calculated
[material_perturbation](#arccalculationsdif3dpersentsens_calcmaterial_perturbation)|SubObject|0 or more|||Description of the type of perturbation on a material
[surface_perturbation](#arccalculationsdif3dpersentsens_calcsurface_perturbation)|TaggedValue|0 or more|||Description of a perturbation on a surface

---

### <a id="arccalculationsdif3dpersentsens_calcmaterial_perturbation">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[dif3d](#arccalculationsdif3d)/[persent](#arccalculationsdif3dpersent)/[sens_calc](#arccalculationsdif3dpersentsens_calc)/[material_perturbation](#arccalculationsdif3dpersentsens_calcmaterial_perturbation)
#### Description of the type of perturbation on a material

##### How Many: 0 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arccalculationsdif3dpersentsens_calcmaterial_perturbationid">&nbsp;</a>|Tag|1|String|__InputKeys__<br>[material id](#arcgeometrymaterialsmaterialid)<br>|
list_isotopes_perturbed<a id="arccalculationsdif3dpersentsens_calcmaterial_perturbationlist_isotopes_perturbed">&nbsp;</a>|Array of Size<br>1 or more|1|String|__Choices__<br>all_from_material<br>REF:[CompNames](#ref-compnames)<br>REF:[NuclideIds](#ref-nuclideids)<br><br>__InputKeys__<br>[lumped_element_text_file id](#arccalculationsmcc3lumped_element_text_fileid)<br>|
density_perturbation_factor<a id="arccalculationsdif3dpersentsens_calcmaterial_perturbationdensity_perturbation_factor">&nbsp;</a>|KeyedValue|0 or 1|Real|__Range__<br>(0.0,+INF)|
new_temp<a id="arccalculationsdif3dpersentsens_calcmaterial_perturbationnew_temp">&nbsp;</a>|KeyedValue|0 or 1|Real|__Range__<br>(0.0,+INF)|

---

### <a id="arccalculationsdif3dpersentsens_calcsurface_perturbation">&nbsp;</a>[/](#root_anchor)[arc](#arc)/[calculations](#arccalculations)/[dif3d](#arccalculationsdif3d)/[persent](#arccalculationsdif3dpersent)/[sens_calc](#arccalculationsdif3dpersentsens_calc)/[surface_perturbation](#arccalculationsdif3dpersentsens_calcsurface_perturbation)
#### Description of a perturbation on a surface

##### How Many: 0 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="arccalculationsdif3dpersentsens_calcsurface_perturbationid">&nbsp;</a>|Tag|1|String|__InputKeys__<br>[hexagon id](#arcgeometrysurfaceshexagonid)<br>[square id](#arcgeometrysurfacessquareid)<br>[cylinder id](#arcgeometrysurfacescylinderid)<br>[plane id](#arcgeometrysurfacesplaneid)<br>|
value<a id="arccalculationsdif3dpersentsens_calcsurface_perturbationvalue">&nbsp;</a>|Value|1|String|__InputKeys__<br>[hexagon id](#arcgeometrysurfaceshexagonid)<br>[square id](#arcgeometrysurfacessquareid)<br>[cylinder id](#arcgeometrysurfacescylinderid)<br>[plane id](#arcgeometrysurfacesplaneid)<br>|

---

### <a id="lumped_element_external_list">&nbsp;</a>[/](#root_anchor)[lumped_element_external_list](#lumped_element_external_list)
#### Description of a list of isotopes in a new lumped element

##### How Many: 0 or 1

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
[afrac](#lumped_element_external_listafrac)|TaggedValue|1 or more|||

---

### <a id="lumped_element_external_listafrac">&nbsp;</a>[/](#root_anchor)[lumped_element_external_list](#lumped_element_external_list)/[afrac](#lumped_element_external_listafrac)
##### How Many: 1 or more

Name|Type|HowMany|ValueType|Restrictions|Description
:---:|:---:|:---:|:---:|:---:|:---:
id<a id="lumped_element_external_listafracid">&nbsp;</a>|Tag|1|String|__Choices__<br>REF:[CompNames](#ref-compnames)<br>REF:[NuclideIds](#ref-nuclideids)<br>|
value<a id="lumped_element_external_listafracvalue">&nbsp;</a>|Value|1|Real|__Range__<br>[0.0,1.0]|

---

[Top Of Document](#topofdoc)

## Referenced Choice Lists<a id="referenced_choice_lists">&nbsp;</a>

### <a id="ref-compnames">&nbsp;</a>CompNames
ac225 ac226 ac227 ag107 ag109 ag110m ag111 al27 am241 am242 am242m am243 am244 am244m ar36 ar38 ar40 as75 au197 b10 b11 ba130 ba132 ba133 ba134 ba135 ba136 ba137 ba138 ba140 be7 be9 bi209 bk249 bk250 br79 br81 c ca40 ca42 ca43 ca44 ca46 ca48 cd106 cd108 cd110 cd111 cd112 cd113 cd114 cd115m cd116 ce136 ce138 ce139 ce140 ce141 ce142 ce143 ce144 cf249 cf250 cf251 cf252 cf253 cf254 cl35 cl37 cm241 cm242 cm243 cm244 cm245 cm246 cm247 cm248 cm249 cm250 co58 co58m co59 cr50 cr52 cr53 cr54 cs133 cs134 cs135 cs136 cs137 cu63 cu65 dy156 dy158 dy160 dy161 dy162 dy163 dy164 er162 er164 er166 er167 er168 er170 es253 es254 es255 eu151 eu152 eu153 eu154 eu155 eu156 eu157 f19 fe54 fe56 fe57 fe58 fm255 ga69 ga71 gd152 gd153 gd154 gd155 gd156 gd157 gd158 gd160 ge70 ge72 ge73 ge74 ge76 h1 h2 h3 he3 he4 hf174 hf176 hf177 hf178 hf179 hf180 hg196 hg198 hg199 hg200 hg201 hg202 hg204 ho165 ho166m i127 i129 i130 i131 i135 in113 in115 ir191 ir193 k39 k40 k41 kr78 kr80 kr82 kr83 kr84 kr85 kr86 la138 la139 la140 li6 li7 lu175 lu176 mg24 mg25 mg26 mn55 mo100 mo92 mo94 mo95 mo96 mo97 mo98 mo99 n14 n15 na22 na23 nb93 nb94 nb95 nd142 nd143 nd144 nd145 nd146 nd147 nd148 nd150 ni58 ni59 ni60 ni61 ni62 ni64 np235 np236 np237 np238 np239 o16 o17 p31 pa231 pa232 pa233 pb204 pb206 pb207 pb208 pd102 pd104 pd105 pd106 pd107 pd108 pd110 pm147 pm148 pm148m pm149 pm151 pr141 pr142 pr143 pu236 pu237 pu238 pu239 pu240 pu241 pu242 pu243 pu244 pu246 ra223 ra224 ra225 ra226 rb85 rb86 rb87 re185 re187 rh103 rh105 ru100 ru101 ru102 ru103 ru104 ru105 ru106 ru96 ru98 ru99 s32 s33 s34 s36 sb121 sb123 sb124 sb125 sb126 sc45 se74 se76 se77 se78 se79 se80 se82 si28 si29 si30 sm144 sm147 sm148 sm149 sm150 sm151 sm152 sm153 sm154 sn112 sn113 sn114 sn115 sn116 sn117 sn118 sn119 sn120 sn122 sn123 sn124 sn125 sn126 sr84 sr86 sr87 sr88 sr89 sr90 ta181 ta182 tb159 tb160 tc99 te120 te122 te123 te124 te125 te126 te127m te128 te129m te130 te132 th227 th228 th229 th230 th232 th233 th234 ti46 ti47 ti48 ti49 ti50 u232 u233 u234 u235 u236 u237 u238 u239 u240 u241 v w182 w183 w184 w186 xe123 xe124 xe126 xe128 xe129 xe130 xe131 xe132 xe133 xe134 xe135 xe136 y89 y91 zn zr90 zr91 zr92 zr93 zr94 zr95 zr96 

[Top Of Document](#topofdoc)

---

### <a id="ref-nuclideids">&nbsp;</a>NuclideIds
1001 1002 1003 2003 2004 3006 3007 5007 5009 5010 5011 6000 7014 7015 8016 8017 9019 11022 11023 12024 12025 12026 13027 14028 14029 14030 15031 16032 16033 16034 16036 17035 17037 18036 18038 18040 19039 19040 19041 20040 20042 20043 20044 20046 20048 21045 22046 22047 22048 22049 22050 23000 24050 24052 24053 24054 25055 26054 26056 26057 26058 27058 27059 28058 28059 28060 28061 28062 28064 29063 29065 30000 31069 31071 32070 32072 32073 32074 32076 33075 34074 34076 34077 34078 34079 34080 34082 35079 35081 36078 36080 36082 36083 36084 36085 36086 37085 37086 37087 38084 38086 38087 38088 38089 38090 39089 39091 40090 40091 40092 40093 40094 40095 40096 41093 41094 41095 42092 42094 42095 42096 42097 42098 42099 42100 43099 44096 44098 44099 44100 44101 44102 44103 44104 44105 44106 45103 45105 46102 46104 46105 46106 46107 46108 46110 47107 47109 47111 48106 48108 48110 48111 48112 48113 48114 48116 49113 49115 50112 50113 50114 50115 50116 50117 50118 50119 50120 50122 50123 50124 50125 50126 51121 51123 51124 51125 51126 52120 52122 52123 52124 52125 52126 52128 52130 52132 53127 53129 53130 53131 53135 54123 54124 54126 54128 54129 54130 54131 54132 54133 54134 54135 54136 55133 55134 55135 55136 55137 56130 56132 56133 56134 56135 56136 56137 56138 56140 57138 57139 57140 58136 58138 58139 58140 58141 58142 58143 58144 59141 59142 59143 60142 60143 60144 60145 60146 60147 60148 60150 61147 61148 61149 61151 62144 62147 62148 62149 62150 62151 62152 62153 62154 63151 63152 63153 63154 63155 63156 63157 64152 64153 64154 64155 64156 64157 64158 64160 65159 65160 66156 66158 66160 66161 66162 66163 66164 67165 68162 68164 68166 68167 68168 68170 71175 71176 72174 72176 72177 72178 72179 72180 73181 73182 74182 74183 74184 74186 75185 75187 77191 77193 79179 80196 80198 80199 80200 80201 80202 80204 82204 82206 82207 82208 83209 88223 88224 88225 88226 89225 89226 89227 90227 90228 90229 90230 90232 90233 90234 91231 91232 91233 92232 92233 92234 92235 92236 92237 92238 92239 92240 92241 93235 93236 93237 93238 93239 94236 94237 94238 94239 94240 94241 94242 94243 94244 94246 95241 95242 95243 95244 96241 96242 96243 96244 96245 96246 96247 96248 96249 96250 97249 97250 98249 98250 98251 98252 98253 98254 99253 99254 99255 100255 1027058 1047110 1048115 1052127 1052129 1061148 1067166 1095242 1095244 

[Top Of Document](#topofdoc)

---

