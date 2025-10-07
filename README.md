local Settings = {
    JoinTeam = "Pirates", -- "Pirates" ou "Marines"
    Translator = true, -- true/false
    ESPEnabled = false -- ESP começa desativado
}

-- Carregar o script principal
loadstring(game:HttpGet("https://raw.githubusercontent.com/ericwww44/Vulc-o-/refs/heads/main/README.lua"))()

-- Função para ativar/desativar ESP
local function toggleESP()
    Settings.ESPEnabled = not Settings.ESPEnabled
    if Settings.ESPEnabled then
        print("✅ ESP Ativado")
        -- Aqui você colocaria o código que ativa o ESP
        -- exemplo: chamar uma função ESP:Enable()
    else
        print("❌ ESP Desativado")
        -- Aqui você colocaria o código que desativa o ESP
        -- exemplo: ESP:Disable()
    end
end

-- Atalho de teclado (pressione "E" para ligar/desligar o ESP)
local UserInputService = game:GetService("UserInputService")
UserInputService.InputBegan:Connect(function(input, gp)
    if not gp and input.KeyCode == Enum.KeyCode.E then
        toggleESP()
    end
end)
