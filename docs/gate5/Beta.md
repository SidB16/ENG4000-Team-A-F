<h1> Beta Release Description </h1>

The original purpose of our Beta Release was to create the first iteration of our final product design, recognizing that the final product would require fine tuning. Due to delays in the delivery of the pneumatic components of our product, we have had to modify our plans to make do with the parts that we had received.  


The automated BVM is controlled by relaying voltages to the 5/2 valve.  The solenoid in the valve moves back and forth depending on the voltage it receives at the port. When the voltage sent into the 5/2 valve is 24 V, the solenoid contracts, causing air to be directed from the 4 outlet.


<img src="https://github.com/SidB16/ENG4000-Team-A-F/blob/main/docs/gate4/Images/Festo_Design.png" alt="Italian Trulli">

When the voltage sent in is 0V, the solenoid retracts, causing air to be directed from the 2 outlet.  This causes the piston in the cylinder to move back and forth, which compresses the BVM.  

Since we have had access to the electronic components of our product, we have prepared them in advance of the final assembly.  Specifically, we have created a voltage control relay which can send 24V signals through a load for a programmable duration.  This relay, a RPi Relay Board, is controlled by a Raspberry Pi 4 Model B.  

The voltage control is at the heart of the operation of the automatic-BVM, since varying the duration of time of the voltage levels sent to the 5/2 Valve allows one to control the pumping rate of the piston.  For our beta release, we made sure that we would be able to send 24V and 0V out of a (name of relay board) for different durations that could be programmed into the Raspberry Pi.  To test this out, we built a simple circuit that would light up an LED for a set duration.  We also measured the output voltage across the resistor coming out of the relay.  
It toggled back and forth between the voltage input by the supply and zero volts as expected.

The goal is to modify the durations of the voltage levels through experimentation to get the piston to pump the bag at the desired rate of 14-20  breaths/min.  This will be done once the rest of the parts have been connected/assembled.  


Here is an electrical diagram of the voltage control.  