# Exercism - Crystal

Rearrangement of the fantastic exercise guide from Exercism.
Check it out at http://exercism.io/languages/crystal.

## Workflow

Specs are provided for each exercise that allow you to test if your implementation fails to satisfy each of the exercises' requirements.

To start, enter the first exercise's directory and run the specs as follows:

```
$ cd 01-hello-world
$ crystal spec hello_world_spec.cr
```

Don't worry if you get an error! You should now be able to write some code to make the first test pass. In this case, you should se a message like:

```
Error in line 1: while requiring "./hello_world_spec.cr"
in ./hello_world_spec.cr:7: undefined constant HelloWorld

      HelloWorld.hello.should eq "Hello, World"
```

This means you should create the namespace `HelloWorld` with a `hello` method in it. Go ahead:

```crystal
# 01-hello-world/hello_world.cr
module HelloWorld
  extend self

  def hello
    "Hello World"
  end
end
```

Run the specs again and you will see that the first one passed. Enable the rest of them by changing `pending` cases to `it` blocks, and make the necessary improvements to the code to make it work for all the required cases.

By the way, you can read about what the `module` and `extend self` parts do [here](https://crystal-lang.org/docs/syntax_and_semantics/modules.html), but for the moment you can just follow along and make the rest of the tests pass.

Good luck!
