# Big Fish, Little Fish
Made with Unreal Engine 4.24 using Blueprints.

\includegraphics[]{Images/Acidfish.png}

Big Fish, Little Fish pits the player against the mysterious depths of the sea and its dangerous terrain. As a peaceful big fish, you must swim across the ocean to reunite with the rest of your species, navigate coral mazes and ship doors, all while avoiding certain doom from hungry predators, apathetic sea urchins, and collapsing ship wreckage. To do so, you're going to need help getting around from your smaller fish friends by eating them to borrow their shape and size for a while. Swallow and spit nearby fish as necessary to adopt their abilities, get through perilous puzzles, and find your family!

# Features

-Recursive swallow and spit mechanic. Swallow stores eaten fish recursively, and spit spawns eaten fish into the level and transforms the player into the current fish on the top of the eaten stack. The direction fish are spawned is based on the player's look direction, and it checks using raycasting to determine if there is an obstacle that prevents them from spawning, in which case they are spawned in the nearest available area. Fish that have been spit out run from the player.

-Fish transformation. When the player swallows a fish, the player possesses the swallowed fish and gains its abilities, speed, look and size. When the player spits out a fish, they gain the abilities, size, and speed of the current fish on top of the eaten stack.

-Fish Abilities. There are 6 different fish the player can swallow and transform into, each with their own ability that allows the player to solve puzzles and navigate the levels. See list below for more details.

-Predator and Prey AI. When the player is not detected by a fish, fish wander by either picking a direction to swim in or following a set path (based on input from the level designer). If smaller than the player, fish flee in the opposite direction from the player. They also will swim into a hiding spot when threatened if a hiding position is defined by the level designer. If larger than the player, the fish will swim towards the player and attempt to eat them. If an obstacle blocks the fish's path, it will stop chasing the player. Fish detect the player when they are close enough to the player and are looking in the player's direction.

-Hazardous obstacles. Seaweed reduces the player's speed when the player runs into it; spikes and poison decrease the player's health when the player runs into it. The player has a short period of invulnerability when they take damage.

-Physics-based movement using velocities and drag.

-UI and Events System. Includes a start screen, level selection that updates when players collect stars, a how to play guide, and tutorial levels.

# Fish

-Acid Fish : Shoots out acid that can corrode metallic and wooden objects in the level.

\includegraphics[]{Images/Acidfish.png}

-Bubble Fish : Shoots out bubbles that can engulf and lift wooden boxes in the level. These bubbles pop when they hit spikes or when the player collides with it.

\includegraphics[]{Images/Bubblefish.png}

-Manta Ray : Can swim through sand in the level while other types of fish can't.

\includegraphics[]{Images/Mantaray.png}

-Starfish : Can break off up to 3 legs, each that move along with the player. When the main body collides with a leg, it reabsorbs the leg, allowing the player to break it off again.


-Swordfish : Can cut through seaweed in the level.


-Tiny Fish : Its small size allows it to swim through small passages.

\includegraphics[]{Images/Tinyfish.png}

# How To Play

-Use the arrow keys to swim around. 
-Swim into fish to automatically swallow them if they are smaller than you. You will lose a life/respawn if you collide with a larger fish. Watch the fish's behavior (they swim towards you if you are bigger than them and swim away if they are smaller) to determine whether you can swallow the fish. 
-Press S to spit out fish that you have already swallowed and transform into the previous fish. You cannot spit out a fish if your difference in size would cause you to get stuck in an area. 
-Press space to use the ability of the current fish you are possessing. For more info on fish abilities, read the How To Play Guide or play the tutorial levels.

