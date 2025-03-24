-- Ziverx v2.0 UI
local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local Title = Instance.new("TextLabel")
local ExecuteButton = Instance.new("TextButton")
local Notifier = Instance.new("TextLabel")
local ScriptBox = Instance.new("TextBox")

ScreenGui.Parent = game.CoreGui
Frame.Parent = ScreenGui
Frame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
Frame.Size = UDim2.new(0, 300, 0, 200)
Frame.Position = UDim2.new(0.5, -150, 0.5, -100)
Frame.Active = true
Frame.Draggable = true

Title.Parent = Frame
Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Title.Size = UDim2.new(1, 0, 0, 50)
Title.Text = "Ziverx v2.0"
Title.TextColor3 = Color3.fromRGB(255, 255, 255)
Title.TextScaled = true

ScriptBox.Parent = Frame
ScriptBox.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ScriptBox.Size = UDim2.new(1, 0, 0, 100)
ScriptBox.Position = UDim2.new(0, 0, 0, 50)
ScriptBox.PlaceholderText = "Enter your script here"

ExecuteButton.Parent = Frame
ExecuteButton.BackgroundColor3 = Color3.fromRGB(0, 170, 0)
ExecuteButton.Size = UDim2.new(1, 0, 0, 50)
ExecuteButton.Position = UDim2.new(0, 0, 0, 150)
ExecuteButton.Text = "Execute"

Notifier.Parent = Frame
Notifier.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Notifier.Size = UDim2.new(1, 0, 0, 50)
Notifier.Position = UDim2.new(0, 0, 0, 200)
Notifier.Text = ""
Notifier.TextColor3 = Color3.fromRGB(255, 0, 0)
Notifier.TextScaled = true

ExecuteButton.MouseButton1Click:Connect(function()
    local scriptToExecute = ScriptBox.Text
    loadstring(scriptToExecute)()
    Notifier.Text = "Script Executed!"
    wait(2)
    Notifier.Text = ""
end)
