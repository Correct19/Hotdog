local spawnPoint = workspace:WaitForChild("SpawnPoint")
local npcModel = game.ServerStorage:WaitForChild("NPCModel")

local function spawnNPC()
    local npc = npcModel:Clone()
    npc:SetPrimaryPartCFrame(spawnPoint.CFrame)
    npc.Parent = workspace
    
   local humanoid = npc:FindFirstChildOfClass("Humanoid")
    if humanoid then
        humanoid:ChangeState(Enum.HumanoidStateType.Physics)
    end

  for _, part in ipairs(npc:GetChildren()) do
        if part:IsA("BasePart") then
            part.BrickColor = BrickColor.new.("Bright.red") 
        end
    end
end

spawnNPC()
