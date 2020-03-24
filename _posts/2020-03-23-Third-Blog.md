---
layout: post
author: Blake
title: Third Blog
excerpt_separator: <!--more-->
---
Pre-Beta 1 and 1/2 of Pre-beta 2 Blog Post

<!--more-->

## Revisiting an Old Design Concept (1 Hour 30 Min)

At our March 8th meeting Gino shared that the project leads decided to have the player's gameplay experience focused more on platforming than combat. This didn't really impact my already comopleted prototypes, but it didn't impact prototypes I had planned to make.

Gino brought up my old design where the boss would summon a wall of projectiles with a small game.

![Old-Design](/WSoft-Dev-Blog/images/Boss_Attack_Sketch1.png)

Flaws of this design were discussed in my first blog post, but Gino wanted to know if I could revisit this concept and make it work in our now platforming-centric game.

I spent around an hour and a half turning this design into a concept that I could make a prototype around.

#### Phase 1

![Phase1-Design](/WSoft-Dev-Blog/images/Wall_Prototype_Phase1.png)

Instead of a wall of projectiles I changed them to just solid crystal walls. I think the player should have the option to blink/teleprot through them since there is a finite amount of teleportation that could be done during this attack. The walls break right before the edge of the arena to prep the player for phase 2 of the attack. 

#### Phase 2

![Phase2-Design](/WSoft-Dev-Blog/images/Wall_Prototype_Phase2.png)

The twist is that there are now spikes at the side of the arena that will damage the player if pushed into them.

#### Phase 3

![Phase3-Design](/WSoft-Dev-Blog/images/Wall_Prototype_Phase3.png)

Phase 3 is more of the same, but more difficult. Spikes come up from the ground in a wave, forcing the player to stay on the moving walls.

## Obtaining Boss Sprite (30 Min)

I really didn't like how in my last prototype the boss was just a black box. I know prototypes are suppossed to be quick implementations and not necessarily meant to look good, but I feel better when things I make are nice to look at. That's why I wanted to put the Bosses' sprite in my next prototype.

However, the only realatively finished sprite I could find of the boss was on Discord with no transparent pixels preserved (the part of the PNG that was suppossed to be transparent was not a white and gray checkerboard). 

![Not-Transparent](/WSoft-Dev-Blog/images/Old_Crystal_Boss.png)

I foolishly started erasing these pixels using Krita and my drawing tablet for 20 minutes and hardly accomplished anything. Then I realized that Krita can use the Fill Tool to erase as well. After altering the Threshold of the Fill Tool, I was able to quickly make the background of the sprite transparent again, allowing it to be used in my Unity prototype scene.

![Transparent](/WSoft-Dev-Blog/images/Crystal_Boss.png)

**I DID NOT CREATE THIS BOSS, I JUST GAVE IT A TRANSPARENT BACKGROUND TO USE IN PROTOTYPES**

## Crystal Wall Protoype (6 hours)

This was my 2nd DOTween prototype so I was more comfortable going into this script, but I still ran into some issues that I will bring up when discussing each phase. I also took some time to make sure my code was a lot cleaner in this protoype script than my previous. In my previous prototype I had a script for each phase and a lot of duplicating code. In this script I had 3 bool variables and 3 functions that had the code for each phase's action. The value of the bool variables determined what actions were executed in the script.

#### Phase 1

![phase1-prototype](/WSoft-Dev-Blog/images/crystal-wall-phase1.gif)

This phase took WAY longer than I was expecting it to. It didn't take too long to create all the crystal walls using primitive Unity objects, but I spent a lot of time on moving the walls. I wanted my walls to move at constant speed, but no matter what Ease I set for the DOMove or DOPath (both DOTween methods I tried) the walls would move faster at the beginning of their Tween Sequance and slow down at the end. I tried many different Eases, but even the Linear Ease maintained the same pattern of speed.

I spent too much time trying to make DOTween move at a constant speed (which may not even be possible). What I ended up doing was adding a Ridigbody to my Wall containers and set their velocity after setting them to be active game objects. 

#### Phase 2

![phase2-prototype](/WSoft-Dev-Blog/images/crystal-wall-phase2.gif)

This was too hard to implement. I just have a container that holds 9 spikes that moves to a certain Transform component with DOMove().

#### Phase 3

![phase3-prototype](/WSoft-Dev-Blog/images/crystal-wall-phase3.gif)

I googled ways to move individual game objects in a wave, but didn't find much. Instead of wasting time looking for a perfect solution I created 18 variables in my script. 9 for each spike and 9 Transform components for the spike to stop at. Then I just call a series of Coroutines with an increasing delay which creates a wave of spikes coming up from the ground.

## Voice Chat Recap

During our voicechat on Friday, Gino said that we need more boss attacks. We espeically need more basic attacks that might not have 3 different phases. For one reason or another, our pod hasn't been able to churn out the number of attacks that we expected to have at this point in Project Blue. So we discussed abandoning the necessity for all attacks to have 3 phases. We might have to abandon the 3 phases of a boss fight altogether. 

## Prototyping a Phase from a previous concept (2 Hours 30 Min)

Dodging a thrown projectile is a pretty basic attack. The Phase 1 of my Guardian prototype is exactly these concept of dodging a projectile. Gino said we needed attacks for the Guardian so I decided to prototype this phase design below.

![phase1-guardian](/WSoft-Dev-Blog/images/Guardian_Prototype_Phase1.png)

Since this prototype was only one phase there was a lot less programming and since I'm becoming more familiar with DOTween I was able to implement it faster. I spent some time looking at DOTween Eases and found this good graph that shows the movement speed graph of various easings.

![easing-chart](/WSoft-Dev-Blog/images/easing-chart.png)

The main time sink associated with this prototype was a bug I found in Robbert's Boss Projectile script. The script has a method of assigning stages to the projectile. I wanted the projectile in this script to be two stages. In the first stage I wanted the sword to spin for a second ro two after it spawns. Then in the second stage I wanted it to fly at the player's position. The bug is after you finish editing the values on the Boss Projectile script, it recompiles and sets NumStages back to one, forgetting the details of the second stage. At first I thought it was something wrong with how I was instantiating the object or editing the prefab, but after communicating with Robert about this scripts behavior we determined it was a bug.

Here is the prototype gif:

## Pod/Studio Meeting Recap

Because of a variety of reasons, we're cutting out the Crystal Caves boss. I had created 2 prototypes for this boss, but I think that work can be salvaged by repurposing those attacks for the Guardian boss instead. I feel really bad for the artists time spent creating boss sprites and animations because they're work can't be salvaged like mine. We talked about how this is a really unfortunate thing that can happen in the industry when working on video games. Sometimes unexpected things will arise the hinder the outcome of your project. Fortunately, our project was set up in a way for us to re-scope. Nico talked about how having a finished AND polished game on your portfolio is better than a finished game. If we had kept the Crystal Caves boss, there was no guarentee that the game would have been polished.

By Wednesday we need to have a list of all the attacks we expect to have on the Guardian boss so that they can be programmed and tested. We discussed that while having Unity prototypes are very useful for fully visualizing the attack, they aren't completely necessary to program the attacks into scriptable objects. Having designs with a written description is enough to program the attacks so that is what I decided to focus on next.

## Creating More Simple Designs (4 Hours 30 Min)

We only have 3 attacks total (ones that I made). I think I am the only designer that took the Studio for credit which might be a reason why we only have 3 designs. My goal for thsi set of designs was to come up with a bunch of simple attacks. Once we have a lot of attacks, later this week when we have a designer meeting we can choose which attacks to use instead of being forced to use what we have.

#### Falling Rubble

![falling-rubble](/WSoft-Dev-Blog/images/falling-rubble.png)

The boss summons rubble from the environment to fall down on the player. In this design I drew them falling in a wave, they could fall in a random pattern as well.

#### Multiple Sideways Swords

![multiple-sideways-sword](/WSoft-Dev-Blog/images/multiple-sideways-sword.png)

This attack is kind of similar to my Guardian prototype. Multiple copies of the Guardian's sword spawn, rotate, and then fly at the player. Again, in the design they fly in a wave, but they could be random instead.

#### Falling Platforms with Spikes

![falling-platforms-spikes](/WSoft-Dev-Blog/images/falling-platforms-spikes.png)

The Guardian creates falling platforms that the player must hop on to avoid summoned spikes at the bottom of the stage.

#### Shield Rush

![shield-rush](/WSoft-Dev-Blog/images/shield-rush.png)

The Guardian uses magic/energy to create a "shield" in front of it and charges towards the player.

#### Flying Shield Rush

![flying-shield-rush](/WSoft-Dev-Blog/images/flying-shield-rush.png)

Very similar concept to the last attack. However, in this version the Guardian jumps up in the air first before rushing towards the player's position.

#### Sword Beam

![sword-beam](/WSoft-Dev-Blog/images/sword-beam.png)

While on the ground, the Guardian spins it's sword in front of itself very fast. A beam then shoots out of the center and is fired at the player.

My computer was acting really weird while I was drawing these sketches. First, my drawing tablet was raising a error about 75% of the time I tried using the "CTRL + Z" macro on my tablet. I had no idea what the error was saying since it was in mandarin. Along with this, every time I tried to press "CTRL + S" to save, my Windows would bring up the accessability window and ask me if I wanted to turn on speech assistance. Krita started sucking up most of my CPU so all of my other programs became unresponsive. For a few minutes I thought Krita crashed before I was able to save my designs. Luckily I was able to save once it became responsive again. I figured a restart was required because something obviously was wrong. When trying to pin my chrome tabs, they would close instead. I have no idea what went wrong and my drawing tablet was still being unresponsive at times. However, another reset of Krita seemed to solve things. I'm not sure if the problem is Krita, my drawing tablet, or Windows. 

## Playtesting Latest Build (30 Min)

I spent some time playtesting teh latest build of the game. This was done before I designed the 6 designs above. I wanted to refresh myself in all the ways Io could move and dodge.

## Confluence Pages (30 Min)

I created some Confluence pages to keep my completed work organized and in one place. Also to create a better way to share the work I've done with my pod.

## Meetings (5 Hours)

March 8th (AKA The Last In-Person Meeting)

March 20th Bosses VC Pod Meeting 

March 22nd Studio Zoom Meeting