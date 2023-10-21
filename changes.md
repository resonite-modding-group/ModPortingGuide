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
| `QuantiyX`          | `Elements.Quantity`      |   |

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
| `LogixBrowser`      | `ComponentSelector`      | `ComponentSelector` starting from a different root location for selecting nodes |
| `StatusManager`     | `EngineStatusSource`     | Also inherits `IUserStatusSource` |
| `Tooltips`          | `Tools`                  |   |

# Modloader

[NeosModLoader](https://github.com/neos-modding-group/NeosModLoader) change to [ResoniteModLoader](https://github.com/resonite-modding-group/ResoniteModLoader)

| Neos                | Resonite         | Additional Notes        |
| ------------------- | ------------------------ | ----------------------------------------------|
| `Engine.Initialize` | `Engine.InitializeAssemblies` | This is where compatibility hash is computed |
| `Engine.Shutdown`   | `Engine.RequestShutdown` |   |
| `NeosMod`           | `ResoniteMod`            |   |
| `NeosModBase`       | `ResoniteModBase`        |   |
| `NeosModLoader`     | `ResoniteModLoader`      |   |
| `SplashChanger`     |                          | Currently disabled, will need to be relooked at |
| `[module: Description("POSTX_PROCESSED")]`     | `[module: Description("FROOXENGINE_WEAVED")]` | Plugins now are `Weaved` when loaded, this is done in `FrooxEngine.Weaver` |

# API

| Neos                | Resonite         | Additional Notes        |
| ------------------- | ------------------------ | ----------------------------------------------|
| `/api/sessions ` | `/sessions` | Active session listing |
| `/api/users/ ` | `/users/` | Base user path, follow with a `U-ID` or a username followed by `?byUsername=true`|
| `api.neos.com` | `api.resonite.com` | Base API url |
| `assets.neos.com` | `assets.resonite.com` | Assets |
