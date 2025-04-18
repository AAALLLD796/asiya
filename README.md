local UIS = game:GetService("UserInputService")
local player = game.Players.LocalPlayer
local mouse = player:GetMouse()

local holding = nil

mouse.Button1Down:Connect(function()
	local target = mouse.Target
	if target and target:IsA("BasePart") then
		holding = target
		local weld = Instance.new("WeldConstraint")
		weld.Part0 = player.Character:FindFirstChild("RightHand")
		weld.Part1 = holding
		weld.Parent = holding
	end
end)
