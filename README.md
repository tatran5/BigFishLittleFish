# BigFishLittleFish
With Blueprint

Fish class(es)
- All inherit from BP_Fish
- All should have unique FishType to be set in constructor or when BeginPlay is called
- May be a good idea to document size and resize in BeginPlay. Different types of fish should have different sizes because this affects prey/predator behavior. Document all fish size/scale within this README.

New fish 
- Make it inherits from BP_Fish because BP_Fish has all movement/action and collision handling implementation.
- Link the node BeginPlay to set FishType to the desired type (ex: "Tiny")
- Update SpawnFish and TransformFish functions within BP_Fish by adding an additional switch case for FishType. These two functions are necessary for Spit and Swallow to work correctly.
- Put the new blueprint inside BluePrints/Fish folder

New level 
- Put BP_Global in the scene regardless for now. This is essential to store all the fish swallowed by player. Tea will try to eliminate this step by looking into static variables within blueprint (currently have not found yet.)

Fish size/scale
- Default/InitialDefault
- Glow
- Acid
- Starfish
- Tiny