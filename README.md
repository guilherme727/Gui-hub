# Gui-hub

```
-- Configurações
local autoFarm = true -- Ativa/Desativa o farm automático
local farmInterval = 5 -- Intervalo entre farms (em segundos)

-- Função de farm
local function farmResources()
    -- Encontre todos os recursos na área
    local resources = game:GetService("Workspace"):FindPartsWithinRadius(Vector3.new(0, 0, 0), 10)
    
    -- Coletar recursos
    for _, resource in pairs(resources) do
        -- Verifique se o recurso é coletável
        if resource:IsA("Part") and resource.Name == "Resource" then
            -- Coletar recurso
            local playerCharacter = game.Players.LocalPlayer.Character
            if playerCharacter then
                playerCharacter.HumanoidRootPart.CFrame = resource.CFrame
                wait(0.5)
                fireclickdetector(resource.ClickDetector)
            end
        end
    end
end

-- Farm em loop
while autoFarm do
    farmResources()
    wait(farmInterval)
end
```
