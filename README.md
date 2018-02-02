# Arty A7-35 Pmod VGA
Created for Vivado 2016.4

This simple VGA Demo project demonstrates usage of a Pmod VGA connected to the Arty A7's Pmod ports. The behavior is as follows:

  * A bouncing box and many test pattern bars are displayed on a connected VGA monitor.
  * The Pmod VGA is controlled by the Arty A7 through Pmod ports JB and JC.
  * The screen resolution is configurable through HDL code.

In order to open the project in Vivado, follow the [Using Digilent Github Demo Projects Tutorial](https://reference.digilentinc.com/learn/programmable-logic/tutorials/github-demos/start). This is an HDL design project, and as such does not support Vivado SDK. Select the tutorial options appropriate for a Vivado-only design. A VGA monitor does not need to be connected to the Arty A7 before it is programmed.

You may want to change the display resolution if your VGA monitor does not support 1080p, or you want to modify the demo for a specific application. 
To select a different display resolution, select the appropriate set of Sync Generation constants for your target resolution from the list starting at line 47 of top.vhd. Uncomment the ten corresponding constants, FRAME_WIDTH through V_POL, and comment the default versions of those same constants. The default resolution is 1920×1080 @ 60Hz.
Next, select Project Manager in the Flow Navigator. In the Hierarchy tab of the Sources box, expand top under Design Sources and double click on clk_div_inst. Change the clk_out1 requested frequency to the required pxl_clk frequency specified in the selected resolution's Sync Generation comment block. Select Ok, then Generate in the Generate Output Products dialog that pops up. To reprogram your board with the new hardware, return to Step 2.