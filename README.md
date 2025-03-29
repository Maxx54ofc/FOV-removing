local function removeFOVScript()
    -- Procurar na pasta Players > [Player] > PlayerScripts
    local players = game:GetService("Players")
    for _, player in pairs(players:GetChildren()) do
        local playerScripts = player:FindFirstChild("PlayerScripts")
        if playerScripts then
            local fovScript = playerScripts:FindFirstChild("FOV")
            if fovScript and fovScript:IsA("Script") then
                fovScript:Destroy()
            end
        end
    end

    -- Procurar na pasta StarterPlayer > StarterPlayerScripts
    local starterPlayer = game:GetService("StarterPlayer")
    local starterPlayerScripts = starterPlayer:FindFirstChild("StarterPlayerScripts")
    if starterPlayerScripts then
        local fovScript = starterPlayerScripts:FindFirstChild("FOV")
        if fovScript and fovScript:IsA("Script") then
            fovScript:Destroy()
        end
    end
end

-- Chama a função para remover o script
removeFOVScript()
