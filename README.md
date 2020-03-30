# BigFishLittleFish
With Blueprint

New fish 
- Make it inherits from BP_Fish because BP_Fish has all movement/action and collision handling implementation.
- DO NOT do the scaling of the fish manually. Set the capsule component to 1.0, 1.0, 1.0. Otherwise, this will affect fish spawned later in the game (they will exponentially be scaled up or down).
- From BeginPlay node, setup FishType, Size, Speed simimlarly to BP_Tiny Fish.
- Update SpawnFish and TransformFish functions within BP_Fish by adding an additional switch case for FishType. These two functions are necessary for Spit and Swallow to work correctly.
- Put the new blueprint inside BluePrints/Fish folder
- May be a good idea to document size and resize in BeginPlay. Different types of fish should have different sizes because this affects prey/predator behavior. Document all fish size/scale within this README.
- Add an image of the fish into Textures so that if this fish is eaten by the main player, the storage is updated with an image of this fish. Then, go to UI_GamePlay blueprint. Within function CreateFishImage, add the appropriate switch case. 

New level 
- Put BP_Global in the scene regardless for now. This is essential to store all the fish swallowed by player.
- For any new puzzle level, open the level blueprint. For level preconstruct, have node Event Preconstruct -> Create Widget (UI_GamePlay) -> Add to Viewport. You can open level TestingGround blueprint to see the setup.

BP_Fish class documentation:
- FishType: stores the type of current fish to avoid lots of casting
- IsAI: only false for player so that other fish responds correctly every tick as an AI
- DistanceOfDetection: player fish has to be within this distance to an AI fish for that fish to detect and hence run to/from the player
- FacingRight: whether fish is facing in the positive Y or negative Y direction
- RunInterval: fish only run away from player for <RunInterval> seconds. It will start to wander again if it does not face towards the player.
- RunTime: once fish is triggered to run from player, this tracks how long the fish has been running away from player (will reset back to 0 once it reaches RunInterval)
- WanderDirection: if the fish is wandering, this tracks the direction that the fish is wandering towards
- WanderInterval:
- WanderTime:

Fish speed and size:
- Default/InitialDefault : 
- Starfish:
- Glow: 
- Acid: 
- Bubble:
- Manta Ray: 
- Tiny: 