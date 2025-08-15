-- Interface de WalkSpeed - Uso em jogo próprio

-- Criar ScreenGui
local gui = Instance.new("ScreenGui")
gui.Parent = game.CoreGui

-- Criar Frame
local frame = Instance.new("Frame")
frame.Size = UDim2.new(0, 200, 0, 120)
frame.Position = UDim2.new(0.5, -100, 0.5, -60)
frame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
frame.Parent = gui

-- Criar Título
local title = Instance.new("TextLabel")
title.Size = UDim2.new(1, 0, 0, 30)
title.BackgroundTransparency = 1
title.Text = "WalkSpeed"
title.TextColor3 = Color3.fromRGB(255, 255, 255)
title.Parent = frame

-- Criar Caixa de Texto
local box = Instance.new("TextBox")
box.Size = UDim2.new(1, -20, 0, 30)
box.Position = UDim2.new(0, 10, 0, 40)
box.PlaceholderText = "Velocidade"
box.Text = ""
box.TextColor3 = Color3.fromRGB(0, 0, 0)
box.BackgroundColor3 = Color3.fromRGB(200, 200, 200)
box.Parent = frame

-- Criar Botão
local button = Instance.new("TextButton")
button.Size = UDim2.new(1, -20, 0, 30)
button.Position = UDim2.new(0, 10, 0, 80)
button.Text = "Aplicar"
button.BackgroundColor3 = Color3.fromRGB(0, 170, 255)
button.TextColor3 = Color3.fromRGB(255, 255, 255)
button.Parent = frame

-- Função para mudar velocidade
button.MouseButton1Click:Connect(function()
    local speed = tonumber(box.Text)
    if speed and game.Players.LocalPlayer.Character then
        game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = speed
    end
end)
