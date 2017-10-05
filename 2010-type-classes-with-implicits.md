# Type Classes as Objects and Implicits

Link: [Paper](http://ropas.snu.ac.kr/~bruno/papers/TypeClasses.pdf)

Hypothesis: Type classes provide a way to solve intrinsic problems in Computer Science. Specifically, they allow us to solve the _retroactive extension_ problem of extending a library without even needing to recompile it. In Scala, we can do this using implicits.

Notes:

- The usual OO way is to define interfaces to be extended by the clients (e.g. Comparable), and then pass them around to use them inside the methods of the library. However, this can get cumbersome.

- In Scala, we can make these "required interfaces" implicit, and create global implicit objects to fulfill them automagically. For example, we may have the implementation of the comparator in an `implicit object SpanishStringComparator`, which the sorting library will just take. This means of course that there can be no conflicts, or two comparators in the same "implicit scope". What does implicit scope mean? Hell if I know.

- Now, we can supply alternative Comparators, but we need to pass them explicitly.

- We can have `implicit val`, `implicit object`, `implicit def`.

- The CONCEPT pattern looks good, but not worth paying attention for now.
