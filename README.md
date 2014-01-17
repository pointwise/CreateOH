# CreateOH
A Glyph script that automatically creates an OH-topology given a loop of four connectors.

## Selection
This script allows the user to select a loop of four connectors that define the outer edge of a desired OH-topology. For best results, the connectors chosen must be dimensionally balanced, i.e. they can or do define the edges of an H-domain. The script locates the endpoints of each of the four connectors, finds their centroid, and then creates new topology based on an interpolation between the centroid and the existing endpoints.

When the script is run, a GUI appears that prompts the user to select "Pick Connectors". After selecting that button, the user must choose the four connectors defining the outer edges of the OH-topology, and then click "Done". This returns the user to the original GUI window, where the additional options are specified prior to selecting "Create OH". The connectors chosen must form a valid loop to be handled by the script. This is most easily checked by constructing a structured domain using the edges prior to running the script. If an existing domain exists using all of the selected edges, it will be removed prior to creating the OH-topology.

## Options
*Radial dimension*: This value specifies the dimension of the connectors created between the "H"-core in the center of the topology to the nodes of the outer edges. Valid values are either 0 or N >= 2.

*Radial extent*: This value specifies where to initially place the corners of the "H"-core created in the center of the topology. The value is directly correlated to the interpolation between the centroid of the outer nodes and the outer nodes themselves. Valid values lie between 0 and 1. Note that the final location of the internal nodes can be significantly different than specified by the "Radial extent" value if the solver is run.

*Run solver*: This option determines whether or not the elliptic solver is run after the topology is created. When checked, the elliptic solver is run 10 iterations with all internal edges set to 'Floating', which allows the grid to relax to an optimal configuration. When not checked, the topology is left as created by the "Radial extent" option.

![ScriptImage](https://raw.github.com/pointwise/CreateOH/master/ScriptImage.png)

## Disclaimer
Scripts are freely provided. They are not supported products of
Pointwise, Inc. Some scripts have been written and contributed by third
parties outside of Pointwise's control.

TO THE MAXIMUM EXTENT PERMITTED BY APPLICABLE LAW, POINTWISE DISCLAIMS
ALL WARRANTIES, EITHER EXPRESS OR IMPLIED, INCLUDING, BUT NOT LIMITED
TO, IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR
PURPOSE, WITH REGARD TO THESE SCRIPTS. TO THE MAXIMUM EXTENT PERMITTED
BY APPLICABLE LAW, IN NO EVENT SHALL POINTWISE BE LIABLE TO ANY PARTY
FOR ANY SPECIAL, INCIDENTAL, INDIRECT, OR CONSEQUENTIAL DAMAGES
WHATSOEVER (INCLUDING, WITHOUT LIMITATION, DAMAGES FOR LOSS OF BUSINESS
INFORMATION, OR ANY OTHER PECUNIARY LOSS) ARISING OUT OF THE USE OF OR
INABILITY TO USE THESE SCRIPTS EVEN IF POINTWISE HAS BEEN ADVISED OF THE
POSSIBILITY OF SUCH DAMAGES AND REGARDLESS OF THE FAULT OR NEGLIGENCE OF
POINTWISE.
	 

