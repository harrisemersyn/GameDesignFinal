GameDesignFinal
---------------

CSC186 Game Development Final Project Files (Unreal 4)

The only (almost) useable asset aesthetic-wise is the SpotlightObject.uasset. The rest need different models. This is only the code side of what is needed for the game in Unreal.

When importing assets, the following needs to be changed: edit > project settings > engine > navigation mesh > runtime generation > dynamic

Another important setting that needs to be changed is going into edit > project settings > physics > surface materials and changing the first surface material to be named "Player" and the second to be named "Object". **This MUST be done in order for ray tracing to work properly and for imports to function!**

In regards to the physical materials files, the player is already set to have the proper surface material. However, whenever you create an asset, and place it in game, you **must** give it the material that is named "ObjectPhysicalMaterial.uasset" in the settings of the actor. If it is not given this material, raytracing won't work with it, and it won't function as an obstacle the player can hide behind.

Current Files
--------------

In Raw_Assets:

SpotlightObject.uasset - Is a combination of a spotlight object and a cone object. The cone is not visible, and used for detecting overlap. Upon overlap, the level will restart. May need resizing.

AICharacter.uasset - This is the object that will pathfind and move. There are multiple things you need to do in order to set this up. First, under place actors, place down a "Nav Mesh Bounds Volume", and size the mesh to cover the entire level. This will keep the AI from pathfinding into objects. To see the objects the navmesh effects, press "P" and it will be highlighted in green. This is all you need to do, unless you don't want the AI pathfinding into a specific area. In that case, use the "NavigationBlocker.uasset" and place it in the spots an AI should not be allowed to pathfind into. Then you will need place in 4 objects called "AIPathPoint1.uasset, AIPathPoint2.uasset, AIPathPoint3.uasset, AIPathPoint4.uasset". The AICharacter is programmed to follow points in the order 1-4. It will pick the closest instance of each number to pathfind to in order, so as long as characters and points are spread out, it should function as planned, and will be reusable. 

The AICharacter object needs to be connected to the spotlight object if you want the spotlights to move with the AI.

Collectible.uasset - Simply gets removed from the level after pickup.

In ThirdPersonBP:

ThirdPersonCharacter.uasset - This is not the completed character asset, and still has more features to be added! Currently, upon pressing E, movement speed and crouch movement speed is increased for 8 seconds, and on cooldown for 20 seconds. There is nothing in the UI to indicate this yet, but there will need to be.

The Q button now adds invisibility functionality. If pressed, the player will not activate spotlights for 10 seconds. After, it is on a 60 second cooldown. This is also not reflected on the UI, and there is no indication the player is invisible. The color of the model may have to be changed to be more opaque during this action to reflect this state.

ThirdPersonExampleMap.umap & ThirdPersonExampleMap_BuiltData.uasset - Contains a global variable for the collectible count to update upon overlap.
