# Monty Hall Problem (modified)

The monty hall problem is a common statistical problem that highlights unexpected outcomes.  In the Monty Hall show, contestants are shown three doors.  Behind one is a car, and behind two there are goats.  The contestant chooses a door, and they are trying to guess which door the car is actually behind.  The odds of being correct are 1 in 3.

The twist of the Monty Hall problem is that the host then chooses another door and opens it, removing it from your set of choices. The question becomes whether it is in the contestants favor to switch.  Most people intuitively say no. At first glance, it looks like there are only two choices left, and your odds are just 50/50 now.  This is actually incorrect, but it is often poorly explained as to why. Up until the host removed the door, we are dealing with random events and choices.  The host, however, is not acting randomly. The host knows where the car is, and is avoiding revealing the car. Essentially, this deviation from random probability changes the outcome and the odds of winning a car when you switch. The host has acted as a "NOT" operator, and eliminated all other incorrect choices.  If you chose the car (which was a 1 in 3 chance of having happened), you would win by sticking with your door. If your initial choice was incorrect, then the door you are left with will have the car, by the design of the host. Since you had a 2 out of 3 chance of being wrong initially, then switching carries a 2 out of 3 chance that you'd win the car.

I have noticed a lot of people tend to disagree with this explanation, and believe even if the host acts randomly that the results will still produce a 1/3 for staying with your original choice, and 2/3 for switching when prompted. I think the argument of those who disagress is that the results aren't caused by the host introducing biased and non-random choices, but rather some complicated application of statistics.  Due to this, I have created a simulation of this scenario.

In this particular scenario, we do not give the host the ability to know what door the car is behind.  The host obviously won't open the door the contestant chose, but he will randomly open one of the other two doors.  The door will either have a car or a goat behind it.  If the host picks a door to open and the car is revealed, then the contestant has chosen incorrectly, and they lose. If the host picks a door to open and a goat is revealed, the contestant has the chance to switch their door (just like in the classic Monty Hall scenario).  After the contestant chooses to switch doors or stay with their choice, both doors are open to reveal if they have won or not.  

The expected results here is that the host will randomly reveal the car (when the first door is opened) 33% of the time.  The contestant is expected to initially choose the correct door another 33% of the time.  The door they'd have the option to switching to will have the car 33% of the time.  All doors have a 1/3 chance of having the car, and no choices made will ever change the fact that both the initial choice and the subsequent switch/stay choices all have the same 1 in 3 odds of being correct.

# Results according to this python simulation:

In this modified example, where the host randomly picks a door to open (and can reveal the car causing the contestant to immediately lose), it does not matter if the contestant switches or stays. The simulation shows that if the contestant makes it to the final round and has the option to switch their door, there is no statistical difference in their odds of winning whether they switch or stay with the original choice. Both scenarios result in a win rate of roughly 33.3% (with only small variations due to randomness).

This proves that the intuitive choice would in fact be correct if randomness was preserved.  The classic Monty Hall problem only offers different odds because of direct manipulation and statistical bias from the host. For comparison, I have also made a simulation for the standard Monty Hall scenario, found here:

https://github.com/nicknomo/MontyHallStandard

# Example Output:

Number of games played: 900000

If contestant STAYS:

  Wins: 299876
  
  Losses: 600124
  
  Win rate: 33.32%


If contestant SWITCHES:

  Wins: 300229
  
  Losses: 599771
  
  Win rate: 33.36%
