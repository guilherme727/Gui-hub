# Gui-hub

-- Importe a Kaitun API
local Kaitun = loadstring(game:HttpGet("(link unavailable)"))()

-- Crie a GUI
local gui = Kaitun.CreateLib("Blox Fruits Hub", "Ocean")

-- Seção de farm
local farmSection = gui:CreateSection("Farm")

-- Botão para farmar frutas
farmSection:CreateToggle("Farmar Frutas", function(state)
    if state then
        -- Código para farmar frutas
    else
        -- Código para parar farm
    end
end)

-- Seção de recursos
local resourceSection = gui:CreateSection("Recursos")

-- Botão para coletar recursos
resourceSection:CreateToggle("Coletar Recursos", function(state)
    if state then
        -- Código para coletar recursos
    else
        -- Código para parar coleta
    end
end)

-- Seção de configurações
local configSection = gui:CreateSection("Configurações")

-- Seleção de fruit para farmar
configSection:CreateDropdown("Fruit para farmar", {"NomeDoFruit1", "NomeDoFruit2"}, function(selected)
    -- Código para atualizar fruit
end)
