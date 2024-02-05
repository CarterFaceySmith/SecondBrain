One of the tenets of [[Object-Oriented Programming]].

Picture this: you've got a bunch of classes, each with their own set of functions. Now, imagine calling a function without caring which class it belongs to. That's polymorphism for you - the chameleon of [[C++]]! It lets you treat objects of different classes as if they were all cut from the same cloth. So, whether you're dealing with a cat, a dog, or a parrot, as long as they all have a `speak()` function, you're golden. I

Allows us to get rid of long if/else and switch statements.

We can implement one method or func differently across various objects, ie if rendering a page in order we don't need one big switch statement, we can simply have one func in each object that specifies a diff load time for each, and then call the func globally. With the rest of the object being the same.