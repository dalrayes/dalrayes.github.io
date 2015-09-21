---
title: Ruby Methods
date: 2014-11-02 21:54 UTC
tags: Learning, DBC, Ruby
---

In my last post, I gave a brief overview of Arrays and Hashes. Arrays and Hashes are members of the Enumerable class, which has a lot of cool methods available for use. Lets take a look at one of these methods : #cycle.

The cycle method can be used to repeat an operation given in the block. The number of cycles can be specified, and if not, the block will repeat forever (until the user breaks it using ctrl-C)

We can use the cycle method on an array:

```ruby
 #For example, to practice spelling words by repeating the list 3 times

          words_array = ["daybreak", "disbursement", "domestic", "deficient", "devour", "diffidence", " " ]

          words_array.cycle(3){|word| puts word}

          #output will be:
          daybreak
          disbursement
          domestic
          deficient
          devour
          diffidence

          daybreak
          disbursement
          domestic
          deficient
          devour
          diffidence

          daybreak
          disbursement
          domestic
          deficient
          devour
          diffidence
```

The cycle method can also be used for hashes. Below, I combine the cycle on the array and hash

```ruby
weekday=%w[Monday Tuesday Wednesday Thursday Friday Saturday Sunday].cycle

          yoga_classes = {
                "Power Hour"=> "Sarah",
                "Core Vinyasa"=> "Kevin",
                "Beginner Yoga"=> "Jill",
                "Ashtanga Vinyasa"=> "Emily",
                "Yin-Yoga"=> "Karen",
                "Advanced Yoga"=> "Tim"
                }

        schedule= yoga_classes.cycle

        10.times do
        today=weekday.next
        todays_class = schedule.next[0]
        todays_instructor = schedule.next[1]
        puts "#{today}'s class is #{todays_class} with #{todays_instructor}"
        end

        #the output is a schedule that changes every week:

          Monday's class is Power Hour with Kevin
          Tuesday's class is Beginner Yoga with Emily
          Wednesday's class is Yin-Yoga with Tim
          Thursday's class is Power Hour with Kevin
          Friday's class is Beginner Yoga with Emily
          Saturday's class is Yin-Yoga with Tim
          Sunday's class is Power Hour with Kevin
          Monday's class is Beginner Yoga with Emily
          Tuesday's class is Yin-Yoga with Tim
          Wednesday's class is Power Hour with Kevin
```
Make sure to add a break or quantify the number of times you want the cycle to run through!

