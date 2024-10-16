# Automated Channel Controller

**Automated Channel Controller** is a LabVIEW-based application designed to automate and control multiple analog and digital channels for measurement and output. The program utilizes DAQmx for the configuration and management of signals across different channels, making it suitable for users who need precise control over hardware channels in their setups.

## Features:
- **Analog Input (AI)**: Reads data from several analog input channels.
- **Analog Output (AO)**: Generates signals for analog output channels.
- **Digital Input (DI)**: Reads digital data from specified channels.
- **Digital Output (DO)**: Writes boolean values to digital output channels.
- **User-Friendly GUI**: A simple graphical user interface (GUI) allows users to easily manage the status of channels, control input/output settings, and monitor data in real-time.

## Components:
- **Analog Input Module**: 
  - Configures and reads data from multiple analog input channels using the `Dev/ai` channels.
  - Supports different acquisition rates and modes, which are adjustable by the user.
  - The values are displayed in the GUI for monitoring.
  
- **Analog Output Module**: 
  - Controls the output of analog signals on specified `Dev/ao` channels.
  - The program allows the user to define the output waveform or constant values to be applied.

- **Digital Input and Output**:
  - The digital I/O section enables reading boolean values from digital input channels (`Dev/port` lines) and writing values to output ports.
  - This is useful for triggering actions or responding to external digital signals.

- **Control Loops**:
  - Each operation (AI, AO, DI, DO) is enclosed in a loop structure to allow continuous acquisition or generation of signals.
  - The loops run until the user stops them using the GUI controls.

## How It Works:
1. **Analog Input (AI)**:
   - The program reads data from the selected analog input channels (e.g., `Dev1/ai0`), which can be configured using the dropdown menu in the GUI.
   - The sampled data is displayed in real-time in the corresponding indicators.

2. **Analog Output (AO)**:
   - The user can select an analog output channel (e.g., `Dev1/ao0`) and define the value or waveform they want to output.
   - The output is continuously applied as long as the program is running or until the user stops the loop.

3. **Digital Input/Output (DI/DO)**:
   - The program reads digital signals from specific digital input lines and displays their status.
   - At the same time, the user can manually set digital outputs via the GUI to control external devices or systems.

4. **User Interface**:
   - The GUI provides various controls for selecting the input/output channels, adjusting output values, and starting/stopping data acquisition.
   - Status indicators show the current value of each channel in real-time.

## Requirements:
- **Hardware**: NI DAQ device (such as NI-USB-600x or similar) with configured analog and digital input/output ports.
- **Software**: LabVIEW with NI-DAQmx drivers installed.

## Usage:
1. Connect the DAQ device to the system.
2. Run the application in LabVIEW.
3. Use the dropdown menus in the GUI to select the desired channels for AI, AO, DI, and DO.
4. For analog output, enter the desired output value or waveform.
5. Monitor the input values in real-time through the GUI.
6. Control digital outputs manually using the interface.

## Example:
- To monitor temperature sensors connected to analog input channels `Dev1/ai0` and `Dev1/ai1`, configure the channels in the GUI, and the system will continuously display the values.
- To output a voltage signal to `Dev1/ao0`, configure the desired output value in the GUI, and the program will apply the signal until the user stops it.

## Troubleshooting:
- Ensure that the NI-DAQmx driver is correctly installed.
- Verify that the correct channels are selected in the GUI, and check the physical wiring for input/output ports.
- If signals are not displaying or generating as expected, check the acquisition rate and hardware setup.
