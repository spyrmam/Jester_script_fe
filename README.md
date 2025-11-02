if game:GetService("RunService"):IsClient() then error("Script must be server-side in order to work; use h/ and not hl/") end local Player,Mouse,mouse,UserInputService,ContextActionService = owner do print("Dis shit was made by spyrmam!") script.Parent = Player.Character

--RemoteEvent for communicating
local Event = Instance.new("RemoteEvent")
Event.Name = "UserInput_Event"


--Creating fake input objects with fake variables
local m = {Target=nil,Hit=CFrame.new(),KeyUp=fakeEvent(),KeyDown=fakeEvent(),Button1Up=fakeEvent(),Button1Down=fakeEvent()}
local UIS = {InputBegan=fakeEvent(),InputEnded=fakeEvent()}
local CAS = {Actions={},BindAction=function(self,name,fun,touch,...)
	CAS.Actions[name] = fun and {Name=name,Function=fun,Keys={...}} or nil
end}
--Merged 2 functions into one by checking amount of arguments
CAS.UnbindAction = CAS.BindAction

--This function will trigger the events that have been :Connect()'ed
local function te(self,ev,...)
	local t = m[ev]
	if t and t._fakeEvent and t.Function then
		t.Function(...)
	end
end
m.TrigEvent = te
UIS.TrigEvent = te

Event.OnServerEvent:Connect(function(plr,io)
    if plr~=Player then return end
	if io.isMouse then
		m.Target = io.Target
		m.Hit = io.Hit
	else
		local b = io.UserInputState == Enum.UserInputState.Begin
		if io.UserInputType == Enum.UserInputType.MouseButton1 then
			return m:TrigEvent(b and "Button1Down" or "Button1Up")
		end
		for _,t in pairs(CAS.Actions) do
			for _,k in pairs(t.Keys) do
				if k==io.KeyCode then
					t.Function(t.Name,io.UserInputState,io)
				end
			end
		end
		m:TrigEvent(b and "KeyDown" or "KeyUp",io.KeyCode.Name:lower())
		UIS:TrigEvent(b and "InputBegan" or "InputEnded",io,false)
    end
end)
Event.Parent = NLS([==[
local Player = owner
local Event = script:WaitForChild("UserInput_Event")

local UIS = game:GetService("UserInputService")
local input = function(io,a)
	if a then return end
	--Since InputObject is a client-side instance, we create and pass table instead
	Event:FireServer({KeyCode=io.KeyCode,UserInputType=io.UserInputType,UserInputState=io.UserInputState})
end
UIS.InputBegan:Connect(input)
UIS.InputEnded:Connect(input)
local h,t
--Give the server mouse data 30 times every second, but only if the values changed
--If player is not moving their mouse, client won't fire events
while wait(1/30) do
	if h~=Mouse.Hit or t~=Mouse.Target then
		h,t=Mouse.Hit,Mouse.Target
		Event:FireServer({isMouse=true,Target=t,Hit=h})
	end
end]==],Player.Character)
Mouse,mouse,UserInputService,ContextActionService = m,m,UIS,CAS
end


--Everything is Meaningless.....
wait(0.1)
local plr = game:GetService("Players").LocalPlayer
print('Local User is '..plr.Name)
print('Jester Loaded')
print([[
	HAHAHAHAHAHA,
	WHO AM I?
	YOU REALLY MUST BE A MORTAL THEN!
	YOU'LL SOON SEE!
]])
local char = plr.Character
local hum = char:FindFirstChildOfClass'Humanoid'
local hed = char.Head
local root = char:FindFirstChild'HumanoidRootPart'
local rootj = root.RootJoint
local tors = char.Torso
local ra = char["Right Arm"]
local la = char["Left Arm"]
local rl = char["Right Leg"]
local ll = char["Left Leg"]
local neck = tors["Neck"]
local mouse = plr:GetMouse()
local RootCF = CFrame.fromEulerAnglesXYZ(-1.57, 0, 3.14)
local RHCF = CFrame.fromEulerAnglesXYZ(0, 1.6, 0)
local LHCF = CFrame.fromEulerAnglesXYZ(0, -1.6, 0)
local maincolor = BrickColor.new("Institutional white")
-------------------------------------------------------
--Start Whitelist and Invincibility--
-------------------------------------------------------	
ff = Instance.new("ForceField",char)
ff.Visible = false
hum.Name = "Base"
hum.MaxHealth = 1.0E298
hum.Health = 1.0E298
game:GetService("RunService"):BindToRenderStep("Base", 0, function()
  if hum.Health > 0.1 and hum.Health < 1.0E298 then
    hum.MaxHealth = 1.0E298
    hum.Health = 1.0E298
  end
end)
-------------------------------------------------------
--End Whitelist and Invincibility--
-------------------------------------------------------	

-------------------------------------------------------
--Start Good Stuff--
-------------------------------------------------------
cam = game.Workspace.CurrentCamera
CF = CFrame.new
angles = CFrame.Angles
attack = false
Euler = CFrame.fromEulerAnglesXYZ
Rad = math.rad
IT = Instance.new
BrickC = BrickColor.new
Cos = math.cos
Acos = math.acos
Sin = math.sin
Asin = math.asin
Abs = math.abs
Mrandom = math.random
Floor = math.floor
-------------------------------------------------------
--End Good Stuff--
-------------------------------------------------------
necko = CF(0, 1, 0, -1, -0, -0, 0, 0, 1, 0, 1, 0)
RSH, LSH = nil, nil 
RW = Instance.new("Weld") 
LW = Instance.new("Weld")
RH = tors["Right Hip"]
LH = tors["Left Hip"]
RSH = tors["Right Shoulder"] 
LSH = tors["Left Shoulder"] 
RSH.Parent = nil 
LSH.Parent = nil 
RW.Name = "RW"
RW.Part0 = tors 
RW.C0 = CF(1.5, 0.5, 0)
RW.C1 = CF(0, 0.5, 0) 
RW.Part1 = ra
RW.Parent = tors 
LW.Name = "LW"
LW.Part0 = tors 
LW.C0 = CF(-1.5, 0.5, 0)
LW.C1 = CF(0, 0.5, 0) 
LW.Part1 = la
LW.Parent = tors
Effects = {}
newWeld = function(wp0, wp1, wc0x, wc0y, wc0z)
    local wld = Instance.new("Weld", wp1)
    wld.Part0 = wp0
    wld.Part1 = wp1
    wld.C0 = CFrame.new(wc0x, wc0y, wc0z)
end
newWeld(tors, ll, -0.5, -1, 0)
ll.Weld.C1 = CFrame.new(0, 1, 0)
newWeld(tors, rl, 0.5, -1, 0)
rl.Weld.C1 = CFrame.new(0, 1, 0)
-------------------------------------------------------
--Start HeartBeat--
-------------------------------------------------------
ArtificialHB = Instance.new("BindableEvent", script)
ArtificialHB.Name = "Heartbeat"
script:WaitForChild("Heartbeat")

frame = 1 / 60
tf = 0
allowframeloss = false
tossremainder = false


lastframe = tick()
script.Heartbeat:Fire()


game:GetService("RunService").Heartbeat:connect(function(s, p)
	tf = tf + s
	if tf >= frame then
		if allowframeloss then
			script.Heartbeat:Fire()
			lastframe = tick()
		else
			for i = 1, math.floor(tf / frame) do
				script.Heartbeat:Fire()
			end
			lastframe = tick()
		end
		if tossremainder then
			tf = 0
		else
			tf = tf - frame * math.floor(tf / frame)
		end
	end
end)
-------------------------------------------------------
--End HeartBeat--
-------------------------------------------------------

-------------------------------------------------------
--Start Important Functions--
-------------------------------------------------------
function swait(num)
	if num == 0 or num == nil then
		game:service("RunService").Stepped:wait(0)
	else
		for i = 0, num do
			game:service("RunService").Stepped:wait(0)
		end
	end
end
function thread(f)
	coroutine.resume(coroutine.create(f))
end
function clerp(a, b, t)
	local qa = {
		QuaternionFromCFrame(a)
	}
	local qb = {
		QuaternionFromCFrame(b)
	}
	local ax, ay, az = a.x, a.y, a.z
	local bx, by, bz = b.x, b.y, b.z
	local _t = 1 - t
	return QuaternionToCFrame(_t * ax + t * bx, _t * ay + t * by, _t * az + t * bz, QuaternionSlerp(qa, qb, t))
end
function QuaternionFromCFrame(cf)
	local mx, my, mz, m00, m01, m02, m10, m11, m12, m20, m21, m22 = cf:components()
	local trace = m00 + m11 + m22
	if trace > 0 then
		local s = math.sqrt(1 + trace)
		local recip = 0.5 / s
		return (m21 - m12) * recip, (m02 - m20) * recip, (m10 - m01) * recip, s * 0.5
	else
		local i = 0
		if m00 < m11 then
			i = 1
		end
		if m22 > (i == 0 and m00 or m11) then
			i = 2
		end
		if i == 0 then
			local s = math.sqrt(m00 - m11 - m22 + 1)
			local recip = 0.5 / s
			return 0.5 * s, (m10 + m01) * recip, (m20 + m02) * recip, (m21 - m12) * recip
		elseif i == 1 then
			local s = math.sqrt(m11 - m22 - m00 + 1)
			local recip = 0.5 / s
			return (m01 + m10) * recip, 0.5 * s, (m21 + m12) * recip, (m02 - m20) * recip
		elseif i == 2 then
			local s = math.sqrt(m22 - m00 - m11 + 1)
			local recip = 0.5 / s
			return (m02 + m20) * recip, (m12 + m21) * recip, 0.5 * s, (m10 - m01) * recip
		end
	end
end
function QuaternionToCFrame(px, py, pz, x, y, z, w)
	local xs, ys, zs = x + x, y + y, z + z
	local wx, wy, wz = w * xs, w * ys, w * zs
	local xx = x * xs
	local xy = x * ys
	local xz = x * zs
	local yy = y * ys
	local yz = y * zs
	local zz = z * zs
	return CFrame.new(px, py, pz, 1 - (yy + zz), xy - wz, xz + wy, xy + wz, 1 - (xx + zz), yz - wx, xz - wy, yz + wx, 1 - (xx + yy))
end
function QuaternionSlerp(a, b, t)
	local cosTheta = a[1] * b[1] + a[2] * b[2] + a[3] * b[3] + a[4] * b[4]
	local startInterp, finishInterp
	if cosTheta >= 1.0E-4 then
		if 1 - cosTheta > 1.0E-4 then
			local theta = math.acos(cosTheta)
			local invSinTheta = 1 / Sin(theta)
			startInterp = Sin((1 - t) * theta) * invSinTheta
			finishInterp = Sin(t * theta) * invSinTheta
		else
			startInterp = 1 - t
			finishInterp = t
		end
	elseif 1 + cosTheta > 1.0E-4 then
		local theta = math.acos(-cosTheta)
		local invSinTheta = 1 / Sin(theta)
		startInterp = Sin((t - 1) * theta) * invSinTheta
		finishInterp = Sin(t * theta) * invSinTheta
	else
		startInterp = t - 1
		finishInterp = t
	end
	return a[1] * startInterp + b[1] * finishInterp, a[2] * startInterp + b[2] * finishInterp, a[3] * startInterp + b[3] * finishInterp, a[4] * startInterp + b[4] * finishInterp
end
function rayCast(Position, Direction, Range, Ignore)
	return game:service("Workspace"):FindPartOnRay(Ray.new(Position, Direction.unit * (Range or 999.999)), Ignore)
end
local RbxUtility = LoadLibrary("RbxUtility")
local Create = RbxUtility.Create

-------------------------------------------------------
--Start Damage Function--
-------------------------------------------------------
function Damage(Part, hit, minim, maxim, knockback, Type, Property, Delay, HitSound, HitPitch)
	if hit.Parent == nil then
		return
	end
	local h = hit.Parent:FindFirstChildOfClass("Humanoid")
	for _, v in pairs(hit.Parent:children()) do
		if v:IsA("Humanoid") then
			h = v
		end
	end
         if h ~= nil and hit.Parent.Name ~= char.Name and hit.Parent:FindFirstChild("UpperTorso") ~= nil then
	
         hit.Parent:FindFirstChild("Head"):BreakJoints()
         end

	if h ~= nil and hit.Parent.Name ~= char.Name and hit.Parent:FindFirstChild("Torso") ~= nil then
		if hit.Parent:findFirstChild("DebounceHit") ~= nil then
			if hit.Parent.DebounceHit.Value == true then
				return
			end
		end
         if insta == true then
         hit.Parent:FindFirstChild("Head"):BreakJoints()
         end
		local c = Create("ObjectValue"){
			Name = "creator",
			Value = localplayer,
			Parent = h,
		}
		game:GetService("Debris"):AddItem(c, .5)
		if HitSound ~= nil and HitPitch ~= nil then
			CFuncs.Sound.Create(HitSound, hit, 1, HitPitch)
		end
		local Damage = math.random(minim, maxim)
		local blocked = false
		local block = hit.Parent:findFirstChild("Block")
		if block ~= nil then
			if block.className == "IntValue" then
				if block.Value > 0 then
					blocked = true
					block.Value = block.Value - 1
					print(block.Value)
				end
			end
		end
		if blocked == false then
			h.Health = h.Health - Damage
			ShowDamage((Part.CFrame * CFrame.new(0, 0, (Part.Size.Z / 2)).p + Vector3.new(0, 1.5, 0)), -Damage, 1.5, tors.BrickColor.Color)
		else
			h.Health = h.Health - (Damage / 2)
			ShowDamage((Part.CFrame * CFrame.new(0, 0, (Part.Size.Z / 2)).p + Vector3.new(0, 1.5, 0)), -Damage, 1.5, tors.BrickColor.Color)
		end
		if Type == "Knockdown" then
			local hum = hit.Parent.Humanoid
			hum.PlatformStand = true
			coroutine.resume(coroutine.create(function(HHumanoid)
				swait(1)
				HHumanoid.PlatformStand = false
			end), hum)
			local angle = (hit.Position - (Property.Position + Vector3.new(0, 0, 0))).unit
			local bodvol = Create("BodyVelocity"){
				velocity = angle * knockback,
				P = 5000,
				maxForce = Vector3.new(8e+003, 8e+003, 8e+003),
				Parent = hit,
			}
			local rl = Create("BodyAngularVelocity"){
				P = 3000,
				maxTorque = Vector3.new(500000, 500000, 500000) * 50000000000000,
				angularvelocity = Vector3.new(math.random(-10, 10), math.random(-10, 10), math.random(-10, 10)),
				Parent = hit,
			}
			game:GetService("Debris"):AddItem(bodvol, .5)
			game:GetService("Debris"):AddItem(rl, .5)
		elseif Type == "Normal" then
			local vp = Create("BodyVelocity"){
				P = 500,
				maxForce = Vector3.new(math.huge, 0, math.huge),
				velocity = Property.CFrame.lookVector * knockback + Property.Velocity / 1.05,
			}
			if knockback > 0 then
				vp.Parent = hit.Parent.Torso
			end
			game:GetService("Debris"):AddItem(vp, .5)
		elseif Type == "Up" then
			local bodyVelocity = Create("BodyVelocity"){
				velocity = Vector3.new(0, 20, 0),
				P = 5000,
				maxForce = Vector3.new(8e+003, 8e+003, 8e+003),
				Parent = hit,
			}
			game:GetService("Debris"):AddItem(bodyVelocity, .5)
		elseif Type == "DarkUp" then
			coroutine.resume(coroutine.create(function()
				for i = 0, 1, 0.1 do
					swait()
					Effects.Block.Create(BrickColor.new("Black"), hit.Parent.Torso.CFrame, 5, 5, 5, 1, 1, 1, .08, 1)
				end
			end))
			local bodyVelocity = Create("BodyVelocity"){
				velocity = Vector3.new(0, 20, 0),
				P = 5000,
				maxForce = Vector3.new(8e+003, 8e+003, 8e+003),
				Parent = hit,
			}
			game:GetService("Debris"):AddItem(bodyVelocity, 1)
		elseif Type == "Snare" then
			local bp = Create("BodyPosition"){
				P = 2000,
				D = 100,
				maxForce = Vector3.new(math.huge, math.huge, math.huge),
				position = hit.Parent.Torso.Position,
				Parent = hit.Parent.Torso,
			}
			game:GetService("Debris"):AddItem(bp, 1)
		elseif Type == "Freeze" then
			local BodPos = Create("BodyPosition"){
				P = 50000,
				D = 1000,
				maxForce = Vector3.new(math.huge, math.huge, math.huge),
				position = hit.Parent.Torso.Position,
				Parent = hit.Parent.Torso,
			}
			local BodGy = Create("BodyGyro") {
				maxTorque = Vector3.new(4e+005, 4e+005, 4e+005) * math.huge ,
				P = 20e+003,
				Parent = hit.Parent.Torso,
				cframe = hit.Parent.Torso.CFrame,
			}
			hit.Parent.Torso.Anchored = true
			coroutine.resume(coroutine.create(function(Part) 
				swait(1.5)
				Part.Anchored = false
			end), hit.Parent.Torso)
			game:GetService("Debris"):AddItem(BodPos, 3)
			game:GetService("Debris"):AddItem(BodGy, 3)
		end
		local debounce = Create("BoolValue"){
			Name = "DebounceHit",
			Parent = hit.Parent,
			Value = true,
		}
		game:GetService("Debris"):AddItem(debounce, Delay)
		c = Create("ObjectValue"){
			Name = "creator",
			Value = Player,
			Parent = h,
		}
		game:GetService("Debris"):AddItem(c, .5)
	end
end
-------------------------------------------------------
--End Damage Function--
-------------------------------------------------------

-------------------------------------------------------
--Start Damage Function Customization--
-------------------------------------------------------
function ShowDamage(Pos, Text, Time, Color)
	local Rate = (1 / 30)
	local Pos = (Pos or Vector3.new(0, 0, 0))
	local Text = (Text or "")
	local Time = (Time or 2)
	local Color = (Color or Color3.new(1, 0, 1))
	local EffectPart = CFuncs.Part.Create(workspace, "SmoothPlastic", 0, 1, BrickColor.new(Color), "Effect", Vector3.new(0, 0, 0))
	EffectPart.Anchored = true
	local BillboardGui = Create("BillboardGui"){
		Size = UDim2.new(3, 0, 3, 0),
		Adornee = EffectPart,
		Parent = EffectPart,
	}
	local TextLabel = Create("TextLabel"){
		BackgroundTransparency = 1,
		Size = UDim2.new(1, 0, 1, 0),
		Text = Text,
		Font = "Bodoni",
		TextColor3 = Color,
		TextScaled = true,
		TextStrokeColor3 = Color3.fromRGB(0,0,0),
		Parent = BillboardGui,
	}
	game.Debris:AddItem(EffectPart, (Time))
	EffectPart.Parent = game:GetService("Workspace")
	delay(0, function()
		local Frames = (Time / Rate)
		for Frame = 1, Frames do
			wait(Rate)
			local Percent = (Frame / Frames)
			EffectPart.CFrame = CFrame.new(Pos) + Vector3.new(0, Percent, 0)
			TextLabel.TextTransparency = Percent
		end
		if EffectPart and EffectPart.Parent then
			EffectPart:Destroy()
		end
	end)
end
-------------------------------------------------------
--End Damage Function Customization--
-------------------------------------------------------

function MagniDamage(Part, magni, mindam, maxdam, knock, Type)
  for _, c in pairs(workspace:children()) do
    local hum = c:findFirstChild("Humanoid")
    if hum ~= nil then
      local head = c:findFirstChild("Head")
      if head ~= nil then
        local targ = head.Position - Part.Position
        local mag = targ.magnitude
        if magni >= mag and c.Name ~= plr.Name then
          Damage(head, head, mindam, maxdam, knock, Type, root, 0.1, "http://www.roblox.com/asset/?id=0", 1.2)
        end
      end
    end
  end
end


CFuncs = {
	Part = {
		Create = function(Parent, Material, Reflectance, Transparency, BColor, Name, Size)
			local Part = Create("Part")({
				Parent = Parent,
				Reflectance = Reflectance,
				Transparency = Transparency,
				CanCollide = false,
				Locked = true,
				BrickColor = BrickColor.new(tostring(BColor)),
				Name = Name,
				Size = Size,
				Material = Material
			})
			RemoveOutlines(Part)
			return Part
		end
	},
	Mesh = {
		Create = function(Mesh, Part, MeshType, MeshId, OffSet, Scale)
			local Msh = Create(Mesh)({
				Parent = Part,
				Offset = OffSet,
				Scale = Scale
			})
			if Mesh == "SpecialMesh" then
				Msh.MeshType = MeshType
				Msh.MeshId = MeshId
			end
			return Msh
		end
	},
	Mesh = {
		Create = function(Mesh, Part, MeshType, MeshId, OffSet, Scale)
			local Msh = Create(Mesh)({
				Parent = Part,
				Offset = OffSet,
				Scale = Scale
			})
			if Mesh == "SpecialMesh" then
				Msh.MeshType = MeshType
				Msh.MeshId = MeshId
			end
			return Msh
		end
	},
	Weld = {
		Create = function(Parent, Part0, Part1, C0, C1)
			local Weld = Create("Weld")({
				Parent = Parent,
				Part0 = Part0,
				Part1 = Part1,
				C0 = C0,
				C1 = C1
			})
			return Weld
		end
	},
	Sound = {
		Create = function(id, par, vol, pit)
			coroutine.resume(coroutine.create(function()
				local S = Create("Sound")({
					Volume = vol,
					Pitch = pit or 1,
					SoundId = id,
					Parent = par or workspace
				})
				wait()
				S:play()
				game:GetService("Debris"):AddItem(S, 6)
			end))
		end
	},
	ParticleEmitter = {
		Create = function(Parent, Color1, Color2, LightEmission, Size, Texture, Transparency, ZOffset, Accel, Drag, LockedToPart, VelocityInheritance, EmissionDirection, Enabled, LifeTime, Rate, Rotation, RotSpeed, Speed, VelocitySpread)
			local fp = Create("ParticleEmitter")({
				Parent = Parent,
				Color = ColorSequence.new(Color1, Color2),
				LightEmission = LightEmission,
				Size = Size,
				Texture = Texture,
				Transparency = Transparency,
				ZOffset = ZOffset,
				Acceleration = Accel,
				Drag = Drag,
				LockedToPart = LockedToPart,
				VelocityInheritance = VelocityInheritance,
				EmissionDirection = EmissionDirection,
				Enabled = Enabled,
				Lifetime = LifeTime,
				Rate = Rate,
				Rotation = Rotation,
				RotSpeed = RotSpeed,
				Speed = Speed,
				VelocitySpread = VelocitySpread
			})
			return fp
		end
	}
}
function RemoveOutlines(part)
	part.TopSurface, part.BottomSurface, part.LeftSurface, part.RightSurface, part.FrontSurface, part.BackSurface = 10, 10, 10, 10, 10, 10
end
function CreatePart(FormFactor, Parent, Material, Reflectance, Transparency, BColor, Name, Size)
	local Part = Create("Part")({
		formFactor = FormFactor,
		Parent = Parent,
		Reflectance = Reflectance,
		Transparency = Transparency,
		CanCollide = false,
		Locked = true,
		BrickColor = BrickColor.new(tostring(BColor)),
		Name = Name,
		Size = Size,
		Material = Material
	})
	RemoveOutlines(Part)
	return Part
end
function CreateMesh(Mesh, Part, MeshType, MeshId, OffSet, Scale)
	local Msh = Create(Mesh)({
		Parent = Part,
		Offset = OffSet,
		Scale = Scale
	})
	if Mesh == "SpecialMesh" then
		Msh.MeshType = MeshType
		Msh.MeshId = MeshId
	end
	return Msh
end
function CreateWeld(Parent, Part0, Part1, C0, C1)
	local Weld = Create("Weld")({
		Parent = Parent,
		Part0 = Part0,
		Part1 = Part1,
		C0 = C0,
		C1 = C1
	})
	return Weld
end


-------------------------------------------------------
--Start Effect Function--
-------------------------------------------------------
EffectModel = Instance.new("Model", char)
Effects = {
  Block = {
    Create = function(brickcolor, cframe, x1, y1, z1, x3, y3, z3, delay, Type)
      local prt = CFuncs.Part.Create(EffectModel, "SmoothPlastic", 0, 0, brickcolor, "Effect", Vector3.new())
      prt.Anchored = true
      prt.CFrame = cframe
      local msh = CFuncs.Mesh.Create("BlockMesh", prt, "", "", Vector3.new(0, 0, 0), Vector3.new(x1, y1, z1))
      game:GetService("Debris"):AddItem(prt, 10)
      if Type == 1 or Type == nil then
        table.insert(Effects, {
          prt,
          "Block1",
          delay,
          x3,
          y3,
          z3,
          msh
        })
      elseif Type == 2 then
        table.insert(Effects, {
          prt,
          "Block2",
          delay,
          x3,
          y3,
          z3,
          msh
        })
      else
        table.insert(Effects, {
          prt,
          "Block3",
          delay,
          x3,
          y3,
          z3,
          msh
        })
      end
    end
  },
  Sphere = {
    Create = function(brickcolor, cframe, x1, y1, z1, x3, y3, z3, delay)
      local prt = CFuncs.Part.Create(EffectModel, "Neon", 0, 0, brickcolor, "Effect", Vector3.new())
      prt.Anchored = true
      prt.CFrame = cframe
      local msh = CFuncs.Mesh.Create("SpecialMesh", prt, "Sphere", "", Vector3.new(0, 0, 0), Vector3.new(x1, y1, z1))
      game:GetService("Debris"):AddItem(prt, 10)
      table.insert(Effects, {
        prt,
        "Cylinder",
        delay,
        x3,
        y3,
        z3,
        msh
      })
    end
  },
  Cylinder = {
    Create = function(brickcolor, cframe, x1, y1, z1, x3, y3, z3, delay)
      local prt = CFuncs.Part.Create(EffectModel, "SmoothPlastic", 0, 0, brickcolor, "Effect", Vector3.new())
      prt.Anchored = true
      prt.CFrame = cframe
      local msh = CFuncs.Mesh.Create("CylinderMesh", prt, "", "", Vector3.new(0, 0, 0), Vector3.new(x1, y1, z1))
      game:GetService("Debris"):AddItem(prt, 10)
      table.insert(Effects, {
        prt,
        "Cylinder",
        delay,
        x3,
        y3,
        z3,
        msh
      })
    end
  },
  Wave = {
    Create = function(brickcolor, cframe, x1, y1, z1, x3, y3, z3, delay)
      local prt = CFuncs.Part.Create(EffectModel, "Neon", 0, 0, brickcolor, "Effect", Vector3.new())
      prt.Anchored = true
      prt.CFrame = cframe
      local msh = CFuncs.Mesh.Create("SpecialMesh", prt, "FileMesh", "rbxassetid://20329976", Vector3.new(0, 0, 0), Vector3.new(x1 / 60, y1 / 60, z1 / 60))
      game:GetService("Debris"):AddItem(prt, 10)
      table.insert(Effects, {
        prt,
        "Cylinder",
        delay,
        x3 / 60,
        y3 / 60,
        z3 / 60,
        msh
      })
    end
  },
  Ring = {
    Create = function(brickcolor, cframe, x1, y1, z1, x3, y3, z3, delay)
      local prt = CFuncs.Part.Create(EffectModel, "SmoothPlastic", 0, 0, brickcolor, "Effect", Vector3.new())
      prt.Anchored = true
      prt.CFrame = cframe
      local msh = CFuncs.Mesh.Create("SpecialMesh", prt, "FileMesh", "rbxassetid://3270017", Vector3.new(0, 0, 0), Vector3.new(x1, y1, z1))
      game:GetService("Debris"):AddItem(prt, 10)
      table.insert(Effects, {
        prt,
        "Cylinder",
        delay,
        x3,
        y3,
        z3,
        msh
      })
    end
  },
  Break = {
    Create = function(brickcolor, cframe, x1, y1, z1)
      local prt = CFuncs.Part.Create(EffectModel, "Neon", 0, 0, brickcolor, "Effect", Vector3.new(0.5, 0.5, 0.5))
      prt.Anchored = true
      prt.CFrame = cframe * CFrame.fromEulerAnglesXYZ(math.random(-50, 50), math.random(-50, 50), math.random(-50, 50))
      local msh = CFuncs.Mesh.Create("SpecialMesh", prt, "Sphere", "", Vector3.new(0, 0, 0), Vector3.new(x1, y1, z1))
      local num = math.random(10, 50) / 1000
      game:GetService("Debris"):AddItem(prt, 10)
      table.insert(Effects, {
        prt,
        "Shatter",
        num,
        prt.CFrame,
        math.random() - math.random(),
        0,
        math.random(50, 100) / 100
      })
    end
  },
Spiral = {
    Create = function(brickcolor, cframe, x1, y1, z1, x3, y3, z3, delay)
      local prt = CFuncs.Part.Create(EffectModel, "SmoothPlastic", 0, 0, brickcolor, "Effect", Vector3.new())
      prt.Anchored = true
      prt.CFrame = cframe
      local msh = CFuncs.Mesh.Create("SpecialMesh", prt, "FileMesh", "rbxassetid://1051557", Vector3.new(0, 0, 0), Vector3.new(x1, y1, z1))
      game:GetService("Debris"):AddItem(prt, 10)
      table.insert(Effects, {
        prt,
        "Cylinder",
        delay,
        x3,
        y3,
        z3,
        msh
      })
    end
  },
Push = {
    Create = function(brickcolor, cframe, x1, y1, z1, x3, y3, z3, delay)
      local prt = CFuncs.Part.Create(EffectModel, "SmoothPlastic", 0, 0, brickcolor, "Effect", Vector3.new())
      prt.Anchored = true
      prt.CFrame = cframe
      local msh = CFuncs.Mesh.Create("SpecialMesh", prt, "FileMesh", "rbxassetid://437347603", Vector3.new(0, 0, 0), Vector3.new(x1, y1, z1))
      game:GetService("Debris"):AddItem(prt, 10)
      table.insert(Effects, {
        prt,
        "Cylinder",
        delay,
        x3,
        y3,
        z3,
        msh
      })
    end
  }
}
function part(formfactor ,parent, reflectance, transparency, brickcolor, name, size)
	local fp = IT("Part")
	fp.formFactor = formfactor 
	fp.Parent = parent
	fp.Reflectance = reflectance
	fp.Transparency = transparency
	fp.CanCollide = false 
	fp.Locked = true
	fp.BrickColor = brickcolor
	fp.Name = name
	fp.Size = size
	fp.Position = tors.Position 
	RemoveOutlines(fp)
	fp.Material = "SmoothPlastic"
	fp:BreakJoints()
	return fp 
end 
 
function mesh(Mesh,part,meshtype,meshid,offset,scale)
	local mesh = IT(Mesh) 
	mesh.Parent = part
	if Mesh == "SpecialMesh" then
		mesh.MeshType = meshtype
	if meshid ~= "nil" then
		mesh.MeshId = "http://www.roblox.com/asset/?id="..meshid
		end
	end
	mesh.Offset = offset
	mesh.Scale = scale
	return mesh
end

function Magic(bonuspeed, type, pos, scale, value, color, MType)
	local type = type
	local rng = Instance.new("Part", char)
	rng.Anchored = true
	rng.BrickColor = color
	rng.CanCollide = false
	rng.FormFactor = 3
	rng.Name = "Ring"
	rng.Material = "Neon"
	rng.Size = Vector3.new(1, 1, 1)
	rng.Transparency = 0
	rng.TopSurface = 0
	rng.BottomSurface = 0
	rng.CFrame = pos
	local rngm = Instance.new("SpecialMesh", rng)
	rngm.MeshType = MType
	rngm.Scale = scale
	local scaler2 = 1
	if type == "Add" then
		scaler2 = 1 * value
	elseif type == "Divide" then
		scaler2 = 1 / value
	end
	coroutine.resume(coroutine.create(function()
		for i = 0, 10 / bonuspeed, 0.1 do
			swait()
			if type == "Add" then
				scaler2 = scaler2 - 0.01 * value / bonuspeed
			elseif type == "Divide" then
				scaler2 = scaler2 - 0.01 / value * bonuspeed
			end
			rng.Transparency = rng.Transparency + 0.01 * bonuspeed
			rngm.Scale = rngm.Scale + Vector3.new(scaler2 * bonuspeed, scaler2 * bonuspeed, scaler2 * bonuspeed)
		end
		rng:Destroy()
	end))
end

function Eviscerate(dude)
	if dude.Name ~= char then
		local bgf = IT("BodyGyro", dude.Head)
		bgf.CFrame = bgf.CFrame * CFrame.fromEulerAnglesXYZ(Rad(-90), 0, 0)
		local val = IT("BoolValue", dude)
		val.Name = "IsHit"
		local ds = coroutine.wrap(function()
			dude:WaitForChild("Head"):BreakJoints()
			wait(0.5)
			target = nil
			coroutine.resume(coroutine.create(function()
				for i, v in pairs(dude:GetChildren()) do
					if v:IsA("Accessory") then
						v:Destroy()
					end
					if v:IsA("Humanoid") then
						v:Destroy()
					end
					if v:IsA("CharacterMesh") then
						v:Destroy()
					end
					if v:IsA("Model") then
						v:Destroy()
					end
					if v:IsA("Part") or v:IsA("MeshPart") then
						for x, o in pairs(v:GetChildren()) do
							if o:IsA("Decal") then
								o:Destroy()
							end
						end
						coroutine.resume(coroutine.create(function()
							v.Material = "Neon"
							v.CanCollide = false
							local PartEmmit1 = IT("ParticleEmitter", v)
							PartEmmit1.LightEmission = 1
							PartEmmit1.Texture = "rbxassetid://284205403"
							PartEmmit1.Color = ColorSequence.new(maincolor.Color)
							PartEmmit1.Rate = 150
							PartEmmit1.Lifetime = NumberRange.new(1)
							PartEmmit1.Size = NumberSequence.new({
								NumberSequenceKeypoint.new(0, 0.75, 0),
								NumberSequenceKeypoint.new(1, 0, 0)
							})
							PartEmmit1.Transparency = NumberSequence.new({
								NumberSequenceKeypoint.new(0, 0, 0),
								NumberSequenceKeypoint.new(1, 1, 0)
							})
							PartEmmit1.Speed = NumberRange.new(0, 0)
							PartEmmit1.VelocitySpread = 30000
							PartEmmit1.Rotation = NumberRange.new(-500, 500)
							PartEmmit1.RotSpeed = NumberRange.new(-500, 500)
							local BodPoss = IT("BodyPosition", v)
							BodPoss.P = 3000
							BodPoss.D = 1000
							BodPoss.maxForce = Vector3.new(50000000000, 50000000000, 50000000000)
							BodPoss.position = v.Position + Vector3.new(Mrandom(-15, 15), Mrandom(-15, 15), Mrandom(-15, 15))
							v.Color = maincolor.Color
							coroutine.resume(coroutine.create(function()
								for i = 0, 49 do
									swait(1)
									v.Transparency = v.Transparency + 0.08
								end
								wait(0.5)
								PartEmmit1.Enabled = false
								wait(3)
								v:Destroy()
								dude:Destroy()
							end))
						end))
					end
				end
			end))
		end)
		ds()
	end
end

function FindNearestHead(Position, Distance, SinglePlayer)
	if SinglePlayer then
		return Distance > (SinglePlayer.Torso.CFrame.p - Position).magnitude
	end
	local List = {}
	for i, v in pairs(workspace:GetChildren()) do
		if v:IsA("Model") and v:findFirstChild("Head") and v ~= char and Distance >= (v.Head.Position - Position).magnitude then
			table.insert(List, v)
		end
	end
	return List
end

function Aura(bonuspeed, FastSpeed, type, pos, x1, y1, z1, value, color, outerpos, MType)
	local type = type
	local rng = Instance.new("Part", char)
	rng.Anchored = true
	rng.BrickColor = color
	rng.CanCollide = false
	rng.FormFactor = 3
	rng.Name = "Ring"
	rng.Material = "Neon"
	rng.Size = Vector3.new(1, 1, 1)
	rng.Transparency = 0
	rng.TopSurface = 0
	rng.BottomSurface = 0
	rng.CFrame = pos
	rng.CFrame = rng.CFrame + rng.CFrame.lookVector * outerpos
	local rngm = Instance.new("SpecialMesh", rng)
	rngm.MeshType = MType
	rngm.Scale = Vector3.new(x1, y1, z1)
	local scaler2 = 1
	local speeder = FastSpeed
	if type == "Add" then
		scaler2 = 1 * value
	elseif type == "Divide" then
		scaler2 = 1 / value
	end
	coroutine.resume(coroutine.create(function()
		for i = 0, 10 / bonuspeed, 0.1 do
			swait()
			if type == "Add" then
				scaler2 = scaler2 - 0.01 * value / bonuspeed
			elseif type == "Divide" then
				scaler2 = scaler2 - 0.01 / value * bonuspeed
			end
			speeder = speeder - 0.01 * FastSpeed * bonuspeed
			rng.CFrame = rng.CFrame + rng.CFrame.lookVector * speeder * bonuspeed
			rng.Transparency = rng.Transparency + 0.01 * bonuspeed
			rngm.Scale = rngm.Scale + Vector3.new(scaler2 * bonuspeed, scaler2 * bonuspeed, 0)
		end
		rng:Destroy()
	end))
end

function SoulSteal(dude)
if dude.Name ~= char then
local bgf = IT("BodyGyro", dude.Head)
bgf.CFrame = bgf.CFrame * CFrame.fromEulerAnglesXYZ(Rad(-90), 0, 0)
local val = IT("BoolValue", dude)
val.Name = "IsHit"
local torso = (dude:FindFirstChild'Head' or dude:FindFirstChild'Torso' or dude:FindFirstChild'UpperTorso' or dude:FindFirstChild'LowerTorso' or dude:FindFirstChild'HumanoidRootPart')
local soulst = coroutine.wrap(function()
local soul = Instance.new("Part",dude)
soul.Size = Vector3.new(1,1,1)
soul.CanCollide = false
soul.Anchored = false
soul.Position = torso.Position
soul.Transparency = 1
local PartEmmit1 = IT("ParticleEmitter", soul)
PartEmmit1.LightEmission = 1
PartEmmit1.Texture = "rbxassetid://569507414"
PartEmmit1.Color = ColorSequence.new(maincolor.Color)
PartEmmit1.Rate = 250
PartEmmit1.Lifetime = NumberRange.new(1.6)
PartEmmit1.Size = NumberSequence.new({
	NumberSequenceKeypoint.new(0, 1, 0),
	NumberSequenceKeypoint.new(1, 0, 0)
})
PartEmmit1.Transparency = NumberSequence.new({
	NumberSequenceKeypoint.new(0, 0, 0),
	NumberSequenceKeypoint.new(1, 1, 0)
})
PartEmmit1.Speed = NumberRange.new(0, 0)
PartEmmit1.VelocitySpread = 30000
PartEmmit1.Rotation = NumberRange.new(-360, 360)
PartEmmit1.RotSpeed = NumberRange.new(-360, 360)
local BodPoss = IT("BodyPosition", soul)
BodPoss.P = 3000
BodPoss.D = 1000
BodPoss.maxForce = Vector3.new(50000000000, 50000000000, 50000000000)
BodPoss.position = torso.Position + Vector3.new(Mrandom(-15, 15), Mrandom(-15, 15), Mrandom(-15, 15))
wait(1.6)
soul.Touched:connect(function(hit)
	if hit.Parent == char then
	soul:Destroy()
	end
end)
wait(1.2)
while soul do
	swait()
	PartEmmit1.Color = ColorSequence.new(maincolor.Color)
	BodPoss.Position = tors.Position
end
end)
	soulst()
	end
end
function FaceMouse()
local	Cam = workspace.CurrentCamera
	return {
		CFrame.new(char.Torso.Position, Vector3.new(mouse.Hit.p.x, char.Torso.Position.y, mouse.Hit.p.z)),
		Vector3.new(mouse.Hit.p.x, mouse.Hit.p.y, mouse.Hit.p.z)
	}
end
function WACKYEFFECT(Table)
	local TYPE = (Table.EffectType or "Sphere")
	local SIZE = (Table.Size or Vector3.new(1,1,1))
	local ENDSIZE = (Table.Size2 or Vector3.new(0,0,0))
	local TRANSPARENCY = (Table.Transparency or 0)
	local ENDTRANSPARENCY = (Table.Transparency2 or 1)
	local CFRAME = (Table.CFrame or tors.CFrame)
	local MOVEDIRECTION = (Table.MoveToPos or nil)
	local ROTATION1 = (Table.RotationX or 0)
	local ROTATION2 = (Table.RotationY or 0)
	local ROTATION3 = (Table.RotationZ or 0)
	local MATERIAL = (Table.Material or "Neon")
	local COLOR = (Table.Color or Color3.new(1,1,1))
	local TIME = (Table.Time or 45)
	local SOUNDID = (Table.SoundID or nil)
	local SOUNDPITCH = (Table.SoundPitch or nil)
	local SOUNDVOLUME = (Table.SoundVolume or nil)
	coroutine.resume(coroutine.create(function()
		local PLAYSSOUND = false
		local SOUND = nil
		local EFFECT = CreatePart(3, Effects, MATERIAL, 0, TRANSPARENCY, BrickC("Pearl"), "Effect", Vector3.new(1,1,1), true)
		if SOUNDID ~= nil and SOUNDPITCH ~= nil and SOUNDVOLUME ~= nil then
			PLAYSSOUND = true
			SOUND = Cso(SOUNDID, EFFECT, SOUNDVOLUME, SOUNDPITCH, false)
		end
		EFFECT.Color = COLOR
		local MSH = nil
		if TYPE == "Sphere" then
			MSH = CreateMesh("SpecialMesh", EFFECT, "Sphere", "", "", SIZE, Vector3.new(0,0,0))
		elseif TYPE == "Block" or TYPE == "Box" then
			MSH = IT("BlockMesh",EFFECT)
			MSH.Scale = SIZE
		elseif TYPE == "Cylinder" then
			MSH = IT("CylinderMesh",EFFECT)
			MSH.Scale = SIZE
		elseif TYPE == "Wave" then
			MSH = CreateMesh("SpecialMesh", EFFECT, "FileMesh", "20329976", "", SIZE, Vector3.new(0,0,-SIZE.X/8))
		elseif TYPE == "Ring" then
			MSH = CreateMesh("SpecialMesh", EFFECT, "FileMesh", "559831844", "", Vector3.new(SIZE.X,SIZE.X,0.1), Vector3.new(0,0,0))
		elseif TYPE == "Slash" then
			MSH = CreateMesh("SpecialMesh", EFFECT, "FileMesh", "662586858", "", Vector3.new(SIZE.X/10,0,SIZE.X/10), Vector3.new(0,0,0))
		elseif TYPE == "Round Slash" then
			MSH = CreateMesh("SpecialMesh", EFFECT, "FileMesh", "662585058", "", Vector3.new(SIZE.X/10,0,SIZE.X/10), Vector3.new(0,0,0))
		elseif TYPE == "Swirl" then
			MSH = CreateMesh("SpecialMesh", EFFECT, "FileMesh", "1051557", "", SIZE, Vector3.new(0,0,0))
		elseif TYPE == "Skull" then
			MSH = CreateMesh("SpecialMesh", EFFECT, "FileMesh", "4770583", "", SIZE, Vector3.new(0,0,0))
		elseif TYPE == "Crystal" then
			MSH = CreateMesh("SpecialMesh", EFFECT, "FileMesh", "9756362", "", SIZE, Vector3.new(0,0,0))
		elseif TYPE == "Crown" then
			MSH = CreateMesh("SpecialMesh", EFFECT, "FileMesh", "173770780", "", SIZE, Vector3.new(0,0,0))
		end
		if MSH ~= nil then
			local MOVESPEED = nil
			if MOVEDIRECTION ~= nil then
				MOVESPEED = (CFRAME.p - MOVEDIRECTION).Magnitude/TIME
			end
			local GROWTH = SIZE - ENDSIZE
			local TRANS = TRANSPARENCY - ENDTRANSPARENCY
			if TYPE == "Block" then
				EFFECT.CFrame = CFRAME*angles(Rad(Mrandom(0,360)),Rad(Mrandom(0,360)),Rad(Mrandom(0,360)))
			else
				EFFECT.CFrame = CFRAME
			end
			for LOOP = 1, TIME+1 do
				swait()
				MSH.Scale = MSH.Scale - GROWTH/TIME
				if TYPE == "Wave" then
					MSH.Offset = Vector3.new(0,0,-MSH.Scale.X/8)
				end
				EFFECT.Transparency = EFFECT.Transparency - TRANS/TIME
				if TYPE == "Block" then
					EFFECT.CFrame = CFRAME*angles(Rad(Mrandom(0,360)),Rad(Mrandom(0,360)),Rad(Mrandom(0,360)))
				else
					EFFECT.CFrame = EFFECT.CFrame*angles(Rad(ROTATION1),Rad(ROTATION2),Rad(ROTATION3))
				end
				if MOVEDIRECTION ~= nil then
					local ORI = EFFECT.Orientation
					EFFECT.CFrame = CF(EFFECT.Position,MOVEDIRECTION)*CF(0,0,-MOVESPEED)
					EFFECT.Orientation = ORI
				end
			end
			EFFECT.Transparency = 1
			if PLAYSSOUND == false then
				EFFECT:remove()
			else
				repeat swait() until SOUND.Playing == false
				EFFECT:remove()
			end
		else
			if PLAYSSOUND == false then
				EFFECT:remove()
			else
				repeat swait() until SOUND.Playing == false
				EFFECT:remove()
			end
		end
	end))
end

-------------------------------------------------------
--End Effect Function--
-------------------------------------------------------
function Cso(ID, PARENT, VOLUME, PITCH)
	local NSound = nil
	coroutine.resume(coroutine.create(function()
		NSound = IT("Sound", PARENT)
		NSound.Volume = VOLUME
		NSound.Pitch = PITCH
		NSound.SoundId = "http://www.roblox.com/asset/?id="..ID
		swait()
		NSound:play()
		game:GetService("Debris"):AddItem(NSound, 10)
	end))
	return NSound
end
function CameraEnshaking(Length, Intensity)
	coroutine.resume(coroutine.create(function()
		local intensity = 1 * Intensity
		local rotM = 0.01 * Intensity
		for i = 0, Length, 0.1 do
			swait()
			intensity = intensity - 0.05 * Intensity / Length
			rotM = rotM - 5.0E-4 * Intensity / Length
			hum.CameraOffset = Vector3.new(Rad(Mrandom(-intensity, intensity)), Rad(Mrandom(-intensity, intensity)), Rad(Mrandom(-intensity, intensity)))
			cam.CFrame = cam.CFrame * CF(Rad(Mrandom(-intensity, intensity)), Rad(Mrandom(-intensity, intensity)), Rad(Mrandom(-intensity, intensity))) * Euler(Rad(Mrandom(-intensity, intensity)) * rotM, Rad(Mrandom(-intensity, intensity)) * rotM, Rad(Mrandom(-intensity, intensity)) * rotM)
		end
		hum.CameraOffset = Vector3.new(0, 0, 0)
	end))
end
NewInstance = function(instance,parent,properties)
	local inst = Instance.new(instance)
	inst.Parent = parent
	if(properties)then
		for i,v in next, properties do
			pcall(function() inst[i] = v end)
		end
	end
	return inst;
end
function CreateWeldOrSnapOrMotor(TYPE, PARENT, PART0, PART1, C0, C1)
	local NEWWELD = IT(TYPE)
	NEWWELD.Part0 = PART0
	NEWWELD.Part1 = PART1
	NEWWELD.C0 = C0
	NEWWELD.C1 = C1
	NEWWELD.Parent = PARENT
	return NEWWELD
end
local DECAL = IT("Decal")
function MagicRing(PART,CFRAME)
	local RING = CreatePart(3, EffectModel, "Granite", 0, 1, "Maroon", "MagicRing", Vector3.new(0,0,0),false)
	local WELD = CreateWeldOrSnapOrMotor("Weld", PART, PART, RING, CFRAME, CF(0, 0, 0))
	local MESH = IT("BlockMesh",RING)
	local BOTTOMTEXTURE = DECAL:Clone()
	BOTTOMTEXTURE.Parent = RING
	BOTTOMTEXTURE.Face = "Bottom"
	BOTTOMTEXTURE.Name = "BottomTexture"
	local TOPTEXTURE = DECAL:Clone()
	TOPTEXTURE.Parent = RING
	TOPTEXTURE.Face = "Top"
	TOPTEXTURE.Name = "TopTexture"
	local LIGHT = IT("PointLight",RING)
	BOTTOMTEXTURE.Texture = "http://www.roblox.com/asset/?id=1208118228"
	TOPTEXTURE.Texture = "http://www.roblox.com/asset/?id=1208118228"
	return RING,WELD,MESH
end
-------------------------------------------------------
--End Important Functions--
-------------------------------------------------------


-------------------------------------------------------
--Start Customization--
-------------------------------------------------------
local Player_Size = 1
if Player_Size ~= 1 then
root.Size = root.Size * Player_Size
tors.Size = tors.Size * Player_Size
hed.Size = hed.Size * Player_Size
ra.Size = ra.Size * Player_Size
la.Size = la.Size * Player_Size
rl.Size = rl.Size * Player_Size
ll.Size = ll.Size * Player_Size
----------------------------------------------------------------------------------
rootj.Parent = root
neck.Parent = tors
RW.Parent = tors
LW.Parent = tors
RH.Parent = tors
LH.Parent = tors
----------------------------------------------------------------------------------
rootj.C0 = RootCF * CF(0 * Player_Size, 0 * Player_Size, 0 * Player_Size) * angles(Rad(0), Rad(0), Rad(0))
rootj.C1 = RootCF * CF(0 * Player_Size, 0 * Player_Size, 0 * Player_Size) * angles(Rad(0), Rad(0), Rad(0))
neck.C0 = necko * CF(0 * Player_Size, 0 * Player_Size, 0 + ((1 * Player_Size) - 1)) * angles(Rad(0), Rad(0), Rad(0))
neck.C1 = CF(0 * Player_Size, -0.5 * Player_Size, 0 * Player_Size) * angles(Rad(-90), Rad(0), Rad(180))
RW.C0 = CF(1.5 * Player_Size, 0.5 * Player_Size, 0 * Player_Size) * angles(Rad(0), Rad(0), Rad(0)) --* RIGHTSHOULDERC0
LW.C0 = CF(-1.5 * Player_Size, 0.5 * Player_Size, 0 * Player_Size) * angles(Rad(0), Rad(0), Rad(0)) --* LEFTSHOULDERC0
----------------------------------------------------------------------------------
RH.C0 = CF(1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * angles(Rad(0), Rad(90), Rad(0)) * angles(Rad(0), Rad(0), Rad(0))
LH.C0 = CF(-1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * angles(Rad(0), Rad(-90), Rad(0)) * angles(Rad(0), Rad(0), Rad(0))
RH.C1 = CF(0.5 * Player_Size, 1 * Player_Size, 0 * Player_Size) * angles(Rad(0), Rad(90), Rad(0)) * angles(Rad(0), Rad(0), Rad(0))
LH.C1 = CF(-0.5 * Player_Size, 1 * Player_Size, 0 * Player_Size) * angles(Rad(0), Rad(-90), Rad(0)) * angles(Rad(0), Rad(0), Rad(0))
--hat.Parent = Character
end
----------------------------------------------------------------------------------
local SONG = 463063479
local SONG2 = 0
local Music = Instance.new("Sound",tors)
Music.Volume = 2.5
Music.Looped = true
Music.Pitch = 1 --Pitcher
----------------------------------------------------------------------------------
local equipped = false
local idle = 0
local change = 1
local val = 0
local toim = 0
local idleanim = 0.4
local sine = 0
local Sit = 1
local WasAir = false
local InAir = false
local LandTick = 0
local movelegs = false
local HatOn = false
----------------------------------------------------------------------------------
hum.WalkSpeed = 16
hum.JumpPower = 55
hum.Animator.Parent = nil
----------------------------------------------------------------------------------
BWJester = IT("Model")
BWJester.Parent = char
BWJester.Name = "BWJester"
RHe = IT("Part")
RHe.Parent = BWJester
RHe.BrickColor = BrickColor.new("Really black")
RHe.Locked = true
RHe.CanCollide = false
RHe.Transparency = 0
PMesh = IT("SpecialMesh")
RHe.formFactor =  "Symmetric"
PMesh.MeshType = "FileMesh"
PMesh.MeshId = "rbxassetid://193760002"
PMesh.TextureId = "rbxassetid://193760041"
PMesh.Scale = Vector3.new(1, 1, 1)
PMesh.Parent = RHe
local RWeld = IT("Weld")
RWeld.Parent = RHe
RWeld.Part0 = RHe
RWeld.Part1 = ra
RWeld.C0 = CF(0, -1.3, -0.4) * angles(Rad(180), Rad(0), Rad(-30))
hed.face:Remove()
hed.Transparency = 1
-------------------------------------------------------
--End Customization--
-------------------------------------------------------


-------------------------------------------------------
--Start Attacks N Stuff--
-------------------------------------------------------
function AttackTemplate()
	attack = true
	for i = 0, 2, 0.1 do
		swait()
		rootj.C0 = clerp(rootj.C0, RootCF * CF(0* Player_Size, 0* Player_Size, -0.1 + 0.1* Player_Size * Cos(sine / 20)) * angles(Rad(0), Rad(0), Rad(0)), 0.1)
		neck.C0 = clerp(neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(0 - 5 * Sin(sine / 20)), Rad(0), Rad(0)), 0.1)
		rl.Weld.C0 = clerp(rl.Weld.C0, CF(0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0), Rad(-10), Rad(0)) * angles(Rad(0), Rad(0), Rad(5)), 0.1)
		ll.Weld.C0 = clerp(ll.Weld.C0, CF(-0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0), Rad(10), Rad(0)) * angles(Rad(0), Rad(0), Rad(-5)), 0.1)
		RW.C0 = clerp(RW.C0, CF(1.5* Player_Size, 0.5 + 0.1 * Sin(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0), Rad(0 + 5 * Sin(sine / 20)), Rad(10 + 5 * Sin(sine / 20))), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.5* Player_Size, 0.5 + 0.1 * Sin(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0), Rad(0 - 5 * Sin(sine / 20)), Rad(-10 - 5 * Sin(sine / 20))), 0.1)
	end
	attack = false
end
function Fun_Times_Ahead()
	attack = true
	movelegs = true
	local Laughing = Cso("2011351501", hed, 5, 0.8)
	swait(2)
	repeat
		swait()
		rootj.C0 = clerp(rootj.C0, RootCF * CF(0* Player_Size, 0* Player_Size, -0.1 + 0.1* Player_Size * Cos(sine / 2)) * angles(Rad(-20), Rad(0), Rad(0)), 0.1)
		neck.C0 = clerp(neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(-30 - 5 * Sin(sine / 2)), Rad(0), Rad(0)), 0.1)
		rl.Weld.C0 = clerp(rl.Weld.C0, CF(0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 2)* Player_Size, 0* Player_Size) * angles(Rad(0), Rad(-10), Rad(0)) * angles(Rad(-20), Rad(0), Rad(5)), 0.1)
		ll.Weld.C0 = clerp(ll.Weld.C0, CF(-0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 2)* Player_Size, 0* Player_Size) * angles(Rad(0), Rad(10), Rad(0)) * angles(Rad(-20), Rad(0), Rad(-5)), 0.1)
		RW.C0 = clerp(RW.C0, CF(1.5 * Player_Size, 0.5 + 0.1 * Cos(sine / 2) * Player_Size, 0 * Player_Size) * angles(Rad(225), Rad(0), Rad(10 + 2.5 * Sin(sine / 20))), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.25 * Player_Size, 0.3 + 0.1 * Cos(sine / 2) * Player_Size, -0.5 * Player_Size) * angles(Rad(35), Rad(15 - 2.5 * Sin(sine / 20)), Rad(85 - 2.5 * Sin(sine / 20))), 0.1)
	until Laughing.Playing == false
	attack = false
	movelegs = false
end
function Fun_Times_Ahead_2()
	attack = true
	movelegs = true
	local Laughing = Cso("2011351501", hed, 5, 0.8)
	swait(2)
	repeat
		swait()
		rootj.C0 = clerp(rootj.C0, RootCF * CF(0* Player_Size, 0* Player_Size, -0.1 + 0.1* Player_Size * Cos(sine / 2)) * angles(Rad(-20), Rad(0), Rad(0)), 0.1)
		neck.C0 = clerp(neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(-30 - 5 * Sin(sine / 2)), Rad(0), Rad(0)), 0.1)
		rl.Weld.C0 = clerp(rl.Weld.C0, CF(0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 2)* Player_Size, 0* Player_Size) * angles(Rad(0), Rad(-10), Rad(0)) * angles(Rad(-20), Rad(0), Rad(5)), 0.1)
		ll.Weld.C0 = clerp(ll.Weld.C0, CF(-0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 2)* Player_Size, 0* Player_Size) * angles(Rad(0), Rad(10), Rad(0)) * angles(Rad(-20), Rad(0), Rad(-5)), 0.1)
		RW.C0 = clerp(RW.C0, CF(1.25 * Player_Size, 0.4 + 0.1 * Sin(sine / 2) * Player_Size, -0.5 * Player_Size) * angles(Rad(35), Rad(-15 + 2.5 * Sin(sine / 2)), Rad(-85 + 2.5 * Sin(sine / 2))), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.25 * Player_Size, 0.3 + 0.1 * Cos(sine / 2) * Player_Size, -0.5 * Player_Size) * angles(Rad(35), Rad(15 - 2.5 * Sin(sine / 2)), Rad(85 - 2.5 * Sin(sine / 2))), 0.1)
	until Laughing.Playing == false
	attack = false
	movelegs = false
end
function Jester_Dash()
	attack = true
	for i = 0, 20, 0.1 do
		swait()
		root.Velocity = root.CFrame.lookVector * 100
		Effects.Block.Create(BrickC("Really black"), la.CFrame * CF(0, -1, 0), 2, 2, 2, 12, 12, 12, 0.05)
		rootj.C0 = clerp(rootj.C0, RootCF * CF(0, 0, 2 + 0.6 * Cos(sine / 20)) * angles(Rad(90), Rad(0), Rad(0 - 255.45 * i)), 0.15)
		tors.Neck.C0 = clerp(tors.Neck.C0, necko * angles(Rad(20 - 2.5 * Sin(sine / 30)), Rad(20), Rad(0)), 0.1)
		rl.Weld.C0 = clerp(rl.Weld.C0, CF(0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0 + 3 * Cos(sine / 20)), Rad(-10), Rad(0)) * angles(Rad(0), Rad(0), Rad(5)), 0.1)
		ll.Weld.C0 = clerp(ll.Weld.C0, CF(-0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0 + 3 * Cos(sine / 20)), Rad(10), Rad(0)) * angles(Rad(0), Rad(0), Rad(-5)), 0.1)
		RW.C0 = clerp(RW.C0, CF(1.5 * Player_Size, 0.5 + 0.1 * Cos(sine / 20) * Player_Size, 0 * Player_Size) * angles(Rad(156), Rad(0), Rad(10 + 2.5 * Sin(sine / 20))), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.5, 0.5 + 0.02 * Sin(sine / 20), 0) * angles(Rad(0), Rad(0), Rad(-90)), 0.1)
		MagniDamage(tors, 12, 40, 60, 10, "Normal")
	end
	attack = false
end
function Sie_alle_sterben()
	attack = true
	--movelegs = true
	local orb = Instance.new("Part", char)
	orb.Anchored = true
	orb.BrickColor = BrickC("Really black")
	orb.CanCollide = false
	orb.FormFactor = 3
	orb.Name = "Ring"
	orb.Material = "Neon"
	orb.Size = Vector3.new(1, 1, 1)
	orb.Transparency = 0
	orb.TopSurface = 0
	orb.BottomSurface = 0
	local orbm = Instance.new("SpecialMesh", orb)
	orbm.MeshType = "Sphere"
	orbm.Name = "SizeMesh"
	orbm.Scale = Vector3.new(0, 0, 0)
	local scaled = 0.1
	local posid = 0
	local RoaringLaugh = Cso("2011355991", char, 5, 0.8)
	swait(2)
	for i = 0, 30, 0.1 do
		swait()
		scaled = scaled + 0.006
		posid = posid - scaled
		orb.CFrame = la.CFrame * CF(0, -0.1 + posid / 1.05, 0)
		orbm.Scale = orbm.Scale + Vector3.new(scaled, scaled, scaled)
		--Magic(5, "Add", root.CFrame * CFrame.new(0, -2.9, 0), Vector3.new(0, 0, 0), 1, maincolor, "Sphere")
		rootj.C0 = clerp(rootj.C0, RootCF * CF(0* Player_Size, 0* Player_Size, -0.1 + 1 * i) * angles(Rad(-5), Rad(-30), Rad(0)), 0.1)
		neck.C0 = clerp(neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(0 - 5 * Sin(sine / 20)), Rad(0), Rad(0)), 0.1)
		rl.Weld.C0 = clerp(rl.Weld.C0, CF(0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0), Rad(-10), Rad(0)) * angles(Rad(-5), Rad(0), Rad(35)), 0.1)
		ll.Weld.C0 = clerp(ll.Weld.C0, CF(-0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0), Rad(10), Rad(0)) * angles(Rad(-5), Rad(0), Rad(-15)), 0.1)
		RW.C0 = clerp(RW.C0, CF(1.5 * Player_Size, 0.5 + 0.1 * Cos(sine / 20) * Player_Size, 0 * Player_Size) * angles(Rad(0), Rad(0), Rad(35 + 2.5 * Sin(sine / 20))), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.5* Player_Size, 0.5 + 0.1 * Sin(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(180), Rad(0 - 5 * Sin(sine / 20)), Rad(-20)), 0.1)
	end
	for i = 0, 10, 0.1 do
		swait()
		rootj.C0 = clerp(rootj.C0, RootCF * CF(0* Player_Size, 0* Player_Size, 30) * angles(Rad(-35), Rad(-30), Rad(0)), 0.1)
		neck.C0 = clerp(neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(0 - 5 * Sin(sine / 20)), Rad(0), Rad(0)), 0.1)
		rl.Weld.C0 = clerp(rl.Weld.C0, CF(0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0), Rad(-10), Rad(0)) * angles(Rad(-5), Rad(0), Rad(35)), 0.1)
		ll.Weld.C0 = clerp(ll.Weld.C0, CF(-0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0), Rad(10), Rad(0)) * angles(Rad(-5), Rad(0), Rad(-15)), 0.1)
		RW.C0 = clerp(RW.C0, CF(1.5 * Player_Size, 0.5 + 0.1 * Cos(sine / 20) * Player_Size, 0 * Player_Size) * angles(Rad(0), Rad(0), Rad(35 + 2.5 * Sin(sine / 20))), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.5* Player_Size, 0.5 + 0.1 * Sin(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(225), Rad(0 - 5 * Sin(sine / 20)), Rad(-20)), 0.1)
	end
	coroutine.resume(coroutine.create(function()
		orb.Anchored = false
		CFuncs.Sound.Create("rbxassetid://907528019", root, 1.85, 1)
		local a = Instance.new("Part", workspace)
		a.Name = "Direction"
		a.Anchored = true
		a.BrickColor = BrickC("Really black")
		a.Material = "Neon"
		a.Transparency = 1
		a.CanCollide = false
		local ray = Ray.new(orb.CFrame.p, (mouse.Hit.p - orb.CFrame.p).unit * 500)
		local ignore = orb
		local hit, position, normal = workspace:FindPartOnRay(ray, ignore)
		a.BottomSurface = 10
		a.TopSurface = 10
		local distance = (orb.CFrame.p - position).magnitude
		a.Size = Vector3.new(0.1, 0.1, 0.1)
		a.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, 0)
		orb.CFrame = a.CFrame
		a:Destroy()
		local bv = Instance.new("BodyVelocity")
		bv.maxForce = Vector3.new(1000000000, 1000000000, 1000000000)
		bv.velocity = orb.CFrame.lookVector * 125
		bv.Parent = orb
		local hitted = false
		game:GetService("Debris"):AddItem(orb, 15)
		swait()
		local hit = orb.Touched:connect(function(hit)
			if hitted == false then
				hitted = true
				CameraEnshaking(10, 20)
				CFuncs.Sound.Create("rbxassetid://304490261", char, 5, 0.7)
				for i, v in pairs(FindNearestHead(orb.CFrame.p, 100)) do
					if v:FindFirstChild("Head") then
						Eviscerate(v)
					end
				end
				Magic(1, "Add", orb.CFrame, Vector3.new(orbm.Scale.x, orbm.Scale.y, orbm.Scale.z), 1, BrickC("Really black"), "Sphere")
				Magic(2, "Add", orb.CFrame, Vector3.new(orbm.Scale.x, orbm.Scale.y, orbm.Scale.z), 2, maincolor, "Sphere")
				orb.Anchored = true
				orb.Transparency = 1
				wait(8)
				orb:Destroy()
			end
		end)
	end))
	for i = 0, 10, 0.1 do
		swait()
		rootj.C0 = clerp(rootj.C0, RootCF * CF(0* Player_Size, 0* Player_Size, 30) * angles(Rad(25), Rad(-30), Rad(0)), 0.1)
		neck.C0 = clerp(neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(0 - 5 * Sin(sine / 20)), Rad(0), Rad(0)), 0.1)
		rl.Weld.C0 = clerp(rl.Weld.C0, CF(0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0), Rad(-10), Rad(0)) * angles(Rad(-5), Rad(0), Rad(35)), 0.1)
		ll.Weld.C0 = clerp(ll.Weld.C0, CF(-0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0), Rad(10), Rad(0)) * angles(Rad(-5), Rad(0), Rad(-15)), 0.1)
		RW.C0 = clerp(RW.C0, CF(1.5 * Player_Size, 0.5 + 0.1 * Cos(sine / 20) * Player_Size, 0 * Player_Size) * angles(Rad(0), Rad(0), Rad(35 + 2.5 * Sin(sine / 20))), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.5* Player_Size, 0.5 + 0.1 * Sin(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(135), Rad(0 - 5 * Sin(sine / 20)), Rad(-20)), 0.1)
	end
	attack = false
	movelegs = false
end
function Apocalypse()
	attack = true
	local bodyVelocity = Create("BodyVelocity")({
      velocity = Vector3.new(0, 100, 0) + root.CFrame.lookVector * 90,
      P = 5000,
      maxForce = Vector3.new(50000, 50000, 50000),
      Parent = root
    })
    game:GetService("Debris"):AddItem(bodyVelocity, 0.2)
	for i = 0, 6, 0.1 do
		swait()
		rootj.C0 = clerp(rootj.C0, RootCF * CF(0, 0, 2 + 0.6 * Cos(sine / 20)) * angles(Rad(0 + 255.45 * i), Rad(0), Rad(0)), 0.15)
		tors.Neck.C0 = clerp(tors.Neck.C0, necko * angles(Rad(45 - 2.5 * Sin(sine / 30)), Rad(0), Rad(0)), 0.1)
		RH.C0 = clerp(RH.C0, CF(1, -0.1 - 0.15 * Cos(sine / 20), -0.6) * angles(Rad(0 - 7.5 * Sin(sine / 20)), Rad(65), Rad(0)) * angles(Rad(-4.5), Rad(0), Rad(0)), 0.1)
		LH.C0 = clerp(LH.C0, CF(-1, -0.1 - 0.15 * Cos(sine / 20), -0.6) * angles(Rad(0 - 7.5 * Sin(sine / 20)), Rad(-75), Rad(0)) * angles(Rad(-4.5), Rad(0), Rad(0)), 0.1)
		RW.C0 = clerp(RW.C0, CF(1.25*Player_Size, 0.2 + 0.02 * Sin(sine / 20) *Player_Size, -0.5*Player_Size) * angles(Rad(35), Rad(-15 + 2.5 * Sin(sine / 20)), Rad(-85 + 2.5 * Sin(sine / 20))), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.25*Player_Size, 0.2 + 0.02 * Sin(sine / 20) *Player_Size, -0.5*Player_Size) * angles(Rad(35), Rad(15 - 2.5 * Sin(sine / 20)), Rad(85 - 2.5 * Sin(sine / 20))), 0.1)
	end
	for i = 0, 3, 0.1 do
		swait()
		rootj.C0 = clerp(rootj.C0, RootCF * CF(0, 0, -1 + 0.1 * Cos(sine / 20)) * angles(Rad(80), Rad(0), Rad(0)), 0.15)
		tors.Neck.C0 = clerp(tors.Neck.C0, necko * angles(Rad(45 - 2.5 * Sin(sine / 30)), Rad(0), Rad(0)), 0.1)
		RH.C0 = clerp(RH.C0, CF(1, -0.1 - 0.15 * Cos(sine / 20), -0.6) * angles(Rad(0 - 7.5 * Sin(sine / 20)), Rad(65), Rad(0)) * angles(Rad(-4.5), Rad(0), Rad(0)), 0.1)
		LH.C0 = clerp(LH.C0, CF(-1, -0.9 - 0.25 * Cos(sine / 20), 0) * angles(Rad(0 - 7.5 * Sin(sine / 20)), Rad(-75), Rad(0)) * angles(Rad(-4.5), Rad(0), Rad(0)), 0.1)
		RW.C0 = clerp(RW.C0, CF(1.5, 0.5 + 0.02 * Sin(sine / 20), 0) * angles(Rad(90), Rad(0), Rad(45)), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.25*Player_Size, 0.2 + 0.02 * Sin(sine / 20) *Player_Size, -0.5*Player_Size) * angles(Rad(35), Rad(15 - 2.5 * Sin(sine / 20)), Rad(85 - 2.5 * Sin(sine / 20))), 0.1)
	end
	CameraEnshaking(3, 10)
	Effects.Ring.Create(BrickC("Really black"), root.CFrame * CF(0, -2.7, 0) * angles(Rad(90),Rad(0),Rad(0)), 2, 2, 2, 3.6, 3.6, 3.6, 0.03)
	Effects.Ring.Create(maincolor, root.CFrame * CF(0, -2.3, 0) * angles(Rad(90),Rad(0),Rad(0)), 2, 2, 2, 5.6, 5.6, 5.6, 0.03)
	Effects.Ring.Create(BrickC("Really black"), root.CFrame * CF(0, -1.7, 0) * angles(Rad(90),Rad(0),Rad(0)), 2, 2, 2, 8.6, 8.6, 8.6, 0.03)
	Effects.Ring.Create(maincolor, root.CFrame * CF(0, -1.3, 0) * angles(Rad(90),Rad(0),Rad(0)), 2, 2, 2, 10.6, 10, 10, 0.03)
	Magic(5, "Add", root.CFrame * CFrame.new(0, -2.9, 0), Vector3.new(0, 0, 0), 1, maincolor, "Sphere")
	MagniDamage(tors, 12, 40, 60, 10, "Normal")
	for i = 0, 4, 0.1 do
		swait()
		rootj.C0 = clerp(rootj.C0, RootCF * CF(0, 0, -0.6 + 0.1 * Cos(sine / 20)) * angles(Rad(90), Rad(0), Rad(90)), 0.15)
		tors.Neck.C0 = clerp(tors.Neck.C0, necko * angles(Rad(45 - 2.5 * Sin(sine / 30)), Rad(0), Rad(0)), 0.15)
		RH.C0 = clerp(RH.C0, CF(1, -0.1 - 0.15 * Cos(sine / 20), -0.6) * angles(Rad(0 - 7.5 * Sin(sine / 20)), Rad(65), Rad(0)) * angles(Rad(-4.5), Rad(0), Rad(0)), 0.15)
		LH.C0 = clerp(LH.C0, CF(-1, -0.9 - 0.25 * Cos(sine / 20), 0) * angles(Rad(0 - 7.5 * Sin(sine / 20)), Rad(-75), Rad(0)) * angles(Rad(-4.5), Rad(0), Rad(0)), 0.15)
		RW.C0 = clerp(RW.C0, CF(1.5, 0.5 + 0.02 * Sin(sine / 20), 0) * angles(Rad(0), Rad(0), Rad(90)), 0.15)
		LW.C0 = clerp(LW.C0, CF(-1.25*Player_Size, 0.2 + 0.02 * Sin(sine / 20) *Player_Size, -0.5*Player_Size) * angles(Rad(35), Rad(15 - 2.5 * Sin(sine / 20)), Rad(85 - 2.5 * Sin(sine / 20))), 0.15)
	end
	attack = false
end
function HattyOn()
	attack = true
	movelegs = true
	for i = 0, 4, 0.1 do
		swait()
		rootj.C0 = clerp(rootj.C0, RootCF * CF(0* Player_Size, 0* Player_Size, -0.1 + 0.1* Player_Size * Cos(sine / 20)) * angles(Rad(0 + 3 * Cos(sine / 20)), Rad(0), Rad(0)), 0.1)
		neck.C0 = clerp(neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(20 - 5 * Sin(sine / 20)), Rad(0), Rad(0)), 0.1)
		rl.Weld.C0 = clerp(rl.Weld.C0, CF(0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0 + 3 * Cos(sine / 20)), Rad(-10), Rad(0)) * angles(Rad(0), Rad(0), Rad(5)), 0.1)
		ll.Weld.C0 = clerp(ll.Weld.C0, CF(-0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0 + 3 * Cos(sine / 20)), Rad(10), Rad(0)) * angles(Rad(0), Rad(0), Rad(-5)), 0.1)
		RW.C0 = clerp(RW.C0, CF(1.3 * Player_Size, 0.9 + 0.1 * Cos(sine / 20) * Player_Size, 0 * Player_Size) * angles(Rad(156), Rad(0), Rad(-65 + 2.5 * Sin(sine / 20))), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.25 * Player_Size, 0.3 + 0.1 * Cos(sine / 20) * Player_Size, -0.5 * Player_Size) * angles(Rad(35), Rad(15 - 2.5 * Sin(sine / 20)), Rad(85 - 2.5 * Sin(sine / 20))), 0.1)
	end
	Magic(5, "Add", root.CFrame * CFrame.new(0, -2.9, 0), Vector3.new(0, 0, 0), 1, maincolor, "Sphere")
	CameraEnshaking(5, 10)
	RWeld.Part1 = hed
	RWeld.C0 = CF(0, -0.8, -0.4) * angles(Rad(0), Rad(0), Rad(0))
	attack = false
	movelegs = false
	HatOn = true
end
function HattyOff()
	attack = true
	movelegs = true
	for i = 0, 6, 0.1 do
		swait()
		rootj.C0 = clerp(rootj.C0, RootCF * CF(0* Player_Size, 0* Player_Size, -0.1 + 0.1* Player_Size * Cos(sine / 20)) * angles(Rad(0 + 3 * Cos(sine / 20)), Rad(0), Rad(0)), 0.1)
		neck.C0 = clerp(neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(20 - 5 * Sin(sine / 20)), Rad(0), Rad(0)), 0.1)
		rl.Weld.C0 = clerp(rl.Weld.C0, CF(0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0 + 3 * Cos(sine / 20)), Rad(-10), Rad(0)) * angles(Rad(0), Rad(0), Rad(5)), 0.1)
		ll.Weld.C0 = clerp(ll.Weld.C0, CF(-0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0 + 3 * Cos(sine / 20)), Rad(10), Rad(0)) * angles(Rad(0), Rad(0), Rad(-5)), 0.1)
		RW.C0 = clerp(RW.C0, CF(1.3 * Player_Size, 0.7 + 0.1 * Cos(sine / 20) * Player_Size, 0 * Player_Size) * angles(Rad(156), Rad(0), Rad(-45 + 2.5 * Sin(sine / 20))), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.25 * Player_Size, 0.3 + 0.1 * Cos(sine / 20) * Player_Size, -0.5 * Player_Size) * angles(Rad(35), Rad(15 - 2.5 * Sin(sine / 20)), Rad(85 - 2.5 * Sin(sine / 20))), 0.1)
	end
	Magic(5, "Add", root.CFrame * CFrame.new(0, -2.9, 0), Vector3.new(0, 0, 0), 1, BrickC("Really black"), "Sphere")
	CameraEnshaking(5, 10)
	RWeld.Part1 = ra
	RWeld.C0 = CF(0, -1.3, -0.4) * angles(Rad(180), Rad(0), Rad(-30))
	attack = false
	movelegs = false
	HatOn = false
end
function Tele()
	local POS = mouse.Hit.p + Vector3.new(0, 4, 0)
	local HITFLOOR,HITPOS = rayCast(root.Position, (CF(root.Position, root.Position + Vector3.new(0, -1, 0))).lookVector, 3.7*Player_Size, char)
	if HITFLOOR then
		attack = true
		local CLERPTO = CF(POS, Vector3.new(root.Position.X, POS.Y, root.Position.Z))
		local RING,WELD,MESH = MagicRing(root,CF(0,0,0))
		WELD:remove()
		RING.Anchored = true
		RING.CFrame = CF(HITPOS)
		local RINGON = true
		--CreateSound(TURNUP,Effects,10,0.8,false)
		coroutine.resume(coroutine.create(function()
			coroutine.resume(coroutine.create(function()
				for i = 1, 15 do
					swait()
					MESH.Scale = MESH.Scale + Vector3.new(55,0,55)
				end
			end))
			repeat
				swait()
				RING.CFrame = RING.CFrame * angles(Rad(0), Rad(2), Rad(0))
			until RINGON == false
			for i = 1, 15 do
				swait()
				MESH.Scale = MESH.Scale - Vector3.new(55,0,55)
				RING.CFrame = RING.CFrame * angles(Rad(0), Rad(2), Rad(0))
			end
			RING:remove()
		end))
		for i = 0, 6, 0.1 do
			swait()
			rootj.C0 = clerp(rootj.C0, RootCF * CF(0* Player_Size, 0* Player_Size, -0.1 + 0.1* Player_Size * Cos(sine / 20)) * angles(Rad(0 + 3 * Cos(sine / 20)), Rad(0), Rad(0)), 0.1)
			neck.C0 = clerp(neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(-35 - 5 * Sin(sine / 20)), Rad(0), Rad(0)), 0.1)
			rl.Weld.C0 = clerp(rl.Weld.C0, CF(0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0 + 3 * Cos(sine / 20)), Rad(-10), Rad(0)) * angles(Rad(0), Rad(0), Rad(5)), 0.1)
			ll.Weld.C0 = clerp(ll.Weld.C0, CF(-0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0 + 3 * Cos(sine / 20)), Rad(10), Rad(0)) * angles(Rad(0), Rad(0), Rad(-5)), 0.1)
			RW.C0 = clerp(RW.C0, CF(1.25 * Player_Size, 0.4 + 0.1 * Sin(sine / 20) * Player_Size, -0.5 * Player_Size) * angles(Rad(35), Rad(-15 + 2.5 * Sin(sine / 20)), Rad(-85 + 2.5 * Sin(sine / 20))), 0.1)
			LW.C0 = clerp(LW.C0, CF(-1.25 * Player_Size, 0.3 + 0.1 * Cos(sine / 20) * Player_Size, -0.5 * Player_Size) * angles(Rad(35), Rad(15 - 2.5 * Sin(sine / 20)), Rad(85 - 2.5 * Sin(sine / 20))), 0.1)
		end
		root.Anchored = true
		for i = 0, 6, 0.1 do
			swait()
			rootj.C0 = clerp(rootj.C0, RootCF * CF(0* Player_Size, 0* Player_Size, -500 + 0.1* Player_Size * Cos(sine / 20)) * angles(Rad(0 + 3 * Cos(sine / 20)), Rad(0), Rad(0)), 0.1)
			neck.C0 = clerp(neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(-35 - 5 * Sin(sine / 20)), Rad(0), Rad(0)), 0.1)
			rl.Weld.C0 = clerp(rl.Weld.C0, CF(0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0 + 3 * Cos(sine / 20)), Rad(-10), Rad(0)) * angles(Rad(0), Rad(0), Rad(5)), 0.1)
			ll.Weld.C0 = clerp(ll.Weld.C0, CF(-0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0 + 3 * Cos(sine / 20)), Rad(10), Rad(0)) * angles(Rad(0), Rad(0), Rad(-5)), 0.1)
			RW.C0 = clerp(RW.C0, CF(1.25 * Player_Size, 0.4 + 0.1 * Sin(sine / 20) * Player_Size, -0.5 * Player_Size) * angles(Rad(35), Rad(-15 + 2.5 * Sin(sine / 20)), Rad(-85 + 2.5 * Sin(sine / 20))), 0.1)
			LW.C0 = clerp(LW.C0, CF(-1.25 * Player_Size, 0.3 + 0.1 * Cos(sine / 20) * Player_Size, -0.5 * Player_Size) * angles(Rad(35), Rad(15 - 2.5 * Sin(sine / 20)), Rad(85 - 2.5 * Sin(sine / 20))), 0.1)
		end
		for i = 1, 170 do
			swait()
			root.CFrame = clerp(root.CFrame, CLERPTO, 0.05)
		end
		root.Anchored = false
		RINGON = false
		attack = false
	end
end
-------------------------------------------------------
--End Attacks N Stuff--
-------------------------------------------------------
mouse.KeyDown:connect(function(key)
	if attack == false then
		if key == "t" and HatOn == false then
			Fun_Times_Ahead()
		elseif key == "t" and HatOn == true then
			Fun_Times_Ahead_2()
		elseif key == "z" then
			Jester_Dash()
		elseif key == "x" then
			Sie_alle_sterben()
		elseif key == "c" then
			Apocalypse()
		elseif key == "v" and HatOn == false then
			HattyOn()
		elseif key == "v" and HatOn == true then
			HattyOff()
		elseif key == "b" and HatOn == true then
			Tele()
		end
	end
end)

 






-------------------------------------------------------
--Start Animations--
-------------------------------------------------------
print("By Makhail07")
while true do
	swait()
	sine = sine + change
	local torvel = (root.Velocity * Vector3.new(1, 0, 1)).magnitude
	local velderp = root.Velocity.y
	hitfloor, posfloor = rayCast(root.Position, CFrame.new(root.Position, root.Position - Vector3.new(0, 1, 0)).lookVector, 4* Player_Size, char)
	if equipped == true or equipped == false then
		if attack == false then
			idle = idle + 1
		else
			idle = 0
		end
		local Landed = false
		if(hitfloor)then
			WasAir = false
		else
			WasAir = true
		end
		if(WasAir == false)then
			if(InAir == true)then
				LandTick = time()
				Landed = true
			end
		end
		if(time()-LandTick < .3)then
			Landed = true
		end
		if(hitfloor)then
			InAir = false
		else
			InAir = true
		end
		if(not char:FindFirstChildOfClass'Shirt')then
			NewInstance("Shirt",char,{ShirtTemplate='rbxassetid://236971115'})
		else
			char:FindFirstChildOfClass'Shirt'.ShirtTemplate='rbxassetid://236971115'
		end
		if(not char:FindFirstChildOfClass'Pants')then
			NewInstance("Pants",char,{PantsTemplate='rbxassetid://236971198'})
		else
			char:FindFirstChildOfClass'Pants'.PantsTemplate='rbxassetid://236971198'
		end
		local Walking = (math.abs(root.Velocity.x) > 1 or math.abs(root.Velocity.z) > 1)
		local State = (hum.PlatformStand and 'Paralyzed' or hum.Sit and 'Sit' or Landed and 'Land' or not hitfloor and root.Velocity.y < -1 and "Fall" or not hitfloor and root.Velocity.y > 1 and "Jump" or hitfloor and Walking and "Walk" or hitfloor and "Idle")
		local WALKSPEEDVALUE = 6 / (hum.WalkSpeed / 16)
		if hum.Sit == false then
		if(State == 'Jump')then
			hum.WalkSpeed = 34
			hum.JumpPower = 55
			if attack == false then
				rootj.C0 = clerp(rootj.C0, RootCF * CF(0* Player_Size, 0* Player_Size, -0.1 + 0.1 * Cos(sine / 20)* Player_Size) * angles(Rad(-16), Rad(0), Rad(0)), 0.1)
				neck.C0 = clerp(neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(10 - 2.5 * Sin(sine / 30)), Rad(0), Rad(0)), 0.3)
				rl.Weld.C0 = clerp(rl.Weld.C0, CF(0.5* Player_Size, -.2 - 0.1 * Cos(sine / 20), -.3* Player_Size) * angles(Rad(0), Rad(-10), Rad(0)) * angles(Rad(-2.5), Rad(0), Rad(0)), 0.1)
				ll.Weld.C0 = clerp(ll.Weld.C0, CF(-0.5* Player_Size, -.9 - 0.1 * Cos(sine / 20), -.5* Player_Size) * angles(Rad(0), Rad(10), Rad(0)) * angles(Rad(-2.5), Rad(0), Rad(0)), 0.1)
				RW.C0 = clerp(RW.C0, CF(1.5* Player_Size, 0.5 + 0.02 * Sin(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(25), Rad(-.6), Rad(13 + 4.5 * Sin(sine / 20))), 0.1)
				LW.C0 = clerp(LW.C0, CF(-1.5* Player_Size, 0.5 + 0.02 * Sin(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(25), Rad(-.6), Rad(-13 - 4.5 * Sin(sine / 20))), 0.1)
			end
		elseif(State == 'Fall')then
			if attack == false then
				rootj.C0 = clerp(rootj.C0, RootCF * CF(0* Player_Size, 0* Player_Size, -0.1 + 0.1 * Cos(sine / 20)* Player_Size) * angles(Rad(24), Rad(0), Rad(0)), 0.1)
				neck.C0 = clerp(neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(10 - 2.5 * Sin(sine / 30)), Rad(0), Rad(0)), 0.3)
				rl.Weld.C0 = clerp(rl.Weld.C0, CF(0.5* Player_Size, -1 - 0.1 * Cos(sine / 20)* Player_Size, -.3* Player_Size) * angles(Rad(0), Rad(-10), Rad(0)) * angles(Rad(-3.5), Rad(0), Rad(0)), 0.1)
				ll.Weld.C0 = clerp(ll.Weld.C0, CF(-0.5* Player_Size, -.8 - 0.1 * Cos(sine / 20)* Player_Size, -.3* Player_Size) * angles(Rad(0), Rad(10), Rad(0)) * angles(Rad(-3.5), Rad(0), Rad(0)), 0.1)
				RW.C0 = clerp(RW.C0, CF(1.5* Player_Size, 0.5 + 0.02 * Sin(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(65), Rad(-.6), Rad(45 + 4.5 * Sin(sine / 20))), 0.1)
				LW.C0 = clerp(LW.C0, CF(-1.5* Player_Size, 0.5 + 0.02 * Sin(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(55), Rad(-.6), Rad(-45 - 4.5 * Sin(sine / 20))), 0.1)
			end
		elseif(State == 'Land')then
			hum.WalkSpeed = 4
			hum.JumpPower = 0
			if attack == false then
				rootj.C0 = clerp(rootj.C0, RootCF * CF(0* Player_Size, 0* Player_Size, -1 + 0.1 * Cos(sine / 20)* Player_Size) * angles(Rad(10), Rad(0), Rad(0)), 0.15)
				neck.C0 = clerp(neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(35 - 2.5 * Sin(sine / 30)), Rad(0), Rad(0)), 0.3)
				rl.Weld.C0 = clerp(rl.Weld.C0, CF(0.5* Player_Size, 0.1 - 0.1 * Cos(sine / 20)* Player_Size, -.3* Player_Size) * angles(Rad(0), Rad(-10), Rad(0)) * angles(Rad(-3.5), Rad(0), Rad(10)), 0.15)
				ll.Weld.C0 = clerp(ll.Weld.C0, CF(-0.5* Player_Size, 0.1 - 0.1 * Cos(sine / 20)* Player_Size, -.3* Player_Size) * angles(Rad(0), Rad(10), Rad(0)) * angles(Rad(-3.5), Rad(0), Rad(-10)), 0.15)
				RW.C0 = clerp(RW.C0, CF(1.5* Player_Size, 0.5 + 0.02 * Sin(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(65), Rad(-.6), Rad(25 + 4.5 * Sin(sine / 20))), 0.1)
				LW.C0 = clerp(LW.C0, CF(-1.5* Player_Size, 0.5 + 0.02 * Sin(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(55), Rad(-.6), Rad(-25 - 4.5 * Sin(sine / 20))), 0.1)
			end
		elseif(State == 'Idle')then
			change = 1
			if attack == false then
				if HatOn == false then
					rootj.C0 = clerp(rootj.C0, RootCF * CF(0* Player_Size, 0* Player_Size, -0.1 + 0.1* Player_Size * Cos(sine / 20)) * angles(Rad(0 + 3 * Cos(sine / 20)), Rad(0), Rad(0)), 0.1)
					neck.C0 = clerp(neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(20 - 5 * Sin(sine / 20)), Rad(0), Rad(0)), 0.1)
					rl.Weld.C0 = clerp(rl.Weld.C0, CF(0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0 + 3 * Cos(sine / 20)), Rad(-10), Rad(0)) * angles(Rad(0), Rad(0), Rad(5)), 0.1)
					ll.Weld.C0 = clerp(ll.Weld.C0, CF(-0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0 + 3 * Cos(sine / 20)), Rad(10), Rad(0)) * angles(Rad(0), Rad(0), Rad(-5)), 0.1)
					RW.C0 = clerp(RW.C0, CF(1.5 * Player_Size, 0.5 + 0.1 * Cos(sine / 20) * Player_Size, 0 * Player_Size) * angles(Rad(156), Rad(0), Rad(10 + 2.5 * Sin(sine / 20))), 0.1)
					LW.C0 = clerp(LW.C0, CF(-1.25 * Player_Size, 0.3 + 0.1 * Cos(sine / 20) * Player_Size, -0.5 * Player_Size) * angles(Rad(35), Rad(15 - 2.5 * Sin(sine / 20)), Rad(85 - 2.5 * Sin(sine / 20))), 0.1)
				else
					rootj.C0 = clerp(rootj.C0, RootCF * CF(0* Player_Size, 0* Player_Size, -0.1 + 0.1* Player_Size * Cos(sine / 20)) * angles(Rad(0 + 3 * Cos(sine / 20)), Rad(0), Rad(-20)), 0.1)
					neck.C0 = clerp(neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(35 - 5 * Sin(sine / 20)), Rad(0), Rad(20)), 0.1)
					rl.Weld.C0 = clerp(rl.Weld.C0, CF(0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0 + 3 * Cos(sine / 20)), Rad(-10), Rad(0)) * angles(Rad(0), Rad(0), Rad(5)), 0.1)
					ll.Weld.C0 = clerp(ll.Weld.C0, CF(-0.5* Player_Size, -0.9 - 0.1 * Cos(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0 + 3 * Cos(sine / 20)), Rad(10), Rad(0)) * angles(Rad(0), Rad(0), Rad(-5)), 0.1)
					RW.C0 = clerp(RW.C0, CF(1.25 * Player_Size, 0.4 + 0.1 * Sin(sine / 20) * Player_Size, -0.5 * Player_Size) * angles(Rad(35), Rad(-15 + 2.5 * Sin(sine / 20)), Rad(-85 + 2.5 * Sin(sine / 20))), 0.1)
					LW.C0 = clerp(LW.C0, CF(-1.25 * Player_Size, 0.3 + 0.1 * Cos(sine / 20) * Player_Size, -0.5 * Player_Size) * angles(Rad(35), Rad(15 - 2.5 * Sin(sine / 20)), Rad(85 - 2.5 * Sin(sine / 20))), 0.1)
				end
			end
		elseif(State == 'Walk')then
			change = 0.76
			hum.WalkSpeed = 16
			hum.JumpPower = 55
			if attack == false then
				if HatOn == false then
					rootj.C0 = clerp(rootj.C0, RootCF * CF(0* Player_Size, 0* Player_Size, -0.3 - 0.15 * Cos(sine / (WALKSPEEDVALUE / 2))) * angles(Rad(10), Rad(0), Rad(0 - 0.75 * Cos(sine / (WALKSPEEDVALUE / 2))) + root.RotVelocity.Y / 75), 0.1)
					neck.C0 = clerp(neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(0 + 5 * Sin(sine / (WALKSPEEDVALUE / 2))), Rad(0), Rad(0) + root.RotVelocity.Y / 13), 0.1)
					rl.Weld.C0 = clerp(rl.Weld.C0, CF(0.5* Player_Size, -0.8 - 0.5 * Cos(sine / WALKSPEEDVALUE) / 2* Player_Size, 0.6 * Cos(sine / WALKSPEEDVALUE) / 2* Player_Size)  * angles(Rad(-10 - 25 * Cos(sine / WALKSPEEDVALUE)) - root.RotVelocity.Y / 75 + -Sin(sine / WALKSPEEDVALUE) / 2.5, Rad(0 - 10 * Cos(sine / WALKSPEEDVALUE)), Rad(0)) * angles(Rad(0 + 2 * Cos(sine / WALKSPEEDVALUE)), Rad(0), Rad(0)), 0.3)
         			ll.Weld.C0 = clerp(ll.Weld.C0, CF(-0.5* Player_Size, -0.8 + 0.5 * Cos(sine / WALKSPEEDVALUE) / 2* Player_Size, -0.6 * Cos(sine / WALKSPEEDVALUE) / 2* Player_Size) * angles(Rad(-10 + 25 * Cos(sine / WALKSPEEDVALUE)) + root.RotVelocity.Y / -75 + Sin(sine / WALKSPEEDVALUE) / 2.5, Rad(0 - 10 * Cos(sine / WALKSPEEDVALUE)), Rad(0)) * angles(Rad(0 - 2 * Cos(sine / WALKSPEEDVALUE)), Rad(0), Rad(0)), 0.3)
					RW.C0 = clerp(RW.C0, CF(1.5 * Player_Size, 0.5 + 0.1 * Cos(sine / WALKSPEEDVALUE) * Player_Size, 0 * Player_Size) * angles(Rad(156), Rad(0), Rad(10 + 2.5 * Sin(sine / WALKSPEEDVALUE))), 0.1)
					LW.C0 = clerp(LW.C0, CF(-1.25 * Player_Size, 0.3 + 0.1 * Cos(sine / WALKSPEEDVALUE) * Player_Size, -0.5 * Player_Size) * angles(Rad(35), Rad(15 - 2.5 * Sin(sine / 20)), Rad(85 - 2.5 * Sin(sine / 20))), 0.1)
				else
					rootj.C0 = clerp(rootj.C0, RootCF * CF(0* Player_Size, 0* Player_Size, -0.3 - 0.15 * Cos(sine / (WALKSPEEDVALUE / 2))) * angles(Rad(10), Rad(0), Rad(0 - 1.35 * Cos(sine / (WALKSPEEDVALUE / 2))) + root.RotVelocity.Y / 75), 0.1)
					neck.C0 = clerp(neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(0 + 5 * Sin(sine / (WALKSPEEDVALUE / 2))), Rad(0), Rad(0) + root.RotVelocity.Y / 13), 0.1)
					rl.Weld.C0 = clerp(rl.Weld.C0, CF(0.5* Player_Size, -0.8 - 0.5 * Cos(sine / WALKSPEEDVALUE) / 2* Player_Size, 0.6 * Cos(sine / WALKSPEEDVALUE) / 2* Player_Size)  * angles(Rad(-10 - 25 * Cos(sine / WALKSPEEDVALUE)) - root.RotVelocity.Y / 75 + -Sin(sine / WALKSPEEDVALUE) / 2.5, Rad(0 - 10 * Cos(sine / WALKSPEEDVALUE)), Rad(0)) * angles(Rad(0 + 2 * Cos(sine / WALKSPEEDVALUE)), Rad(0), Rad(0)), 0.3)
         			ll.Weld.C0 = clerp(ll.Weld.C0, CF(-0.5* Player_Size, -0.8 + 0.5 * Cos(sine / WALKSPEEDVALUE) / 2* Player_Size, -0.6 * Cos(sine / WALKSPEEDVALUE) / 2* Player_Size) * angles(Rad(-10 + 25 * Cos(sine / WALKSPEEDVALUE)) + root.RotVelocity.Y / -75 + Sin(sine / WALKSPEEDVALUE) / 2.5, Rad(0 - 10 * Cos(sine / WALKSPEEDVALUE)), Rad(0)) * angles(Rad(0 - 2 * Cos(sine / WALKSPEEDVALUE)), Rad(0), Rad(0)), 0.3)
					RW.C0 = clerp(RW.C0, CF(1.25 * Player_Size, 0.4 + 0.1 * Sin(sine / 20) * Player_Size, -0.5 * Player_Size) * angles(Rad(35), Rad(-15 + 2.5 * Sin(sine / 20)), Rad(-85 + 2.5 * Sin(sine / 20))), 0.1)
					LW.C0 = clerp(LW.C0, CF(-1.25 * Player_Size, 0.3 + 0.1 * Cos(sine / 20) * Player_Size, -0.5 * Player_Size) * angles(Rad(35), Rad(15 - 2.5 * Sin(sine / 20)), Rad(85 - 2.5 * Sin(sine / 20))), 0.1)
				end	
			elseif attack == true and movelegs == true then
				rl.Weld.C0 = clerp(rl.Weld.C0, CF(0.5* Player_Size, -0.8 - 0.5 * Cos(sine / WALKSPEEDVALUE) / 2* Player_Size, 0.6 * Cos(sine / WALKSPEEDVALUE) / 2* Player_Size)  * angles(Rad(-10 - 25 * Cos(sine / WALKSPEEDVALUE)) - root.RotVelocity.Y / 75 + -Sin(sine / WALKSPEEDVALUE) / 2.5, Rad(0 - 10 * Cos(sine / WALKSPEEDVALUE)), Rad(0)) * angles(Rad(0 + 2 * Cos(sine / WALKSPEEDVALUE)), Rad(0), Rad(0)), 0.3)
         		ll.Weld.C0 = clerp(ll.Weld.C0, CF(-0.5* Player_Size, -0.8 + 0.5 * Cos(sine / WALKSPEEDVALUE) / 2* Player_Size, -0.6 * Cos(sine / WALKSPEEDVALUE) / 2* Player_Size) * angles(Rad(-10 + 25 * Cos(sine / WALKSPEEDVALUE)) + root.RotVelocity.Y / -75 + Sin(sine / WALKSPEEDVALUE) / 2.5, Rad(0 - 10 * Cos(sine / WALKSPEEDVALUE)), Rad(0)) * angles(Rad(0 - 2 * Cos(sine / WALKSPEEDVALUE)), Rad(0), Rad(0)), 0.3)
			end
		end
		else
			Sit.Value = true
			if attack == false then
			rootj.C0 = clerp(rootj.C0, RootCF * CF(0* Player_Size, 0* Player_Size, -0.5 + 0.1* Player_Size * Cos(sine / 20)) * angles(Rad(0), Rad(0), Rad(5)), 0.1)
			neck.C0 = clerp(neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(15 - 2.5 * Sin(sine / 30)), Rad(0), Rad(-5)), 0.1)
			rl.Weld.C0 = clerp(rl.Weld.C0, CF(1* Player_Size, -0.35 - 0.05 * Cos(sine / 20)* Player_Size, -0.5* Player_Size) * angles(Rad(15), Rad(75), Rad(0)) * angles(Rad(-5), Rad(0), Rad(5)), 0.1)
			ll.Weld.C0 = clerp(ll.Weld.C0, CF(-1* Player_Size, -0.35 - 0.05 * Cos(sine / 20)* Player_Size, -0.5* Player_Size) * angles(Rad(15), Rad(-75), Rad(0)) * angles(Rad(-5), Rad(0), Rad(5)), 0.1)
			RW.C0 = clerp(RW.C0, CF(1.3* Player_Size, 0.4 + 0.1 * Sin(sine / 20)* Player_Size, -0.3* Player_Size) * angles(Rad(35), Rad(-20), Rad(-45 - 4.5 * Sin(sine / 20))), 0.1)
			LW.C0 = clerp(LW.C0, CF(-1.3* Player_Size, 0.4 + 0.1 * Sin(sine / 20)* Player_Size, -0.3* Player_Size) * angles(Rad(35), Rad(20), Rad(45 + 4.5 * Sin(sine / 20))), 0.1)
			end
		end
	end
	for _, c in pairs(char:GetChildren()) do
		if c.ClassName == "Part" and c.Name ~= "Detail" then
			if c:FindFirstChildOfClass("ParticleEmitter") then
				c:FindFirstChildOfClass("ParticleEmitter"):remove()
			end
		elseif c.ClassName == "CharacterMesh" or c.ClassName == "Accessory" or c.Name == "Body Colors" then
			c:remove()
		end
	end
	Music.SoundId = "rbxassetid://"..SONG
	Music.Looped = true
	Music.Pitch = 1
	Music.Volume = 2
	Music.Parent = tors
	Music.Playing = true
	if 0 < #Effects then
		for e = 1, #Effects do
			if Effects[e] ~= nil then
				local Thing = Effects[e]
				if Thing ~= nil then
					local Part = Thing[1]
					local Mode = Thing[2]
					local Delay = Thing[3]
					local IncX = Thing[4]
					local IncY = Thing[5]
					local IncZ = Thing[6]
					if 1 >= Thing[1].Transparency then
						if Thing[2] == "Block1" then
							Thing[1].CFrame = Thing[1].CFrame * CFrame.fromEulerAnglesXYZ(math.random(-50, 50), math.random(-50, 50), math.random(-50, 50))
							local Mesh = Thing[1].Mesh
							Mesh.Scale = Mesh.Scale + Vector3.new(Thing[4], Thing[5], Thing[6])
							Thing[1].Transparency = Thing[1].Transparency + Thing[3]
						elseif Thing[2] == "Block2" then
							Thing[1].CFrame = Thing[1].CFrame + Vector3.new(0, 0, 0)
							local Mesh = Thing[7]
							Mesh.Scale = Mesh.Scale + Vector3.new(Thing[4], Thing[5], Thing[6])
							Thing[1].Transparency = Thing[1].Transparency + Thing[3]
						elseif Thing[2] == "Block3" then
							Thing[1].CFrame = Thing[1].CFrame * CFrame.fromEulerAnglesXYZ(math.random(-50, 50), math.random(-50, 50), math.random(-50, 50)) + Vector3.new(0, 0.15, 0)
							local Mesh = Thing[7]
							Mesh.Scale = Mesh.Scale + Vector3.new(Thing[4], Thing[5], Thing[6])
							Thing[1].Transparency = Thing[1].Transparency + Thing[3]
						elseif Thing[2] == "Cylinder" then
							local Mesh = Thing[1].Mesh
							Mesh.Scale = Mesh.Scale + Vector3.new(Thing[4], Thing[5], Thing[6])
							Thing[1].Transparency = Thing[1].Transparency + Thing[3]
						elseif Thing[2] == "Blood" then
							local Mesh = Thing[7]
							Thing[1].CFrame = Thing[1].CFrame * Vector3.new(0, 0.5, 0)
							Mesh.Scale = Mesh.Scale + Vector3.new(Thing[4], Thing[5], Thing[6])
							Thing[1].Transparency = Thing[1].Transparency + Thing[3]
						elseif Thing[2] == "Elec" then
							local Mesh = Thing[1].Mesh
							Mesh.Scale = Mesh.Scale + Vector3.new(Thing[7], Thing[8], Thing[9])
							Thing[1].Transparency = Thing[1].Transparency + Thing[3]
						elseif Thing[2] == "Disappear" then
							Thing[1].Transparency = Thing[1].Transparency + Thing[3]
						elseif Thing[2] == "Shatter" then
							Thing[1].Transparency = Thing[1].Transparency + Thing[3]
							Thing[4] = Thing[4] * CFrame.new(0, Thing[7], 0)
							Thing[1].CFrame = Thing[4] * CFrame.fromEulerAnglesXYZ(Thing[6], 0, 0)
							Thing[6] = Thing[6] + Thing[5]
						end
					else
						Part.Parent = nil
						table.remove(Effects, e)
					end
				end
			end
		end
	end
end
-------------------------------------------------------
--End Animations And Script--
-------------------------------------------------------
