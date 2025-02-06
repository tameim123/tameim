local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local TextBox = Instance.new("TextBox")
local Button = Instance.new("TextButton")
local Players = game:GetService("Players")

-- إعداد الـ GUI
ScreenGui.Parent = game.CoreGui
Frame.Parent = ScreenGui
Frame.Size = UDim2.new(0, 200, 0, 150)
Frame.Position = UDim2.new(0.5, -100, 0.5, -75)
Frame.BackgroundColor3 = Color3.fromRGB(50, 50, 50)

TextBox.Parent = Frame
TextBox.Size = UDim2.new(1, -10, 0, 30)
TextBox.Position = UDim2.new(0, 5, 0, 10)
TextBox.PlaceholderText = "أدخل اسم اللاعب"
TextBox.Text = ""
TextBox.TextColor3 = Color3.fromRGB(255, 255, 255)
TextBox.BackgroundColor3 = Color3.fromRGB(30, 30, 30)

Button.Parent = Frame
Button.Size = UDim2.new(1, -10, 0, 40)
Button.Position = UDim2.new(0, 5, 0, 50)
Button.Text = "طرد اللاعب"
Button.TextColor3 = Color3.fromRGB(255, 255, 255)
Button.BackgroundColor3 = Color3.fromRGB(200, 0, 0)

-- وظيفة زر الطرد
Button.MouseButton1Click:Connect(function()
    local playerName = TextBox.Text
    for _, player in ipairs(Players:GetPlayers()) do
        if player.Name == playerName then
            player:Kick("تم طردك من السيرفر!")
            print(playerName .. " تم طرده من السيرفر!")
        end
    end
end)
