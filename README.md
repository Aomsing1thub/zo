Name_Dangerous = {"cIharger","Zelnect","TamperedReality","StevenMacLeod","ImLazuli","bink1337","Duckagon","RaRaRetlukk","Jonesybirb","SergeantSicarius","Jamix6","TyrantStrategizer","b1nkster","Vallithm","OniSinister","spegattii","RedFragment","HazelnutsChocolates","Olafinsky","Lewis_Schumer","sambirb","zboys"}
Total = #game:GetService("Players"):GetChildren()
ao = math.random(1,3)
if ao == 1 then 
    a = "Fuck"
    else 
    a = "Holy Fuck"
end
bo = math.random(1,3)
if bo == 1 then 
    b = "You"
    else 
    b = "Zo"
end
co = math.random(1,3)
if co == 1 then 
    c = "Yes"
    else 
    c = "No"
end
eo = math.random(1,3)
if eo == 1 then 
    e = "Random"
    else 
    e = "Name"
end
Name_GUI = (""..a..""..b..""..c..""..e)
local Ui = game:GetService("CoreGui"):FindFirstChild(Name_GUI)
if Ui then
    Ui:Destroy()
end
local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/naypramx/Ui__Project/Script/XeNonUi", true))()
library:CreateWatermark(Name_GUI ) -- Config แตกนะเดียวค่อยแก้รอเน็ตมาก่อน By MeowX#0001
local CenterHubNo1 = library:CreateWindow("ZOぞ [WIP] Auto Farm Soul ❤ ",Enum.KeyCode.RightControl)
local Tab = CenterHubNo1:CreateTab("Auto Farm")
local Sector1 = Tab:CreateSector("Auto Farm","left")
Sector1:AddLabel("Auto Farm Soul")
Sector1:AddToggle("Auto Farm",_G.Auto_Farm_Soul,function(v)
if game:GetService("Players").LocalPlayer.Weapon.Value == "Naginata" then
    Start = v
else 
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-70.09310913085938, 20.998374938964844, 149.26210021972656)
wait(.3)
game:GetService("VirtualInputManager"):SendKeyEvent(true,101,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
game:GetService("VirtualInputManager"):SendKeyEvent(false,101,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
wait(1)
Start = v
end
end)

Sector1:AddToggle("Auto Farm Hope",_G.Auto_Farm_Hope,function(GG)
if GG then
    Start = false
    num = 1
    wait(.5)
    HOPESERVER = true
end
end)

Sector1:AddButton("Hope server",function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/Aomsing1thub/Hope-server/main/README.md"))()
end)

num = 1
spawn(function()
while wait() do
if Start then
pcall(function()
if Total == num then 
    num = 1
end
for i,v in pairs(game:GetService("Workspace"):GetDescendants()) do -- GetDescendants
    if v.Name == "TouchInterest" then 
        v.Parent:Destroy()
    end
end
for i,v in pairs(game:GetService("Players"):GetChildren()) do
a = num
if a == i then
    if v.Character:WaitForChild("Humanoid") then  
game.Players.LocalPlayer.Character.Humanoid:EquipTool(game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Naginata"))
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.Character.HumanoidRootPart.CFrame * CFrame.new(0,-10,-1.3) * CFrame.Angles(math.rad(90),0,0)
workspace.CurrentCamera.CameraSubject = v.Character.Humanoid        
        end
    end
end --
end)
end
end
end) -- Normal

spawn(function()
while wait() do
if HOPESERVER then
pcall(function()
if Total == num then 
loadstring(game:HttpGet("https://raw.githubusercontent.com/Aomsing1thub/Hope-server/main/README.md"))()
end
for i,v in pairs(game:GetService("Workspace"):GetDescendants()) do -- GetDescendants
    if v.Name == "TouchInterest" then 
        v.Parent:Destroy()
    end
end
for i,v in pairs(game:GetService("Players"):GetChildren()) do
a = num
if a == i then
    if v.Character:WaitForChild("Humanoid") then  
game.Players.LocalPlayer.Character.Humanoid:EquipTool(game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Naginata"))
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.Character.HumanoidRootPart.CFrame * CFrame.new(0,-10,-1.3) * CFrame.Angles(math.rad(90),0,0)
workspace.CurrentCamera.CameraSubject = v.Character.Humanoid        
        end
    end
end --
end)
end
end
end) -- HOPE

spawn(function()
while wait(1) do
if HOPESERVER then
pcall(function()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(26.32699203491211, 12.974864959716797, -63.72871398925781)
HOPESERVER = false
wait(.5)
num = num + 1
wait()
HOPESERVER = true
end)
end
end
end) -- HOPE

spawn(function()
while wait(.5) do
if Start or HOPESERVER then
pcall(function()
game:GetService'VirtualUser':CaptureController()
game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
end)
end
end
end)

spawn(function()
while wait(1) do
if Start then
pcall(function()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(26.32699203491211, 12.974864959716797, -63.72871398925781)
Start = false
wait(.5)
num = num + 1
wait()
Start = true
end)
end
end
end)

spawn(function() 
while wait() do
if Start or HOPESERVER then
pcall(function()
---
for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
    if v:IsA "Tool" then 
        v.Name = "Naginata"
    end
end
if game.Players.LocalPlayer.Character.Humanoid.Health < 0 then 
    num = 2
    Start = false 
    wait(5)
    Start = true
    for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
        if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(v) then 
            for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
                if v:IsA "Tool" then 
                    v.Name = "Naginata"
                end
            end
        end
    end
end
---
end)
end
end
end)

spawn(function()
        game:GetService("RunService").Heartbeat:Connect(function()
        if Start or AA or HOPESERVER then
            if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
                setfflag("HumanoidParallelRemoveNoPhysics", "False")
                setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
                game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
            end
        end
    end)
end)

local Sector1 = Tab:CreateSector("Mics","Right")

Sector1:AddLabel("Auto rejoin")
Sector1:AddToggle("Auto rejoin",false,function(t)
pcall(function()
local queue_on_teleport = syn.queue_on_teleport or queue_on_teleport
local rejoin
rejoin = game:GetService("CoreGui").RobloxPromptGui.promptOverlay.ChildAdded:Connect(function(child)
if child.Name == 'ErrorPrompt' and child:FindFirstChild('MessageArea') and child.MessageArea:FindFirstChild("ErrorFrame") then
queue_on_teleport([[
local rejoin
local queue_on_teleport = syn.queue_on_teleport or queue_on_teleport
rejoin = game:GetService("CoreGui").RobloxPromptGui.promptOverlay.ChildAdded:Connect(function(child)
        if child.Name == 'ErrorPrompt' and child:FindFirstChild('MessageArea') and child.MessageArea:FindFirstChild("ErrorFrame") then
            game:GetService("TeleportService"):Teleport(game.PlaceId, game:GetService("Players").LocalPlayer)
        end
]])
if t then
    game:GetService("TeleportService"):Teleport(game.PlaceId, game:GetService("Players").LocalPlayer)
end
end
end)
end)
end)

Sector1:AddToggle("Anti Admin Check",true,function(t)
    if t then 
        Found = true
    end
end)

spawn(function()
while Found do wait()
pcall(function()
for i,v in pairs(Name_Dangerous) do
    Dangerous = v
for i,v in pairs(game:GetService("Players"):GetChildren()) do
if v.Name == Dangerous then 
    game.Players.LocalPlayer:Kick("Found Admin") 
    wait(2)
    game:Shutdown()
end --
end
end
end)
end 
end)

Sector1:AddButton("rejoin",function()
game:GetService("TeleportService"):Teleport(game.PlaceId, game:GetService("Players").LocalPlayer)
end)

local Tab = CenterHubNo1:CreateTab("Combat")
local Sector1 = Tab:CreateSector("Combat","left")

players = {}
for i,v in pairs(game:GetService("Players"):GetChildren()) do
   table.insert(players,v.Name)
end

local dropdoxwn = Sector1:AddDropdown("Select Players",players,"Select Players",false,function(t)
Select_Players = t
end)

Sector1:AddButton("Teleport",function()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Players[Select_Players].Character.HumanoidRootPart.CFrame
end)

local wea = game:GetService("Players").LocalPlayer.Weapon.Value

Sector1:AddToggle("Auto Kill",nil,function(S)
if S then
    AA = true
    elseif S == false then
    AA = false
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(26.32699203491211, 12.974864959716797, -63.72871398925781)
end
end)

spawn(function()
while wait() do
if AA then
pcall(function()
for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
    if v:IsA "Tool" then 
        game.Players.LocalPlayer.Character.Humanoid:EquipTool(game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(v.Name))
    end
end
for i,v in pairs(game:GetService("Workspace"):GetDescendants()) do -- GetDescendants
    if v.Name == "TouchInterest" then 
        v.Parent:Destroy()
    end
end
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Players[Select_Players].Character.HumanoidRootPart.CFrame * CFrame.new(0,-9,-2) * CFrame.Angles(math.rad(90),0,0)
if game.Players[Select_Players].Character.Humanoid.Health <= 0 then 
    AA = false
    repeat wait()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(26.32699203491211, 12.974864959716797, -63.72871398925781)
    until AA == false
end
end)
end
end
end)

spawn(function()
while wait(.2) do
if AA then
pcall(function()
game:GetService'VirtualUser':CaptureController()
game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
end)
end
end
end)

Sector1:AddToggle("Spectate",false,function(gg)
if gg then 
workspace.CurrentCamera.CameraSubject = game.Players[Select_Players].Character.Humanoid
else 
workspace.CurrentCamera.CameraSubject = game.Players.LocalPlayer.Character.Humanoid
end
end)

local Sector2 = Tab:CreateSector("Weapon","Right")
local Weaponlist = {"Kanabo","Naginata","Katana","Tanto"}

Sector2:AddDropdown("Select Weapons",Weaponlist,wea,false,function(t)
Select_weapon = t
end)

Sector2:AddButton("Kanabo",function()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(41.56386947631836, -7.000000953674316, 262.7695617675781)
wait()
game:GetService("VirtualInputManager"):SendKeyEvent(true,101,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
game:GetService("VirtualInputManager"):SendKeyEvent(false,101,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
end)

Sector2:AddButton("Naginata",function()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-70.09310913085938, 20.998374938964844, 149.26210021972656)
wait()
game:GetService("VirtualInputManager"):SendKeyEvent(true,101,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
game:GetService("VirtualInputManager"):SendKeyEvent(false,101,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
end)

Sector2:AddButton("Katana",function()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-226.84986877441406, -5.399991989135742, 206.5946807861328)
wait()
game:GetService("VirtualInputManager"):SendKeyEvent(true,101,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
game:GetService("VirtualInputManager"):SendKeyEvent(false,101,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
end)

Sector2:AddButton("Tanto",function()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(41.020172119140625, -7.249948024749756, 62.1593017578125)
wait()
game:GetService("VirtualInputManager"):SendKeyEvent(true,101,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
game:GetService("VirtualInputManager"):SendKeyEvent(false,101,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
end)
