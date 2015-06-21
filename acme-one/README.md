# `acme-zero` and `acme-one`

[Cabal][cabal] package dependencies form a commutative monoid with an absorbing
element. They satisfy the following axioms:

[cabal]: https://www.haskell.org/cabal/users-guide/developing-packages.html

* **Associativity**

  For all dependencies `a`, `b` and `c`,

  ```
  (a , b) , c = a , (b , c)
  ```

  In fact, the Cabal syntax does not even allow you to use the parentheses for
  this reason.

* **Commutativity**

  For all dependencies `a` and `b`,

  ```
  a , b = b , a
  ```

* **Identity element**

  For all dependencies `a`,

  ```
  acme-one , a = a
  a , acme-one = a
  ```

  Depending on [`acme-one`][acme-one] has no additional effect.

* **Absorbing element**

  For all dependencies `a`,

  ```
  acme-zero , a = acme-zero
  a , acme-zero = acme-zero
  ```

  Depending on [`acme-zero`][acme-zero] in addition has the same effect as
  *only* depending on `acme-zero`.

[acme-one]:  https://hackage.haskell.org/package/acme-one
[acme-zero]: https://hackage.haskell.org/package/acme-zero
