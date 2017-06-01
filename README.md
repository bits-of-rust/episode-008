# episode-008
Where we introduce functions

## Setup
The following needs to be prepared

* A project with the name `functions`
* Repetition of printing `hello` and `goodbye` to two different subjects.

## Script
Look at the following code

```rust
let mut subject = "world";

println!("Hello, {}!", subject);
println!("Goodbye, {}!", subject);

subject = "moon";

println!("Hello, {}!", subject);
println!("Goodbye, {}!", subject);
```

It looks very familiar. In fact in [episode 004](https://github.com/bits-of-rust/episode-004)
we already saw something similar. The difference is that now we greet both
`world` and `moon`, instead of one or the other.

Just as in episode 004 if we wanted to change the code, for example, change
`Hello` into `What's up` we would have to change that in to places. This seems
wastefull.

Lets see how a function could help in this situation.

A function is defined with the `fn` keyword, followed by the name of the
function and its arguments.

```rust
fn greet(subject) {
  println!("Hello, {}", subject);
  println!("Goodbye, {}", subject);
}
```

When we try to compile this code, Rust will complain. When using variables Rust
could infer the type of the variable for us. Rust will not do that when we are
defining a function.

For now we will provide the type without going into details. They will be
addressed in a different episode.

```rust
fn greet(subject: &str) {
  println!("Hello, {}", subject);
  println!("Goodbye, {}", subject);
}
```

This time Rust still complains, but now with a friendly reminder that we haven't
used the `greet` function. So let's go ahead an use it.

```rust
let mut subject = "world";
greet(subject);

subject = "moon";
greet(subject);
```

And there you have it, we have introduced a function.
