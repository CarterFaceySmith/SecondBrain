Header files allow for importing of common classes, etc between c++ files without duplicating the code all over the place.

Contents can be imported using #include "header filename" along with your other imports at file top.

Header files use the .h and sometimes .hpp file extensions.

File begins:

	#ifndef FILENAME_H
	#define FILENAME_H
	

File ends:

	#endif FILENAME_H
	
#### But Carter what the fuck does that do?

Basically, 