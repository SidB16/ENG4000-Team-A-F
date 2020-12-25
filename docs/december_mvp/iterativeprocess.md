Upon talking to stakeholders, we narrowed down our project scope by understanding the need on the ground (refer to product vision section). We did a deep dive into BVM peripherals and equipment availabilities on board a government ambulance which would transport patients to larger medical facilities from smaller ones. Below we have listed some of these components and concluded that they had all necessary components required to monitor a patients health during the journey and had a BVM available either onboard or loaned by the smaller medical setup. However, there is a need to automate the ventilation process as a single paramedic or family members cannot efficiently ensure the patient’s vitals are good while they are pumping the bag. 

Items available onboard a 108 Ambulance (relevant to our project) in Gujarat, India:
<li>Oxygen Cylinder</li>
<li>Blood Pressure detectors (sphygmomanometer)</li>
<li>AMBU/BVM (if not available onboard, borrowed from the hospital)</li>
<li>Intravenous Set</li>
<li>Pulse Oximeter</li>
<li>Medical Suction Machine</li>

BVM Components: 

A BVM has three parts: a patient connector, a self-inflating bag, and an oxygen inlet.
Optional components include a positive end-expiratory pressure (PEEP) valve, an oxygen
reservoir, and a pressure gauge[6].



Figure1: Shows the components of an AMBU/BVM including optional peripherals.
<ul>
<li>Patient Connector: This component includes an exhalation port, patient valve and patient connector port. 
<ul>
<li>Exhalation port: Serves to eliminate CO2 from the breathing circuit. Thus, it's positioned as near to the patient as possible- for more effective capture of CO2exhaled by the patient and to decrease the chance of it being washed up into the breathing circuit [7]. </li>
<li>Patient (inspiratory) valve: A unidirectional patient valve (non-rebreathing valve: NRVs) used to minimize build-up of CO2 through rebreathing their own exhaled air.</li>
<li>Patient Connector Port: A unidirectional silicone/plastic flap connected to either a venti-mask (face-mask) or an endotracheal tube to facilitate inspiration (breathing in).</li>
</ul>
</li>
</ul>
Figure 2: shows the difference between venti-mask and endotracheal tube connection.


</li>Self-inflated bag: A bag made of silicon/plastic materials that re-expands after being compressed.
It has an oxygen inlet which is connected to an oxygen cylinder or left unconnected to supply air, depending on the patient’s needs
The gas enters in the self-expanding bag through the one-way valve which restricts the flow back from the inlet [10].
When the bag is attached to an oxygen supply, oxygen delivery rate can be set between 5-12 litres per minute and provide 40-60% concentration of O2(when not connected to reservoir bag) due to potential leakage. </li>
<li>Oxygen Inlet: an inlet nipple through which air andO2is supplied.</li>
</li>Reservoir Bag: Increases theO2concentration pumped by preventing leakage
Adding a reservoir bag and running O2at 5-12 L/min raises the concentration to 100%, but only if the reservoir is allowed to fill.
 It is important to ensure that a sufficient oxygen flow rate is used so the oxygen reservoir bag does not collapse during inspiration.
They are made of latex-free material or silicone, ranging in size from 1-8L. </li>

<li>Positive End-Expiratory Pressure (PEEP) Valve: it is simply a spring-loaded valve that the patient exhales against. 
PEEP prevents ventilator-induced lung injury.
Ambu PEEP Valves are fitted directly to the patient (inspiratory) valve </li>

<li>Pressure Gauge (manometer): Can be used for monitoring Airway Pressure.</li>

On understanding the functions of each component, we concluded that we only required the self-inflating bag and the patient connector for automating the pumping mechanism.

Below is a summary of basic requirements from the automated pumping functionality(for the purpose of our MVP):
The required pump rate, i.e. the number of breaths per minute is 12-16,
Ensure the bag gets squeezed completely (ensuring maximum volume of gas pumped each time) and consistently
The amount of voltage and current to be supplied in order to provide enough torque required to achieve the previous requirement
We must ensure no damage is caused to the BVM as currently patients are charged a deposit for the BVM. It is refunded only if the BVM is undamaged during its use. Hence, the liability now lies on us.

In order to ensure the basic functional requirements were accounted for, we built evaluation criteria to judge the different design ideas explored. The criteria were as follows:

Criteria
Metric
Economic
Low-Cost (< 500 Rs?)
Mechanical
Evaluation Criteria:
Portable
Size (don’t want to be intrusive)
weight
Compression (it's able to handle/afford compression and decompression
Programmable 
Compatibility (work with many components/peripherals?)
Modifiability (parts can be replaced with different technologies)
power requirement (we want minimal/efficient)
Readily sourced
Repairable parts

Functional Constraints: 
Battery-powered 

Repeatability
Code has to be simple enough to replicate.
Medical  


Stakeholder-specified breath/min insp./exp ratio, tidal volume


We explored different ways of designing the pumping mechanism such as gear pumping, DC motor-driven pumping, pneumatic pumping and stepper motor-driven pumping with a strap. Since our team comprises of only Software and Computer Engineers and we are an Agile group, we decided to explore different design ideas via experimentation. We decided to implement the simplest approach because of expertise, time and budget constraints. We recognized that changing the hardware design in an agile fashion was not affordable as we could not keep buying new/expensive parts and increase electronic waste just for the sake of experimentation, hence, we decided to implement our design with repurposed parts.

Our current experimentation design consists of a battery-powered motor, which rotates a shaft that a displaceable arm/mould/piston is attached to, which moves in a horizontal back and forth fashion (rotational motion translated to linear motion) enabling pumping of the self-inflating bag held in place. We adjust pump speed, displacement of the arm/mould/piston by configuring the motor using a microcontroller.

We decided to use a 1.8degree 2phases Nema17 stepper motor by repurposing a damaged 3D printer as it would be able to provide us higher torque than other (readily available) motors. In order to ensure programmability of the motor, we connected it to a driver, Easy Driver (ROB-12779 by Sparkfun), borrowed from an acquaintance and an Arduino microcontroller (available at home). We used the 3D printer internal frame to access its rotational shafts. 