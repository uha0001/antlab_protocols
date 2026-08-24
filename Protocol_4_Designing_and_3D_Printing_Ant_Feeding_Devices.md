# Protocol for Designing and 3D Printing Ant Feeding Devices

## Purpose

This protocol describes the workflow used to design, prepare, and print a removable feeding system for ants housed in 15 mL centrifuge tubes.

The feeding system consists of two main parts:

- a **cap** that fits into the opening of a 15 mL centrifuge tube
- a **removable feeding slider/spoon** that passes through the cap and allows food to be added or removed without opening the tube completely

The components are designed as CAD models, exported as STL files, sliced in Bambu Studio, and printed using a Bambu Lab P1S 3D printer.

The design is iterative. Dimensions may need to be adjusted depending on the centrifuge tubes, filament, printer tolerances, ant species, and desired feeding volume.

---

## 1. Materials and Software

### Hardware

- Bambu Lab P1S 3D printer
- 0.4 mm nozzle
- PLA filament
- Textured PEI build plate
- Computer
- microSD card and card reader
- 15 mL centrifuge tubes
- Calipers, if available
- Fine tweezers or flush cutters for removing supports when needed

### Software

- **FreeCAD** for designing or modifying the CAD model
- **Bambu Studio** for preparing and slicing the model for printing

---

## 2. General Workflow

The complete workflow is:

**CAD design → STL export → Bambu Studio → slicing → `.gcode.3mf` → microSD card → Bambu Lab P1S → physical testing**

The CAD model contains the actual geometry and dimensions of the feeder.

The STL file is an exported mesh representation of the CAD model.

Bambu Studio converts the STL into printer instructions.

---

## 3. Designing the Cap in FreeCAD

### 3.1 Create the Basic Cap

1. Open **FreeCAD**.
2. Create a new document.
3. Switch to the **Part Design** workbench.
4. Create a new **Body**.
5. Create a **Sketch** on an appropriate plane.
6. Draw a circle representing the part of the cap that will enter the centrifuge tube.
7. Constrain the diameter of the circle.

The diameter should initially be based on the measured internal diameter of the tube.

Because both 3D printers and centrifuge tubes have manufacturing tolerances, the nominal CAD measurement may not produce the desired physical fit. It is therefore useful to print several test versions before finalizing the design.

For the currently tested 15 mL tubes, a **14.8 mm plug diameter** produced the preferred fit.

8. Close the sketch.
9. Use **Pad** to extrude the circular profile.

A plug length of approximately **8 mm** is sufficient for the current design.

---

## 4. Adding the External Flange

The cap should contain a flange that remains outside the centrifuge tube.

This prevents the cap from being pushed completely into the tube and provides a surface that can be handled easily.

1. Create a second circular sketch on the outer end of the cap.
2. Make this circle larger than the tube-opening diameter.
3. Pad the sketch by approximately 2 mm.

For the current prototype, the flange diameter is approximately **18 mm**.

The resulting part should resemble a short cylindrical plug with a wider rim at the outside end.

---

## 5. Creating the Feeding-Slider Opening

A rectangular passage must pass through the cap to accommodate the removable feeding slider.

1. Create a sketch on the front or side face of the cap.
2. Draw a rectangle corresponding to the required slider opening.
3. Position the opening toward the lower portion of the cap, leaving sufficient material above it for ventilation holes.
4. Constrain the dimensions of the opening.
5. Use **Pocket** to cut the opening completely through the cap.

The opening should be slightly larger than the slider.

It should provide enough clearance for the slider to move when deliberately pushed or pulled, but not so much clearance that the slider moves freely under its own weight.

The feeding end of the current slider is wider than the central rail, so the passage must also be wide enough for the feeding station to pass through.

---

## 6. Adding the External Slider Guide

An external guide can be added to the outside of the cap to keep the slider aligned.

1. Create a rectangular sketch surrounding the slider opening.
2. Pad this geometry outward from the cap.
3. Leave the centre open so the slider can travel through the guide.

The external guide should keep the slider approximately parallel to the tube.

It also increases the contact area between the cap and slider and can improve stability.

---

## 7. Adding Ventilation Holes

Ventilation openings are added above the slider passage.

The holes must satisfy two competing requirements:

- they must print reliably
- they must be small enough to prevent ants from escaping

Very small holes may be present in the CAD model but become partially or completely closed during FDM printing.

The initial **0.6 mm holes** were difficult to produce reliably, so larger nominal hole diameters were tested.

The current ventilation test uses:

- **1.4 mm nominal hole diameter**
- **12 holes**
- arranged in approximately **3 rows × 4 columns**

These dimensions should **not automatically be considered escape-proof**.

The actual printed openings must be checked with the ant species being used.

For *Lasius niger*, the cap should first be tested with a small number of workers under observation before being used with a full colony.

---

## 8. Designing the Feeding Slider

The slider is modeled as a separate FreeCAD Body.

### 8.1 Main Rail

1. Create a new **Body**.
2. Create a rectangular sketch.
3. Define the width and length of the main rail.
4. Use **Pad** to give the slider its thickness.

The slider should be long enough that one end remains outside the cap while the feeding station is positioned inside the tube.

The current design has a total length of approximately **40 mm**.

---

## 9. Creating the Feeding Spoon

The inner end of the slider contains the feeding station.

Rather than making the entire slider wider, a circular or widened section is added to the end.

1. Create a sketch at the inner end of the slider.
2. Draw a circular feeding platform.
3. Pad the feeding platform to the same height as the slider.

The current design uses a feeding platform approximately:

- **10 mm in diameter**

The feeding platform should be large enough for ants to access the food but small enough to pass through the cap opening.

---

## 10. Creating the Feeding Well

A recess is cut into the feeding platform to hold liquid or semi-liquid food.

1. Create a circular sketch on the upper surface of the feeding platform.
2. Use **Pocket** to create a shallow bowl.

The well should not pass completely through the slider.

For the current slider:

- slider thickness: approximately **2.6 mm**
- feeding recess depth: approximately **1.8 mm**
- remaining floor thickness: approximately **0.8 mm**

The deeper recess was introduced after prototype testing indicated that a larger feeding volume would be preferable.

If the feeding well is made too deep, the remaining floor may become fragile or print inconsistently.

---

## 11. Adding a Mechanical Stop

The slider should not be capable of being accidentally pushed completely into the centrifuge tube.

A physical stop is therefore added to the outer part of the slider.

1. Create a wider section on the slider.
2. Make this section wider than the cap passage.
3. Position it so that it contacts the external cap guide when the feeding spoon reaches the intended internal position.

The stop should physically prevent further insertion.

The stop geometry should also have a **flat lower surface** so the slider can be printed directly on the build plate without floating geometry.

An earlier prototype contained geometry extending below the main slider plane and produced a floating/cantilever warning in Bambu Studio. This was corrected by flattening the entire underside of the slider.

---

## 12. Checking the CAD Model Before Export

Before exporting the model:

1. Inspect it from several angles.
2. Confirm that all parts are connected properly.
3. Confirm that no section of the model is floating.
4. Confirm that the bottom surface intended for printing is flat.
5. Check that the feeding spoon can physically pass through the cap opening.
6. Confirm that the mechanical stop is wider than the opening.
7. Confirm that ventilation holes do not intersect the slider passage.

It is useful to keep the **cap and slider as separate CAD bodies or files** so each can be printed and modified independently.

---

## 13. Exporting the Model as an STL

Once the design is complete:

1. Select the finished **Body** in the FreeCAD model tree.
2. Go to:

   **File → Export**

3. Select **STL Mesh (`.stl`)** as the file type.
4. Save the file with a descriptive name.

Example filenames:

- `ant_feeder_cap_14.8mm.stl`
- `ant_feeder_slider_2.6mm.stl`

The cap and slider should normally be exported as separate STL files.

This makes it easier to test different combinations of cap diameter and slider thickness.

---

## 14. Importing the STL into Bambu Studio

1. Open **Bambu Studio**.
2. Select:

   **Bambu Lab P1S**

3. Confirm the nozzle size:

   **0.4 mm**

4. Select the appropriate PLA filament profile.
5. Import the STL file.

The model should appear on the virtual build plate.

---

## 15. Orienting the Model

The component should be placed so that the largest suitable flat surface contacts the build plate.

For the slider, the flat underside should face downward.

For the cap, select an orientation that minimizes unsupported internal geometry while maintaining good print quality.

Use **Lay on Face** if necessary.

Before continuing, check that Bambu Studio does not report:

- floating objects
- unsupported floating sections
- model intersections

A floating or unsupported warning should not automatically be ignored.

If a component cannot be placed flat without generating floating geometry, return to the CAD model and modify the design if possible.

Designing the part to print without support is generally preferable for these small functional components.

---

## 16. Slicing Settings

For routine functional prototypes, the following settings are suitable:

- Printer: **Bambu Lab P1S**
- Nozzle: **0.4 mm**
- Material: **PLA**
- Layer height: approximately **0.20 mm**
- Build plate: textured PEI
- Supports: disabled unless necessary

A smaller layer height can be used if greater detail is required, but this is generally unnecessary for the feeder components.

After selecting the settings, press:

**Slice Plate**

---

## 17. Inspecting the Sliced Model

Before exporting the print file, inspect the sliced model in Bambu Studio.

Check:

- whether the feeding well is clearly present
- whether the ventilation holes remain open
- whether the slider channel is continuous
- whether thin walls have disappeared
- whether unsupported areas are present
- whether the model is fully attached to the build plate

This is particularly important for small ventilation holes, because geometry that exists in the STL may not survive the slicing process.

---

## 18. Exporting the Sliced Print File

Once the sliced model looks correct:

1. Select **Export plate sliced file**.
2. Save the file as:

   `.gcode.3mf`

3. Copy the resulting file to the microSD card.
4. Safely eject the microSD card.
5. Insert it into the Bambu Lab P1S.

---

## 19. Printing

Select the desired file from the printer interface and begin the print.

The P1S may perform several preparation steps before printing, including:

- heating
- homing
- bed leveling
- purging filament

For PLA, typical temperatures used during the prototype prints were approximately:

- nozzle: **220°C**
- build plate: **55°C**

Do not touch the nozzle or build plate while hot.

Observe the first layers to confirm that the model is adhering properly.

---

## 20. Removing the Printed Part

After printing, allow the build plate to cool.

PLA generally releases more easily from the textured PEI plate once the plate temperature decreases.

Ideally wait until the bed is below approximately **35–40°C**, or near room temperature.

If necessary:

1. Remove the build plate.
2. Flex it gently.
3. Lift the component from the surface.

Avoid forcing the print from a hot build plate.

---

## 21. Fit Testing

Do not immediately produce large numbers of components.

Test one prototype first.

### Cap

Insert the cap into the centrifuge tube.

The cap should:

- enter with light or moderate pressure
- remain securely in place
- show little or no wobbling
- not fall out when the tube is moved
- remain removable without excessive force

Several cap diameters were tested during development.

For the currently tested tubes, **14.8 mm produced the preferred fit**.

Because tube dimensions can vary between manufacturers and batches, the fit should be rechecked if a different tube type is used.

---

## 22. Slider Testing

Insert the slider into the cap.

The slider should:

- move when deliberately pushed or pulled
- remain stationary when released
- not slide inward under its own weight
- move without excessive force
- stop before the entire slider can enter the tube

Different slider thicknesses may be printed to determine the appropriate friction fit.

The current design uses approximately **2.6 mm thickness**.

---

## 23. Biological Testing

Mechanical fit alone is not sufficient.

Before using the device with an experimental colony:

1. Place a small number of workers in a test tube.
2. Install the printed cap and feeder.
3. Observe the ants.
4. Check whether ants can access the feeding well easily.
5. Check whether ants become trapped around the slider.
6. Confirm that they cannot move the feeder unexpectedly.
7. Check all ventilation holes and gaps for escape attempts.
8. Confirm that the feeding well holds an adequate volume.

If a worker can partially pass through a ventilation opening, the design should be considered unsuitable until modified.

This small-scale test should be completed before printing large numbers of feeders.

---

## 24. Iterative Modification

The feeder should be treated as an iterative prototype.

After each test, record:

- version number
- cap diameter
- slider thickness
- feeding-well dimensions
- ventilation-hole dimensions
- filament/material
- print settings
- observed problems
- modifications made

Example version history:

| Version | Modification |
|---|---|
| V4 | Initial functional cap and sliding feeder |
| V5 | Shorter feeding spoon, larger feeding station, and mechanical stop |
| V5b | Slider modified to have a completely flat print surface |
| V5c | 2.6 mm slider with 1.8 mm deep feeding well |
| Current cap | 14.8 mm plug diameter with enlarged ventilation-hole test |

Keeping a version history is useful because multiple prototypes may look almost identical after printing, despite having different dimensions.

---

## 25. Batch Production

Only begin batch production once the final design has passed both mechanical and biological testing.

In Bambu Studio:

1. Import the final STL.
2. Select the object.
3. Duplicate it using **Clone/Add Copies**.
4. Use **Arrange** to distribute copies across the build plate.
5. Slice the complete plate.
6. Check total filament consumption and print time.
7. Print one complete batch first.
8. Check several parts from that batch for consistent dimensions.
9. Proceed with additional batches if the fit remains consistent.

For larger-scale production, keep the finalized STL files unchanged and clearly labeled so all printed components originate from the same design version.
