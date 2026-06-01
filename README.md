# 3D Printing and Modeling - Final Project
### 🌊 Kinetic Sculptures: Mechanical Water Droplet

This repository contains the final project for the **3D Printing and Modeling** course (2025-2026). 

🔬 [About](#-about) | 📐 [Design & Contribution](#-design--contribution) | ⚙️ [Movement & Simulation](#%EF%B8%8F-movement--simulation) | 🖨️ [Printability & Tolerances](#%EF%B8%8F-printability--tolerances) | 📎 [Components & Files](#-components--files)

---

## 🔬 About

### Course Objectives:
* Development of 3D Modeling and CAD prototyping skills inside Autodesk Fusion 360.
* Understanding parametric design principles and mechanical assemblies.
* Designing functional parts with strict printability and mechanical constraints.
* Simulating physical assemblies using constraints, motion links, and motion studies.

### Project Description:
This project is a functional, 3D-printable kinetic sculpture designed inside Fusion 360. It replicates the organic movement of a water droplet ripple or an acoustic wave using a purely mechanical assembly. By rotating a central crank handle, a sequential series of eccentric cams/disks pushes an array of vertical push-rods upward in a precise wave-like phase shift, which in turn drives a series of concentric top rings.

---

## 📐 Design & Contribution

### Inspiration Sources:
The design was inspired by DIY cardboard automation mechanisms found online:
* *3D printing a Mechanical Water droplet* (Inspired by YouTube references: XYdF-B0r_V0 & A-rVbZ-GepY)

### My Design Contribution (Redesign Process):
While inspired by cardboard mockups, translating a dynamic mechanism from cardboard (a flexible, forgiving material glued with hot glue) into a precise, rigid, digital CAD model required heavy redesigning:
1. **Structural Rigidity:** Re-engineered the open frame into a rigid, self-supporting pillar system (`baza+laterale`) with a centralized internal guide plate (`sertar_mij`) to prevent the rods from buckling or tilting.
2. **From Cardboard to Solid Bodies:** Designed custom parametric thicknesses for all concentric circles (`Cercuri_superioare`) and the drive shaft cams to withstand physical material stress.
3. **Contact Optimization:** Modified the bottom tip of the vertical push-rods into spherical/rounded profiles. Cardboard designs use flat joints which create high friction and lock up; rounded contact points ensure smooth tangential sliding over the cam surfaces.
4. **CAD Organization:** Cleaned, renamed, and modularized the Browser Tree into dedicated sub-assemblies (e.g., grouping the upper rings and vertical rods) ensuring a professional project structure.

---

## ⚙️ Movement & Simulation

The mechanism requires integrated complex motions to accurately mimic wave propagation:

* **Joints Defined:** * `Revolute Joint` on the main crank shaft (`bara_32cm` & `Maner`) to allow constant rotation.
  * `Slider Joints` on the vertical rods (`Bar_vert`) allowing them to guide smoothly up and down.
  * `Slider Joints` on the upper rings (`Cercuri_sup`) allowing them to guide smoothly up and down.
* **Tangent Relationships:** Implemented precise geometric tangent relationships between the tip of each vertical rod and its corresponding eccentric drive disc to map out the exact wave profile physically.
* **Motion Link:** Created an interconnected kinematic motion link (`Assemble -> Motion Link`) linking the crank shaft's rotary movement to the linear motion of the guide rods ($360^\circ$ rotation $\rightarrow$ specific linear stroke amplitude in mm). *Note: Due to Fusion 360's over-constraint safety protocols with combined mathematical links and non-linear geometric tangents, the link is preserved in the history tree under 'Relationships' and suppressed where needed to avoid software freeze.*
* **Motion Study:** Configured a native Motion Study timeline animation executing a continuous loop ($0^\circ \rightarrow 360^\circ \rightarrow 720^\circ$) to simulate the automated kinetic sequence without needing manual mouse dragging.

---

## 🖨️ Printability & Tolerances

Although printing is optional, the model was engineered strictly from a **Design-for-Additive-Manufacturing (DfAM)** perspective:

* **Support Minimization:** The main base plate, structural pillars, and concentric top rings are designed to be printed flat on the build plate, completely removing the need for support material on those components.
* **Chamfers and Fillets:** Added safety fillets on the large outer base profile to distribute impact stresses and eliminate sharp edges. 

---

## 📎 Components & Files

### Components Used:
1. **`baza+laterale` (Main Base Frame):** Serves as the stable foundation and holds the horizontal rotating shaft.
2. **`bara_32cm` (Crank Shaft Assembly):** Houses the array of phased eccentric disks/cams that generate the mechanical wave.
3. **`Cercuri_mici` (Mechanism small circles):** the circles that rotate with the crank and lift/lower the push-rods.
4. **`Bar_vert` (Push-Rods Array):** Translates the rotary cam action into vertical linear motion.
5. **`Cercuri_superioare` (Concentric Wave Rings):** The final visual output that represents the undulating water ripple.

### Included Project Files:
* `montare_finala.f3d` - Full parametric Autodesk Fusion 360 Project File.
* `*.stl` files - Exported print-ready meshes for each structural component.
* `*.gcode` files - Sliced files tailored with appropriate print orientations.

---

## 📐 Resources & Credits

* 📹 **Functional Demo Video:** [(https://youtu.be/YVgBpsRyGC8)]
* 📦 Inspiration Reference: Mechanical Water Droplet Automaton Concepts.
