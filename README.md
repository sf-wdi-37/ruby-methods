<!--
Creator: Team, editing by Cory
Market: SF
-->

![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)

# Ruby Control Flow and Methods

### Why is this important?
<!-- framing the "why" in big-picture/real world examples -->
*This workshop is important because:*

In order to write Ruby code, you're going to need some practice writing Ruby methods. Once you can divide your Ruby code into methods, you'll have greater mastery over your project.

### What are the objectives?
<!-- specific/measurable goal for students to achieve -->
*After this workshop, developers will be able to:*

- Write conditionals, loops, and methods in Ruby
- Apply methods in ruby to solve problems
- Explain the two main differences between Ruby methods and JavaScript functions: isolated scope and implicit return.

## Quick review
Make a table with 2 columns. Label one column Ruby and the other column JavaScript. Add at least 3 pieces of JavaScript syntax and the analogous Ruby syntax we've learned.

| Ruby | JavaScript     |
| :------------- | :------------- |
| `p`, `puts`, `print`       | `console.log()`     |

<details>
  <summary>Identify the operators in Javascript and Ruby and find the contrasts.</summary>


  <h4>JavaScript operators</h4>
  <ul>
    <li>`=`, `+=`, `*=`, ...</li>
    <li>`==`, `===`, `>`, `>=`, ... </li>
    <li> `!`, `||`, `&&` </li>
    <li> `+`, `-`, `/`, `*` </li>
  </ul>
  <h4>Ruby operators</h4>
  <ul>
    <li> `=`, `+=`, `*=`, ...</li>
    <li> `==`, `.equal?`, `>`, `>=`, ... </li>
    <li>`!`, `not`, `||`, `&&`</li>
    <li>`** `, `+`, `-`, `/`, `*`</li>
  </ul>
</details>

### Control flow

#### ([Ruby Control Flow Structures](http://en.wikibooks.org/wiki/Ruby_Programming/Syntax/Control_Structures))

Create a demo of two conditionals and one loop/iterator:

* Conditionals
    * `if`, `elsif`, `else`, `unless`, `case when else` ...
* Loops/iterators
    * `until`, `while`, `times` ...
    * `.each`, `for ... in`

#### Blocks

   * block - chunks of code between braces or between do..end:
     * used with `.each`, `.map`

    ```ruby
    [1, 2, 3].each do |n|
      puts "Number #{n}"
    end

    ```
    ^ is the same as
    ```ruby
    [1, 2, 3].each {|n| puts "Number #{n}"}
    ```

[Further Reading on Blocks](http://mixandgo.com/blog/mastering-ruby-blocks-in-less-than-5-minutes)

## Ruby Methods

### The basics

  * use `def` when defining a method.
  * Methods implicitly returns last evaluation.
  * Ruby is locally scoped.

#### Defining a method

```ruby
# announce you are creating a method with 'def'
def say_hello
  # all logic and action within belongs to the method
  puts "Hello"
# end your method definition with 'end'
end

# call the method 'say_hello'
say_hello
```

#### Defining a method with a parameter

```ruby
def say(something)
  puts something
end

say('hello')

say 'hello'
```

Ruby allows us to specify parameters omitting parentheses:

```ruby
# calling method, not using parentheses
results = method_name parameter1
```

If you want to chain another method off the result of your method call, you *do* need parentheses as you can see below:

```ruby
# You need to use parentheses if you want to work with the result immediately.
# e.g., if a method returns an array and we want to reverse element order:
results = method_name(parameter1).reverse
```


#### Parameters can have default values

```ruby
def say(something = "Hello")
  puts something
end

say # prints "Hello"
say "Goodbye" # prints "Goodbye"
```
#### Recursion: methods can call themselves

```ruby
def recurse(depth)
  if depth > 0
    puts "Spiraling down..."
    recurse(depth - 1)
    puts "Spiraling up..."
  else
    puts "Bottom of the rabbit hole"
  end
end

recurse(5)
recurse 5
```

#### Define a method that operates on two parameters
```ruby
def add_numbers(first, second)
  puts first + second
end

add_numbers(1,2)
add_numbers 1, 2
```

### Returning in Ruby

**Prompt**: What is the difference between printing and returning?

#### Printing and returning are different

The following method returns a value, but doesn't print anything.

```ruby
def add_numbers_quietly(first, second)
  first + second
end

add_numbers_quietly(1,2)
add_numbers_quietly 1, 2
```

#### Methods in Ruby always return the value of the last evaluated expression
```ruby
def implicitly_return_5
  if true
    5
  end
end

implicitly_return_5
```

## Method scope: the biggest difference from javascript

**Prompt:** Write some Ruby that demonstrates the scoping of variables.

#### Functions have locally scoped variables
The following code wont work. Why?

```ruby
foo = 1

def do_stuff
  foo += 1
  bar = 1
  puts foo
  puts bar
end

do_stuff

puts foo
puts bar
```

The problem is the ruby is locally scoped. Meaning that a function only has access to its variables and the variables it defined inside of itself.

```ruby
foo = 1

def do_stuff
  foo = 1
  foo += 1
  bar = 1
  puts foo
  puts bar
end

do_stuff

puts foo
puts bar

def do_stuff2(x)
  foo = x
  foo += 1
  bar = 1
  puts foo
  puts bar
end

puts do_stuff2(foo)
```

[Ruby Method Calls In Depth](https://en.wikibooks.org/wiki/Ruby_Programming/Syntax/Method_Calls)

### Exercises
Please complete [these exercises](exercises.md).

### Further Reading

* [Tutorialspoint Ruby Quick Guide](http://www.tutorialspoint.com/ruby/ruby_quick_guide.htm)
* [Ruby Hash in Detail](http://ruby-doc.org/core-2.2.0/Hash.html)
* [Online IRB Environment](http://joshnuss.github.io/mruby-web-irb/)
