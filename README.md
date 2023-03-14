
_G.Auto_Farm_Soul = false -- true
_G.Auto_Farm_Hope = false -- true

a1 = _G.Auto_Farm_Soul
_G.Hope = _G.Auto_Farm_Hope
spawn(function()
Name_GUI = "Duck HUB"
local Ui = game:GetService("CoreGui"):FindFirstChild(Name_GUI)
if Ui then
    Ui:Destroy()
end
for i,v in pairs(game:GetService("Workspace"):GetDescendants()) do -- GetDescendants
    if v.Name == "TouchInterest" then 
        v.Parent:Destroy()
    end
end
end)

local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/naypramx/Ui__Project/Script/XeNonUi", true))()
local CenterHubNo1 = library:CreateWindow("Duck HUB 🙂 ",Enum.KeyCode.RightControl)
local Tab = CenterHubNo1:CreateTab("Auto Farm")
local Sector1 = Tab:CreateSector("Auto Farm","left")

if workspace:FindFirstChild("Chil") then
else
local a = Instance.new("Part",game:GetService("Workspace"))
a.CFrame = CFrame.new(276.0135498046875, 2, 838.9736328125)
a.Anchored = true
a.Size = Vector3.new(3,1,3)
a.BrickColor = BrickColor.new("Pastel Blue")
a.Name = "Chil"
end

function EquipTool()
    for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do -- GetDescendants
        if v:IsA "Tool" then
            game.Players.LocalPlayer.Character.Humanoid:EquipTool(v)
        end
    end
end

function TP(T1)
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = T1
end

function GetPlayer(String)
   local Found = {}
   local strl = String:lower()
       for i,v in pairs(game.Players:GetPlayers()) do
           if v.Name:lower():sub(1, #String) == String:lower() then
               table.insert(Found,v.Name)
           end
       end    
   return Found    
end

Sector1:AddTextbox("Select",false,function(t)
    print(GetPlayer(t)[1])
end)

Sector1:AddToggle("Auto Farm",false,function(t)
    a1 = t
    spawn(function()
    if game:GetService("Players").LocalPlayer.Weapon.Value == "Naginata" then
        a1 = t
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(276.0135498046875, 4.291771411895752, 838.9736328125)
        number = 2
    else 
        game:GetService("ReplicatedStorage").EquipWeapon:InvokeServer("Naginata","NoWepEquip")
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(276.0135498046875, 4.291771411895752, 838.9736328125)
        wait(.5)
        a1 = t
        number = 2
    end
    
    if not a1 then
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(276.0135498046875, 4.291771411895752, 838.9736328125)
        if game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("GGEZ") then
            game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("GGEZ"):Destroy()
        end
        for i, v in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do
            if v:IsA("BasePart") and v.CanCollide == false then
                v.CanCollide = true -- Script ทะลุกำเเพง
            end
        end
        number = 2
        workspace.CurrentCamera.CameraSubject = game.Players.LocalPlayer.Character.Humanoid
    end
    end)
end)

Sector1:AddToggle("Auto Hope",false,function(t)
    _G.Hope = t
end)

Sector1:AddToggle("Set Time",false,function(t)
    Set_Time = t
end)

spawn(function()
while wait() do
if Set_Time then
pcall(function()
    Time = game:GetService("Lighting")
    Time.TimeOfDay = "14:00:00"
    Time.GlobalShadows = false
end)
end
end
end)

spawn(function()
while wait() do
if a1 then
pcall(function()
    for i,v in pairs(game:GetService("Players"):GetChildren()) do
        if i == number then
            if v.Character.Humanoid.Health <= 0 or v.IsInSafezone.Value then
                Total = #game:GetService("Players"):GetChildren()
                if number < Total then
                    number = number + 1
                else
                    if _G.Hope then
                        loadstring(game:HttpGet("https://raw.githubusercontent.com/Aomsing1thub/Hope-server/main/README.md"))()
                    else
                        number = 2
                    end
                end
            end
        end
    end
    EquipTool()
end)
end
end
end)

spawn(function()
while wait(.5) do
if a1 then
pcall(function()
    for i,v in pairs(game:GetService("Players"):GetChildren()) do
        if i == number then
            Select_You = v.Character
        end
    end

    for x,y in pairs(Select_You:GetChildren()) do
        if y:IsA "Tool" then
            if y.Blocking.Value then
                game:GetService("VirtualInputManager"):SendKeyEvent(true,102,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
                game:GetService("VirtualInputManager"):SendKeyEvent(false,102,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
                wait(.5)
            end
        end
    end
    game:GetService'VirtualUser':CaptureController()
    game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
end)
end
end
end)

spawn(function()
while wait() do
if a1 then
pcall(function()
    for i,v in pairs(game:GetService("Players"):GetChildren()) do
        if i == number then
            TP(v.Character.HumanoidRootPart.CFrame * CFrame.new(0,-9.5,-1.3) * CFrame.Angles(math.rad(90),0,0))
            workspace.CurrentCamera.CameraSubject = v.Character.Humanoid
        end
    end
end)
end
end
end)

function Noclip()
    for i, v in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do
        if v:IsA("BasePart") and v.CanCollide == true then
            v.CanCollide = false -- Script ทะลุกำเเพง
        end
    end
end

spawn(function()
    game:GetService("RunService").Heartbeat:Connect(function()
        if a1 then
            if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
                setfflag("HumanoidParallelRemoveNoPhysics", "False")
                setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
                game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
            end
        end
    end)
end)

spawn(function()
    game:GetService("RunService").Stepped:Connect(function()
        pcall(function()
            if a1 then
                Noclip()
                game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
            end
        end)
    end)
end)

spawn(function()
while wait() do
if a1 then
pcall(function()
    for i,v in pairs(game:GetService("Workspace"):GetDescendants()) do -- GetDescendants
        if v.Name == "TouchInterest" then 
            v.Parent:Destroy()
        end
    end
    for i,v in pairs(game:GetService("Workspace").SpewingObjects:GetChildren()) do -- GetDescendants
        v.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
    end
    if not game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("GGEZ") then
        local Noclip = Instance.new("BodyVelocity")
        Noclip.Name = "GGEZ"
        Noclip.Parent = game.Players.LocalPlayer.Character.HumanoidRootPart
        Noclip.MaxForce = Vector3.new(100000,100000,100000)
        Noclip.Velocity = Vector3.new(0,0,0)
    end
end)
end
end
end)
