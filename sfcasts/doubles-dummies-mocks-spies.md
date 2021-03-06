# Test Doubles, Dummies, Mocks & Spies

Now that we've seen *all* the things we can do with test doubles... we need to
talk a *bit* more about some words and language that you'll see with prophecy...
otherwise... it all looks a bit crazy.

Google for "php prophecy"... because, remember, this whole test double system in
phpspec actually comes from prophecy.

In their documentation, they talk about *four* different types of objects! Dummy
objects, stub objects, mock objects and spy objects. Woh! For me... this was...
confusing! So let's walk through and see what's actually going on - it's really
nothing new for us. These four different words all different ways to describe test
doubles... the "things" that we just finished learning *all* about.

## Dummies

First, look at dummies. A dummy object is both what I look like if you ask me to
remember where I left the car keys... *and* also the object you get if you add an
argument with a type-hint in phpspec to get a test double... then do absolutely
nothing with it. So if we get a test double and add *no* behavior and make *no*
assertions on its methods, it's called a "dummy object".

Oh, and inside of their documentation, you'll see things like `$prophecy->reveal()`.
That's a detail that we don't need to worry about because phpspec takes care of
that for us. Score!

## Stubs

As *soon* as you start controlling even *one* return value of even *one* method...
boom! This object is suddenly known as a stub. From the docs: "a stub is an object
double" - *all* of these things are known as test doubles, or object doubles - that
when put in a specific environment, behaves in a specific way. That's a fancy way
of saying: as soon as we add one of these `willReturn()` things, it becomes
a stub.

And actually, most of the documentation is spent talking about stubs and the different
ways to control exactly how it behaves, including the Argument wildcarding that we
saw earlier.

## Mocks

If you keep reading down, the next thing you'll find are "mocks". An object becomes
a mock when you call `shouldBeCalled()`. So, if you want to add an *assertion* that
a method is called a certain number of times and you want to put that assertion *before*
the actual code - using `shouldBeCalledTimes()` or `shouldBeCalled()` - congratulations!
Your object is now known as a mock.

## Spies

And *finally*, at the bottom, we have spies. A spy is the *exact* same thing as a
mock, except it's when you add the expectation *after* the code - like with
`shouldHaveBeenCalledTimes()`.

## Putting it All Together

So there's a lot of language here... but these are all different words to describe
the different things you can do with a test double. Doing nothing? It's a dummy.
Controlling the return value? It's a stub. Adding an assertion to make sure a method
was called? It's a mock or a spy, depending on your style. And yes, you *can* be
a stub *and* a mock or spy at the same time - that's exactly what we're doing in
our example.

I find these terms fun, but a little confusing and I don't think about them when
I'm actually coding: I just think about what I need to get done. But now that you're
familiar with them, reading the docs should be a breeze. And also, these words are
used *everywhere* in the testing world - not just in phpspec - so it's kinda cool
to know them. You're now part of the cool-kids testing club.

Next, let's do some more mocking... cause it's awesome! And we'll say hello to a
helper method that we can use inside our spec class to run some code before *every*
example.
