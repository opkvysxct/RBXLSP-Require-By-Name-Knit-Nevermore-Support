# FORK README:
okay so, the main change here is that it supports NevermoreEngine and Knit a little bit better, by better i mean that before it was pretty hard to usem them both, so now we do have two functions and not like before one
## Knit
```lua
local KnitRequire = Knit.GetService/Knit.GetController
local DataStore = KnitRequire("DataStore")
```
## NevermoreEngine
```lua
local NevermoreRequire = require(script.Parent.loader).load(script)
local Spring = NevermoreRequire("Spring")
```

# ORIGINAL README:
## Roblox LSP Require-by-Name
Adds context-aware require-by-name module linking to [Roblox LSP](https://github.com/NightrainsRbx/RobloxLsp).

![Code_mGZO39ONWF](https://user-images.githubusercontent.com/2924585/162556118-bebe2db1-95ec-4179-9967-d3fc8a96ecad.gif)

Last tested with Roblox LSP 1.5.11 on Windows 11

<br/>

### Installation:

1. Install [Roblox LSP Plugin Loader](https://github.com/Meta-Maxim/RobloxLsp-plugin-loader).

2. Save this repository root folder (**RobloxLsp-Require-by-Name**) into the `plugins` folder.

  *- or -*

1. Save this repository root folder and configure your editor's runtime plugin (`robloxLsp.runtime.plugin`) to `YOUR_PATH_HERE/RobloxLsp-Require-by-Name/plugin.lua`.

<br/>

### Operation:

*(Rojo project required)*

When a string argument is passed to any function named `require`, it will attempt to link the most context-relevant file.

Contexts: Client, Server, Shared

Context is detected by (highest priority first):
1. Script class (`Script` vs. `LocalScript`)
2. If script path contains:
   - `/client/`
   - `/shared/`
   - `/server/`
3. Ancestor service of script
