---
title: Ruby Arrays and Hashes
date: 2014-10-26 21:54 UTC
tags: Learning, DBC, Ruby
---

We started Ruby this week and its been fun running programs to do fun things, like figure out leap years, calculate triangles and collect and print information. This post will cover two classes in Ruby: the Array and the Hash .

##[ Arrays ]

An array is a list of items, and it can be filled with any type of object: integers, floats, strings, even other arrays or hashes. The objects are listed in order and are separated by commas.

```ruby
 numbers_array = [-1, -2, 10, 20 , 100]
          array_ofwords = ["hey", "there", "delilah"]
          combined_array = [-1, "hey", "October", 11.99, ["a", "b", "c" ]]
```

An array can also be defined without any elements inside it, and later added to/deleted from:

```ruby
 animals = Array.new #defines a new empty array called "animals"

          animals.push("dog") #adds "dog" to "animals" array
          animals.push("cat") #another way to add to an array

          animals.delete("cat")  #deletes "cat" from the array
          animals.pop  #removes and returns the last element in the animals array

```

Arrays are really neat: they are ordered and are integer-indexed starting at 0. This indexing allows us to access elements in an array easily

```ruby
array_ofwords = ["hey", "there", "delilah"]

          array_ofwords[0]      # returns the zeroth element ("hey")
          array_ofwords[2]      # returns the third element  ("delilah")
          array_ofwords[-1]     # returns the last (1st from the end) element
          array_ofwords.first   # returns the first element
          array_ofwords.last    # returns the last element
```

There are a lot of methods that can be used on arrays, and they can be found [here](http://www.ruby-doc.org/core-2.1.3/Array.html)!

##{ Hashes }

A hash is a list of of pairs, to be specific, key-value pairs. They are similar to arrays, but instead of being integer indexed, hashes are indexed by the keys. This means that you use a key to find something in a hash. Keys can be integers, strings or symbols, but must be unique to the hash they are part of, and values can be any Ruby object. There are several ways to create a hash:

```ruby
   grades_hash = Hash.new #creates a new hash

            #another way

            grades_hash ={
              "Joe" => grade1,   # "key" => value,
              :Sara => grade2    #another way to create :key=>value pair
              }


              #to retrieve info from the hash
              grades_hash["Joe"]
```

More information on hashes and the methods that can be used can be found [here](http://ruby-doc.org/core-2.1.3/Hash.html) .

Although both arrays and hashes can be expanded to hold new elements, hashes provide more flexibility. Also, hashes have a default value that is returned when a command tries to access keys that do not exist in a hash. The default value for this is nil, but it can be reset to anything else.

