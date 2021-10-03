# Installation
- Ensure meta_libs v1.3+ is installed (https://github.com/meta-hub/meta_libs/releases).
- Extract the `fivem-drilling` folder into your `resources` directory.
- Add `start fivem-drilling` to your `server.cfg` file.
- Trigger the drilling event from your script, or test it with the example below.

# Example
```lua
RegisterCommand('sf_drilling', function(...)                               
    local drill_hash = GetHashKey("hei_prop_heist_drill")
    RequestModel(drill_hash)
    while not HasModelLoaded(drill_hash) do
        Wait(0)
    end
    drillEntity = CreateObject(drill_hash, GetEntityCoords(PlayerPedId()), true, false)
    SetEntityAsMissionEntity(drill, true, true)
    local boneIndex = GetPedBoneIndex(PlayerPedId(), 57005)
    AttachEntityToEntity(drillEntity, PlayerPedId(), boneIndex, 0.125, 0.0, -0.05, 100.0, 300.0, 135.0, true, true, false, true, 1, true)
    TriggerEvent("Drilling:Start",function(success)
        print(success)
        Wait(5000)
        ClearPedTasks(PlayerPedId())
        DeleteEntity(drillEntity)
    if (success) then
      print("Drilling complete.")
    else
      print("Drilling failed.")
    end
  end)
end)
```

# Preview Image
- Note: Image from GTAV.
![Image of Drilling](https://www.gadgetreview.com/wp-content/uploads/2016/07/the_fleeca_job_3.jpg)
