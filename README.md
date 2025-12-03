# AuxBlockSVG

[AuxBlock.SVG](AuxBlock.svg)

This is an SVG (Scalable Vector Graphics, an internet graphics format) which shows how
the Sea King Auxiliary Hydraulic control block (Aux Block) operates. It is drawn completely with
native SVG graphics (no bitmaps), a grouped by component. Javascript is used to allow
the Aux Block to respond to inputs as follows:
- Aux Pressure can be turned on / off;
- Beeper Trim can be turned on / off;
- The Control Input can be dragged left and right;
- ASE input can be set proportionally; and
- The trim can be adjusted left or right.
  
This project came about as a result of investigating the use of the original Sea King
Operational Flight and Tactics Trainer (OFTT) as a working display item in the 
Shearwater Aviation Museum. The OFTT uses the real aircraft Aux Block, and it was quickly
determined that it is not feasible to use hydraulics in a museum environemnt. Therefore,
the Aux Block will have to be replicated using electrical actuators. To do that, a
thourough understanding of how the Aux Block operates is required, and thus it was decided
create a simulation of it. Creating the simulation with the ability to web serve it means
it may be used in the future as an interpretive item by itself.

This represents a single fore and aft, or lateral, Aux Block channel. Roll and collective
channels are simpler in that they do not contain a trim (the Beeper Trim only operates on
pitch and roll). The Aux Block operates as follows:
- the Bypass Valve is held open by a spring, allowing the Power Piston to freely move, until
  Aux Pressure closes it;
- the Control Input is connected to the flight controls and moved by them;
- movement of the Control Input is linked to the pilot valve through control links. If the
  Control Input is moved passed the limits imposed by the Pilot Valve (such as during no
  Aux Pressure) it will directly move the Power Piston (resulting in much greater flight
  control weights);
- displacing the Pilot Valve will allow Aux Pressure to move the Power Piston, amplifying
  flight control input force;
- the Power Piston is further connected through the mixing unit, Primary Servos (except
  for the YAW channel), and rotary couplings (swash plate for the main rotor) to change
  the pitch of the main and tail rotor blades as required;
- the ASE provides a reduced pressure to one side of the Pilot Valve and moves it against
  spring force, allowing reduced authority activation of the Power Piston; and
- Beeper Trim pressure holds the Beeper Trim Piston in place, allowing the centering
  springs to return the cyclic (pitch and roll) stick to the selected trimmed position
  in the absence of a pilot input. When Beeper Trim pressure is removed (via a loss of
  Aux Pressure or selecting it off) the Beeper Trim valves allow reverse flow, and thus
  the Beeper Trim Piston moves freely, and no centering force is applied.

To replicate this electrically:
- the Power Piston can be replaced by an electrical linear induction motor;
- the Pilot Valve can be replaced by microswitches activated by the control linkages;
- the ASE Valve can be removed and directly mixed with the microswitches to the linear
  actuator;
- the Beeper Trim Psiton can be replaced with a belt assembly, driven by an electrical
  motor through a worm gear (to lock it) and magnetic clutch (to allow Beeper Trim to
  be off).

It is also possible to model the mixing unit, but doing so will require a 3D web
capable modelling package, as it is not possible to understand the functioning of
the mixing unit as a whole in two dimensions.
