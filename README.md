**Recycle** allows players to recycle items into their resources.



## Permissions

* `recycle.use` -- Allows players to use the recycler
* `recycle.admin` -- Allows players to destroy all recyclers or dropped bags currently created by **Recycle**
* `recycle.bypass` -- Allows players to bypass the cooldown of recycling

## Commands

* `/recycle` and `recycle` -- Opens a recycler, can be configured
* `/purgerecyclers` -- Destroys all recyclers and drops their contents to a locked bag at the owner's position
* `/purgebags` -- Destroys all bags created by **Recycle**

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
    "Send Recycled Items To Inventory": false,
    "Send Items To Inventory Before Bag": true,
    "Command To Open Recycler": "recycle",
    "NPC Ids": [],
    "Recyclable Types": [
      "Ammunition",
      "Attire",
      "Common",
      "Component",
      "Construction",
      "Electrical",
      "Fun",
      "Items",
      "Medical",
      "Misc",
      "Tool",
      "Traps",
      "Weapon"
    ],
    "Blacklisted Items": []
  },
  "VERSION": "3.0.4"
}
```

## For Developers

### Hooks

Invoked when checking if a recycler is safe to open.
```csharp
bool CanOpenRecycler(BasePlayer player)
```

### API Calls

Adds an NPC to the NPC list
```csharp
public void AddNPC(string npcID)
```

Removes an NPC from the NPC list
```csharp
public void RemoveNPC(string npcID)
```

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
