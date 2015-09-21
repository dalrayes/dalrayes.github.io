---
title: Javascript vs Ruby
date: 2014-11-24 21:54 UTC
tags: Learning, DBC, Ruby, Javascript
---

###Looping Through!

A week into using Javascript and I miss Ruby already. Ruby is more intuitive and to the point, but Javascript feels more verbose, like something from English literature

Below, is an example of an annoying loop using ruby.

```ruby

  loopy = true

  while loopy == true
    puts "Are we there yet?"
    answer = gets.chomp

    if answer == 'yes'
      puts "Finally!"

    elsif answer == 'no'
      puts "nooo"

    else answer == 'stop'
      loopy == false
      break

    end
  end
  ```

On the other hand, if we were to do something similar in Javascript it would look something like this:

```javascript

  loopy = true

  while(loopy)
  {
    var answer = prompt("Are we there yet?")
      if(answer == "yes") {
        alert("Finally!!!");
      }
      else if (answer == "no") {
        alert("Nooo!!!");
      }
      else {
      loopy = false;
      }
  }
```

Although they look fairly similar, Javascript requires much more syntax (brackets and colons) than ruby. For looping, in addition to _while_, _for_ and _for...in_ loops, ruby provides methods _until_, _each_, and _times_.

<li>More on Ruby loops [here](http://www.tutorialspoint.com/ruby/ruby_loops.htm)</li>
<li>More on Javascript loops [here](http://www.w3schools.com/js/js_loop_for.asp) and [here](http://www.w3schools.com/js/js_loop_while.asp)</li>
