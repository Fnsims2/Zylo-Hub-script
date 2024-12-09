local WindUI = loadstring(game:HttpGet("https://tree-hub.vercel.app/api/UI/WindUI"))()

local Window = WindUI:CreateWindow({
    Title = "Zylo Hub", -- UI Title
    Author = "By Devs", -- Author & Creator
    Folder = "Zylo Hub", -- Folder name for saving data (And key)
    Size = UDim2.fromOffset(560, 820), -- UI Size 
    Transparent = true,-- UI Transparency
    Theme = "Dark", -- UI Theme
    SideBarWidth = 200, -- UI Sidebar Width (number)
    HasOutline = false, -- Adds Oultines to the window
})

local MainTab = Window:Tab({
    Title = "Universal",
    Icon = "ball",
})

Window:SelectTab(1)

local Divider = Window:Divider()

MainTab:Section({ 
    Title = "Walk and jump changer",
    TextXAlignment = "Left"
})

local Slider = MainTab:Slider({
    Title = "Walkspeed changer",
    Desc = "Changes speed up to 500",
    Step = 1,
    Value = {
        Min = 5,
        Max = 500,
        Default = 16,
    },
    Callback = function(value)
        game.Workspace[game.Players.LocalPlayer.Name].Humanoid.WalkSpeed = value
    end
})

local Slider = MainTab:Slider({
    Title = "JumpPower Changer",
    Desc = "Changes JumpPower up to 500",
    Step = 1,
    Value = {
        Min = 20,
        Max = 500,
        Default = 50,
    },
    Callback = function(value)
        game.Workspace[game.Players.LocalPlayer.Name].Humanoid.JumpPower = value
    end
})

MainTab:Section({ 
    Title = "Universal Scripts",
    TextXAlignment = "Right"
})

local Button = MainTab:Button({
    Title = "Inf Yield",
    Desc = "Opens Inf Yield",
    Callback = function()
        loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))()
        Dialog:Open()
    end,
})

local MainTab = Window:Tab({
    Title = "Fisch",
    Icon = "fish",
})

local Divider = Window:Divider()

local WindowTab = Window:Tab({
    Title = "Window and File Configuration",
    Icon = "settings",
})

WindowTab:Section({ Title = "Keybinds" })

local KeybindClicked = false
local Keybind = WindowTab:Keybind({
    Title = "Keybind Toggle UI",
    Desc = "Keybind Toggle UI Desc",
    Value = "LeftShift",
    CanChange = true,
    Callback = function(k)
        if not KeybindClicked then
            Window:Close()
        else
            Window:Open()
        end
        KeybindClicked = not KeybindClicked
    end
})
