local function removeFOVScript()
    -- Procurar na pasta Players
    local players = game:GetService("Players")
    for _, player in pairs(players:GetChildren()) do
        local fovScript = player:FindFirstChild("FOV")
        if fovScript and fovScript:IsA("Script") then
            fovScript:Destroy()
        end
    end

    -- Procurar na pasta StarterPlayer
    local starterPlayer = game:GetService("StarterPlayer")
    local fovScript = starterPlayer:FindFirstChild("FOV")
    if fovScript and fovScript:IsA("Script") then
        fovScript:Destroy()
    end
end

-- Chama a função para remover o script
removeFOVScript()
