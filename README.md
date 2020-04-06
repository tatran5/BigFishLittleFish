# BigFishLittleFish
Made with in Unreal Engine 4.24 using Blueprints.

## Adding New Types of Fish 
- Make the new fish inherit from BP_Fish. BP_Fish includes all moveand collision handling implementation.
- DO NOT scale fish manually in the viewport. Set the capsule component to 1.0, 1.0, 1.0. Otherwise, this will affect fish spawned later in the game (they will exponentially be scaled up or down).
- From the BeginPlay node, setup FishType, Size, Speed simimlarly to BP_FishTiny.
- Update SpawnFish and TransformFish functions within BP_Fish by adding an additional switch case for FishType. These two functions are necessary for Spit and Swallow to work correctly.
- Put the new blueprint inside BluePrints/Fish folder
- May be a good idea to document size and resize in BeginPlay. Different types of fish should have different sizes because this affects prey/predator behavior. Document all fish size/scale within this README.
- Add an image of the fish into Textures so that if this fish is eaten by the main player, the storage is updated with an image of this fish. Then, go to UI_GamePlay blueprint. Within function CreateFishImage, add the appropriate switch case. 

##New level 
- Put BP_Global in the scene regardless for now. This is essential to store all the fish swallowed by player.
- For any new puzzle level, open the level blueprint. For level preconstruct, have node Event Preconstruct -> Create Widget (UI_GamePlay) -> Add to Viewport. You can open level TestingGround blueprint to see the setup.

##BP_Fish class documentation:
- FishType: stores the type of current fish to avoid lots of casting
- IsAI: only false for player so that other fish responds correctly every tick as an AI
- DistanceOfDetection: player fish has to be within this distance to an AI fish for that fish to detect and hence run to/from the player
- FacingRight: whether fish is facing in the positive Y or negative Y direction
- RunInterval: fish only run away from player for <RunInterval> seconds. It will start to wander again if it does not face towards the player.
- RunTime: once fish is triggered to run from player, this tracks how long the fish has been running away from player (will reset back to 0 once it reaches RunInterval)
- WanderDirection: if the fish is wandering, this tracks the direction that the fish is wandering towards
- WanderInterval:
- WanderTime:

##Fish Size Order
- Default/InitialDefault: 1
- Swordfish: 1.7
- Manta Ray: 1.5
- Glowfish: 1.2
- Acid: 0.9
- Starfish: 0.8
- Bubble: 0.5
- Tiny: 0.4