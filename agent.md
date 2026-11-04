# Project Document Editing Guidance

Keep the HLDD aligned with the two-axis sensorized balance assessment platform
shown in the project block diagram and circuit diagrams.

## Required framing and section structure

- Use a descriptive project heading that identifies both the balance platform
  and its foot-load sensing, with belt-driven two-axis motion and dual-controller
  architecture reflected in the subtitle where useful.
- In the introduction, Section 2.1 should describe the relevant industrial or
  laboratory balance-assessment setup and state the project's identified gap.
  Phrase the gap as a project design need unless a market survey substantiates
  broader claims about commercial products.
- Consolidate former Sections 2.2 and 2.3 into one heading: **Proposed
  Innovation and Gap-Closing Approach**. Explain how the proposed architecture
  addresses the stated gap.
- Keep the Executive Abstract substantive: summarize the platform, two foot
  force sensors, two belt-driven axes, homing, controllers, UART, intended use,
  unresolved validation work, and future algorithm.
- Preserve the load-to-motion algorithm as an explicit future-work placeholder;
  do not invent decision logic or imply unvalidated automatic behavior.

## Project architecture facts to preserve

- Two stacked linear stages provide orthogonal, belt-driven platform motion.
- Each axis uses a PR86HS155-6004 stepper motor driven by a DM556 driver.
- Inductive proximity sensors provide homing/limit detection.
- Two sensors under the respective foot positions measure relative loading; exact
  force values are not the current objective. Sensor type, range, conditioning,
  calibration, and overload behavior require evaluation.
- Use 150 kg as the initial maximum participant mass design target (about
  1.47 kN static weight). Apply a preliminary 1.5--2 system-level overload
  factor (about 2.2--2.9 kN total) to structural/load-path design; do not claim
  that this is the rating of a sensor element or film.
- Compare the commercial Tekscan FlexiForce A201 option, which has nominal
  ranges up to 445 N per element and therefore needs an engineered multi-element
  load path, with a custom Velostat/Linqstat pad. Include analog conditioning,
  calibration, and overload/range validation; a sensor matrix additionally
  requires multiplexed acquisition and diagram updates.
- The Arduino Uno/TFT is the operator/display-side controller. The STM32
  controller handles motor drives, homing inputs, and sensor acquisition; UART
  carries commands, readings, and status.
- Check written architecture claims against the diagrams. Where the diagrams
  disagree with the text, flag the discrepancy and identify the needed diagram
  change instead of silently claiming they match.
- Current known diagram mismatches to keep visible until corrected: the raster
  block diagram has generic controller names and one pressure sensor while the
  circuit identifies Arduino Uno/STM32 and depicts two sensor elements labeled
  YL-83; verify their exact model and suitability as foot-load sensors. The
  editable Draw.io source labels a 12 V motor rail while the raster block and
  circuit indicate 24 V. The final diagrams must also show sensor signal
  conditioning.
- Treat motor, belt, supply, and load calculations as preliminary until the
  actual stage mass, dynamic torque, driver supply requirements, and safety
  limits are verified. Do not characterize this prototype as a clinical device.
