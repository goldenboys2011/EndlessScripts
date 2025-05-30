# Available actions through variables

## `MC`

## `thePlayer`
> ### Reference (`EntityPlayerSP` or `EntityPlayer`)

#### Properties

| Name                   | Type            | Description                                            |
|------------------------|-----------------|--------------------------------------------------------|
| `mc`                   | `Minecraft`     | Reference to the Minecraft game instance.              |
| `username`             | `String`        | The player’s username.                                 |
| `dimension`            | `int`           | The dimension the player is currently in.              |
| `inventory`            | `InventoryPlayer` | Player's inventory system.                           |
| `inventorySlots`       | `Container`     | Active container the player is interacting with.       |
| `score`                | `int`           | Player's current score (saved in NBT).                 |
| `movementInput`        | `MovementInput` | Handles player's input (movement, jumping, sneaking).  |
| `moveStrafing`         | `float`         | Left-right strafe input.                               |
| `moveForward`          | `float`         | Forward-backward movement input.                       |
| `isJumping`            | `boolean`       | Whether the player is attempting to jump.              |
| `sleeping`             | `boolean`       | Whether the player is sleeping in a bed.               |
| `sleepTimer`           | `int`           | Ticks since the player started sleeping.               |
| `bedChunkCoordinates`  | `ChunkCoordinates` | Coordinates of bed when sleeping.                  |
| `playerSpawnCoordinate`| `ChunkCoordinates` | Player's set spawn position.                       |
| `startMinecartRidingCoordinate` | `ChunkCoordinates` | Position at minecart entry.                     |
| `inPortal`             | `boolean`       | Whether the player is in a portal.                     |
| `timeInPortal`         | `float`         | Portal teleportation progress.                         |
| `prevTimeInPortal`     | `float`         | Previous tick's portal progress.                       |
| `timeUntilPortal`      | `int`           | Portal cooldown in ticks.                              |

---

#### Methods

| Method                          | Signature                                           | Description                                                  |
|---------------------------------|-----------------------------------------------------|--------------------------------------------------------------|
| `moveEntity`                    | `(double dx, double dy, double dz)`                | Moves the player in the world.                               |
| `moveEntityWithHeading`         | `(float strafe, float forward)`                    | Applies player movement input to velocity.                   |
| `updatePlayerActionState`       | `()`                                               | Updates strafing, jumping, sneaking, and sprinting state.    |
| `onLivingUpdate`                | `()`                                               | Called every tick. Handles movement, portals, effects.       |
| `onUpdate`                      | `()`                                               | Standard tick update. Often overridden in subclasses.        |
| `jump`                          | `()`                                               | Makes the player jump.                                       |
| `swingItem`                     | `()`                                               | Performs hand swing animation.                               |
| `getCurrentEquippedItem`        | `(): ItemStack`                                    | Returns currently held item.                                 |
| `destroyCurrentEquippedItem`    | `()`                                               | Destroys the currently held item.                            |
| `attackTargetEntityWithCurrentItem` | `(Entity target)`                             | Attacks an entity with the current weapon.                   |
| `collideWithPlayer`            | `(Entity entity)`                                  | Handles entity collision.                                    |
| `dropCurrentItem`              | `()`                                               | Drops the currently equipped item.                           |
| `dropPlayerItem`               | `(ItemStack itemstack)`                            | Drops a specific item.                                       |
| `dropPlayerItemWithRandomChoice`| `(ItemStack itemstack, boolean flag)`             | Drops item with random offset.                               |
| `joinEntityItemWithWorld`      | `(EntityItem item)`                                | Adds dropped item entity to the world.                       |
| `preparePlayerToSpawn`         | `()`                                               | Prepares player instance to enter the world.                 |
| `readEntityFromNBT`            | `(NBTTagCompound nbt)`                             | Loads player data from NBT.                                  |
| `writeEntityToNBT`             | `(NBTTagCompound nbt)`                             | Saves player data to NBT.                                    |
| `setEntityDead`                | `()`                                               | Marks player for removal.                                    |
| `onDeath`                      | `(Entity killer)`                                  | Called when player dies.                                     |
| `respawnPlayer`                | `()`                                               | Respawn logic for singleplayer.                              |
| `onKillEntity`                 | `(EntityLiving target)`                            | Called when player kills an entity.                          |
| `getScore`                     | `(): int`                                          | Returns the player’s score.                                  |
| `addToPlayerScore`             | `(Entity entity, int value)`                       | Adds to player score on kill.                                |
| `addStat`                      | `(StatBase stat, int amount)`                      | Increments a given statistic.                                |
| `triggerAchievement`           | `(StatBase achievement)`                           | Awards a specific achievement.                               |
| `addChatMessage`               | `(String message)`                                 | Adds a chat message to the HUD.                              |
| `displayGUIChest`             | `(IInventory chest)`                               | Opens chest GUI.                                             |
| `displayWorkbenchGUI`          | `(int x, int y, int z)`                            | Opens workbench GUI at the given location.                   |
| `displayGUIFurnace`            | `(TileEntityFurnace furnace)`                      | Opens furnace GUI.                                           |
| `displayGUIDispenser`          | `(TileEntityDispenser dispenser)`                  | Opens dispenser GUI.                                         |
| `displayGUIEditSign`           | `(TileEntitySign sign)`                            | Opens sign editing GUI.                                      |
| `closeScreen`                  | `()`                                               | Closes the current GUI.                                      |
| `onItemPickup`                 | `(Entity item, int amount)`                        | Triggered when picking up items.                             |
| `sleepInBedAt`                 | `(int x, int y, int z): EnumStatus`                | Tries to sleep in a bed.                                     |
| `wakeUpPlayer`                 | `(boolean, boolean, boolean)`                      | Wakes player up.                                             |
| `isInBed`                      | `(): boolean`                                      | Returns true if the player is in bed.                        |
| `isPlayerSleeping`             | `(): boolean`                                      | Returns true if the player is sleeping.                      |
| `isPlayerFullyAsleep`          | `(): boolean`                                      | Returns true if sleep timer passed threshold.                |
| `isMovementBlocked`            | `(): boolean`                                      | True if movement is currently restricted.                    |
| `attackEntityFrom`             | `(Entity attacker, int damage): boolean`           | Handles being attacked.                                      |
| `damageEntity`                 | `(int damage)`                                     | Applies raw damage.                                          |
| `getEyeHeight`                 | `(): float`                                        | Gets the eye height.                                         |
| `getCurrentPlayerStrVsBlock`   | `(Block block): float`                             | Returns block break strength modifier.                       |
| `canHarvestBlock`             | `(Block block): boolean`                           | Whether the player can harvest the block.                    |
| `setInPortal`                 | `()`                                               | Marks the player as being inside a portal.                   |
| `addMovementStat`             | `(double dx, double dy, double dz)`                | Stats for regular movement.                                  |
| `addMountedMovementStat`      | `(double dx, double dy, double dz)`                | Stats for vehicle movement.                                  |
| `fall`                         | `(float distance)`                                 | Handles fall damage.                                         |

