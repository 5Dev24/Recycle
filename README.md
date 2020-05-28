**Recycle** allows players to recycle items into their resources.



## Permissions

* `recycle.use` -- Allows players to use `/recycle` chat command and `recycle` console command
* `recycle.admin` -- Allows players to forcefully destroy all recyclers currently created by **Recycle**

## Commands

* `/recycle` and `recycle` -- Opens a recycler
* `/purgerecyclers` -- Destroys all recyclers and drops their contents to a locked bag at the owner's position

## Configuration

```json
{
	"Settings": {
		"Cooldown (in minutes)": 5.0,
		"Maximum Radiation": 1.0,
		"Refund Ratio": 0.5,
		"NPCs Only": false,
		"Allowed In Safe Zones": true,
		"Instant Recycling": false,
		"NPC Ids": [],
		"Recyclable Types": [
			"Ammunition",
			"Attire",
			"Common",
			"Component",
			"Construction",
			"Items",
			"Medical",
			"Misc",
			"Tool",
			"Traps",
			"Weapon"
		],
		"Blacklisted Items": []
	},
	"VERSION": "3.0.0"
}
```

## For Developers

### Hooks

Invoked when checking if a recycler is safe to open.
```csharp
bool CanOpenRecycler(BasePlayer player)
```

### API Calls

Checks if an entity is a recycler managed by **Recycler**.
```csharp
public bool IsRecycleBox(BaseNetworkable entity)
```

Checks if a player can safely open a recycler.
```csharp
public bool CanPlayerOpenRecycler(BasePlayer player)
```

Checks if the player is current on cooldown from using the recycler.
```csharp
public bool IsOnCooldown(BasePlayer player)
```

Forcefully opens a recycler for the player

!! No checks are done, including calling the hook !!
```csharp
public void OpenRecycler(BasePlayer player)
```

## Credits

- **Calytic**, the original author of this plugin
