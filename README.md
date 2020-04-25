# easyeda_multichannel
Python script allowing multi-channel design in EasyEDA.
Script is already capable of generating multi-channel PCB matched with the schematic.
Works with EasyEDA 6.3.39 (the version where global unique identifiers are introduced).

# Installation
Python 3.6 (or compatible version) is required. No additional modules are used.

# How to use
1. Split your design into 2 separate projects:
- One with a single channel (schematic and PCB). Schematic shall contain only 1 sheet.
- One with the rest of your design.

2. Download both projects, unzip them and put to the same directory as the script.
Copy **config.py.template** as your local **config.py** and edit it. Set desired file names,
channel names, PCB offset X and Y, then run the script.

3. Open the generated output schematic and PCB with EasyEDA. Preferrably save as a new project.
Try to update PCB from schematic in order to check whether they match.

# Maintaining your design
Make changes to your original projects (channel and main), then use the script to generate final version.

Script will update all of the channel prefixes, net names, etc, by adding an underscore and a channel name.
For example, a part named **U1** will become **U1_CH1**, **U1_CH2** in the output design. Only power/ground ports remain
unmodified.

# Known Issues
- Some dummy warnings are produced (to be improved in future)
- PCB text labels remain unupdated until modified by user
