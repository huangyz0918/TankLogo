# TankLogo
[![platform](https://img.shields.io/badge/platform-netlogo-blue.svg)](https://shields.io/) [![contributions](https://img.shields.io/badge/contributions-welcome-green.svg)](https://github.com/huangyz0918/TankNetLogo) 

A tank war strategy built by [NetLogo](https://ccl.northwestern.edu/netlogo/). Share your ideas and strategies and win the game!

Want to have a try? See [demo](http://www.netlogoweb.org/launch#https://raw.githubusercontent.com/huangyz0918/TankLogo/master/TankLogo.nlogo).

![](https://i.loli.net/2018/10/17/5bc6eeb182cf0.png)

You can see two kinds of tank here:
- The Red one
- The Blue one

In this project, the red tank has a temporary strongest strategy, which means it is very strong and you may lose it easily. You can not modify the code of the red one, but you can modify the blue one, and make it better than the red one.

__If you have made your own red tank stronger than the blue tank__, You win! :collision:

You can submit your tank strategy (yours blue tank code) through a [pull request](https://yangsu.github.io/pull-request-tutorial/), and we will update our red tank code according to your blue tank code until there is another better blue tank to strategy beat yours. During this time, your github id and avatar will displaied in the `README.md` [here](https://github.com/huangyz0918/TankLogo#current-winner).

It's like a game of fighting, let's cheer, the first place is yours!


## What's NetLogo?
You can checkout for more information at it's [homepage](https://ccl.northwestern.edu/netlogo/).

Here is the definition of NetLogo programming language from [wikipedia](https://en.wikipedia.org/wiki/NetLogo):

> NetLogo was designed, by Uri Wilensky, in the spirit of the Logo programming language, to be "low threshold and no ceiling". It teaches programming concepts using agents in the form of turtles, patches, links and the observer. NetLogo was designed for multiple audiences in mind, in particular: teaching children in the education community, and for domain experts without a programming background to model related phenomena. Many scientific articles have been published using NetLogo.

After all, it's a very easy programming language which can let you focus more on the programming logic of our battles.

## How to get start?
- Install NetLogo in your machine or using the [NetLogo Web](http://www.netlogoweb.org/launch#https://raw.githubusercontent.com/huangyz0918/TankLogo/master/TankLogo.nlogo).
- Open the `TankLogo.nlogo` file (upload to the web server or double click in your computer).
- See the UI, and click the `setup` button, and you can see the yellow boundary which means the wall.
- Type a name for the red tank (or the blue one) in the `TankName` (input box), and click `create tank` button.
- Type another name for the another tank in `TankName` (input box), and click `create tank` button to create it.
- Use button `run` to begin the battle, use `reset` button to restart a game.


## The Tank Battle Strategy

![](https://i.loli.net/2018/10/17/5bc6c7486353e.png)

Introduction to the UI:

- The `setup` button: Initialize the user interface.
- The `reset` button: Reset the war.
- The `go` button: Start animation and confrontation.
- You can use the `TankName` to put a name for your tank before creating it.
- You can set the `FirePower` through the progress bar, which is the power of per bullet.
- If you want to watch the track of tanks, you can set the `LeaveTrack?` to `on`.

The finite element state machine was used for the core part of this tank war game. We set the default status to `status-forward[v]` , `status-dodge-forward[args]` or `status-random-forward[tickNum]`, they have diffierent characteristics and downsides:

- In the status `status-forward[v]`, the tank will use the `v` as it's velocity to move forward.
- In status `status-back`, `status-right`, `status-left` and `status-stop`, the tank will go back, turn right/left and just stop.
- `status-random-forward[tickNum]` allows the tank to move forward at a random direction in a fixed time interval, which is can be set by input paramemter `tickNum`.
- `status-dodge-forward[args]` is a pretty tricky status, if other tank shooting by aiming at your tank, the best dodge strategy is to move in a direction perpendicular to its direction of motion, since the bullet has a delay before hitting yours.


## Contribution Guides

The NetLogo is a pretty easy programming language, we wish you can get start as soon as possible, so if you have any question about NetLogo, please check out for the official [document](http://ccl.northwestern.edu/netlogo/docs/index2.html).

In this project, the only area you can modify are marked in the code via comments, you cannot make any changes related to the red tank, or we wouldn't accept your PR and update yours strategy. 

In your code, you can not modify the opponent's attributes, such as resetting the health and velocity of the red tank, but you can detect others' attributes. For example, you can detect the patch of the red code using `patch-here`.

To do some contributions, you need to install NetLogo firstly then clone your fork, double click the `TankLogo.nlogo` and run!

## FAQ
Why choose NetLogo as programming language? 
> Because NetLogo is quite easy and there are less people know how to use it than other languages, so if you want to get start, everybody is equal.

How can I get start ?
> Two steps, the first is install NetLogo. The second one is clone this repo and double click the `.nlogo` file and improve the tank.

How can I get if I win your tank ?
> The best tank will update according to your solution, and your Github avatar and name will display until somebody beats yours.

How to submit my solution ?
> Fork this repo and improve your code, test if it can really win the red tank, submit a pull request, done!

If I don't want to install NetLogo, how can I get start?
> You can use [NetLogo Web](http://www.netlogoweb.org/launch#https://raw.githubusercontent.com/huangyz0918/TankLogo/master/TankLogo.nlogo) to run your code.

## Current Winner 

|![](https://github.com/huangyz0918.png?size=60)|
|:----:|
|[huangyz0918](https://github.com/huangyz0918)|


## Licence

```
   Copyright 2018 Yizheng Huang

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.

```


