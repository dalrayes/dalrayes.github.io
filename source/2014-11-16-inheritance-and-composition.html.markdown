---
title: Inheritance & Composition
date: 2014-11-16 21:54 UTC
tags: Learning, DBC, Ruby
---

In Ruby, we use classes to group the behaviors, or methods, that objects can use. To connect these classes, we have several options, among them are inheritance and composition.

##Inheritance

<li>Inheritance allows one class (child, sub-class) to get most or all features from another class (parent, superclass). The sub-class is usually a specialized form of its super class.</li>

<li>A sub-class can only have one super-class. This is called single inheritance. A superclass can have many subclasses.</li>

<li>In the real world, a child inherits certain traits from his / her parent. In Ruby, this is called implicit inheritance, where a subclass inherits methods of a parent class.</li>

<li>In Ruby, a subclass can also choose to change certain parent methods, or override them. Unfortunately, we do not have that option as humans! Ruby also allows the subclass to call a parent's method using (super).</li>

For example:

```ruby
class Homer
  def skintone
    puts "Skintone: yellow"
  end

  def clothing_top
    puts "White polo"
  end

  def clothing_bottom
    puts "Blue bottom"
  end
end

class Bart < Homer     #inheritance illustrates an "is a" relationship
  def clothing_top
    puts "Red t-shirt"
  end

  def clothing_bottom
    puts "Blue shorts"
    puts "--or alternatively--"
    super()
  end
end

homer = Homer.new
bart = Bart.new


#Implicit Inheritance
homer.skintone          #Skintone: yellow
bart.skintone           #Skintone: yellow

#Overriding Inheritance
homer.clothing_top      #White polo
bart.clothing_top       #Red t-shirt

#Calling the parent's method using Super
homer.clothing_bottom   #Blue Bottom
bart.clothing_bottom    #Blue shorts
                        #--or alternatively--
                        #Blue bottom
```
Although inheritance makes it easy to access methods of a parent class easily, it increases complexity when the code grows in size, multiple subclasses are added and new functions are added to the parent class. Overtime, it may appear that there is less and less in common between the super class and sub classes, but the linkage is too deep to alter, causing difficulties with your code.

##Composition

Composition is an alternative to inheritance; it links classes but allows objects to be independent of each other.

```ruby
class Homer
  def skintone
    puts "Skintone: yellow"
  end

  def clothing_top
    puts "White polo"
  end

  def clothing_bottom
    puts "Blue bottom"
  end
end

class Bart
  def initialize
    @dad = Homer.new    #composition illustrates a "has a" relationship
  end

  def skintone
    @dad.skintone       #added in the Bart class but calls the Homer method
  end

  def clothing_top
    puts "Red t-shirt"
  end

  def clothing_bottom
    puts "Blue shorts"
    puts "--or alternatively--"
    @dad.clothing_bottom
  end
end

homer = Homer.new
bart = Bart.new


homer.skintone          #Skintone: yellow
bart.skintone           #Skintone: yellow

homer.clothing_top      #White polo
bart.clothing_top       #Red t-shirt

homer.clothing_bottom   #Blue Bottom
bart.clothing_bottom    #Blue shorts
                        #--or alternatively--
                        #Blue bottom
```

As you can see, the resulting output is the same as what was done with inheritance.

