# TankNetLogo
[![platform](https://img.shields.io/badge/platform-netlogo-red.svg)](https://shields.io/) [![contributions](https://img.shields.io/badge/contributions-welcome-green.svg)](https://github.com/huangyz0918/TankNetLogo) 

A tank war strategy built by [NetLogo](https://ccl.northwestern.edu/netlogo/). 

![](https://i.loli.net/2018/10/17/5bc6eeb182cf0.png)

You can see two kinds of tank here:
- The Red one
- The Blue one

In this project, the blue tank has a temporary strongest strategy, which means it is very strong and you may lose it easily. You can not modify the code of the blue one, but you can modify the red one, and make it better than the blue one.

__If you have made your own red tank stronger than the blue tank__, You win! :collision:

You can submit your tank strategy (yours red tank code) through a pull request, and we will update our blue tank code according to your red tank code until there is another better red tank to strategy beat it. During this time, your github id and avatar will shown in the `README.md` here.

It's like a game of fighting, let's cheer, the first place is yours!


### What's NetLogo ?
You can checkout for more information at it's [homepage](https://ccl.northwestern.edu/netlogo/).

Here is the definition of NetLogo programming language from [wikipedia](https://en.wikipedia.org/wiki/NetLogo):

> NetLogo was designed, by Uri Wilensky, in the spirit of the Logo programming language, to be "low threshold and no ceiling". It teaches programming concepts using agents in the form of turtles, patches, links and the observer. NetLogo was designed for multiple audiences in mind, in particular: teaching children in the education community, and for domain experts without a programming background to model related phenomena. Many scientific articles have been published using NetLogo.

After all, it's a very easy programming language which can let you focus more on the programming logic of our battles.


### The Tank Battle Strategy

![](https://i.loli.net/2018/10/17/5bc6c7486353e.png)

Introduction to the UI:

- The `setup` button: Initialize the user interface.
- The `reset` button: Reset the war.
- The `go` button: Start animation and confrontation.
- You can use the `TankName` to put a name for your tank before creating it.
- You can set the `FirePower` through the progress bar, which is the power of per bullet.
- If you want to watch the tarck of tanks, you can set the `LeaveTrack?` to `on`.

The finite element state machine was used for the core part of this tank war game. We set the default status to `status-forward[v]` , `status-dodge-forward[args]` or `status-random-forward[tickNum]`, they have diffierent characteristics and downsides:

- In the status `status-forward[v]`, the tank will use the `v` as it's velocity to move forward.
- In status `status-back`, `status-right`, `status-left` and `status-stop`, the tank will go back, turn right/left and just stop.
- `status-random-forward[tickNum]` allows the tank to move forward at a random direction in a fixed time interval, which is can be set by input paramemter `tickNum`.
- `status-dodge-forward[args]` is a pretty tricky status, if other tank shooting by aiming at your tank, the best dodge strategy is to move in a direction perpendicular to its direction of motion, since the bullet has a delay before hitting yours.

