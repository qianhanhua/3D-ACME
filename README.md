# 3D-ACME
3D-IC thermal simulator with modeling of Anisotropic TSV Conductance and Microchannel Entrance effects (3D-ACME)
-------------------------------------------------

Contents
--------

1) License
2) Introduction
3) File List
4) Howto
5) Acknowledgement
6) Contact
7) Reference

---------------

1) License
-------
LICENSE TERMS

Copyright (c)2012 Hanhua Qian, Hao Liang, Chip-Hong Chang, Wei Zhang and Hao Yu.  All rights reserved.

Permission is hereby granted, without written agreement and without license or
royalty fees, to use, copy, modify, and distribute this software and its
documentation for any purpose, provided that the above copyright notice and the
following four paragraphs appear in all copies of this software, whether in
binary form or not.

IN NO EVENT SHALL THE AUTHORS, OR NANYANG TECHNOLOGICAL UNIVERSITY (NTU) OF SIN-
GAPORE BE LIABLE TO ANY PARTY FOR DIRECT, INDIRECT, SPECIAL, INCIDENTAL, OR CON-
SEQUENTIAL DAMAGES ARISING OUT OF THE USE OF THIS SOFTWARE AND ITS DOCUMENTATION, 
EVEN IF THEY HAVE BEEN ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

THE AUTHORS, AND NANYANG TECHNOLOGICAL UNIVERSITY (NTU) OF SINGAPORE SPECIFICALLY
DISCLAIM ANY WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES
OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE. THE SOFTWARE PROVIDED
HEREUNDER IS ON AN "AS IS" BASIS, AND THE AUTHORS HAVE NO OBLIGATION TO PROVIDE
MAINTENANCE, SUPPORT, UPDATES, ENHANCEMENTS, OR MODIFICATIONS.

NEITHER THE NAME OF ANY NTU ENTITY NOR THE NAMES OF THE CONTRIBUTORS MAY
BE USED TO ENDORSE OR PROMOTE PRODUCTS DERIVED FROM THIS SOFTWARE WITHOUT
SPECIFIC PRIOR WRITTEN PERMISSION.

If you use this software or a modified version of it, please cite the following
paper: H. Qian, C-H CHANG AND H. YU, "An efficient channel clustering and flow rate 
allocation algorithm for non-uniform microfluidic cooling of 3D integrated circuits", 
INTEGRATION, the VLSI journal (2012), doi:10.1016/j.vlsi.2011.12.005.

-------------------------------------------------------------------------------------

2) Introduction
------------

3D-ACME stands for 3D-IC thermal simulator with modeling of Anisotropic TSV Conductance and Microchannel Entrance effects. It is a software that simulates the steady state temperature of heatsink or microfluidic cooled 
3DICs given power consumption, cooling setting and physical set-ups of 3D circuit stacks. Accuracy of 
this thermal model has been verified against commercial multiphysics solver COMSOL (http://www.comsol.com/). 

This software is written in 'C' with the ultilization of KLU solver for solving the sparse thermal balance equations. 
Releasing this software is mainly for the interest of academic research. Verification against direct measurement of 
prototypes is recommended before its application in industry or commerce.

------------------------------------------------------------------------------------------------------

3) File List
------------

4) Howto
--------

This software was developed under Linux environment, specifically, Ubuntu 10.04 and later versions. 
Thus it is recommended to run this software under Linux system. Nevertheless, this software should have
no problem to run under WINDOWS if the C compiler and KLU are both correctly installed. The following 
instructions assume the operating system to be Linux by default.


1. Download the compressed package 3D-ACME.zip from ******** URL ********

2. Unzip the 3D-ACME.zip file using the following command:
	a) unzip 3D-ACME.zip

3. Enter the extracted folder 3DSST, check the makefile, make sure the math library and KLU library are
included and pointing to the correct path. KLU can be easily installed in Debian-like Linux distrbutions
such as Ubuntu through the following commands.
	a) apt-cache search libklu
The name of latest KLU package will be shown, e.g. libklu1.1.0, you can then install the shown package by
	b) sudo apt-get install libklu1.1.0
For other Linux distributions and WINDOWS, KLU can be downloaded from http://www.cise.ufl.edu/research/sparse/klu/.
Please follow KLU's instruction to compile or install it on your system.

4. Build 3D-ACME 
	a) make

5. Run 3D-ACME
	a) 3dacme
will print the usage information on all the parameters of the command needs.
	b) 3dacme -lcf ./examples/example_hs.lcf
gives an simple example of simulating a 2-layer circuit stack with uniform power consumption. The format
of the layer configuration file (lcf) has been explained in comments of those files.

6. Clean compilation.
	a) make clean

------------------------------------------------------------------------------------------------------------------------

5) Acknowledgement
-------------------
This software evolved from a modified version of Hotspot. Thus some data structure and functions are inheritated from
Hotspot, such as the floorplan related structures and mapping of power and temperature from unit to grid cells. The 
authors hereby want to thank Hotspot on accelerating the development of this 3D-ACME software by reusing some of its code. 
Below attaches Hotspot's license terms:

Hotspot License Terms

Copyright (c)2003 Wei Huang, Sivakumar Velusamy, Karthik Sankaranarayanan,
David Tarjan, Mircea R. Stan, and Kevin Skadron.  All rights reserved.

Permission is hereby granted, without written agreement and without license or
royalty fees, to use, copy, modify, and distribute this software and its
documentation for any purpose, provided that the above copyright notice and the
following four paragraphs appear in all copies of this software, whether in
binary form or not.

IN NO EVENT SHALL THE AUTHORS, THE UNIVERSITY OF VIRGINIA, OR THE STATE OF
VIRGINIA BE LIABLE TO ANY PARTY FOR DIRECT, INDIRECT, SPECIAL, INCIDENTAL, OR
CONSEQUENTIAL DAMAGES ARISING OUT OF THE USE OF THIS SOFTWARE AND ITS
DOCUMENTATION, EVEN IF THEY HAVE BEEN ADVISED OF THE POSSIBILITY OF SUCH
DAMAGE.

THE AUTHORS, THE UNIVERSITY OF VIRGINIA, AND THE STATE OF VIRGINIA SPECIFICALLY
DISCLAIM ANY WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES
OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE. THE SOFTWARE PROVIDED
HEREUNDER IS ON AN "AS IS" BASIS, AND THE AUTHORS HAVE NO OBLIGATION TO PROVIDE
MAINTENANCE, SUPPORT, UPDATES, ENHANCEMENTS, OR MODIFICATIONS.

NEITHER THE NAME OF ANY VIRGINIA ENTITY NOR THE NAMES OF THE CONTRIBUTORS MAY
BE USED TO ENDORSE OR PROMOTE PRODUCTS DERIVED FROM THIS SOFTWARE WITHOUT
SPECIFIC PRIOR WRITTEN PERMISSION.

------------------------------------------------------------------------------------------------------------------------

6) Contact
-----------
For any equiries on usage or any comments to the software, Please contact the first author via his email address:
QIAN0028@E.NTU.EDU.SG. We will get back to you as soon as possible.
------------------------------------------------------------------------------------------------------------------------

7) Reference
-------------

[1] H. Qian, C-H CHANG AND H. YU, "An efficient channel clustering and flow rate 
allocation algorithm for non-uniform microfluidic cooling of 3D integrated circuits", 
INTEGRATION, the VLSI journal (2012), doi:10.1016/j.vlsi.2011.12.005.
