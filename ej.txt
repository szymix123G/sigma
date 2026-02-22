-- Case Paradise AUTO QUEST + OPEN + BATTLE + SELL + ANTI-AFK
-- WERSJA BEZ SYSTEMU LICENCJI

local sg = Instance.new("ScreenGui")
sg.Parent = game.CoreGui
sg.Name = "CaseParadiseAuto"

local frame = Instance.new("Frame")
frame.Size = UDim2.new(0, 380, 0, 160)
frame.Position = UDim2.new(0.5, -190, 0.5, -80)
frame.BackgroundColor3 = Color3.fromRGB(30, 30, 35)
frame.Parent = sg

local title = Instance.new("TextLabel")
title.Size = UDim2.new(1, 0, 0.6, 0)
title.Text = "AUTO FARM URUCHOMIONY"
title.TextColor3 = Color3.new(1, 1, 1)
title.BackgroundTransparency = 1
title.Font = Enum.Font.GothamBold
title.TextSize = 26
title.Parent = frame

local info = Instance.new("TextLabel")
info.Size = UDim2.new(1, 0, 0.4, 0)
info.Position = UDim2.new(0, 0, 0.6, 0)
info.Text = "Ładowanie systemu..."
info.TextColor3 = Color3.new(0.7, 0.7, 0.7)
info.BackgroundTransparency = 1
info.Font = Enum.Font.Gotham
info.TextSize = 18
info.Parent = frame

task.wait(1)

warn("START AUTO FARM")

-- Główny skrypt
loadstring(game:HttpGet("https://pastebin.com/raw/3r1YUrmY"))()

-- Anti-AFK
spawn(function()
    while wait(55) do
        game:GetService("VirtualUser"):CaptureController()
        game:GetService("VirtualUser"):ClickButton2(Vector2.new())
    end
end)

-- Zamknij GUI po 3 sekundach
task.wait(3)
sg:Destroy()