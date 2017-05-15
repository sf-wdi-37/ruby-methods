### How do you convert a written problem statement to a ruby method?


**Example**:

1.) Write a method called `p_times` that takes a `statement` and a `num` and `puts` the `statement` some `num` of times to the console.

**Clarify/decide output and input with examples**

  input: `"high five", 5`   
  output: print `"high fivehigh fivehigh fivehigh fivehigh five"`   
  OR...?   
  input: `"high five", 5`   
  output: print the line `"high five"` five times   

**Look at key words for method name and parameters.**  
  paremeters: `statement, num`
  name: `p_times`

**Write a method "stub" or "skeleton" structure**
  structure:  
  
  ```ruby
  def p_times(statement,num)
  end
  ```

**Pseudocode logic (only okay to skip if answer is very very simple)**
  ```ruby
  def p_times(statement,num)
    puts statement*num
  end
  ```

  ```ruby
  def p_times(statement,num)
    # loop num times
      # every time, puts the statement
  end
  ```

**Fill in code**

```ruby
def p_times(statement,num)
  # loop num times
  num.times do |i|
    # every time, puts the statement
    puts statement
  end
end
```

**Test it**

  * call the method with some parameters:
    `p_times("high five", 5)`
  * see if you got the expected output when you run the method 
