# Scope

Scope, AKA 'access scope' AKA 'encapsulation', is the practice of setting the accessibility of methods, properties, classes, etc, etc.

The whole thing with this is *modesty baby*. We don't need everything hanging out in public for the world to see right? People don't need access to everything, unless that's your thing, but when it comes to code it shouldn't be your thing unless you like fucked code and malware.

### Public, private and protected, AKA don't touch the beer stash mate

Let's say you're a father, and because you have kids of course you drink alcohol, basically mandatory. You keep a stash of beers in the fridge and wanna control who can access them.

If we make those beers **_protected_**, then you're keeping them in the family so to speak, only subclasses (family members) can call the method (beers) and unrelated classes cannot, fuck 'em.

Let's say though, that you're feeling selfish and/or no one in your family is of legal drinking age. We'll channel our inner capitalist and **_private_** that method mate. Only you get access to it, a private method can only be called by the method that implements.

If you're feeling rich and generous though, well give everyone a beer mate, **_public_** that bad boy and watch them fly out the fucking door. Anything can access this method, object or whatever you're working with here.

See also:
- [[Computer Science Fundamentals]]

