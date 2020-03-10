---
layout: post
author: Blake
title: Second Blog
excerpt_separator: <!--more-->
---
Pre-Alpha Final Sprint Post

<!--more-->

In this sprint I was tasked with implementing prototypes of my boss attack designs in Unity using DOTween, a Unity package. At the beginning of the sprint I was waiting for the boss projectile system to get finished so I spent some time looking into DOTween, BitBucket, and managing branches in a large project. 

## Reviewing DOTween Documentation (3 Hours)

DOTween is a Unity package that I have not worked with before. In my opinion it appears advertised as an animation package, but apparently it can be used to create quick prototypes of boss attacks.

I started at the Confluence page Gino made about DOTween. It gave very general concepts about what the package is and what it does. He linked the [Official DOTween documentation](http://dotween.demigiant.com/documentation.php) at the bottom of the Confluence page. I spent time looking at the different built in functions in the documentation.

I was still a little confused so I looked up some YouTube videos that gave examples of how to use DOTween.

- [Easy Movement Queueing, Paths, and Tweening in Unity](https://www.youtube.com/watch?v=PLFQp0TvsK0)

- [Unity + DoTween](https://www.youtube.com/watch?v=uRXm3UscUJM&t=3s)

## Working with Git/BitBucket (3 Hours)

Much like Seyhyun, I am not a big fan of git and really didn't use it before this semester. We're using BitBucket to handle our repository and branches. Max created a "Git Guidelines" Confluence page. I spent some time looking through this and familiarizing myself with how BitBucket works and how the Project_Blue repository is meant to be organized.

I encountered an issue with BitBucket when creating a new branch. I followed the Confluence page instructions, but for some reason my branch was not showing up in my shell client when typing "git branch". It did show up when running "git branch -a", but I was not able to checkout the branch for some reason, the command would not run. I tried deleting the branch and recreating it, but that didn't solve the issue. I found that using the GitHub for Desktop GUI application allowed me to switch to my branch. 

When launching the project in Unity, I thought I had some errors with my branch, but after reading through some Discord messages from Max I realized I could ignore the errors I was getting (Wwise errors).

Lastly, I reviewed how assets should be stored/organized in the Unity Project. I was initally confused about the purpose of the "_Development" folder. I didn't know if I should place my DOTween prototype scripts in this "_Development" folder or not. Later I found out that these prototype scripts won't be in the final project build so they should be placed in "_Development".

## Reviewing Boss Pod Tools (2 Hours)

Members of the Boss pod have created tools that will make it easier to me to implement my attack prototypes. Robert Keller implemented a detailed script that handles Boss Projectiles. Since both of my prototypes utilize projectiles, I needed to learn how this script works. Robert included many properties in his script such as multiple stages, different methods of projectile destruction, stage transitions, movement settings, etc so this took some time to look through and figure out what settings would effect my prototypes. 

An issue I found/ran into was instantiating projectiles. Gino set up a template prototype scene as a guide on how to build these prototypes. The projectile in his scene was not functioning correctly. It was meant to be set active in the Start() function and then instantiated/move towards the player after the boss jumps from one end of the template scene to the other. What was actually happening was it would instantiate after the boss moves and wouldn't move toward the player. A weird fix to these was to set the projectile game object as inactive in the scene heirarchy. I'm not sure how this fixed the issue, but I was now able to instantiate projectiles in my prototypes.

## Crystal Slam Attack Scripts (8 Hours)

Working with the DOTween package was tricky even after spending time looking through the documentation. A lot fo time was spent minorly agjusting float values and Game Object destinations until I achieved an attack prototype that looked good enough to share with the studio team. 

Making minor adjustments to variable after writing the scripts did annoy me that much. What ending up being a large issue was this delay that was being inserted into my DOTween sequence. My scripts are written to call a coroutine in the Start() function of the script. This coroutine calls my function that runs my DOTween sequence after a minor delay (never more than 2 seconds). However, my DOTween actions weren't actually executing until 20-30 seconds AFTER the code was seen. I proved this by writing a Debug.Log statement after my DOTween appends. This issue occured over all 3 of my scripts.

I brought this up with Gino and we spent some time looking at my Attack Phase scripts. Nothing was fundamentally different from my code than DOTween code he has written in the past. This is a persisting issue and I hope I can figure it out when implementing my next prototype. 

#### Phase 1

![Phase 1 Gif](/WSoft-Dev-Blog/images/crystal-slam-phase1.gif)

#### Phase 2

![Phase 1 Gif](/WSoft-Dev-Blog/images/crystal-slam-phase2.gif)

#### Phase 3 Version 1

![Phase 1 Gif](/WSoft-Dev-Blog/images/crystal-slam-phase3.gif)

#### Phase 3 Version 2

![Phase 1 Gif](/WSoft-Dev-Blog/images/crystal-slam-phase3-2.0.gif)

My one regret in this prototype was not making the arms flap on the blocky bird boss. I initially thought that this would have been impossible because you cannot Tween the position of a Game Object in 2 actions happening at the same time, but I realized afterwards that I could have rotated the arm Game Objects with a different DOTween action.

Initially when I shared my Phase 3 of this attack I got some feedback that it might not be extreme enough. I took that feedback and make version 2 of Phase 3 by adding moy projectiles for Io to dodge.

## Sprint Meetings (4 Hours)
<!--(4 Hours)-->

Feb 16th, 2020 - 2 Hours

Feb 23rd, 2020 - 2 Hours

We did not have an end of spring meeting because of spring break conflicting with our normal meeting times. We plan to have a makeup meeting as soon as possible after break. My hours this week were about 4 hours short. Next sprint I will do a better job of taking on more tasks and making sure I devote enough time to Project Blue. 