# Shallow vs. Deep Copies in [[C++]]

When duplicating objects using copy constructors.

A shallow copy results in a variable or whatever that points to the same location in memory as the variable or whatever you've copied from. Modifications to the area are reflected by both variables.

A deep copy takes the values at the location and copie them into a seperate memory area that is then pointed to by the new variable or whatever you're using. Later modifications to either area remain unique.

