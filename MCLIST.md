# Available actions through variables

## `MC`

## `thePlayer`
> ### Reference (`EntityPlayerSP` or `EntityPlayer`)

#### Properties

| Type                | Name                                | Description                                             |
|---------------------|-------------------------------------|---------------------------------------------------------|
| Minecraft           | mc                                  | Reference to the Minecraft game instance.               |
| String              | username                            | The player’s username.                                  |
| int                 | dimension                           | The dimension the player is currently in.               |
| String              | skinUrl                             | URL to the player's skin texture.                       |
| int                 | score                               | Player's current score. Saved in NBT.                   |
| InventoryPlayer     | inventory                           | Player’s inventory instance.                            |
| Container           | inventorySlots                      | Current open container GUI.                             |
| boolean             | sleeping                            | Whether the player is sleeping.                         |
| ChunkCoordinates    | bedChunkCoordinates                 | Player's bed location.                                  |
| int                 | sleepTimer                          | How long the player has been sleeping.                  |
| ChunkCoordinates    | playerSpawnCoordinate               | Player’s set spawn point.                               |
| ChunkCoordinates    | startMinecartRidingCoordinate       | Initial coordinate when starting to ride a minecart.    |
| boolean             | inPortal                            | Whether the player is currently inside a portal.        |
| float               | timeInPortal                        | Progress of portal teleportation.                       |
| float               | prevTimeInPortal                    | Portal progress from previous tick.                     |
| int                 | timeUntilPortal                     | Cooldown before portal teleportation can happen again.  |
| MovementInput       | movementInput                       | Handles player's input (movement, jumping, sneaking).   |
| float               | moveStrafing                        | Left-right strafe input.                                |
| float               | moveForward                         | Forward-backward movement input.                        |
| boolean             | isJumping                           | Whether the player is attempting to jump.               |
| float               | moveSpeed                           | Player's movement speed.                                |
| float               | defaultPitch                        | Default pitch angle.                                    |
| float               | cameraPitch                         | Camera tilt.                                            |
| boolean             | isMultiplayerEntity                 | Whether the player is in a multiplayer world.           |
| float               | swingProgress                       | Swing animation progress.                               |
| float               | prevSwingProgress                   | Previous tick’s swing progress.                         |
| int                 | health                              | Current health.                                         |
| int                 | prevHealth                          | Health from previous tick.                              |
| int                 | hurtTime                            | Time since last damage.                                 |
| int                 | maxHurtTime                         | Max duration of hurt animation.                         |
| int                 | deathTime                           | Time since player died.                                 |
| int                 | attackTime                          | Time between attacks.                                   |
| float               | attackedAtYaw                       | Direction player was hit from.                          |
| float               | field_9365_p (camera yaw?)          | Internal animation variable.                            |
| int                 | livingSoundTime                     | Cooldown for ambient sounds.                            |
| int                 | scoreValue                          | Score awarded when killed.                              |
| Entity              | currentTarget                       | Target the player is attacking or interacting with.     |
| int                 | numTicksToChaseTarget               | Ticks remaining to chase a target.                      |


---

#### Methods

| Return Type         | Function Name                        | Arguments                                         | Description                                             |
|---------------------|--------------------------------------|--------------------------------------------------|---------------------------------------------------------|
| void                | moveEntity                           | (double dx, double dy, double dz)                | Moves the player in the world.                          |
| void                | updatePlayerActionState              | ()                                               | Updates movement (strafing, jumping, etc.).            |
| void                | onLivingUpdate                       | ()                                               | Tick handler: portals, achievements, movement.         |
| void                | resetPlayerKeyState                  | ()                                               | Resets all movement key states.                        |
| void                | handleKeyPress                       | (int key, boolean pressed)                       | Handles key state changes.                             |
| void                | writeEntityToNBT                     | (NBTTagCompound nbt)                             | Serializes player data.                                |
| void                | readEntityFromNBT                    | (NBTTagCompound nbt)                             | Deserializes player data.                              |
| void                | closeScreen                          | ()                                               | Closes current GUI screen.                             |
| void                | displayGUIEditSign                   | (TileEntitySign sign)                              | Opens sign editor GUI.                                 |
| void                | displayGUIChest                      | (IInventory chest)                                 | Opens chest GUI.                                       |
| void                | displayWorkbenchGUI                  | (int x, int y, int z)                              | Opens crafting GUI.                                    |
| void                | displayGUIFurnace                    | (TileEntityFurnace furnace)                        | Opens furnace GUI.                                     |
| void                | displayGUIDispenser                  | (TileEntityDispenser dispenser)                  | Opens dispenser GUI.                                   |
| void                | onItemPickup                         | Entity item, int amount                          | Triggers item pickup effect.                           |
| int                 | getPlayerArmorValue                  | ()                                               | Gets player's total armor level.                       |
| void                | sendChatMessage                      | (String message)                                   | Sends a chat message. Supports `#` commands.           |
| void                | dropCurrentItem                      | ()                                               | Drops currently held item.                             |
| void                | dropPlayerItem                       | (ItemStack itemstack)                              | Drops a specified item.                                |
| void                | dropPlayerItemWithRandomChoice       | (ItemStack itemstack, boolean flag)                | Drops item with possible randomization.                |
| void                | joinEntityItemWithWorld              | (EntityItem entityitem)                            | Joins an item with the world entity list.              |
| boolean             | canHarvestBlock                      | (Block block)                                      | Checks if player can harvest a block.                  |
| float               | getCurrentPlayerStrVsBlock           | (Block block)                                      | Gets block breaking speed.                             |
| boolean             | isMovementBlocked                    | ()                                               | Whether player movement is blocked.                    |
| void                | collideWithPlayer                    | (Entity entity)                                    | Called on entity collision.                            |
| void                | onDeath                              | (Entity entity)                                    | Called when player dies.                               |
| void                | addToPlayerScore                     | (Entity entity, int i)                             | Increments score.                                      |
| float               | getEyeHeight                         | ()                                               | Returns player’s eye height.                           |
| boolean             | attackEntityFrom                     | (Entity entity, int i)                            | Called when damaged.                                   |
| void                | damageEntity                         | (int i                                            | Applies damage to the player.                          |
| void                | useCurrentItemOnEntity               | (Entity entity)                                   | Uses held item on entity.                              |
| ItemStack           | getCurrentEquippedItem               | ()                                               | Returns currently held item.                           |
| void                | destroyCurrentEquippedItem           | ()                                               | Destroys held item.                                    |
| void                | swingItem                            | ()                                               | Performs swing animation.                              |
| void                | attackTargetEntityWithCurrentItem    | (Entity entity)                                   | Attacks the target with held item.                     |
| void                | respawnPlayer                        | ()                                               | Respawns the player.                                   |
| void                | onItemStackChanged                   | (ItemStack itemstack)                             | Called when itemstack changes.                         |
| void                | setEntityDead                        | ()                                               | Marks entity as dead.                                  |
| boolean             | isEntityInsideOpaqueBlock            | ()                                               | Checks if inside an opaque block.                      |
| EnumStatus          | sleepInBedAt                         | (int x, int y, int z)                             | Attempts to sleep.                                     |
| boolean             | isInBed                              | ()                                               | Returns if player is in bed.                           |
| float               | getBedOrientationInDegrees           | ()                                               | Gets player’s bed orientation.                         |
| boolean             | isPlayerSleeping                     | ()                                               | Is player sleeping.                                    |
| boolean             | isPlayerFullyAsleep                  | ()                                               | Is player fully asleep.                                |
| void                | addChatMessage                       | (String s)                                         | Adds a chat message.                                   |
| ChunkCoordinates    | getPlayerSpawnCoordinate             | ()                                               | Gets player’s spawn point.                             |
| void                | setPlayerSpawnCoordinate             | (ChunkCoordinates coords)                          | Sets player’s spawn point.                             |
| void                | triggerAchievement                   | (StatBase statbase)                                | Triggers an achievement.                               |
| void                | addStat                              | (StatBase statbase, int i)                         | Increments a stat.                                     |
| void                | jump                                 | ()                                               | Makes player jump.                                     |
| void                | moveEntityWithHeading                | (float strafe, float forward)                      | Moves player based on input.                           |
| void                | addMovementStat                      | (double x, double y, double z)                     | Increments movement stat.                              |
| void                | addMountedMovementStat               | (double x, double y, double z)                    | Increments mounted movement stat.                      |
| void                | fall                                 | (float distance)                                   | Applies fall logic.                                    |
| void                | onKillEntity                         | (EntityLiving entity)                              | Called when player kills something.                    |
| void                | setInPortal                          | ()                                               | Triggers portal behavior.                              |
