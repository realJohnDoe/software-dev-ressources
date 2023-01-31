

- `to_owned`: goes from borrowed to owned, usually by implementing the clone
  trait.

- The difference between arrays and slices is that arrays have a fixed size
  and are denoted with `[T, n]` or `&[T, n]` while slices have a variable
  size and are denoted with `[T]` or `&[T]`.

- Slices

  - have a `.windows(n)` method that returns all possible windows of length
    `n` for that slice.

  - have a `.any(predicate) bool` method that returns true if any of the
    contained ites evaluates true under the predicate.

  - have a `.len()` and a `.is_empty()` method.

- Lambdas can be defined with a `|x, y| x*y` syntax.

- `match` can receive mutliple values, like

  ```rust
  match (a, b) {
       true, false => {},
       ...
  }`
  ```

- We can use `||` syntax to return a first simple expression and forward to a
  more complex expression in case the first one is false.

- The crate `int_enum` can be used to build integer-valued enums with the syntax

  ```rust
  #[repr(usize)]
  #[derive(Clone, Copy, Debug, PartialEq, Eq, IntEnum)]
  enum Colors {
    Red = 1,
    Blue = 2
  }

  let red = Color::from_int(1).expect("value out of range");
  let int_value = red.int_value();

  ```

- The crate `enum_iterator` can be used to iterate over enums.

- `?` can be used to unwrap a result, only use it when it is ok and pass the
  error up otherwise.
- `.expect()` can be used to reformat a Result or Optional

- Structs

  - Struct construction is done via `Struct { member_1, member_2 }`.
  - The class itself can be referenced in methods via `Self` while the instance
    can be accessed using `self`

- `Iterator` trait objects

  - have a method `step_by` which allows to skip some items.
  - have a method `filter_map` to do filtering and mapping in one go.

- We can use `|(a, _)| a % 2 == 0` syntax to combine pattern matching and a
  lambda function.

- `map` can be used on `Option` to run function on the `Some` case

- bools can be converted to an `Option` by using `.then()` or `then_some()`.

- Traits can be combined with `+`.🤯
- The `std::cmp::Eq` trait and `std::hash::Hash` traits are required for HashMap
  keys.
- The `std::cmp::Ord` trait is required for comparing.

- HashMap entries

  - can be set with `.insert()`
  - can be retrieved with `.get()` or
  - modified with `.get_mut()`.
  - can be modified in place with `.entry()`

- `Iter` vs `IntoIterator` traits :

  - `IntoIterator` is required for `for`-loops, but yields values, immutable
    references or mutable references depending on context.
  - `Iter` yields immutable references.

- `map().all(|x| x)` can be simplified to `all()`

- `.unwrap_or` can be used on `Option` to easily define a default in the `None`
  case.

- `vec![0; 5]` can be used to create a vector of five zeroes.
- `vec![1, 2, 3]` will compile into a vector with elements 1, 2, and 3.

- Don't put a semicolon `;` at the end of lines if the value shall be returned.

- `Vec` elements can be accessed and modified using square brackets `[]`.

- A range can be defined using `1..4`.
  The last value will not be included.
