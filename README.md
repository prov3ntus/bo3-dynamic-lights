# Dynamic/Swaying lights

By yours truly (prov3ntus)

## INSTRUCTIONS:

### Step 1 - Drag n' Drop

Drag & drop the folders into your BO3 Root.

### Step 2 - Prefabs & Targeting

In Radiant's prefab browser, search for "dynamic" and you’ll see `pv_dynamic_lights.map`.

Stamp the prefab, and make sure on ALL LIGHTS to get the `targetname` KVP and copy it to
the `targetName` KVP in the `SCRIPTING` section in entity info.
THIS IS REALLY IMPORTANT because the game looks at the KVP with the capital "N", not the
lower-case one.

You must also make sure that the `rope` ent (red box) is targeting the `info_null`
ent (green box), which is targeting the `script_model`. The `script_model` must be
targeting every light that you want to follow the `script_model` when it sways.

For the specific model I used, the bulb is a separate model, and so I had to use
Ctrl + L to link the lamp and bulb models, so they move together.

### Step 3 - KVPs

Make sure all models are `script_models`, and all lights have these KVPs set like so:

SCRIPTING
- `client_server`: `ServerSide`
- `scriptable`: `True` (checked)

... and of course the `targetName` below those two needs to be the same as the `target` KVP on the `script_model`.

For the main `script_model`, you ***MUST*** have a `script_noteworthy` key with the value of `dyn_light_model`.

You can use any models you like!

### Step 4

Open your `<MapName>.gsc` file, and add this line below `#using scripts\zm\zm_usermap;`

```cpp
#using scripts\_pv\pv_dynamic_lights;
```

AAAAND you're done!

## Notes

If it doesn't work, 3x check everything and read thru the instructions again.

If you ***still*** can't figure it out, then DM me on discord: @prov3ntus

Enjoy!
