# Flasher
Flasher tool is the Phinia product for communicating with an ECU. At the beginning, its purpose was to program the internal flash memory of electronic control units. These basic features have been upgraded making this software a versatile tool for testing and diagnosing control units.

Tool has proved itself for diagnostic ECU communication after being used in many different projects, starting from 2005. Tool started it's journey in Delphi company. It belongs to Phinia currently. It requires a valid license to run, and requires update annually.

<img src="https://github.com/user-attachments/assets/96b740a5-be75-46d7-9f48-6eba3da61a2c" width="700" />

Flasher tool supports two modes, Reprogramming and Expert. Reprogramming mode is intended for new starters. It hides advanced-configuration, scripting and running projects.

## Technical Data
**Requirements:** Min Win10 required after version 6.

**Calibration data:** Intel HEX, Motorola S19, S28, S37

**Protocols & Standards:** ISO 15765-2 (Diagnostic on CAN), ISO 10681-2 (Diagnostic on Flexray), AUTOSAR FlexRay TP, ISO 13400-2 (Diagnostic on IP), Diagnostic on LIN, ISO 14229-2 (UDS session layer services), SAE J1939/21, SAE J1939/22
SAE J2534 (V04.04 and V05.00), ODX (V2.2)

**Measurement devices:** CAN (Vector, Peak, Softing, Kvaser, any SAE J2534 compliant device), CAN-FD (Vector, Peak, Kvaser), Flexray (Vector), LIN (Vector, Intrepid, Peak)

**Development Languages:** C#, Flasher-script-language

## Applications

**Develop and execute code:** Flasher is the container tool for running diagnostic routines (e.g. flashing ECU software). It handles session/transport/network layers for you. All you need is to develop application layer for the needs.
Supports session and transport protocols for UDS and J1939 as well as direct bus communication (see "protocols & standards") in various bus types.

![Flasher_diag](https://github.com/user-attachments/assets/2780e167-8c17-417f-8dba-606d7cce0adb)

Flasher supports running diagnostic routines in following formats:

* Plugin DLL (.NET or C++)
* Script (Flasher’s script format or single C# file)
* Flasher Project (list of plugins and scripts)

**Logging:** Supports logging application level. It also records all bus activities during execution.

**Automation:** Flasher supports running from command prompt, both in silent and graphical mode. That provides the tool to be executed from an <u>automation tool</u>.
Additionally, Flasher-project can be used for executing multiple test-scripts and generating report at the end.

## Plugin Support (.NET DLL)
Flasher supports loading plugin (.NET DLL) file. Plugin file can contain one or more diagnostic functions. Once DLL is loaded by Flasher, supported functions are listed. It is easy to run the selected function.

<img src="https://github.com/user-attachments/assets/7be9385a-76ea-4cc6-b069-10238d2dec7a" width="500">

Flasher displays the trace after running the plugin function.
![Flasher_plugin_result](https://github.com/user-attachments/assets/5441cfb6-bae4-46de-8832-b84e45290a67)

### Plugin Development
Flasher provides a “cs” file for easily developing plugin. That “cs” file defines all interface between your code and Flasher. In addition, a sample plugin project comes with Flasher setup.

## Plugin Support (C++ DLL)
Flasher still supports C++ plugin DLL for **backward compatibility**. New features are not included to C++ plugin interface.

## Flasher Script
Flasher supports script format for developing diagnostic routines. It provides an easy way to develop simple diagnostic routines.<br>
![Flasher_script](https://github.com/user-attachments/assets/d1e0b744-5ade-424a-86ca-1712c2c61b0f)

Script format supports commands for sending/receiving frames, changing default configurations, if condition, loop etc.

Flasher has text editor for coloring the text, and displaying the errors/warnings. Flasher also supports displaying the trace after running the script.

## C# Code Support
In some cases, Flasher’s script format can be insufficient for developing complex diagnostic routines. C# is a full language that will be sufficient for all needs. Flasher has support to **build** C# code, and run **OnStart** function.

<img src="https://github.com/user-attachments/assets/ad21e1e5-5744-43a6-88ff-1595b8a872e6" width="500" />

C# code can use Flasher’s Plugin Interface to send orders to Flasher tool. In other words, plugin C# code can be used without any change. Only limitation is, the C# code must be located in a single "cs" file.

Suggestions:
* If your diagnostic routine is simple, use Flasher’s script format.
* If your diagnostic routine is complex, e.g. you need variable definition,
  * develop C# code in Flasher, or
  * develop plugin DLL
* If you don’t have Visual Studio in your PC, you can use C# code in Flasher.

Flasher has text editor for coloring the C# code, and displaying the errors/warnings. Flasher also supports displaying the trace after running the code.

## Flasher Project
Flasher **project** is a file ( extension dfproj) that stores one or many script/plugin file links in a structure. It provides running scripts/plugins in a row.

<img src="https://github.com/user-attachments/assets/2715d9f9-d505-4b47-9da6-76bb16db551d" width="500" />

The **verdict result** will be displayed on the icon after running the project. In addition, the verdict results are stored in the project file. It is possible to clear verdict results.

The execution configuration can be updated individually for each script/plugin.

## ODX Support
With ODX integration, Flasher provides translation for hexadecimal exchange with ECU. By using meaningful names instead of byte values, it is aimed to make the exchange easier to understand and less prone to errors.

An "ODX database" is used to maintain a collection of ODX and PDX files.

After setting up ODX database, Flasher script auto-complete will be enabled with CTRL+space shortcut:

![Flasher_odx](https://github.com/user-attachments/assets/776fe074-0dfb-418b-b169-d207e9f0b562)

