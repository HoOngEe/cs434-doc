# CleanCode
## Chaper 2 : Meaningful Names
- Don't hesitate to change variable names after you find better ones.
- Try to avoid number-series(a1, a2, .. ,aN) naming which is noninformative.
- `Info` and `Data` are indistinct noise words like a, an, and the(I used to work with those variable suffixes).
  - In the similar sense, pick one word for one abstract concept and stick with it.
  - It is more important not to mix similar names when a group of peopole contribute to a same code base.
- Use serachable names! (In a large project, I had a hard time searching some variables by name because of magic numberings)
- Clarity is king
- Shorter names are generally better than longer ones, so long as **they are clear**.

## Chapter 3 : Functions
- The first rule of functions is that they should be small!
- The indent level of a function should not be greater than one or two.
- Functions should do one thing!
  - bury the switch statement in the basement of an `ABSTRACT FACTORY` and utilize `Polymorphism` to dispatch
- One level of abstraction per function
  - Mixing levels of abstraction within a function is always confusing. Readers may not be able to tell whether a particular expression is an essential concept or a detail.
- Flag arguments are ugly
  - I've tried avoid those ugly arguments
- Anything that forces you to check the function signature
  - Hmm....
- If your function must change the state of something, have it change the state of its owning object.
- Seperate `Command` and `Query`
  - That's what I often was criticised by peers
- extract the bodies of the try and catch blocks out into functions of their own.
  - Remeber what you've done in `foundry` project when handling errors (cascading errors with `Result` type in Rust)
- Master programmers think of systems as stories to be told rather than programs to be written.