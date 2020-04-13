---
layout: post
author: Blake
title: Fourth Blog
excerpt_separator: <!--more-->
---
1/2 of Pre-beta 2 and Pre-beta FINAL Blog Post

<!--more-->

## Current Progress + Boss Attacks Meeting

I left off on my last blog post talking about how we had very little boss attacks implemented/planned to be implemented. I had created a lot more simple designs that could be easily implemented. Obviously COVID-19 impacted our ability to turn this boss into what it could be. There's also a lot of animation that has to be done with every boss attack so we were limited in what we were able to do moving forward.

During the week after the March 22nd studio meeting, Gino, Thomas, Tolu, and I held a designers meeting. During this meeting we talked about how we don't have a lot of time left to implement new things. Every attack we design requires a cetain amount of animation and at this point in time we had virtually no boss animations. In this meeting we discussed what we would be satisfied with as an end result. 

After a lot of discussion we settled on 6 attacks.

1. The wall attack that I prototyped

2. Throw sword/slam

3. Throw sword/slam w/ spikes

4. An air lazer attack

5. A ground lazer attack

6. A charging attack

Some are a little similar. The overall goal of this meeting was to try to make as many attacks as possible while reusing as many animations as possible. A lot of these attacks start out the same, have different intermediate actions, and similar endings. We ended the meeting with the impression that the lazor attack could potentially not make it into the game because it requires the most assets from other pods. 

## Playtesting

Once Gino got a few of the Boss attacks implemented they needed to be tested. This was my only Jira task for the remainder of this sprint. I spent time looping each attack that had been implemented so far. Theis was teh feedback that I had for Gino.

- Boss doesn't give any indication that it's charging versus teleporting to it's sword/slam

- Boss charges too fast for the player to react

- Missing Reference bug breaks the Boss Attack - Scriptable Object generator

- Wall Attack missing spikes

- Boss teleport VFX happens when Io teleports

Without Boss health and Io health implemented in this Unity MVP scene, it was too difficult to dertermine if Io had a large enough window to damage the boss. 


## Studio Meetings

March 29th - Discord

April 5th - Discord