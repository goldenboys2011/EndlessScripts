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

## ``theWorld``

### Properties

| Type                        | Name                       |
|-----------------------------|----------------------------|
| boolean                     | flag                       |
| boolean                     | flag1                      |
| boolean                     | flag2                      |
| boolean                     | flag3                      |
| boolean                     | flag4                      |
| boolean                     | scheduledUpdatesAreImmediate |
| boolean                     | editingBlocks              |
| boolean                     | isNewWorld                 |
| boolean                     | findingSpawnPoint          |
| boolean                     | allPlayersSleeping         |
| boolean                     | multiplayerWorld           |
| boolean                     | field_31055_L              |
| int                         | i, j, k, l, i1, j1, k1, l1, i2, j2, k2, l2, i3, j3, k3, l3, i4, j4, k4 |
| int                         | autosavePeriod             |
| int                         | difficultySetting          |
| int                         | skylightSubtracted         |
| int                         | field_9437_g               |
| int                         | field_9436_h               |
| int                         | field_27168_F              |
| int                         | field_27172_i              |
| int                         | lightingUpdatesCounter     |
| int                         | lightingUpdatesScheduled   |
| int                         | soundCounter               |
| byte                        | byte0                      |
| double                      | d, d1, d2, d3, d4, d5, d6, d7, d8 |
| float                       | f1, f2, f3, f4, f5, f6, f7, f8, f9, f10, f11, f12, f13 |
| float                       | prevRainingStrength        |
| float                       | rainingStrength            |
| float                       | prevThunderingStrength     |
| float                       | thunderingStrength         |
| long                        | field_1019_F               |
| long                        | lockTimestamp              |
| long                        | l, l1                      |
| Random                      | rand                       |
| Chunk                       | chunk, chunk1              |
| Block                       | block, block1              |
| TileEntity                  | tileentity, tileentity1    |
| Entity                      | entity, entity1, entity2   |
| EntityPlayer                | entityplayer, entityplayer1 |
| MovingObjectPosition        | movingobjectposition, movingobjectposition1 |
| AxisAlignedBB               | axisalignedbb, axisalignedbb1 |
| ChunkProviderLoadOrGenerate| chunkproviderloadorgenerate |
| WorldProvider               | worldProvider              |
| IChunkProvider              | chunkProvider              |
| ISaveHandler                | saveHandler                |
| WorldInfo                   | worldInfo                  |
| BiomeGenBase                | biomegenbase               |
| NextTickListEntry           | nextticklistentry          |
| MetadataChunkBlock          | metadatachunkblock         |
| ChunkCoordIntPair           | chunkcoordintpair          |
| ChunkCache                  | chunkcache                 |
| Vec3D                       | vec3d, vec3d2              |
| Explosion                   | explosion                  |
| NBTTagCompound              | nbttagcompound             |
| List                        | lightingToUpdate, loadedEntityList, unloadedEntityList, loadedTileEntityList, field_30900_E, playerEntities, weatherEffects, field_1012_M |
| ArrayList                   | collidingBoundingBoxes     |
| TreeSet                     | scheduledTickTreeSet       |
| Set                         | scheduledTickSet, positionsToUpdate |
| MapStorage                  | field_28108_z              |
| Iterator                    | iterator, iterator1        |

### Methods

| Return Type            | Function Name                       | Arguments                                                                 |
|------------------------|-------------------------------------|---------------------------------------------------------------------------|
| WorldChunkManager      | getWorldChunkManager                | ()                                                                           |
| World                  | World                               | (ISaveHandler isavehandler, String s, WorldProvider worldprovider, long l) |
| World                  | World                               | (World world, WorldProvider worldprovider)                                  |
| World                  | World                               | (ISaveHandler isavehandler, String s, long l)                               |
| World                  | World                               | (ISaveHandler isavehandler, String s, long l, WorldProvider worldprovider)  |
| IChunkProvider         | getChunkProvider                    | ()                                                                         |
| void                   | getInitialSpawnLocation             | ()                                                                          |
| void                   | setSpawnLocation                    | ()                                                                          |
| int                    | getFirstUncoveredBlock              | (int i, int j)                                                              |
| int                    | getBlockId                          | (int i, int k, int j)                                                       |
| void                   | emptyMethod1                        | ()                                                                        |
| void                   | spawnPlayerWithLoadedChunks         | (EntityPlayer entityplayer)                                                 |
| void                   | saveWorld                           | (boolean flag, IProgressUpdate iprogressupdate)                             |
| void                   | saveLevel                           | ()                                                                        |
| boolean                | func_650_a                          | (int i)                                                                     |
| int                    | getBlockId                          | (int i, int j, int k)                                                       |
| Chunk                  | getChunkFromChunkCoords             | (int i, int j)                                                              |
| boolean                | isAirBlock                          | (int i, int j, int k)                                                       |
| boolean                | blockExists                         | (int i, int j, int k)                                                       |
| boolean                | doChunksNearChunkExist              | (int i, int j, int k, int l)                                                |
| boolean                | checkChunksExist                    | (int i, int j, int k, int l, int i1, int j1)                                |
| Chunk                  | getChunkFromBlockCoords             | (int i, int j)                                                              |
| boolean                | setBlockAndMetadata                 | (int i, int j, int k, int l, int i1)                                        |
| boolean                | setBlock                            | (int i, int j, int k, int l)                                                |
| Material               | getBlockMaterial                    | (int i, int j, int k)                                                       |
| int                    | getBlockMetadata                    | (int i, int j, int k)                                                       |
| void                   | setBlockMetadataWithNotify          | (int i, int j, int k, int l)                                                |
| boolean                | setBlockMetadata                    | (int i, int j, int k, int l)                                                |
| boolean                | setBlockWithNotify                  | (int i, int j, int k, int l)                                                |
| boolean                | setBlockAndMetadataWithNotify       | (int i, int j, int k, int l, int i1)                                        |
| void                   | markBlockNeedsUpdate                | (int i, int j, int k)                                                       |
| void                   | notifyBlockChange                   | (int i, int j, int k, int l)                                                |
| void                   | markBlocksDirtyVertical             | (int i, int j, int k, int l)                                                |
| void                   | markBlockAsNeedsUpdate              | (int i, int j, int k)                                                       |
| void                   | markBlocksDirty                     | (int i, int j, int k, int l, int i1, int j1)                                |
| void                   | notifyBlocksOfNeighborChange        | (int i, int j, int k, int l)                                                |
| void                   | notifyBlockOfNeighborChange         | (int i, int j, int k, int l)                                                |
| boolean                | canBlockSeeTheSky                   | (int i, int j, int k)                                                       |
| int                    | getFullBlockLightValue              | (int i, int j, int k)                                                       |
| int                    | getBlockLightValue                  | (int i, int j, int k)                                                       |
| int                    | getBlockLightValue_do               | (int i, int j, int k, boolean flag)                                         |
| boolean                | canExistingBlockSeeTheSky           | (int i, int j, int k)                                                       |
| int                    | getHeightValue                      | (int i, int j)                                                              |
| void                   | neighborLightPropagationChanged     | (EnumSkyBlock enumskyblock, int i, int j, int k, int l)                     |
| int                    | getSavedLightValue                  | (EnumSkyBlock enumskyblock, int i, int j, int k)                            |
| void                   | setLightValue                       | (EnumSkyBlock enumskyblock, int i, int j, int k, int l)                     |
| float                  | getBrightness                       | (int i, int j, int k, int l)                                                |
| float                  | getLightBrightness                  | (int i, int j, int k)                                                       |
| boolean                | isDaytime                           | ()                                                                          |
| MovingObjectPosition   | rayTraceBlocks                      | (Vec3D vec3d, Vec3D vec3d1)                                                 |
| MovingObjectPosition   | rayTraceBlocks_do                   | (Vec3D vec3d, Vec3D vec3d1, boolean flag)                                   |
| MovingObjectPosition   | func_28105_a                        | (Vec3D vec3d, Vec3D vec3d1, boolean flag, boolean flag1)                    |
| void                   | playSoundAtEntity                   | (Entity entity, String s, float f, float f1)                                |
| void                   | playSoundEffect                     | (double d, double d1, double d2, String s, float f, float f1)               |
| void                   | playRecord                          | (String s, int i, int j, int k)                                             |
| void                   | spawnParticle                       | (String s, double d, double d1, double d2, double d3, double d4, double d5) |
| boolean                | addWeatherEffect                    | (Entity entity)                                                             |
| boolean                | entityJoinedWorld                   | (Entity entity)                                                             |
| void                   | obtainEntitySkin                    | (Entity entity)                                                             |
| void                   | releaseEntitySkin                   | (Entity entity)                                                             |
| void                   | setEntityDead                       | (Entity entity)                                                             |
| void                   | addWorldAccess                      | (IWorldAccess iworldaccess)                                                 |
| void                   | removeWorldAccess                   | (IWorldAccess iworldaccess)                                                 |
| List                   | getCollidingBoundingBoxes           | (Entity entity, AxisAlignedBB axisalignedbb)                                |
| int                    | calculateSkylightSubtracted         | (float f)                                                                   |
| Vec3D                  | func_4079_a                         | (Entity entity, float f)                                                    |
| float                  | getCelestialAngle                   | (float f)                                                                   |
| Vec3D                  | func_628_d                          | (float f)                                                                   |
| Vec3D                  | getFogColor                         | (float f)                                                                   |
| int                    | findTopSolidBlock                   | (int i, int j)                                                              |
| float                  | getStarBrightness                   | (float f)                                                                   |
| void                   | scheduleBlockUpdate                 | (int i, int j, int k, int l, int i1)                                        |
| void                   | updateEntities                      | ()                                                                          |
| void                   | func_31054_a                        | (Collection collection)                                                     |
| void                   | updateEntity                        | (Entity entity)                                                             |
| void                   | updateEntityWithOptionalForce       | (Entity entity, boolean flag)                                               |
| boolean                | checkIfAABBIsClear                  | (AxisAlignedBB axisalignedbb)                                               |
| boolean                | getIsAnyLiquid                      | (AxisAlignedBB axisalignedbb)                                               |
| boolean                | isBoundingBoxBurning                | (AxisAlignedBB axisalignedbb)                                               |
| boolean                | handleMaterialAcceleration          | (AxisAlignedBB axisalignedbb, Material material, Entity entity)            |
| boolean                | isMaterialInBB                      | (AxisAlignedBB axisalignedbb, Material material)                            |
| boolean                | isAABBInMaterial                    | (AxisAlignedBB axisalignedbb, Material material)                            |
| Explosion              | createExplosion                     | (Entity entity, double d, double d1, double d2, float f)                    |
| Explosion              | newExplosion                        | (Entity entity, double d, double d1, double d2, float f, boolean flag)      |
| float                  | func_675_a                          | (Vec3D vec3d, AxisAlignedBB axisalignedbb)                                  |
| void                   | onBlockHit                          | (EntityPlayer entityplayer, int i, int j, int k, int l)                     |
| Entity                 | func_4085_a                         | (Class class1)                                                              |
| TileEntity             | getBlockTileEntity                  | (int i, int j, int k)                                                       |
| void                   | setBlockTileEntity                  | (int i, int j, int k, TileEntity tileentity)                                |
| void                   | removeBlockTileEntity               | (int i, int j, int k)                                                       |
| boolean                | isBlockOpaqueCube                   | (int i, int j, int k)                                                       |
| boolean                | isBlockNormalCube                   | (int i, int j, int k)                                                       |
| void                   | saveWorldIndirectly                 | (IProgressUpdate iprogressupdate)                                           |



