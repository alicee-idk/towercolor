local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

local Window = Rayfield:CreateWindow({
    Name = "Tower of Colors! 🌈",
    Icon = 0, -- Icon in Topbar. Can use Lucide Icons (string) or Roblox Image (number). 0 to use no icon (default).
    LoadingTitle = "Tower of Colors! 🌈",
    LoadingSubtitle = "https://discord.gg/5Y4pyevZZT",
    Theme = "Default", -- Check https://docs.sirius.menu/rayfield/configuration/themes
 
    DisableRayfieldPrompts = false,
    DisableBuildWarnings = false, -- Prevents Rayfield from warning when the script has a version mismatch with the interface
 
    ConfigurationSaving = {
       Enabled = true,
       FolderName = nil, -- Create a custom folder for your hub/game
       FileName = "Frusteddy hub"
    },
 
    Discord = {
       Enabled = true, -- Prompt the user to join your Discord server if their executor supports it
       Invite = "https://discord.gg/5Y4pyevZZT", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ ABCD would be ABCD
       RememberJoins = true -- Set this to false to make them join the discord every time they load it up
    },
 
    KeySystem = false, -- Set this to true to use our key system
    KeySettings = {
       Title = "Untitled",
       Subtitle = "Key System",
       Note = "No method of obtaining the key is provided", -- Use this to tell the user how to get a key
       FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
       SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
       GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
       Key = {"Hello"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
    }
})

local Tab = Window:CreateTab("Teleport", 4483362458) -- Title, Image

Rayfield:Notify({
    Title = "Script Executado!",
    Content = "Frusteddy Hub",
    Duration = 6.5,
    Image = 4483362458,
})

local Toggle = Tab:CreateToggle({
    Name = "Auto farm (You can't disable)",
    CurrentValue = false,
    Flag = "Toggle1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
    Callback = function(Value)
        -- Código para executar o teleporte em loop
        local player = game.Players.LocalPlayer -- Referência ao jogador local
        local character = player.Character or player.CharacterAdded:Wait() -- Garante o personagem carregado
        local rootPart = character:WaitForChild("HumanoidRootPart") -- Parte principal do personagem
        while Value do
            local newCFrame = CFrame.new(-3.49996948, 430.5, -68.5, 1, 0, 0, 0, 1, 0, 0, 0, 1)
            rootPart.CFrame = newCFrame
            wait(3)
        end
    end,
})

local Tab = Window:CreateTab("Discord", 4483362458)

local Button = Tab:CreateButton({
    Name = "https://discord.gg/5Y4pyevZZT (button don't work)",
    Callback = function()
    print("https://discord.gg/5Y4pyevZZT")
    end,
 })
