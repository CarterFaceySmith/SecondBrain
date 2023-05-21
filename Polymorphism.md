# Polymorphism

One of the tenets of [[Object-Oriented Programming]].

Allows us to get rid of long if/else and switch statements.

We can implement one method or func differently across various objects, ie if rendering a page in order we dont need one big switch statement, we can simply have one func in each object that specifies a diff load time for each, and then call the func globally. With the rest of the object being the same.