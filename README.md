# Sola-Gui-hub


repeat wait() until game:IsLoaded()

local Players = game:GetService("Players")
local TweenService = game:GetService("TweenService")
local UserInputService = game:GetService("UserInputService")


local function createNotification(title, content, duration, color, parent)
    duration = duration or 5
    color = color or Color3.fromRGB(255, 188, 254)
    
    local Notification = Instance.new("Frame")
    Notification.Name = "Notification"
    Notification.AnchorPoint = Vector2.new(1, 1)
    Notification.BackgroundTransparency = 0.06
    Notification.AutomaticSize = Enum.AutomaticSize.XY
    Notification.BackgroundColor3 = Color3.fromRGB(16, 16, 16)
    Notification.BorderSizePixel = 0
    Notification.Position = UDim2.new(1, -25, 1, -25)
    Notification.Size = UDim2.fromOffset(232, 59)
    Notification.Parent = parent
    
    local NotifStroke = Instance.new("UIStroke")
    NotifStroke.Name = "_CHILD"
    NotifStroke.Color = Color3.fromRGB(158, 114, 158)
    NotifStroke.Transparency = 0.9
    NotifStroke.Parent = Notification
    
    local NotifAcrylic1 = Instance.new("ImageLabel")
    NotifAcrylic1.Name = "acrylicthing"
    NotifAcrylic1.Image = "rbxassetid://9968344105"
    NotifAcrylic1.ImageTransparency = 0.98
    NotifAcrylic1.ScaleType = Enum.ScaleType.Tile
    NotifAcrylic1.TileSize = UDim2.fromOffset(128, 128)
    NotifAcrylic1.BackgroundTransparency = 1
    NotifAcrylic1.Size = UDim2.fromScale(1, 1)
    
    local NotifAcrylicCorner1 = Instance.new("UICorner")
    NotifAcrylicCorner1.CornerRadius = UDim.new(0, 12)
    NotifAcrylicCorner1.Parent = NotifAcrylic1
    
    NotifAcrylic1.Parent = Notification
    
    local NotifAcrylic2 = Instance.new("ImageLabel")
    NotifAcrylic2.Name = "acrylicthing"
    NotifAcrylic2.Image = "rbxassetid://9968344227"
    NotifAcrylic2.ImageTransparency = 0.9
    NotifAcrylic2.ScaleType = Enum.ScaleType.Tile
    NotifAcrylic2.TileSize = UDim2.fromOffset(128, 128)
    NotifAcrylic2.BackgroundTransparency = 1
    NotifAcrylic2.Size = UDim2.fromScale(1, 1)
    
    local NotifAcrylicCorner2 = Instance.new("UICorner")
    NotifAcrylicCorner2.CornerRadius = UDim.new(0, 12)
    NotifAcrylicCorner2.Parent = NotifAcrylic2
    
    NotifAcrylic2.Parent = Notification
    
    local TextHolder = Instance.new("Frame")
    TextHolder.Name = "TextHolder"
    TextHolder.AutomaticSize = Enum.AutomaticSize.XY
    TextHolder.BackgroundTransparency = 1
    TextHolder.Position = UDim2.new(0, 7, 0.12, 0)
    TextHolder.Size = UDim2.fromOffset(20, 12)
    
    local TextLayout = Instance.new("UIListLayout")
    TextLayout.Padding = UDim.new(0, -4)
    TextLayout.SortOrder = Enum.SortOrder.LayoutOrder
    TextLayout.Parent = TextHolder
    
    local TitleText = Instance.new("TextLabel")
    TitleText.FontFace = Font.new("rbxassetid://12187365364", Enum.FontWeight.SemiBold)
    TitleText.Text = title
    TitleText.TextColor3 = Color3.fromRGB(199, 199, 203)
    TitleText.TextSize = 14
    TitleText.TextXAlignment = Enum.TextXAlignment.Left
    TitleText.AutomaticSize = Enum.AutomaticSize.X
    TitleText.BackgroundTransparency = 1
    TitleText.Position = UDim2.fromOffset(10, 8)
    TitleText.Size = UDim2.fromOffset(212, 20)
    TitleText.Parent = TextHolder
    
    local ContentText = Instance.new("TextLabel")
    ContentText.Name = "TextLabel"
    ContentText.FontFace = Font.new("rbxassetid://12187365364", Enum.FontWeight.SemiBold, Enum.FontStyle.Normal)
    ContentText.Text = content
    ContentText.TextColor3 = Color3.fromRGB(127, 127, 130)
    ContentText.TextSize = 12
    ContentText.TextXAlignment = Enum.TextXAlignment.Left
    ContentText.AutomaticSize = Enum.AutomaticSize.X
    ContentText.BackgroundTransparency = 1
    ContentText.Position = UDim2.fromOffset(10, 8)
    ContentText.Size = UDim2.fromOffset(212, 20)
    ContentText.Parent = TextHolder
    
    local TextPadding = Instance.new("UIPadding")
    TextPadding.PaddingBottom = UDim.new(0, 25)
    TextPadding.Parent = TextHolder
    
    TextHolder.Parent = Notification
    
    local ProgressBar = Instance.new("Frame")
    ProgressBar.BackgroundColor3 = Color3.fromRGB(44, 38, 44)
    ProgressBar.BorderSizePixel = 0
    ProgressBar.Position = UDim2.fromScale(0.0282, 0.8)
    ProgressBar.Size = UDim2.new(1, -20, 0, 7)
    
    local ProgressLayout = Instance.new("UIListLayout")
    ProgressLayout.Name = "UIListLayout"
    ProgressLayout.Wraps = true
    ProgressLayout.FillDirection = Enum.FillDirection.Horizontal
    ProgressLayout.SortOrder = Enum.SortOrder.LayoutOrder
    ProgressLayout.VerticalAlignment = Enum.VerticalAlignment.Bottom
    ProgressLayout.Parent = ProgressBar
    
    local ProgressFill = Instance.new("Frame")
    ProgressFill.BackgroundColor3 = color
    ProgressFill.BorderSizePixel = 0
    ProgressFill.Size = UDim2.fromScale(1, 1)
    
    local ProgressFillCorner = Instance.new("UICorner")
    ProgressFillCorner.Parent = ProgressFill
    
    local ProgressGradient = Instance.new("UIGradient")
    ProgressGradient.Color = ColorSequence.new{
        ColorSequenceKeypoint.new(0, Color3.fromRGB(255, 255, 255)),
        ColorSequenceKeypoint.new(0.752, Color3.fromRGB(147, 147, 147)),
        ColorSequenceKeypoint.new(1, Color3.fromRGB(127, 127, 127))
    }
    ProgressGradient.Parent = ProgressFill
    
    ProgressFill.Parent = ProgressBar
    
    local ProgressBarCorner = Instance.new("UICorner")
    ProgressBarCorner.Parent = ProgressBar
    
    ProgressBar.Parent = Notification
    
    local NotifCorner = Instance.new("UICorner")
    NotifCorner.CornerRadius = UDim.new(0, 4)
    NotifCorner.Parent = Notification
    
    local NotifPadding = Instance.new("UIPadding")
    NotifPadding.PaddingBottom = UDim.new(0, 12)
    NotifPadding.Parent = Notification
    
    local DismissButton = Instance.new("TextButton")
    DismissButton.Name = "DismissButton"
    DismissButton.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
    DismissButton.BackgroundTransparency = 1
    DismissButton.Size = UDim2.fromScale(1, 1)
    DismissButton.Text = ""
    DismissButton.Parent = Notification
    
    TweenService:Create(ProgressFill, TweenInfo.new(duration, Enum.EasingStyle.Linear), {Size = UDim2.new(0, 0, 1, 0)}):Play()
    
    task.delay(duration, function()
        TweenService:Create(Notification, TweenInfo.new(0.5), {Position = UDim2.new(1, 25, 1, -25)}):Play()
        task.wait(0.5)
        Notification:Destroy()
    end)
    
    DismissButton.MouseButton1Click:Connect(function()
        TweenService:Create(Notification, TweenInfo.new(0.5), {Position = UDim2.new(1, 25, 1, -25)}):Play()
        task.wait(0.5)
        Notification:Destroy()
    end)
    
    DismissButton.MouseEnter:Connect(function()
        TweenService:Create(DismissButton, TweenInfo.new(0.1), {BackgroundTransparency = 0.65}):Play()
    end)
    
    DismissButton.MouseLeave:Connect(function()
        TweenService:Create(DismissButton, TweenInfo.new(0.1), {BackgroundTransparency = 1}):Play()
    end)
    
    return Notification
end


local function getScriptLoaderUrl()
    local creatorId = game.CreatorId
    
    local scriptMap = {
        [4372130] = "https://api.luarmor.net/files/v3/loaders/e2718ddebf562c5c4080dfce26b09398.lua", -- Blox Fruits
        [11867394] = "https://api.luarmor.net/files/v3/loaders/98f5c64a0a9ecca29517078597bbcbdb.lua", -- Dead Rails
        [4294803] = "https://api.luarmor.net/files/v3/loaders/9b64d07193c7c2aef970d57aeb286e70.lua", -- Demonfall
        [1226491] = "https://api.luarmor.net/files/v3/loaders/fefdf5088c44beb34ef52ed6b520507c.lua", -- Shindo Life
        [2613928] = "https://api.luarmor.net/files/v3/loaders/0e0166cb8f3c5c189c6a1f2532db2125.lua", -- Counterblox
        [3229308] = "https://api.luarmor.net/files/v3/loaders/4b2841eb3e1345dd1aa50da164ca2bbe.lua", -- Grand Piece Online
        [7381705] = "https://api.luarmor.net/files/v3/loaders/8bbc8a7c4e023bc0c80799fec3233162.lua", -- Fisch
        [15557357] = "https://api.luarmor.net/files/v3/loaders/4fe2dfc202115670b1813277df916ab2.lua", -- JJI
        [1848960] = "https://api.luarmor.net/files/v3/loaders/9c916252a9f79bbf5a108f97c531e807.lua", -- MM2
        [3959677] = "https://api.luarmor.net/files/v3/loaders/e95ef6f27596e636a7d706375c040de4.lua", -- PS99
        [3461453] = "https://api.luarmor.net/files/v3/loaders/3bb7969a9ecb9e317b0a24681327c2e2.lua", -- Rivals
        [17219742] = "https://api.luarmor.net/files/v3/loaders/25116432b45b1a5ea7811c264a731941.lua", -- ANime Vanugard
        [3059674] = "https://api.luarmor.net/files/v3/loaders/21ad7f491e4658e9dc9529a60c887c6e.lua", -- Jailbreak
        [34644452] = "https://api.luarmor.net/files/v3/loaders/0c8fdf9bb25a6a7071731b72a90e3c69.lua", -- Arise Crossover
        [3333298] = "https://api.luarmor.net/files/v3/loaders/e1d276b47f79a40a336a530f3bd6268c.lua", -- Bobule gum
        [35789249] = "https://api.luarmor.net/files/v3/loaders/e4ea33e9eaf0ae943d59ea98f2444ebe.lua", -- Grow a garden
        [34160477] = "https://api.luarmor.net/files/v3/loaders/22843f88cd6ebbd164621b3c115446c8.lua", -- Ghoul RE
    }
    
    return scriptMap[creatorId]
end

local function isGameSupported()
    return getScriptLoaderUrl() ~= nil
end

local function initLuarmorAPI()
    local success, result = pcall(function()
        return loadstring(game:HttpGet("https://sdkapi-public.luarmor.net/library.lua"))()
    end)
    
    if not success then
        return nil
    end
    
    local scriptUrl = getScriptLoaderUrl()
    if not scriptUrl then
        return nil
    end
    
    local scriptId = scriptUrl:match("loaders/([^.]+)%.lua")
    if not scriptId then
        return nil
    end
    
    result.script_id = scriptId
    
    return result
end


local function executeScript(key)
    local scriptUrl = getScriptLoaderUrl()
    
    if not scriptUrl then
        return false, "Game not supported"
    end
    

    getgenv().script_key = key
    
    local success, result = pcall(function()
        return loadstring(game:HttpGet(scriptUrl))()
    end)
    
    if not success then
        return false, "Failed to execute script: " .. tostring(result)
    end
    
    return true
end


local function validateKey(key)
    if not key or key == "" then
        return false, "KEY_NOT_FOUND"
    end
    
    if not isGameSupported() then
        return false, "GAME_NOT_SUPPORTED"
    end
    
    local api = initLuarmorAPI()
    if not api then
        return false, "API_INIT_FAILED"
    end
    
    local success, status = pcall(function()
        return api.check_key(key)
    end)
    
    if not success then
        return false, "API_CALL_FAILED"
    end
    
    if status.code == "KEY_VALID" then
        return true, status
    else
        return false, status.code
    end
end

local function main()

    local notifGui = Instance.new("ScreenGui")
    notifGui.Name = "NotificationGui"
    notifGui.ResetOnSpawn = false
    notifGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
    notifGui.Parent = game:GetService("Players").LocalPlayer:WaitForChild("PlayerGui")
    

    local keySuccess, keyContent = pcall(function()
        return readfile("Key.txt")
    end)
    

    if not keySuccess or not keyContent or keyContent == "" then
     
        if keySuccess then
            pcall(function() delfile("Key.txt") end)
        end
        
        createNotification("Key System", "No valid key found. Please enter your key.", 5, Color3.fromRGB(255, 85, 85), notifGui)
        return false
    end
    
 
    local api = initLuarmorAPI()
    if not api then
        createNotification("API Error", "Failed to initialize Luarmor API", 5, Color3.fromRGB(255, 85, 85), notifGui)
        return false
    end
    

    local success, status = pcall(function()
        return api.check_key(keyContent)
    end)
    

    if not success then
        createNotification("API Error", "Failed to check key with Luarmor", 5, Color3.fromRGB(255, 85, 85), notifGui)
        pcall(function() delfile("Key.txt") end)
        return false
    end
    

    if status.code ~= "KEY_VALID" then
        pcall(function() delfile("Key.txt") end)
        
        local statusMessage = "Invalid key"
        if status.code == "KEY_EXPIRED" then
            statusMessage = "Key expired"
        elseif status.code == "KEY_HWID_LOCKED" then
            statusMessage = "Key HWID locked"
        elseif status.code == "KEY_BANNED" then
            statusMessage = "Key banned"
        elseif status.code == "KEY_INCORRECT" or status.code == "KEY_INVALID" then
            statusMessage = "Invalid key - key does not exist"
        end
        
        createNotification("Key Error", statusMessage, 5, Color3.fromRGB(255, 85, 85), notifGui)
        return false
    end
    

    local saveSuccess, saveError = pcall(function()
        writefile("Key.txt", keyContent)
    end)
    
    if not saveSuccess then
        createNotification("Warning", "Failed to save key: " .. tostring(saveError), 5, Color3.fromRGB(255, 170, 0), notifGui)
    else

        local readSuccess, savedKey = pcall(function()
            return readfile("Key.txt")
        end)
        
        if not readSuccess or savedKey ~= keyContent then
            createNotification("Warning", "Key verification failed. Teleport may not  correctly.", 5, Color3.fromRGB(255, 170, 0), notifGui)
        else
         
            queue_on_teleport([[
                loadstring(game:HttpGet("https://raw.githubusercontent.com/debunked69/Solixreworkkeysystem/refs/heads/main/solix%20new%20keyui.lua"))()
            ]])
            
            createNotification("Info", "Key saved successfully. Ready for teleport.", 3, Color3.fromRGB(85, 255, 127), notifGui)
        end
    end
    
 
    local execSuccess, execError = executeScript(keyContent)
    
  
    if not execSuccess then
        createNotification("Script Error", execError, 5, Color3.fromRGB(255, 85, 85), notifGui)
        return false
    end
    
 
    task.delay(1, function()
        notifGui:Destroy()
    end)
    
    return true
end


if main() then
    return
end


local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Name = "SolixHubLogin"
ScreenGui.ResetOnSpawn = false
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
ScreenGui.Parent = Players.LocalPlayer:WaitForChild("PlayerGui")

local MainFrame = Instance.new("Frame")
MainFrame.Name = "MainFrame"
MainFrame.AnchorPoint = Vector2.new(0.5, 0.5)
MainFrame.BackgroundColor3 = Color3.fromRGB(16, 16, 16)
MainFrame.BackgroundTransparency = 0.06
MainFrame.BorderSizePixel = 0
MainFrame.Position = UDim2.fromScale(0.5, 0.5)
MainFrame.Size = UDim2.fromOffset(400, 370)
MainFrame.Parent = ScreenGui

local UICorner = Instance.new("UICorner")
UICorner.CornerRadius = UDim.new(0, 12)
UICorner.Parent = MainFrame

local AcrylicEffect1 = Instance.new("ImageLabel")
AcrylicEffect1.Name = "acrylicthing"
AcrylicEffect1.Image = "rbxassetid://9968344105"
AcrylicEffect1.ImageTransparency = 0.98
AcrylicEffect1.ScaleType = Enum.ScaleType.Tile
AcrylicEffect1.TileSize = UDim2.fromOffset(128, 128)
AcrylicEffect1.BackgroundTransparency = 1
AcrylicEffect1.Size = UDim2.fromScale(1, 1)
AcrylicEffect1.ZIndex = 0
AcrylicEffect1.Parent = MainFrame

local AcrylicCorner1 = Instance.new("UICorner")
AcrylicCorner1.CornerRadius = UDim.new(0, 12)
AcrylicCorner1.Parent = AcrylicEffect1

local AcrylicEffect2 = Instance.new("ImageLabel")
AcrylicEffect2.Name = "acrylicthing"
AcrylicEffect2.Image = "rbxassetid://9968344227"
AcrylicEffect2.ImageTransparency = 0.9
AcrylicEffect2.ScaleType = Enum.ScaleType.Tile
AcrylicEffect2.TileSize = UDim2.fromOffset(128, 128)
AcrylicEffect2.BackgroundTransparency = 1
AcrylicEffect2.Size = UDim2.fromScale(1, 1)
AcrylicEffect2.ZIndex = 0
AcrylicEffect2.Parent = MainFrame

local AcrylicCorner2 = Instance.new("UICorner")
AcrylicCorner2.CornerRadius = UDim.new(0, 12)
AcrylicCorner2.Parent = AcrylicEffect2

local UIStroke = Instance.new("UIStroke")
UIStroke.Name = "_CHILD"
UIStroke.Color = Color3.fromRGB(158, 114, 158)
UIStroke.Transparency = 0.9
UIStroke.Parent = MainFrame

local SideIndicator = Instance.new("Frame")
SideIndicator.Name = "sideindicator"
SideIndicator.AnchorPoint = Vector2.new(0.5, 0)
SideIndicator.BackgroundColor3 = Color3.fromRGB(255, 188, 254)
SideIndicator.BorderSizePixel = 0
SideIndicator.Position = UDim2.fromScale(0.5, 0)
SideIndicator.Size = UDim2.new(1, -50, 0, 2)
SideIndicator.Parent = MainFrame

local SideIndicatorCorner = Instance.new("UICorner")
SideIndicatorCorner.CornerRadius = UDim.new(0, 634)
SideIndicatorCorner.Parent = SideIndicator

local TitleLabel = Instance.new("TextLabel")
TitleLabel.Name = "title"
TitleLabel.FontFace = Font.new("rbxassetid://12187361378", Enum.FontWeight.Medium, Enum.FontStyle.Normal)
TitleLabel.Text = "SolixHub"
TitleLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
TitleLabel.TextSize = 19
TitleLabel.BackgroundTransparency = 1
TitleLabel.Position = UDim2.fromOffset(37, 15)
TitleLabel.Size = UDim2.new(0, 88, 0, 30)
TitleLabel.TextXAlignment = Enum.TextXAlignment.Left
TitleLabel.Parent = MainFrame

local ControlsFrame = Instance.new("Frame")
ControlsFrame.Name = "Frame"
ControlsFrame.BackgroundTransparency = 1
ControlsFrame.Position = UDim2.new(1, -75, 0, 15)
ControlsFrame.Size = UDim2.new(0, 60, 0, 30)
ControlsFrame.Parent = MainFrame

local ControlsLayout = Instance.new("UIListLayout")
ControlsLayout.FillDirection = Enum.FillDirection.Horizontal
ControlsLayout.HorizontalAlignment = Enum.HorizontalAlignment.Center
ControlsLayout.Padding = UDim.new(0, 6)
ControlsLayout.SortOrder = Enum.SortOrder.LayoutOrder
ControlsLayout.VerticalAlignment = Enum.VerticalAlignment.Center
ControlsLayout.Parent = ControlsFrame

local CloseButton = Instance.new("TextButton")
CloseButton.Name = "Close"
CloseButton.Text = ""
CloseButton.BackgroundColor3 = Color3.fromRGB(252, 95, 83)
CloseButton.Size = UDim2.fromOffset(7, 7)
CloseButton.AutoButtonColor = false
CloseButton.Parent = ControlsFrame

local CloseButtonCorner = Instance.new("UICorner")
CloseButtonCorner.CornerRadius = UDim.new(0, 50)
CloseButtonCorner.Parent = CloseButton

local MinimizeButton = Instance.new("TextButton")
MinimizeButton.Name = "Minimize"
MinimizeButton.Text = ""
MinimizeButton.BackgroundColor3 = Color3.fromRGB(242, 191, 60)
MinimizeButton.Size = UDim2.fromOffset(7, 7)
MinimizeButton.AutoButtonColor = false
MinimizeButton.Parent = ControlsFrame

local MinimizeButtonCorner = Instance.new("UICorner")
MinimizeButtonCorner.CornerRadius = UDim.new(0, 50)
MinimizeButtonCorner.Parent = MinimizeButton

local OpenButton = Instance.new("TextButton")
OpenButton.Name = "Open"
OpenButton.Text = ""
OpenButton.BackgroundColor3 = Color3.fromRGB(117, 166, 87)
OpenButton.Size = UDim2.fromOffset(7, 7)
OpenButton.AutoButtonColor = false
OpenButton.Parent = ControlsFrame

local OpenButtonCorner = Instance.new("UICorner")
OpenButtonCorner.CornerRadius = UDim.new(0, 50)
OpenButtonCorner.Parent = OpenButton

local ContentFrame = Instance.new("Frame")
ContentFrame.Name = "ContentFrame"
ContentFrame.BackgroundTransparency = 1
ContentFrame.Position = UDim2.fromOffset(0, 60)
ContentFrame.Size = UDim2.new(1, 0, 1, -60)
ContentFrame.Parent = MainFrame

local GameLabel = Instance.new("TextLabel")
GameLabel.Name = "GameLabel"
GameLabel.FontFace = Font.new("rbxassetid://12187365364")
GameLabel.Text = "Game: " .. game:GetService("MarketplaceService"):GetProductInfo(game.PlaceId).Name
GameLabel.TextColor3 = Color3.fromRGB(200, 200, 200)
GameLabel.TextSize = 12
GameLabel.BackgroundTransparency = 1
GameLabel.Position = UDim2.fromOffset(20, 0)
GameLabel.Size = UDim2.new(1, -40, 0, 20)
GameLabel.Parent = ContentFrame

local KeySection = Instance.new("Frame")
KeySection.Name = "KeySection"
KeySection.BackgroundTransparency = 1
KeySection.Position = UDim2.fromOffset(20, 25) 
KeySection.Size = UDim2.new(1, -40, 0, 70)
KeySection.Parent = ContentFrame

local KeyLabel = Instance.new("TextLabel")
KeyLabel.Name = "KeyLabel"
KeyLabel.FontFace = Font.new("rbxasse
