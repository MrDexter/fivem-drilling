# Installation
- Ensure meta_libs v1.3+ is installed (https://github.com/meta-hub/meta_libs/releases).
- Extract the `fivem-drilling` folder into your `resources` directory.
- Add `start fivem-drilling` to your `server.cfg` file.
- Trigger the drilling event from your script, or test it with the example below.
- Changed coords on line 78 to drilling location. Config setup soon

# Example
```lua
RegisterCommand('sf_drilling', function(...)                               
    TriggerEvent("Drilling:Start", function(success)
        if success then
            -- Success code
        else
            -- Failed code
        end
    end)
end)
```

# Preview Image
- Note: Image from GTAV.
![Image of Drilling](https://i.gyazo.com/8dc821883ef86c69c9edd483b8281210.jpg)
