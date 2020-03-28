# BigFishLittleFish
With Blueprint

Beta Merge includes new puzzle, bubble fish implementation, UI, and updated swallow. Spit still remains buggy

New fish 
- Make it inherits from BP_Fish because BP_Fish has all movement/action and collision handling implementation.
- DO NOT do the scaling of the fish manually. Set the capsule component to 1.0, 1.0, 1.0. Otherwise, this will affect fish spawned later in the game (they will exponentially be scaled up or down).
- From BeginPlay node, setup FishType, Size, Speed simimlarly to BP_Tiny Fish.
- Update SpawnFish and TransformFish functions within BP_Fish by adding an additional switch case for FishType. These two functions are necessary for Spit and Swallow to work correctly.
- Put the new blueprint inside BluePrints/Fish folder
- May be a good idea to document size and resize in BeginPlay. Different types of fish should have different sizes because this affects prey/predator behavior. Document all fish size/scale within this README.
- Add an image of the fish into Textures so that if this fish is eaten by the main player, the storage is updated with an image of this fish. Then, go to UI_GamePlay blueprint. Within function CreateFishImage, add the appropriate switch case. 

New level 
- Put BP_Global in the scene regardless for now. This is essential to store all the fish swallowed by player. Tea will try to eliminate this step by looking into static variables within blueprint (currently have not found yet.)
- For any new puzzle level, open the level blueprint. For level preconstruct, have node Event Preconstruct -> Create Widget (UI_GamePlay) -> Add to Viewport. You can open level TestingGround blueprint to see the setup.

Fish speed and size:
- Default/InitialDefault : 1.0, 1.0
- Starfish: 0.85, 0.85
- Glow: 0.75, 0.75
- Acid: 0.65, 0.65
- Bubble: 0.35, 0.35
- Tiny: 0.25, 0.25
