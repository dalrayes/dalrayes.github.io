---
title: Ruby Classes
date: 2014-11-04 21:54 UTC
tags: Learning, DBC, Ruby
---

The Ruby language comes with a variety of built in classes, or kinds, of objects.

Objects are the building blocks of a program. Objects:
<li>have properties & know things</li>
<li>do things</li>

Objects can be grouped by classes. Existing classes include: String, Integer, Float, and Array, which can be easily created by using the _new_ method

```ruby
   game = Array.new
          game[0] = 'basketball'
          game[1] = 'baseball'
          game[2] = 'soccer'
```
We can also create our own classes to do a serve a specific purpose. A ruby class, like those above, is always capitalized. Here, I will create a new class, Investment, that can have different methods to assess a portfolio of investments.

```ruby
  class Investment

        attr_accessor :cashflow0, :cashflow1, :cashflow2, :cashflow3, :rate

        def initialize
            @cashflow0 = -2000
            @cashflow1 = 100
            @cashflow2 = 100
            @cashflow3 = 2600
            @rate = 0.06
        end

        def npv
          my_npv = '%.2f' % (@cashflow0 + (@cashflow1/(1+@rate)) + (@cashflow2/(1+@rate)**2) + (@cashflow3/(1+rate)**3))

            if my_npv.to_i > 0
              puts "Your portfolio return is: $#{my_npv}. Looks like it may be a good investment!"
            else my_npv.to_i <=0
              puts "Your portfolio return is: $#{my_npv}. I would pass on this investment"
            end
        end
      end

      portfolio = Investment.new
      puts portfolio.npv

      #Your portfolio return is: $366.35. Looks like it may be a good investment!
```

Other related methods, such as calculating the investment's internal rate of return (or IRR) can be later added. Each method in the class can use the information that the class is initialized with, here, the cash flows and the rate. Although the (cash flows) are not defined within the (npv) method, we can use them because we created them as instance variables using the (@) sign. If the @ sign was not included, the variables would become local variables, and could only be used inside the method in which they are defined (here - the initialize method). As instance variables, they is available to every method of the object.

We can check that the method (npv) is available to any object of the class Investment.new by using portfolio.methods.sort. The list of methods available will now include npv.

