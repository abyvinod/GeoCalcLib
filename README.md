[Click here for the full description][home]

This file is part of the geometric calculation library.

The geometric calculation library uses David Avis' [LRS library][lrs], 
to compute the vertex enumeration of a polyhedral set P = {x: A*x<=b}. 
It also computes the facet enumeration to P = conv(V) + cone(R). 
It has a function to compute the projection of a polyhedron, as well as reduction functions
to obtain minimal representations of both V and H-representations of
polyhedra.

INSTALL:
The geometric calculation library offers an interface to Matlab for all
its functionality. It requires the GMP library to be installed for the same
word length as Matlab, i.e. with an ABI=64 or ABI=32 variable set during the 
autoconfig process.

Create a text file named User.make containing the variables MATLABROOT and INSTALLDIR
which provide the absolute path to your Matlab installation and to the desired installation 
directory respectively.
Run 
	
	make

Then, run Matlab and edit your startup file

	>> edit startup

add 
	
	[~,~] = loadlibrary('libgeocalc','PATH/mainFunctions.h');
	display('GeoCalc library loaded.');

where PATH is the path where mainFunctions.h is located. Then edit the finishfile

	>> edit finish

add
	
	unloadlibrary('libgeocalc');

Notice, that if you have not loaded the library Matlab will not allow you to quit,
since it tries to unload the library by calling finish.m

[lrs]: http://cgm.cs.mcgill.ca/~avis/C/lrs.html
[home]: http://worc4021.github.io