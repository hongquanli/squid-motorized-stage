# Squid motorized stages
![collections](collections.png)
## Stages
- 13 mm travel focus stage (ball bearing), with adapters for mounting Thorlabs SM1 lens tube
- 25 mm travel XY stage (ball bearing), with adapters for mounting glass slide or 35 mm glass bottom dish
- 50 mm travel XY stage (linear guideway with recirculating bell bearings) for the original gravity machine
- 130 mm travel X or XY stage (cross roller bearing), with kinematic well plate holder, also used for Nautilus (Octopi/Squid-based plate reader)

## Stage controller PCB
<img src="https://github.com/hongquanli/squid-motorized-stage/raw/main/driver%20stack/driver%20stack.png" width=40%>

Right now we're using a custom PCB stack for controlling the stages. The microcontroller is an Arduino Due (we intend to switch to teensy 4.1) and the stepper motor drivers are Trinamic TMC2209 SilentStepSticks (we intend to switch to using Trinamic motion controller TMC4361 + one of the Trinamic stepper drivers so that the limit switches and encoders are interfaced by the motion controllers instead of the micontroller, which will also reduce the number of GPIOs needed from the micontroller). 

The driver stack development is led by Ethan (Github repo: [link](https://github.com/prakashlab/octopi-driver-board)). Currently used the PCB and PCBA fab files can be found on the squid-imaging website [www.squid-imaging.org](www.squid-imaging.org) and in [driver stack](driver%20stack).

## Control panel
<img src="https://github.com/hongquanli/squid-motorized-stage/blob/main/control%20panel/control%20panel.png" width=40%>

## Software
The stages can be controled with the Arduino firmware and python software we have written. 

Microscope software Github repo: [link](https://github.com/hongquanli/octopi-research), simple GUI example: [link](https://github.com/hongquanli/squid-tutorials/tree/main/example_stepper_control) (we also explained how the software is written in these two short READMEs: [overview](https://github.com/hongquanli/squid-tutorials/tree/main/example_led_control), [more detailed note](https://github.com/hongquanli/squid-tutorials/tree/main/example_led_control/software)).

## References
[1] Hongquan Li, Deepak Krishnamurthy, Ethan Li, Pranav Vyas, Nibha Akireddy, Chew Chai, Manu Prakash, "**Squid: Simplifying Quantitative Imaging Platform Development and Deployment**." BiorXiv [ [repo](https://github.com/hongquanli/octopi-research) | [preprint](https://doi.org/10.1101/2020.12.28.424613) | [website](https://squid-imaging.org)]

[2] Deepak Krishnamurthy, Hongquan Li, François Benoit du Rey, Pierre Cambournac, Adam G. Larson, Ethan Li, and Manu Prakash. "**Scale-free vertical tracking microscopy.**" Nature Methods 17, no. 10 (2020): 1040-1051. [ [Github](https://github.com/deepakkrishnamurthy/gravitymachine-research) | [paper](https://www.nature.com/articles/s41592-020-0924-7) | [website](https://gravitymachine.org) ]

[3] Janie R. Byrum, Eric Waltari, Owen Janson, Syuan-Ming Guo, Jenny Folkesson, Bryant B. Chhun, Joanna Vinden, Ivan E. Ivanov, Marcus L. Forst, Hongquan Li, Adam G. Larson, Wesley Wu1, Cristina M. Tato, Krista M. McCutcheon, Michael J. Peluso, Timothy J. Henrich, Steven G. Deeks, Manu Prakash, Bryan Greenhouse, John E. Pak, Shalin B. Mehta. "**multiSero: Open multiplex-ELISA platform for analyzing antibody responses to SARS-CoV-2 infection**." bioRxiv [ [preprint](https://doi.org/10.1101/2021.05.07.21249238) | [repo](https://github.com/czbiohub/pysero)  ]
