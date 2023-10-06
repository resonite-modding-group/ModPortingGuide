# Porting Guide

Updating a mod from Neos to Resonite? Here are some notable changes to assist in that process.

[Mods](#mods)<br>
[Modloader](#modloader)<br>
[API](#api)<br>

# Mods

## Assembly References

| Neos                | Resonite         | Additional Notes        |
| ------------------- | ------------------------ | ----------------------------------------------|
| `BaseX`             | `Elements.Core`          |   |
| `CloudX.Shared`     | `SkyFrost.Base`          |   |
| `CodeX`             | `Elements.Assets`        |   |
| `CommandX`          | `FrooxEngine.Commands`   |   |
| `PostX`             | `FrooxEngine.Weaver`     |   |

## Assets

| Neos                | Resonite         | Additional Notes        |
| ------------------- | ------------------------ | ----------------------------------------------|
| `NeosAssets`        | `OfficialAssets`         |   |
| `neosdb:///`        | `resdb:///`              | The assets need to exist in Resonite already. |
| `neosrec:///`       | `resrec:///`             | The assets need to exist in Resonite already. |

## Classes and Types

| Neos                | Resonite         | Additional Notes        |
| ------------------- | ------------------------ | ----------------------------------------------|
| `color`             | `colorX`                 | Not everything will be `colorX`, they are two separate Types, however most usage will change to `colorX` |
| `CommonTool`        | `InteractionHandler`     |   |
| `ComponentAttacher` | `ComponentSelector`      |   |
| `FriendsDialog`     | `ContactsDialog`         | Friends are now referred to as Contacts more universally |
| `LogixBrowser`      | `ComponentSelector`      |   |
| `LogixBrowser`      | `ComponentSelector`      |   |
| `StatusManager`     | `EngineStatusSource`     | Also inherits `IUserStatusSource` |
| `Tooltips`          | `Tools`                  |   |

# Modloader

[NeosModLoader](https://github.com/neos-modding-group/NeosModLoader) change to [ResoniteModLoader](https://github.com/resonite-modding-group/ResoniteModLoader)

| Neos                | Resonite         | Additional Notes        |
| ------------------- | ------------------------ | ----------------------------------------------|
| `NeosMod`           | `ResoniteMod`            |   |
| `NeosModLoader`     | `ResoniteModLoader`      |   |

# API
