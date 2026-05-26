-- LocalScript dentro de StarterGui

local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")

local MainFrame = Instance.new("Frame")
MainFrame.Parent = ScreenGui
MainFrame.Size = UDim2.new(0, 450, 0, 300)
MainFrame.Position = UDim2.new(0.3, 0, 0.2, 0)
MainFrame.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
MainFrame.BorderSizePixel = 0

local SideMenu = Instance.new("Frame")
SideMenu.Parent = MainFrame
SideMenu.Size = UDim2.new(0, 120, 1, 0)
SideMenu.BackgroundColor3 = Color3.fromRGB(35, 35, 35)

local Title = Instance.new("TextLabel")
Title.Parent = SideMenu
Title.Size = UDim2.new(1, 0, 0, 50)
Title.Text = "MENU"
Title.TextColor3 = Color3.new(1,1,1)
Title.BackgroundTransparency = 1
Title.TextScaled = true

local MainButton = Instance.new("TextButton")
MainButton.Parent = SideMenu
MainButton.Size = UDim2.new(1, -10, 0, 40)
MainButton.Position = UDim2.new(0, 5, 0, 60)
MainButton.Text = "Principal"
MainButton.BackgroundColor3 = Color3.fromRGB(60,60,60)
MainButton.TextColor3 = Color3.new(1,1,1)

local ContentFrame = Instance.new("Frame")
ContentFrame.Parent = MainFrame
ContentFrame.Position = UDim2.new(0, 130, 0, 10)
ContentFrame.Size = UDim2.new(1, -140, 1, -20)
ContentFrame.BackgroundTransparency = 1

local AutoMoney = false
local Auto2X = false

local AutoMoneyButton = Instance.new("TextButton")
AutoMoneyButton.Parent = ContentFrame
AutoMoneyButton.Size = UDim2.new(0, 250, 0, 45)
AutoMoneyButton.Position = UDim2.new(0, 10, 0, 20)
AutoMoneyButton.Text = "Dinheiro Automático: OFF"
AutoMoneyButton.BackgroundColor3 = Color3.fromRGB(70,70,70)
AutoMoneyButton.TextColor3 = Color3.new(1,1,1)

AutoMoneyButton.MouseButton1Click:Connect(function()
    AutoMoney = not AutoMoney

    if AutoMoney then
        AutoMoneyButton.Text = "Dinheiro Automático: ON"
    else
        AutoMoneyButton.Text = "Dinheiro Automático: OFF"
    end
end)

local Auto2XButton = Instance.new("TextButton")
Auto2XButton.Parent = ContentFrame
Auto2XButton.Size = UDim2.new(0, 250, 0, 45)
Auto2XButton.Position = UDim2.new(0, 10, 0, 80)
Auto2XButton.Text = "2X Click: OFF"
Auto2XButton.BackgroundColor3 = Color3.fromRGB(70,70,70)
Auto2XButton.TextColor3 = Color3.new(1,1,1)

Auto2XButton.MouseButton1Click:Connect(function()
    Auto2X = not Auto2X

    if Auto2X then
        Auto2XButton.Text = "2X Click: ON"
    else
        Auto2XButton.Text = "2X Click: OFF"
    end
end)

-- Exemplo de loop
spawn(function()
    while true do
        wait(1)

        if AutoMoney then
            print("Pegando dinheiro automático...")
        end

        if Auto2X then
            print("Coletando tudo que tem 2X...")
        end
    end
end)
