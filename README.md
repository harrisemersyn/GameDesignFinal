GameDesignFinal
---------------

CSC186 Game Development Final Project Files (Unreal 4)

The only (almost) useable asset aesthetic-wise is the SpotlightObject.uasset. The rest need different models. This is only the code side of what is needed for the game in Unreal.

Current Files
--------------

In Raw_Assets:

SpotlightObject.uasset - Is a combination of a spotlight object and a cone object. The cone is not visible, and used for detecting overlap. Upon overlap, the level will restart. May need resizing.

Collectible.uasset - Simply gets removed from the level after pickup.

In ThirdPersonBP:

ThirdPersonCharacter.uasset - This is not the completed character asset, and still has more features to be added! Currently, upon pressing E, movement speed and crouch movement speed is increased for 8 seconds, and on cooldown for 20 seconds. There is nothing in the UI to indicate this yet, but there will need to be.

The Q button now adds invisibility functionality. If pressed, the player will not activate spotlights for 10 seconds. After, it is on a 60 second cooldown. This is also not reflected on the UI, and there is no indication the player is invisible. The color of the model may have to be changed to be more opaque during this action to reflect this state.

ThirdPersonExampleMap.umap & ThirdPersonExampleMap_BuiltData.uasset - Contains a global variable for the collectible count to update upon overlap.
