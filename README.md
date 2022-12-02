-- Instances:

local ScreenGui = Instance.new("ScreenGui")
local inventory = Instance.new("ImageLabel")
local items = Instance.new("ScrollingFrame")
local template = Instance.new("TextLabel")
local round = Instance.new("ImageLabel")
local grid = Instance.new("UIGridLayout")
local close = Instance.new("TextButton")
local round_2 = Instance.new("ImageLabel")
local playername = Instance.new("ImageLabel")
local put = Instance.new("TextBox")
local round_3 = Instance.new("ImageLabel")
local show = Instance.new("TextButton")
local round_4 = Instance.new("ImageLabel")

-- Variables:

local PlayerThing = nil

--Properties:

ScreenGui.Parent = game.CoreGui

playername.Name = "playername"
playername.Parent = ScreenGui
playername.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
playername.BackgroundTransparency = 1.000
playername.Position = UDim2.new(0.385670722, 0, 0.407361954, 0)
playername.Size = UDim2.new(0, 300, 0, 150)
playername.Image = "rbxassetid://3570695787"
playername.ImageColor3 = Color3.fromRGB(24, 24, 24)
playername.ScaleType = Enum.ScaleType.Slice
playername.SliceCenter = Rect.new(100, 100, 100, 100)
playername.SliceScale = 0.060
playername.Active = true
playername.Draggable = true

put.Name = "put"
put.Parent = playername
put.BackgroundColor3 = Color3.fromRGB(46, 228, 255)
put.BackgroundTransparency = 1.000
put.BorderSizePixel = 0
put.Position = UDim2.new(0.0500000007, 0, 0.100000001, 0)
put.Size = UDim2.new(0, 270, 0, 45)
put.ZIndex = 3
put.Font = Enum.Font.FredokaOne
put.PlaceholderColor3 = Color3.fromRGB(40, 40, 40)
put.PlaceholderText = "Player Name"
put.Text = ""
put.TextColor3 = Color3.fromRGB(0, 0, 0)
put.TextScaled = true
put.TextSize = 14.000
put.TextWrapped = true

round_3.Name = "round"
round_3.Parent = put
round_3.Active = true
round_3.AnchorPoint = Vector2.new(0.5, 0.5)
round_3.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
round_3.BackgroundTransparency = 1.000
round_3.Position = UDim2.new(0.5, 0, 0.5, 0)
round_3.Selectable = true
round_3.Size = UDim2.new(1, 0, 1, 0)
round_3.ZIndex = 2
round_3.Image = "rbxassetid://3570695787"
round_3.ImageColor3 = Color3.fromRGB(46, 228, 255)
round_3.ScaleType = Enum.ScaleType.Slice
round_3.SliceCenter = Rect.new(100, 100, 100, 100)
round_3.SliceScale = 0.060

show.Name = "show"
show.Parent = playername
show.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
show.BackgroundTransparency = 1.000
show.BorderSizePixel = 0
show.Position = UDim2.new(0.0500000007, 0, 0.566666663, 0)
show.Size = UDim2.new(0, 270, 0, 50)
show.ZIndex = 3
show.Font = Enum.Font.FredokaOne
show.Text = "   Show Inventory   "
show.TextColor3 = Color3.fromRGB(0, 0, 0)
show.TextScaled = true
show.TextSize = 14.000
show.TextWrapped = true
show.MouseButton1Click:Connect(function()
	if put.Text == "" then
		
	else
		PlayerThing = put.Text
		playername.Visible = false
		inventory.Visible = true
		for _, Item in ipairs(game.Players:FindFirstChild(PlayerThing).Items:GetChildren()) do
			local Dupe = show.Parent.Parent.template:Clone()
			Dupe.Parent = show.Parent.Parent.inventory.items
			Dupe.Text = " "..Item.Name.."  ".."-".."  "..Item.Value
			Dupe.Visible = true
			wait()
		end
		show.Parent.Parent.close.Visible = true
	end
end)

round_4.Name = "round"
round_4.Parent = show
round_4.Active = true
round_4.AnchorPoint = Vector2.new(0.5, 0.5)
round_4.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
round_4.BackgroundTransparency = 1.000
round_4.Position = UDim2.new(0.5, 0, 0.5, 0)
round_4.Selectable = true
round_4.Size = UDim2.new(1, 0, 1, 0)
round_4.ZIndex = 2
round_4.Image = "rbxassetid://3570695787"
round_4.ImageColor3 = Color3.fromRGB(46, 228, 255)
round_4.ScaleType = Enum.ScaleType.Slice
round_4.SliceCenter = Rect.new(100, 100, 100, 100)
round_4.SliceScale = 0.060

inventory.Name = "inventory"
inventory.Parent = ScreenGui
inventory.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
inventory.BackgroundTransparency = 1.000
inventory.Position = UDim2.new(0.309451222, 0, 0.284662575, 0)
inventory.Size = UDim2.new(0, 500, 0, 350)
inventory.Visible = false
inventory.Image = "rbxassetid://3570695787"
inventory.ImageColor3 = Color3.fromRGB(31, 31, 31)
inventory.ScaleType = Enum.ScaleType.Slice
inventory.SliceCenter = Rect.new(100, 100, 100, 100)
inventory.SliceScale = 0.060
inventory.Active = true
inventory.Draggable = true

items.Name = "items"
items.Parent = inventory
items.Active = true
items.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
items.BackgroundTransparency = 1.000
items.BorderSizePixel = 0
items.Position = UDim2.new(0.0120000001, 0, 0.0171428565, 0)
items.Size = UDim2.new(0, 487, 0, 338)
items.ZIndex = 2
items.CanvasSize = UDim2.new(0, 0, 50, 0)

template.Name = "template"
template.Parent = ScreenGui
template.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
template.BackgroundTransparency = 1.000
template.BorderSizePixel = 0
template.Size = UDim2.new(0, 486, 0, 26)
template.ZIndex = 4
template.Font = Enum.Font.FredokaOne
template.Text = "   N/A  -  N/A"
template.TextColor3 = Color3.fromRGB(0, 0, 0)
template.TextScaled = true
template.TextSize = 14.000
template.TextWrapped = true
template.TextXAlignment = Enum.TextXAlignment.Left
template.Visible = false

round.Name = "round"
round.Parent = template
round.AnchorPoint = Vector2.new(0.5, 0.5)
round.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
round.BackgroundTransparency = 1.000
round.Position = UDim2.new(0.5, 0, 0.5, 0)
round.Size = UDim2.new(1, 0, 1, 0)
round.ZIndex = 3
round.Image = "rbxassetid://3570695787"
round.ImageColor3 = Color3.fromRGB(34, 182, 133)
round.ScaleType = Enum.ScaleType.Slice
round.SliceCenter = Rect.new(100, 100, 100, 100)
round.SliceScale = 0.060

grid.Name = "grid"
grid.Parent = items
grid.FillDirection = Enum.FillDirection.Vertical
grid.SortOrder = Enum.SortOrder.LayoutOrder
grid.CellSize = UDim2.new(0, 469, 0, 32)

close.Name = "close"
close.Parent = ScreenGui
close.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
close.BackgroundTransparency = 1.000
close.BorderSizePixel = 0
close.Position = UDim2.new(0.423, 0, 0.123, 0)
close.Size = UDim2.new(0, 200, 0, 50)
close.Visible = false
close.ZIndex = 4
close.Font = Enum.Font.FredokaOne
close.Text = "X"
close.TextColor3 = Color3.fromRGB(0, 0, 0)
close.TextScaled = true
close.TextSize = 14.000
close.TextWrapped = true
close.MouseButton1Click:Connect(function()
	ScreenGui:Destroy()
end)

round_2.Name = "round"
round_2.Parent = close
round_2.Active = true
round_2.AnchorPoint = Vector2.new(0.5, 0.5)
round_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
round_2.BackgroundTransparency = 1.000
round_2.Position = UDim2.new(0.5, 0, 0.5, 0)
round_2.Selectable = true
round_2.Size = UDim2.new(1, 0, 1, 0)
round_2.ZIndex = 3
round_2.Image = "rbxassetid://3570695787"
round_2.ImageColor3 = Color3.fromRGB(168, 0, 2)
round_2.ScaleType = Enum.ScaleType.Slice
round_2.SliceCenter = Rect.new(100, 100, 100, 100)
round_2.SliceScale = 0.060
