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

## Chapter 7 : Comments
- I have not commented to codes because I had heard it's better to clarify the code before writing it. Nonetheless, here I have some helpfuls about comments.
- Comments are not “pure good.” Indeed, they are, at best, a necessary evil.
- Unfortunately the comments don’t always follow code chunks—can’t always follow them. ( I did made some commits fixing old comments in the last project )
- Sometimes a comment goes beyond just useful information about the implementation and provides the intent behind a decision.
- It is sometimes reasonable to leave “To do” notes in the form of `//TODO` comments.
  - Whatever else a TODO might be, it is not an excuse to leave bad code in the system.
- Any comment that forces you to look in another module for the meaning of that comment has failed to communicate to you and is not worth the bits it consumes.
- Avoid writing nonlocal Information in comments.

## Chapter 8 : Error handling
- Create informative error messages to provide context with exceptions.
- In fact, wrapping third-party APIs is a best practice. I think it really is!
- Clean code is readable but it must also be robust.
  
**I read this chapter but I'm not familiar with java style error handling so that I could not "understand" fully. Let's revisit later on**