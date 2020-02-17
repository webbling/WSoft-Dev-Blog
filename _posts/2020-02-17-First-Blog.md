---
layout: post
author: Blake
title: First Blog
excerpt_separator: <!--more-->
---
Pre-Alpha 1 Sprint Post

<!--more-->

It has now been 2 weeks since Project Blue officially kicked off. I have been placed in the Bosses pod as part of the Design and Programming teams.

My Jira task for this sprint was to design potential boss attacks that could work for either the Crystal Caves boss (Bird) or the Abandoned City boss (Guardian).

## Pre-Design

Before thinking of the attacks I did a little bit of prep that would help me think of better attacks. Gino linked some videos related to designing boss battles on Confluence that I watched. I also watched some videos on my own of exciting boss battles. Another source of inspiration I had was to think of different Shonen Animes I've watched such as My Hero Academia and Attack of Titan. These shows have been interesting and hyped fight sequences that could work in a boss battle.

## Initial Concepts

Here are the first two concepts I came up with

![Ground Slam](/WSoft-Dev-Blog/images/Boss_Attack_Sketch3.png)

<!--more-->

![Spinning Projectile](/WSoft-Dev-Blog/images/Boss_Attack_Sketch2.png)

Best way to summarize my attack prototypes... ENVIRONMENT.

I really like the idea of the boss using the environment to help defeat the enemy. In my opinion, when bosses in video games do this it creates a feeling that the boss belongs in that area/level. I also tried to keep the players ability into account to make it feel like the player was adequately equipped to fight this boss. 

<!--more-->

In the first image the boss punches/slams the ground. As a result of this action, crystals/debris flies up from the ground. My main inspiration for this attack was from a few episodes of (no spoilers) My Hero Academia. I won't go into more specifics than that, but if you know then you know. 

This one is probably my favorite design of the two (which you can probably tell from increased quality). The player, who attacks in melee range, would use their teleport ability to escape the damaging environment the boss creates.

<!--more-->

The second image attack is a projectile orriented attack. The boss summons/levitates a single object that is launched quickly at the players position. My inspiration for this attack was the Enchanted Sword enemy from Terraria.

<!--more-->

![Terraria Sword](/WSoft-Dev-Blog/images/terraria_sword.jpg) 

This enemy in Terraria finds you underground, spins around for a seconds, and then launches itself at the player. That's how I'm envisioning the projectile would fly in this attack.

## Concept Feedback

Gino, the bosses pod lead, gave me some feedback about these concepts.

- Ground/Slam Attack

	- Great example of an attack I could see being used for the Crystal Caves boss. Straightforward explanation as how it forces the player to move. I am curious how exactly how the hazards should come up from the ground through. Should it all come up at once? Or should it move outward from the boss, appearing like a wave of crystals? Also, will it continue movement from the floor to the walls, and possibly even the ceiling? Don't worry about addressing these questions now though, as they can be answered after this attack is implemented.
	
- Projectile Targeted Attack

	- I could see this attack being more characteristic of the Abandoned City boss. Still prototype this. Consider using DOLookAt() to aim the projectile towards the player.

## Failed Concept

I had a third concept that I discovered wouldn't be impactful after recieving feedback about it.

![Failed Wall Concept](/WSoft-Dev-Blog/images/Boss_Attack_Sketch1.png)

This attack features a wall of environment/crystals/debris/whatever that the boss summons or levitates. After a brief moment for the boss to get the environment objects in position, it launches them outwards towards the player. There will be gaps in the wall of objects that the player can teleport to in order to dodge.

This wouldn't work in its current state because as Gino pointed out:

- Wall Attack

	- Does this assume the player cannot teleport through the boss's attacks?
	
The player has an ability where they can throw their sword and teleport to it. They wouldn't need to look for the gap in the current state of the attack because they could throw their sword through the projectile and teleport to it. This attack could still work, but it needs to be redesigned.

## Using Feedback

After speaking with Gino in person he reminded me of the 3 phases each boss will go through. The first phase introduces an attack, phase two will introduce a twist to the attack, and phase 3 will be a slightly amplified version of phase 2.

I went back to my first two concepts and created the attack in all 3 phases.

## Design Iteration

#### Crystal Ground Slam

![Crystal 1](/WSoft-Dev-Blog/images/Crystal_Prototype_Phase1.png)

Phase 1: An addition. The boss does a little bit of light flapping. While flapping its wings, it shoots crystals out from its wings. The boss lands lightly.

<!--more-->

![Crystal 2](/WSoft-Dev-Blog/images/Crystal_Prototype_Phase2.png)

Phase 2: Same core concept as before. In this phase the boss lands heavily instead of lightly after shooting projectiles from its wings. This heavy slam "breaks the ground" and sends out a wave of crystals from the ground. The crystals quickly degrade and break without additional effect.

<!--more-->

![Crystal 3](/WSoft-Dev-Blog/images/Crystal_Prototype_Phase3.png) 

Phase 3: A slight addition. After the actions of the Phase 1 and Phase 2 portion of this attack, the boss raises its wings and breaks off pieces of the crystals that came from the ground at the player, creating additional projectiles for the player to dodge.

#### Guardian Weapon Proficiency

![Guardian 1](/WSoft-Dev-Blog/images/Guardian_Prototype_Phase1.png)

Phase 1: The same mechanic from the original concept. The Guardian summons a phantom sword object that will teleport blink to the player very similar to the player's core ability. Might make the sword reappear right before hitting the player to give the player the chance to dodge when first encountering the attack.

<!--more-->

![Guardian 2](/WSoft-Dev-Blog/images/Guardian_Prototype_Phase2.png)

Phase 2: Where things get very interesting. Using its second bracelet, the Guardian summons a clone of itself and hovers above the player, demonstrating its mastery of the bracelet/weapon. After hovering for a second or two, they teleport and strike the player. I think it would be smart to give the player a chance to parry this attack rather than simply dodging, but if Io parries the clone she will take damage. 

<!--more-->

![Guardian 2](/WSoft-Dev-Blog/images/Guardian_Prototype_Phase3.png)

Phase 3: Combines Phase 1 and 2 essentially. The swords will strike first and then the Guardian + clone. The projectiles are staggered making it require a sequence of skilled dodging from the player.

## Next Sprint Plans

Currently I am awaiting approval from Gino on my iterated designs. Once approved I will be working on implementing them in Unity as Scriptable Objects.

## Meetings this Sprint

Feb. 2nd (2 Hours)

Feb. 9th (2 Hours) ABSENT
