local leaderS = game.Players.PlayerAdded
local RS = game:GetService("ReplicatedStorage")
local playerData = {}

leaderS:Connect(function(player)
	local dropperUpgraded = false
	local dropperUp = false
	local dropper4 = false   --variables :)
	local dropper3 = false
	local dropper2 = false
	local cooldown = false
	local RS = game:GetService("ReplicatedStorage")
	
	local leaderstats = Instance.new("Folder", player)
	leaderstats.Name = "leaderstats"

	-- Create the Points value inside leaderstats
	local Points = Instance.new("IntValue", leaderstats)
	Points.Name = "Points"
	Points.Value = 0   -- how many points the player starts with

	playerData[player] = Points
	
	
	local MoneyButton = workspace.BuyButtons.ButtonM.ClickDetector
	
	MoneyButton.MouseClick:Connect(function(player)
		Points.Value = Points.Value + 500
	end)
	
	
	
	workspace.Conveyer.PartCollect.Touched:Connect(function(hit)      --checks to make sure what touched the "PartCollect" has a certain name before destroying
		if hit.Name == "Box" then
			hit:Destroy()
			Points.Value = Points.Value + 1
		end
		if hit.Name == "Box2" then
			hit:Destroy()
			Points.Value = Points.Value + 2
		end	
		if hit.Name == "Box3" then
			hit:Destroy()
			Points.Value = Points.Value + 5
		end
	end)
	

	local ClickDetector = workspace.BuyButtons.Button1.ClickDetector         -- DROPPER 2 buy and spawn it
		ClickDetector.MouseClick:Connect(function(player)
			
				if Points.Value >= 10 and dropper2 == false then
					wait(0.5)
					dropper2 = true
					print("Purchased!")
					workspace.BuyButtons.Button1.Parent = RS
					Points.Value = Points.Value - 10
					local clonedModel = RS.Dropper2:clone()
					clonedModel.Parent = workspace
					
						else
							print("Not enough points or has been bought already!")
					end
				
		while dropper2 == true do
			wait(1)    -- time that it takes to spawn 1 "box"
			local newPart = Instance.new("Part", workspace.Parts)
			newPart.Size = Vector3.new(1, 1, 1)
			newPart.Position = Vector3.new(-10.4, 6.5, 32.6)
			newPart.Name = "Box"
			newPart.Material = "Plastic"
			newPart.Color = Color3.fromRGB(39, 224, 227)
		end  

	

			
end)

	 
	local ClickDetector2 = workspace.BuyButtons.Button2.ClickDetector                -- DROPPER 3 buy and spawn it
	ClickDetector2.MouseClick:Connect(function(player)

		if Points.Value >= 50 and dropper3 == false then
			wait(0.5)
			dropper3 = true
			print("Purchased!")
			workspace.BuyButtons.Button2.Parent = RS
			Points.Value = Points.Value - 50
			local clonedModel = RS.Dropper3:clone()
			clonedModel.Parent = workspace

		else
			print("Not enough points or has been bought already!")
		end

		while dropper3 == true do
			wait(1)    -- time that it takes to spawn 1 "box"
			local newPart = Instance.new("Part", workspace.Parts)
			newPart.Size = Vector3.new(1, 1, 1)
			newPart.Position = Vector3.new(-10.5, 6.5, 37.8)
			newPart.Name = "Box2"
			newPart.Material = "Neon"
			newPart.Color = Color3.fromRGB(1, 235, 28)
		end




	end)
	
	
	local ClickDetector3 = workspace.BuyButtons.Button3.ClickDetector                -- DROPPER 4 buy and spawn it
	ClickDetector3.MouseClick:Connect(function(player)

		if Points.Value >= 100 and dropper4 == false then
			wait(0.5)
			dropper4 = true
			print("Purchased!")
			workspace.BuyButtons.Button3.Parent = RS
			Points.Value = Points.Value - 100
			local clonedModel = RS.Dropper4:clone()
			clonedModel.Parent = workspace

		else
			print("Not enough points or has been bought already!")
		end

		while dropper4 == true do
			wait(0.75)      -- time that it takes to spawn 1 "box"
			local newPart = Instance.new("Part", workspace.Parts)
			newPart.Size = Vector3.new(1, 1, 1)
			newPart.Position = Vector3.new(-10.5, 6.5, 43.1)
			newPart.Name = "Box3"
			newPart.Material = "Neon"
			newPart.Color = Color3.fromRGB(235, 208, 0)
		end




	end)
	
	local ClickDetector4 = workspace.BuyButtons.Button4.ClickDetector                -- DROPPER 4 buy and spawn it
	ClickDetector4.MouseClick:Connect(function(player)

		if Points.Value >= 250 and dropperUpgraded == false then
			dropperUpgraded = true
			wait(0.5)
			dropperUp = true
			print("Purchased Upgrade!")
			workspace.BuyButtons.Button4.Parent = RS
			Points.Value = Points.Value - 250
			workspace.Button.Material = "Neon"

		else
			print("Not enough points or has been bought already!")
		end

		while dropperUp == true do
			wait(0.20)      -- time that it takes to spawn 1 "box"
			local newPart = Instance.new("Part", workspace.Parts)
			newPart.Size = Vector3.new(1, 1, 1)
			newPart.Position = Vector3.new(-10.5, 5.5, 26.25)
			newPart.Name = "Box"
			newPart.Material = "Marble"
			newPart.Color = Color3.fromRGB(61, 21, 133)
		end




	end)
	
	
	
end)
		
	
