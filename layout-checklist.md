# Layout review checklist

## General

* [x] [Schematic review](schematic-checklist.md) complete and signed off, including pin swaps done during layout
* [x] Layout DRC 100% clean

## Decoupling

* [x] Decoupling caps as close to power pins as possible
* [x] Low inductance mounting used for decoupling (prefer ViP if available, otherwise "[]8" shaped side vias

## DFM / yield enhancement

* [x] All design rules within manufacturer's capability
* [x] Minimize use of vias/traces that push fab limits
* [x] Controlled impedance specified in fab notes if applicable
* [ ] Confirm impedance calculations include soldermask, or mask removed from RF traces
* [x] Stackup verified with manufacturer and specified in fab notes
* [x] Board finish specified in fab notes
* [x] If panelizing, add panel location indicators for identifying location-specific reflow issues
* [x] (recommended) Layer number markers specified to ensure correct assembly
* [x] Fiducials present (on both sides of board) if targeting automated assembly
* [x] Fiducial pattern asymmetric to detect rotated or flipped boards
* [x] Soldermask/copper clearance on fiducials respected
* [x] Panelization specified if required

## Footprints

* [x] Confirm components are available in the selected package
* [x] Confirm components (especially connectors and power regulators) are capable of desired current in the selected package
* [x] Verify schematic symbol matches the selected package
* [x] Confirm pinout diagram is from top vs bottom of package
* [ ] (recommended) PCB printed 1:1 on paper and checked against physical parts
* [x] 3D models obtained (if available) and checked against footprints
* [ ] Soldermask apertures on all SMT lands and PTH pads

## Differential pairs
* [x] Routed differentially
* [x] Skew matched
* [x] Correct clearance to non-coupled nets

## High-speed signals

* [x] Sufficient clearance to potential aggressors
* [x] Length matched if required
* [x] Minimize crossing reference plane splits/slots or changing layers, use caps/stitching vias if unavoidable
* [x] Confirm fab can do copper to edge of PCB for edge launch connectors
* [x] Double-check pad width on connectors and add plane cutouts if needed to minimize impedance discontinuities

## Power
* [x] Minimal slots in planes from via antipads
* [x] Sufficient width for planes/traces for required current

## Sensitive analog
* [ ] Guard ring / EMI cages provided if needed
* [ ] Physically separated from high current SMPS or other noise sources
* [ ] Consider microphone effect on MLCCs if near strong sound sources

## Mechanical
* [ ] Confirm all connectors to other systems comply with the appropriate mechanical standard (connector orientation, key position, etc)
* [ ] LEDs, buttons, and other UI elements on outward-facing side of board
* [ ] Keep-outs around PCB perimeter, card guides, panelization mouse-bites, etc respected
* [ ] Stress-sensitive components (MLCC) sufficiently clear from V-score or mouse bite locations, and oriented to reduce
bending stress
* [ ] Clearance around large ICs for heatsinks/fans if required
* [ ] Clearance around pluggable connectors for mating cable/connector
* [ ] Clearance around mounting holes for screws
* [ ] Plane keepouts and clearance provided for shielded connectors, magnetics, etc
* [ ] Confirm PCB dimensions and mounting hole size/placement against enclosure or card rack design
* [ ] Verify mounting hole connection/isolation
* [ ] Components not physically overlapping/colliding
* [ ] Clearance provided around solder-in test points for probe tips

## Thermal

* [ ] Thermal reliefs used for plane connections (unless via is used for heatsinking)
* [ ] Solid connections used to planes if heatsinking
* [ ] Ensure thermal balance on SMT chip components to minimize risk of tombstoning

## Solder paste

* [ ] No uncapped vias in pads (except low-power QFNs where some voiding is acceptable)
* [ ] QFN paste prints segmented
* [ ] Small pads 100% size, larger pads reduced to avoid excessive solder volume
* [ ] No paste apertures on card edge connectors or test points

## Solder mask

* [ ] Confirm SMD vs NSMD pad geometry
* [ ] Adequate clearance around pads (typ. 50 um)

## Silkscreen

* [ ] Text size within fab limits
* [ ] Text not overlapping drills or component pads
* [ ] Text removed entirely in, or moved outside of, high component/via density areas
* [ ] Traceability markings (rev, date, name, etc) provided
* [ ] Silkscreen box provided for writing/sticking serial number
* [ ] Text mirrored properly on bottom layer
* [ ] Test points labeled if space permits

## Flex specific
* [ ] Components oriented to reduce bending forces
* [ ] Teardrops on all wire-to-pad connections

## CAM production
* [ ] KiCAD specific: rerun DRC and zone fills before exporting CAM files to ensure proper results
* [ ] Export gerber/drill files at the same time to ensure consistency
* [ ] Visually verify final CAM files to ensure no obvious misalignments
