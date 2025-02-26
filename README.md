# Gui-hub
-- Settings
local farmArea = Vector3.new(0, 10, 0) -- Farm area
local farmRadius = 10 -- Farm radius
local farmInterval = 1 -- Interval between farms

-- Farm function
local function farmResources()
-- Find all resources within the farm area
local resources = game:GetService("Workspace"):FindPartsWithinRadius(farmArea, farmRadius)

```-- Collect resources
for _, resource in pairs(resources) do
    -- Check if the resource is collectable
    if resource:IsA("Part") and resource.Name == "Resource" then
        -- Collect resource
        local playerCharacter = game.Players.LocalPlayer.Character
        if playerCharacter then
            playerCharacter.HumanoidRootPart.CFrame = resource.CFrame
            wait(0.5)
            fireclickdetector(resource.ClickDetector)
        end
    end
end
```
end

-- Farm in loop
while true do
farmResources()
wait(farmInterval)
end
