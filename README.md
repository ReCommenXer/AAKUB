------------------wait load
if not game:IsLoaded() then repeat game.Loaded:Wait() until game:IsLoaded() end
----------------------------------- save


function loadcheck()
    local fileName = "RebornXer Hub Anime Adventures" .. game.Players.LocalPlayer.Name .. ".json"
    
    if not isfile(fileName) then
        writefile(fileName, game:GetService("HttpService"):JSONEncode(_G.SST))
        return
    end
end

pcall(function()
    _G.SST = {
        Select_Map = "",
        Select_Act = "",
        Select_Mode = "",
        Select_Friend_Only = false,
        Auto_Join = false,
        Auto_ReJoin = false,
        Farm_Sukuna = false,
        Select_Farme_Rate = "60",
        Auto_Rejoin_Kick = true,
        Boost_Fps = false,
        Black_Screen = false,
        Sent_WebHook = false,
        WebHook_Link = "",
        Auto_Back_To_Lobby = false,
        Farm_Gem = false,
        Auto_Farm_HolidayStars = false,
        Farm_Level = false,
        Anti_AFK = true,
        Auto_Upgrade_Unit = false,
        Select_To_Upgrade = "All Unit",
        Feed_Easter = false,
        Claim_Easter = false
    }
end)

function LoadSetting()
    local fileName = "RebornXer Hub Anime Adventures" .. game.Players.LocalPlayer.Name .. ".json"
    
    if isfile(fileName) then
        local fileContent = readfile(fileName)
        local success, decoded = pcall(function()
            return game:GetService("HttpService"):JSONDecode(fileContent)
        end)
        
        if success then
            _G.SST = decoded
        end
    else
        SS()
    end
end

function SS()
    local fileName = "RebornXer Hub Anime Adventures" .. game.Players.LocalPlayer.Name .. ".json"
    
    if isfile(fileName) then
        writefile(fileName, game:GetService("HttpService"):JSONEncode(_G.SST))
    else
        loadcheck()
    end
end

loadcheck()
LoadSetting()


---------------------------------------------------- Ui
local OCui = game.CoreGui:FindFirstChild("RebormXerOC")
if OCui then
	OCui:Destroy()
end
local RebornXer = Instance.new("ScreenGui")
local Open = Instance.new("TextButton")
local fuckshit = Instance.new("UICorner")
local MODILEMAGE = Instance.new("ImageLabel")
local posto = Instance.new("UIStroke")

local ScreenGui = Instance.new("ScreenGui")
local ImageButton = Instance.new("ImageButton")

-- กำหนดค่าเริ่มต้น
ScreenGui.Parent = game.CoreGui
ScreenGui.Name = "RebormXerOC"
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

ImageButton.Parent = ScreenGui
ImageButton.Name = "Open/CloseUi"
ImageButton.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
ImageButton.BorderSizePixel = 0
ImageButton.Position = UDim2.new(0.1, 0, 0.1, 0)
ImageButton.Size = UDim2.new(0, 45, 0, 45)
ImageButton.Draggable = true
ImageButton.Image = "rbxassetid://108287073891881"

-- ฟังก์ชันสำหรับการคลิก
local TweenService = game:GetService("TweenService")
ImageButton.MouseButton1Click:Connect(function()
    local ui = game:GetService("CoreGui"):FindFirstChild("RebornXer Hub") -- ค้นหา UI
    if ui and ui:FindFirstChild("Main") then -- ตรวจสอบว่ามี "Main" อยู่ใน UI
        local main = ui.Main
        if main.Size.X.Offset == 600 and main.Size.Y.Offset == 400 then
            local tween = TweenService:Create(
                main,
                TweenInfo.new(0.20, Enum.EasingStyle.Sine, Enum.EasingDirection.In), -- กำหนดเวลา 0.35 วินาที
                {Size = UDim2.new(0, 0, 0, 0)}
            )
            tween:Play() -- เล่น Tween
        else
            local tween = TweenService:Create(
                main,
                TweenInfo.new(0.20, Enum.EasingStyle.Sine, Enum.EasingDirection.Out), -- กำหนดเวลา 0.35 วินาที
                {Size = UDim2.new(0, 600, 0, 400)}
            )
            tween:Play() -- เล่น Tween
        end
    end
end)


fuckshit.Parent = Open

 MODILEMAGE.Name = "MODILEMAGE"
 MODILEMAGE.Parent = Open
 MODILEMAGE.BackgroundColor3 = Color3.fromRGB(51,255,255)
 MODILEMAGE.BackgroundTransparency = 1.000
 MODILEMAGE.BorderSizePixel = 0
 MODILEMAGE.Position = UDim2.new(0, 0.5, 0, 0)
 MODILEMAGE.Size = UDim2.new(0, 38, 0, 31)
 MODILEMAGE.Image = "rbxassetid://"
 
posto.Name = "posto"
 posto.Parent = Open
 posto.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
 posto.Color = Color3.fromRGB(51,255,255)
 posto.LineJoinMode = Enum.LineJoinMode.Round
 posto.Thickness = 1
 posto.Transparency = 0
 posto.Enabled = true
 posto.Archivable = true



 _G.WindowBackgroundColor = Color3.fromRGB(0, 0, 0) -- พื้นหลังหน้าต่าง (ดำ)
 _G.BackgroundItemColor = Color3.fromRGB(30, 30, 30) -- พื้นหลังของไอเทม (ดำเข้ม)
 _G.TabWindowColor = Color3.fromRGB(20, 20, 20) -- สีแท็บหน้าต่าง (ดำเข้ม)
 _G.ContainerColor = Color3.fromRGB(40, 40, 40) -- สีคอนเทนเนอร์ (ดำเข้ม)
 _G.TitleTextColor = Color3.fromRGB(255, 255, 255) -- สีข้อความหัวเรื่อง (ขาว)
 _G.ImageColor = Color3.fromRGB(255, 255, 255) -- สีของรูปภาพ (ขาว)
 _G.LineThemeColor = Color3.fromRGB(255, 255, 255) -- สีเส้น (ขาว)
 _G.TabTextColor = Color3.fromRGB(255, 255, 255) -- สีข้อความในแท็บ (ขาว)
 _G.TabImageColor = Color3.fromRGB(255, 255, 255) -- สีรูปภาพในแท็บ (ขาว)
 _G.TabThemeColor = Color3.fromRGB(255, 255, 255) -- สีธีมของแท็บ (ขาว)
 _G.SectionColor = Color3.fromRGB(30, 30, 30) -- สีพื้นหลังของ Section (ดำเข้ม)
 _G.SectionImageColor = Color3.fromRGB(255, 255, 255) -- สีรูปภาพใน Section (ขาว)
 _G.SectionTextColor = Color3.fromRGB(255, 255, 255) -- สีข้อความใน Section (ขาว)
 _G.SectionOn = Color3.fromRGB(0, 255, 0) -- สีสถานะเปิดของ Section (เขียว)
 
_G.Color1 = Color3.fromRGB(255,255,255)
do local GUI = game.CoreGui:FindFirstChild("RebornXer Hub");if GUI then GUI:Destroy();end;if _G.Color == nil then
_G.Color = Color3.fromRGB(255,255,255)
end 
end

local tween = game:GetService("TweenService")
local tweeninfo = TweenInfo.new
local input = game:GetService("UserInputService")
local run = game:GetService("RunService")
local plr = game.Players.LocalPlayer
local mouse = plr:GetMouse()

local UserInputService = game:GetService("UserInputService")
local TweenService = game:GetService("TweenService")

local function MakeDraggable(topbarobject, object)
	local Dragging = nil
	local DragInput = nil
	local DragStart = nil
	local StartPosition = nil

	local function Update(input)
		local Delta = input.Position - DragStart
		local pos = UDim2.new(StartPosition.X.Scale, StartPosition.X.Offset + Delta.X, StartPosition.Y.Scale, StartPosition.Y.Offset + Delta.Y)
		local Tween = TweenService:Create(object, TweenInfo.new(0.15), {Position = pos})
		Tween:Play()
	end

	topbarobject.InputBegan:Connect(
		function(input)
			if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
				Dragging = true
				DragStart = input.Position
				StartPosition = object.Position

				input.Changed:Connect(
					function()
						if input.UserInputState == Enum.UserInputState.End then
							Dragging = false
						end
					end
				)
			end
		end
	)

	topbarobject.InputChanged:Connect(
		function(input)
			if
				input.UserInputType == Enum.UserInputType.MouseMovement or
				input.UserInputType == Enum.UserInputType.Touch
			then
				DragInput = input
			end
		end
	)

	UserInputService.InputChanged:Connect(
		function(input)
			if input == DragInput and Dragging then
				Update(input)
			end
		end
	)
end

local Update = {}

function Update:AddWindow(name,logo,keybind)
	local uihide = false
	local abc = false
	local logo = logo or 0
	local currentpage = ""
	local keybind = keybind or Enum.KeyCode.RightControl
	local yoo = string.gsub(tostring(keybind),"Enum.KeyCode.","")
	
	local RebornXer_Hub = Instance.new("ScreenGui")
	RebornXer_Hub.Name = "RebornXer Hub"
	RebornXer_Hub.Parent = game.CoreGui
	RebornXer_Hub.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

local osfunc = {}
 local osfunc2 = {}
	local Main = Instance.new("Frame")
	local WindowStrokemain = Instance.new("UIStroke")
	Main.Name = "Main"
	Main.Parent = RebornXer_Hub
	Main.ClipsDescendants = true
	Main.AnchorPoint = Vector2.new(0.5,0.5)
	Main.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
	Main.Position = UDim2.new(0.5, 0, 0.5, 0)
	Main.Size = UDim2.new(0, 0, 0, 0)
	
	WindowStrokemain.Name = "WindowStroke"
 WindowStrokemain.Parent = Main
 WindowStrokemain.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
 WindowStrokemain.Color = Color3.fromRGB(255,255,255)
 WindowStrokemain.LineJoinMode = Enum.LineJoinMode.Round
 WindowStrokemain.Thickness = 1
 WindowStrokemain.Transparency = 0
 WindowStrokemain.Enabled = true
 WindowStrokemain.Archivable = true
	
	Main:TweenSize(UDim2.new(0, 600, 0, 400),"Out","Quad",0,true)

	local MCNR = Instance.new("UICorner")
	MCNR.Name = "MCNR"
	MCNR.Parent = Main

	local Top = Instance.new("Frame")
	Top.Name = "Top"
	Top.Position = UDim2.new(0,0,0,4)
	Top.Parent = Main
	Top.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
	Top.Size = UDim2.new(0, 560, 0, 28)



	local Logo = Instance.new("ImageLabel")
	Logo.Name = "Logo"
	Logo.Parent = Top
	Logo.BackgroundColor3 = Color3.fromRGB(255,255,255)
	Logo.BackgroundTransparency = 1.000
	Logo.Position = UDim2.new(0, 9, 0, 1)
	Logo.Size = UDim2.new(0, 30, 0, 25)
	Logo.Image = "rbxassetid://"..tostring(logo)

	local Name = Instance.new("TextLabel")
	Name.Name = "Name"
	Name.Parent = Top
	Name.BackgroundColor3 = Color3.fromRGB(0,255,255)
	Name.BackgroundTransparency = 1.000
	Name.Position = UDim2.new(0.1, 0, 0, 0)
	Name.Size = UDim2.new(0, 80, 0, 27)
	Name.Font = Enum.Font.Code
	Name.RichText = true;
	Name.Text = name
	Name.TextColor3 = Color3.fromRGB(225, 225, 225)
	Name.TextSize = 15.000

local LocalizationService = game:GetService("LocalizationService")
 local Players = game:GetService("Players")
 local player = Players.LocalPlayer
 local name = player.Name
 local result, code = pcall(function()
	 return LocalizationService:GetCountryRegionForPlayerAsync(player)
 end)
 
function osfunc:Refresh(textadd)
 ServerTime.Text = textadd
 end
 function osfunc2:Refresh(textadd2)
 ServerDate.Text = textadd2
 end

 
local ListNof = Instance.new("Frame")
	local NofList = Instance.new("UIListLayout")

	ListNof.Name = "ListNof"
	ListNof.Parent = RebornXer_Hub
	ListNof.BackgroundColor3 = Color3.fromRGB(255,255,255)
	ListNof.BackgroundTransparency = 1.000
	ListNof.Position = UDim2.new(0.778017223, 0, -0.00217864919, 0)
	ListNof.Size = UDim2.new(0, 206, 0, 400)

	NofList.Name = "NofList"
	NofList.Parent = ListNof
	NofList.SortOrder = Enum.SortOrder.LayoutOrder
	NofList.VerticalAlignment = Enum.VerticalAlignment.Top
	
	function Update:Nof(txt,tine)
		spawn(function()
			local Nof1 = Instance.new("Frame")
			local Nof2 = Instance.new("Frame")
			local Nof3 = Instance.new("Frame")
			local NofLabel = Instance.new("TextLabel")
			local slidenof = Instance.new("Frame")
			local Slide2 = Instance.new("Frame")

			Nof1.Name = "Nof1"
			Nof1.Parent = ListNof
			Nof1.BackgroundColor3 = Color3.fromRGB(51,255,255)
			Nof1.BackgroundTransparency = 1.000
			Nof1.BorderSizePixel = 0
			Nof1.Size = UDim2.new(0, 206, 0, 83)

			Nof2.Name = "Nof2"
			Nof2.Parent = Nof1
			Nof2.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
			Nof2.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Nof2.Position = UDim2.new(0, 0, 0.0120481923, 0)
			Nof2.Size = UDim2.new(0, 189, 0, 65)
			Instance.new("UICorner",Nof2)
			Instance.new("UICorner",slidenof)
			Instance.new("UICorner",Slide2)


			Nof3.Name = "Nof3"
			Nof3.Parent = Nof1
			Nof3.BackgroundColor3 = Color3.fromRGB(90, 90, 255)
			Nof3.BackgroundTransparency = 1
			Nof3.BorderSizePixel = 0
			Nof3.Position = UDim2.new(0, 0, 0.638554215, 0)
			Nof3.Size = UDim2.new(0, 189, 0, 7)

			NofLabel.Name = "NofLabel"
			NofLabel.Parent = Nof1
			NofLabel.BackgroundColor3 = Color3.fromRGB(51,255,255)
			NofLabel.BackgroundTransparency = 1.000
			NofLabel.BorderSizePixel = 0
			NofLabel.Position = UDim2.new(0, 0, 0.00463949936, 0)
			NofLabel.Size = UDim2.new(0, 188, 0, 52)
			NofLabel.ZIndex = 4
			NofLabel.Font = Enum.Font.Code
			NofLabel.TextColor3 = main_color or Color3.fromRGB(51,255,255)
			NofLabel.TextScaled = false
			NofLabel.TextSize = 18.000
			NofLabel.TextStrokeTransparency = 0.100
			NofLabel.TextTransparency = 0.100
			NofLabel.TextWrapped = true
			NofLabel.Text = txt or ""

			slidenof.Name = "slidenof"
			slidenof.Parent = Nof1
			slidenof.BackgroundColor3 = Color3.fromRGB(100, 100, 255)
			slidenof.BorderSizePixel = 0
			slidenof.Position = UDim2.new(0, 0, 0.638554215, 0)
			slidenof.Size = UDim2.new(0, 189, 0, 7)

			Slide2.Name = "Slide2"
			Slide2.Parent = Nof1
			Slide2.BorderSizePixel = 0
			Slide2.BackgroundColor3 = main_color or Color3.fromRGB(51,255,255)
			Slide2.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Slide2.Position = UDim2.new(0, 0, 0.0120481923, 0)
			Slide2.Size = UDim2.new(0, 0, 0, 65)
			Slide2.ZIndex = 15
			Slide2.Visible = false

			tween:Create(slidenof,tweeninfo(tine or 2),{Size = UDim2.new(0, 0, 0, 7)}):Play()
			wait(tine or 2)
			Slide2.Visible = true
			tween:Create(Slide2,tweeninfo(0.2),{Size = UDim2.new(0, 190, 0, 65)}):Play()
			wait(0.2)
			tween:Create(Slide2,tweeninfo(0.2),{Size = UDim2.new(0, 0, 0, 65)}):Play()
			tween:Create(Nof3,tweeninfo(0.2),{Size = UDim2.new(0, 0, 0, 7)}):Play()
			tween:Create(NofLabel,tweeninfo(0.2),{Size = UDim2.new(0, 0, 0, 52)}):Play()
			tween:Create(Nof2,tweeninfo(0.2),{Size = UDim2.new(0, 0, 0, 65)}):Play()
			wait(0.2)
			Nof2.Visible = false
			game.Debris:AddItem(Nof1,0)
		end)
	end

 
function Update:AddNotification(textdesc)
    local NotificationFrame = Instance.new("Frame")
    local OkayBtn = Instance.new("TextButton")
    local OkayBtnCorner = Instance.new("UICorner")
    local NotificationTitle = Instance.new("TextLabel")
    local NotificationDesc = Instance.new("TextLabel")
    local NotifCorner = Instance.new("UICorner")
    local NotifHolderUIStroke = Instance.new("UIStroke")
    local Line = Instance.new("Frame")

    local SectionColor = _G.SectionColor or Color3.fromRGB(255, 255, 255)
    local defaultOkayColor = Color3.fromRGB(12, 12, 12)

    NotificationFrame.Name = "NotificationFrame"
    NotificationFrame.Parent = RebornXer_Hub
    NotificationFrame.AnchorPoint = Vector2.new(0.5, 0.5) -- ตั้งจุดยึดตรงกลาง
    NotificationFrame.BackgroundColor3 = Color3.fromRGB(15, 15, 15)
    NotificationFrame.BorderColor3 = SectionColor
    NotificationFrame.BorderSizePixel = 0
    NotificationFrame.ClipsDescendants = true
    NotificationFrame.Position = UDim2.new(0.5, 0, 0.5, 0) -- ตั้งตำแหน่งตรงกลางจอ
    NotificationFrame.Size = UDim2.new(0, 0, 0, 0)

    NotificationFrame:TweenSize(UDim2.new(0, 400, 0, 200), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)

    NotifCorner.Parent = NotificationFrame
    NotifCorner.CornerRadius = UDim.new(0, 10) -- เพิ่มความโค้งเล็กน้อย

    NotifHolderUIStroke.Parent = NotificationFrame
    NotifHolderUIStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
    NotifHolderUIStroke.Color = SectionColor
    NotifHolderUIStroke.Thickness = 1

    OkayBtn.Name = "OkayBtn"
    OkayBtn.Parent = NotificationFrame
    OkayBtn.BackgroundColor3 = defaultOkayColor
    OkayBtn.BorderSizePixel = 1
    OkayBtn.BorderColor3 = SectionColor
    OkayBtn.Position = UDim2.new(0.95, -25, 0.02, 0) -- ปุ่มปิดอยู่มุมขวาบน
    OkayBtn.Size = UDim2.new(0, 30, 0, 30)
    OkayBtn.Text = "X"
    OkayBtn.TextColor3 = Color3.fromRGB(255, 0, 0)
    OkayBtn.TextSize = 22.000

    OkayBtnCorner.CornerRadius = UDim.new(0, 5)
    OkayBtnCorner.Parent = OkayBtn

    NotificationTitle.Parent = NotificationFrame
    NotificationTitle.BackgroundTransparency = 1.000
    NotificationTitle.Position = UDim2.new(0.5, -200, 0, 20) -- ตำแหน่งกลาง
    NotificationTitle.Size = UDim2.new(0, 400, 0, 40)
    NotificationTitle.Font = Enum.Font.Code
    NotificationTitle.Text = "Notification"
    NotificationTitle.TextColor3 = Color3.fromRGB(0, 255, 255)
    NotificationTitle.TextSize = 28.000
    NotificationTitle.TextXAlignment = Enum.TextXAlignment.Center

    Line.Parent = NotificationFrame
    Line.BackgroundColor3 = SectionColor
    Line.BorderSizePixel = 0
    Line.Position = UDim2.new(0, 0, 0, 70)
    Line.Size = UDim2.new(1, 0, 0, 2)

    NotificationDesc.Parent = NotificationFrame
    NotificationDesc.BackgroundTransparency = 1.000
    NotificationDesc.Position = UDim2.new(0.5, -180, 0, 80)
    NotificationDesc.Size = UDim2.new(0, 360, 0, 100) -- ปรับขนาดข้อความให้เหมาะกับกรอบ
    NotificationDesc.Font = Enum.Font.Code
    NotificationDesc.Text = textdesc
    NotificationDesc.TextColor3 = _G.SectionTextColor or Color3.fromRGB(255, 255, 255)
    NotificationDesc.TextSize = 18.000
    NotificationDesc.TextWrapped = true
    NotificationDesc.TextXAlignment = Enum.TextXAlignment.Center

    OkayBtn.MouseEnter:Connect(function()
        TweenService:Create(OkayBtn, TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {BackgroundColor3 = Color3.fromRGB(30, 30, 30)}):Play()
    end)

    OkayBtn.MouseLeave:Connect(function()
        TweenService:Create(OkayBtn, TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {BackgroundColor3 = defaultOkayColor}):Play()
    end)

    OkayBtn.MouseButton1Click:Connect(function()
        NotificationFrame:TweenSize(UDim2.new(0, 0, 0, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
        wait(0.6)
        NotificationFrame:Destroy()
    end)
end



local Tab = Instance.new("ImageLabel")
local WindowStrokelol = Instance.new("UIStroke")
 Tab.Name = "Tab"
 Tab.Parent = Top
 Tab.BackgroundColor3 = Color3.fromRGB(42, 42, 42)
 Tab.ImageTransparency = 1
 Tab.Position = UDim2.new(0, 160, 0, -2)
 Tab.Size = UDim2.new(0, 410, 0, 29)
 Tab.Image = "rbxassetid://6675147486"
 
 WindowStrokelol.Name = "WindowStroke"
 WindowStrokelol.Parent = Tab
 WindowStrokelol.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
 WindowStrokelol.Color = Color3.fromRGB(255,255,255)
 WindowStrokelol.LineJoinMode = Enum.LineJoinMode.Round
 WindowStrokelol.Thickness = 1
 WindowStrokelol.Transparency = 0
 WindowStrokelol.Enabled = true
 WindowStrokelol.Archivable = true
 
 local TCNR = Instance.new("UICorner")
 TCNR.Name = "TCNR"
 TCNR.Parent = Tab
 
 local ScrollTab = Instance.new("ScrollingFrame")
 ScrollTab.Name = "ScrollTab"
 ScrollTab.Parent = Tab
 ScrollTab.Active = true
 ScrollTab.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
 ScrollTab.BackgroundTransparency = 0
 ScrollTab.Size = UDim2.new(0, 433, 0, 29)
 ScrollTab.CanvasSize = UDim2.new(0, 0, 0, 0)
 ScrollTab.ScrollBarThickness = 0
 
 local PLL = Instance.new("UIListLayout")
 PLL.Name = "PLL"
 PLL.Parent = ScrollTab
 PLL.FillDirection = Enum.FillDirection.Horizontal
 PLL.SortOrder = Enum.SortOrder.LayoutOrder
 PLL.Padding = UDim.new(0)
 
 local PPD = Instance.new("UIPadding")
 PPD.Name = "PPD"
 PPD.Parent = ScrollTab
 PPD.PaddingLeft = UDim.new(0.01)
 
 local Page = Instance.new("Frame")
 local WindowStrokeshit = Instance.new("UIStroke")
 Page.Name = "Page"
 Page.Parent = Main
 Page.BackgroundColor3 = Color3.fromRGB(42, 42, 42)
 Page.BackgroundTransparency = 1
 Page.Position = UDim2.new(0, 1, 0.100000003, -5)
 Page.Size = UDim2.new(0, 300, 0, 380)
 
 WindowStrokeshit.Name = "WindowStroke"
 WindowStrokeshit.Parent = Page
 WindowStrokeshit.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
 WindowStrokeshit.Color = Color3.fromRGB(255,255,255)
 WindowStrokeshit.LineJoinMode = Enum.LineJoinMode.Round
 WindowStrokeshit.Thickness = 1
 WindowStrokeshit.Transparency = 0
 WindowStrokeshit.Archivable = false
 WindowStrokeshit.Enabled = true
 
 local lolshit = Instance.new("UICorner")
 
 lolshit.Parent = Top1
 
 
 local PCNR = Instance.new("UICorner")
 PCNR.Name = "PCNR"
 PCNR.Parent = Page
 
 local MainPage = Instance.new("Frame")
 MainPage.Name = "MainPage"
 MainPage.Parent = Page
 MainPage.ClipsDescendants = true
 MainPage.BackgroundColor3 = Color3.fromRGB(255,255,255)
 MainPage.BackgroundTransparency = 1.000
 MainPage.Size = UDim2.new(0, 300, 0, 380)
 
 local PageList = Instance.new("Folder")
 PageList.Name = "PageList"
 PageList.Parent = MainPage
 
 local UIPageLayout = Instance.new("UIPageLayout")
 
 UIPageLayout.Parent = PageList
 UIPageLayout.SortOrder = Enum.SortOrder.LayoutOrder
 UIPageLayout.EasingDirection = Enum.EasingDirection.InOut
 UIPageLayout.EasingStyle = Enum.EasingStyle.Quad
 UIPageLayout.FillDirection = Enum.FillDirection.Vertical
 UIPageLayout.Padding = UDim.new(0, 15)
 UIPageLayout.TweenTime = 0.400
 UIPageLayout.GamepadInputEnabled = false
 UIPageLayout.ScrollWheelInputEnabled = false
 UIPageLayout.TouchInputEnabled = false

local Page2 = Instance.new("Frame")
 local WindowStrokeshit2 = Instance.new("UIStroke")
 Page2.Name = "Page2"
 Page2.Parent = Main
 Page2.BackgroundColor3 = Color3.fromRGB(42, 42, 42)
 Page2.BackgroundTransparency = 1
 Page2.Position = UDim2.new(0, 302, 0.100000003, -5)
 Page2.Size = UDim2.new(0, 300, 0, 378)
 
 WindowStrokeshit2.Name = "WindowStroke"
 WindowStrokeshit2.Parent = Page2
 WindowStrokeshit2.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
 WindowStrokeshit2.Color = Color3.fromRGB(255,255,255)
 WindowStrokeshit2.LineJoinMode = Enum.LineJoinMode.Round
 WindowStrokeshit2.Thickness = 1
 WindowStrokeshit2.Transparency = 0
 WindowStrokeshit2.Archivable = false
 WindowStrokeshit2.Enabled = true
 
 local lolshit2 = Instance.new("UICorner")
 
 lolshit2.Parent = Top1
 
 
 local PCNR2 = Instance.new("UICorner")
 PCNR2.Name = "PCNR"
 PCNR2.Parent = Page2
 
 local MainPage2 = Instance.new("Frame")
 MainPage2.Name = "MainPage"
 MainPage2.Parent = Page2
 MainPage2.ClipsDescendants = true
 MainPage2.BackgroundColor3 = Color3.fromRGB(255,255,255)
 MainPage2.BackgroundTransparency = 1.000
 MainPage2.Size = UDim2.new(0, 300, 0, 378)
 
 local PageList2 = Instance.new("Folder")
 PageList2.Name = "PageList"
 PageList2.Parent = MainPage2
 
 local UIPageLayout2 = Instance.new("UIPageLayout")
 
 UIPageLayout2.Parent = PageList2
 UIPageLayout2.SortOrder = Enum.SortOrder.LayoutOrder
 UIPageLayout2.EasingDirection = Enum.EasingDirection.InOut
 UIPageLayout2.EasingStyle = Enum.EasingStyle.Quad
 UIPageLayout2.FillDirection = Enum.FillDirection.Vertical
 UIPageLayout2.Padding = UDim.new(0, 15)
 UIPageLayout2.TweenTime = 0.400
 UIPageLayout2.GamepadInputEnabled = false
 UIPageLayout2.ScrollWheelInputEnabled = false
 UIPageLayout2.TouchInputEnabled = false
 
 MakeDraggable(Top,Main)
 
local TweenService = game:GetService("TweenService")
local UserInputService = game:GetService("UserInputService")

local uihide = false
UserInputService.InputBegan:Connect(function(input)
    if input.KeyCode == Enum.KeyCode[yoo] then -- แก้ไขเป็น KeyCode ที่ต้องการ
        if uihide == false then
            uihide = true
            local tween = TweenService:Create(
                Main,
                TweenInfo.new(0.35, Enum.EasingStyle.Sine, Enum.EasingDirection.In), -- กำหนดเวลา 1 วินาที
                {Size = UDim2.new(0, 0, 0, 0)}
            )
            tween:Play()
        else
            uihide = false
            local tween = TweenService:Create(
                Main,
                TweenInfo.new(0.35, Enum.EasingStyle.Sine, Enum.EasingDirection.Out), -- กำหนดเวลา 1 วินาที
                {Size = UDim2.new(0, 600, 0, 400)}
            )
            tween:Play()
        end
    end
end)
	


 
	local uitab = {}
	
	function uitab:AddTab(text, img)
		local TabButton = Instance.new("TextButton")
		local TabImage = Instance.new("ImageLabel")
		local WindowStroke = Instance.new("UIStroke")
		local Label3 = Instance.new("TextLabel")
		local LabelTitle = Instance.new("TextLabel")
local LabelTitle = Instance.new("TextLabel")

		TabButton.Parent = ScrollTab
		TabButton.Name = text.."Server"
		TabButton.Text = text
		TabButton.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
		TabButton.BackgroundTransparency = 0.1
		TabButton.Position = UDim2.new(0, 2, 0, 0)
		TabButton.Size = UDim2.new(0, 100, 0, 28)
		TabButton.Font = Enum.Font.Code
		TabButton.TextColor3 = Color3.fromRGB(255, 225, 225)
		TabButton.TextSize = 12.000
		TabButton.TextTransparency = 0
		
		
local MCNR1 = Instance.new("UICorner")
	MCNR1.Name = "MCNR"
	MCNR1.Parent = TabButton

WindowStroke.Name = "WindowStroke"
 WindowStroke.Parent = TabButton
 WindowStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
 WindowStroke.Color = Color3.fromRGB(45,45,45)
 WindowStroke.LineJoinMode = Enum.LineJoinMode.Round
 WindowStroke.Thickness = 1
 WindowStroke.Transparency = 0
 WindowStroke.Enabled = true
 WindowStroke.Archivable = true

		local MainFramePage = Instance.new("ScrollingFrame")
		MainFramePage.Name = text.."_Page"
		MainFramePage.Parent = PageList
		MainFramePage.Active = true
		MainFramePage.BackgroundColor3 = Color3.fromRGB(51,255,255)
		MainFramePage.BackgroundTransparency = 1.000
		MainFramePage.BorderSizePixel = 1
		MainFramePage.Size = UDim2.new(0, 390, 0, 370)
		MainFramePage.CanvasSize = UDim2.new(0, 0, 0, 0)
		MainFramePage.ScrollBarThickness = 0
		

		
		local UIPadding = Instance.new("UIPadding")
		local UIListLayout = Instance.new("UIListLayout")
		
		UIPadding.Parent = MainFramePage
		UIPadding.PaddingLeft = UDim.new(0, 10)
		UIPadding.PaddingTop = UDim.new(0, 10)

		UIListLayout.Padding = UDim.new(0,4)
		UIListLayout.Parent = MainFramePage
		UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
		
		TabButton.MouseButton1Click:Connect(function()
        Sound = Instance.new("Sound", game:GetService("Workspace")) -- ตรงนี้ไม่ต้องไปสน นาจา ;0;
Sound.Name = "Notify" -- ชื่อเสียง \;
Sound.SoundId = "rbxassetid://903267862" -- เลขขขขขเสียง ;/
Sound.Looped = false -- วนลูป :>
Sound.Playing = true -- เล่นเสียง :<
Sound.Volume = 1 -- ระดับเสียงงงงงงง ;-;
			for i,v in next, ScrollTab:GetChildren() do
				if v:IsA("TextButton") then
					TweenService:Create(
						v,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0}
					):Play()
				end
				TweenService:Create(
					TabButton,
					TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{TextTransparency = 0}
				):Play()
			end
			for i,v in next, PageList:GetChildren() do
				currentpage = string.gsub(TabButton.Name,"Server","").."_Page"
				if v.Name == currentpage then
					UIPageLayout:JumpTo(v)
				end
			end
		end)

		if abc == false then
            
			for i,v in next, ScrollTab:GetChildren() do
				if v:IsA("TextButton") then
					TweenService:Create(
						v,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0}
					):Play()
				end
				TweenService:Create(
					TabButton,
					TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{TextTransparency = 0}
				):Play()
			end
			UIPageLayout:JumpToIndex(0)
			abc = true
		end
		
		game:GetService("RunService").Stepped:Connect(function()
			pcall(function()
				MainFramePage.CanvasSize = UDim2.new(0,0,0,UIListLayout.AbsoluteContentSize.Y + 20)
				ScrollTab.CanvasSize = UDim2.new(0,PLL.AbsoluteContentSize.X + 20,0,0)
			end)
		end)
 
 coroutine.wrap(function()
 while wait() do
 end
 end)()
 
	 
 
 coroutine.wrap(function()
 while wait() do
 end
 end)()
	
	
	local MainFramePage2 = Instance.new("ScrollingFrame")
		MainFramePage2.Name = text.."_Page"
		MainFramePage2.Parent = PageList2
		MainFramePage2.Active = true
		MainFramePage2.BackgroundColor3 = Color3.fromRGB(51,255,255)
		MainFramePage2.BackgroundTransparency = 1.000
		MainFramePage2.BorderSizePixel = 0
		MainFramePage2.Size = UDim2.new(0, 320, 0, 370)
		MainFramePage2.CanvasSize = UDim2.new(0, 0, 0, 0)
		MainFramePage2.ScrollBarThickness = 0
		
		local UIPadding2 = Instance.new("UIPadding")
		local UIListLayout2 = Instance.new("UIListLayout")
		
		UIPadding2.Parent = MainFramePage2
		UIPadding2.PaddingLeft = UDim.new(0, 10)
		UIPadding2.PaddingTop = UDim.new(0, 10)

		UIListLayout2.Padding = UDim.new(0,4)
		UIListLayout2.Parent = MainFramePage2
		UIListLayout2.SortOrder = Enum.SortOrder.LayoutOrder
		
		TabButton.MouseButton1Click:Connect(function()
			for i,v in next, ScrollTab:GetChildren() do
				if v:IsA("TextButton") then
					TweenService:Create(
						v,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0}
					):Play()
				end
				TweenService:Create(
					TabButton,
					TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{TextTransparency = 0}
				):Play()
			end
			for i,v in next, PageList2:GetChildren() do
				currentpage = string.gsub(TabButton.Name,"Server","").."_Page"
				if v.Name == currentpage then
					UIPageLayout2:JumpTo(v)
				end
			end
		end)

		if abc == false then
			for i,v in next, ScrollTab:GetChildren() do
				if v:IsA("TextButton") then
					TweenService:Create(
						v,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0}
					):Play()
				end
				TweenService:Create(
					TabButton,
					TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{TextTransparency = 0}
				):Play()
			end
			UIPageLayout2:JumpToIndex(0)
			abc = true
		end
		
		game:GetService("RunService").Stepped:Connect(function()
			pcall(function()
				MainFramePage2.CanvasSize = UDim2.new(0,0,0,UIListLayout2.AbsoluteContentSize.Y + 20)
				ScrollTab.CanvasSize = UDim2.new(0,PLL.AbsoluteContentSize.X + 20,0,0)
			end)
		end)
 
 coroutine.wrap(function()
 while wait() do
 end
 end)()
 
	 
 
 coroutine.wrap(function()
 while wait() do
 end
 end)()
	local abcd = false
	 function uitab:AddTabH(text,img)
	 local mainDiscord = Instance.new("ImageButton")

	 mainDiscord.Name = "mainDiscord"
    mainDiscord.Parent = Top
    mainDiscord.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    mainDiscord.BackgroundTransparency = 1.000
    mainDiscord.Position = UDim2.new(0, 565, 0, 0)
    mainDiscord.Size = UDim2.new(0, 30, 0, 30)
    mainDiscord.Image = "rbxassetid://"..tostring(img)
    mainDiscord.ImageColor3 = Color3.fromRGB(200, 200, 200)
    
        local MainFramePage = Instance.new("ScrollingFrame")
		MainFramePage.Name = text.."_Page"
		MainFramePage.Parent = PageList
		MainFramePage.Active = true
		MainFramePage.BackgroundColor3 = Color3.fromRGB(51,255,255)
		MainFramePage.BackgroundTransparency = 1.000
		MainFramePage.BorderSizePixel = 1
		MainFramePage.Size = UDim2.new(0, 390, 0, 370)
		MainFramePage.CanvasSize = UDim2.new(0, 0, 0, 0)
		MainFramePage.ScrollBarThickness = 0
		

		
		local UIPadding = Instance.new("UIPadding")
		local UIListLayout = Instance.new("UIListLayout")
		
		UIPadding.Parent = MainFramePage
		UIPadding.PaddingLeft = UDim.new(0, 10)
		UIPadding.PaddingTop = UDim.new(0, 10)

		UIListLayout.Padding = UDim.new(0,4)
		UIListLayout.Parent = MainFramePage
		UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
		
		mainDiscord.MouseButton1Click:Connect(function()
        Sound = Instance.new("Sound", game:GetService("Workspace")) -- ตรงนี้ไม่ต้องไปสน นาจา ;0;
Sound.Name = "Notify" -- ชื่อเสียง \;
Sound.SoundId = "rbxassetid://3020841054" -- เลขขขขขเสียง ;/
Sound.Looped = false -- วนลูป :>
Sound.Playing = true -- เล่นเสียง :<
Sound.Volume = 1 -- ระดับเสียงงงงงงง ;-;
			for i,v in next, ScrollTab:GetChildren() do
				if v:IsA("TextButton") then
					TweenService:Create(
						v,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0}
					):Play()
				end
				TweenService:Create(
					TabButton,
					TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{TextTransparency = 0}
				):Play()
			end
			for i,v in next, PageList:GetChildren() do
				currentpage2 = string.gsub(TabButton.Name,"Server","").."_Page"
				if v.Name == currentpage2 then
					UIPageLayout:JumpTo(v)
				end
			end
		end)

		if abc == false then
            
			for i,v in next, ScrollTab:GetChildren() do
				if v:IsA("TextButton") then
					TweenService:Create(
						v,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0}
					):Play()
				end
				TweenService:Create(
					TabButton,
					TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{TextTransparency = 0}
				):Play()
			end
			UIPageLayout:JumpToIndex(0)
			abc = true
		end
		
		game:GetService("RunService").Stepped:Connect(function()
			pcall(function()
				MainFramePage.CanvasSize = UDim2.new(0,0,0,UIListLayout.AbsoluteContentSize.Y + 20)
				ScrollTab.CanvasSize = UDim2.new(0,PLL.AbsoluteContentSize.X + 20,0,0)
			end)
		end)
 
 coroutine.wrap(function()
 while wait() do
 end
 end)()
 
	 
 
 coroutine.wrap(function()
 while wait() do
 end
 end)()
	
	
	local MainFramePage2 = Instance.new("ScrollingFrame")
		MainFramePage2.Name = text.."_Page"
		MainFramePage2.Parent = PageList2
		MainFramePage2.Active = true
		MainFramePage2.BackgroundColor3 = Color3.fromRGB(51,255,255)
		MainFramePage2.BackgroundTransparency = 1.000
		MainFramePage2.BorderSizePixel = 0
		MainFramePage2.Size = UDim2.new(0, 320, 0, 370)
		MainFramePage2.CanvasSize = UDim2.new(0, 0, 0, 0)
		MainFramePage2.ScrollBarThickness = 0
		
		local UIPadding2 = Instance.new("UIPadding")
		local UIListLayout2 = Instance.new("UIListLayout")
		
		UIPadding2.Parent = MainFramePage2
		UIPadding2.PaddingLeft = UDim.new(0, 10)
		UIPadding2.PaddingTop = UDim.new(0, 10)

		UIListLayout2.Padding = UDim.new(0,4)
		UIListLayout2.Parent = MainFramePage2
		UIListLayout2.SortOrder = Enum.SortOrder.LayoutOrder
		
		mainDiscord.MouseButton1Click:Connect(function()
			for i,v in next, ScrollTab:GetChildren() do
				if v:IsA("TextButton") then
					TweenService:Create(
						v,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0}
					):Play()
				end
				TweenService:Create(
					TabButton,
					TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{TextTransparency = 0}
				):Play()
			end
			for i,v in next, PageList2:GetChildren() do
				currentpage2 = string.gsub(TabButton.Name,"Server","").."_Page"
				if v.Name == currentpage2 then
					UIPageLayout2:JumpTo(v)
				end
			end
		end)

		if abc == false then
			for i,v in next, ScrollTab:GetChildren() do
				if v:IsA("TextButton") then
					TweenService:Create(
						v,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0}
					):Play()
				end
				TweenService:Create(
					mainDiscord,
					TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{TextTransparency = 0}
				):Play()
			end
			UIPageLayout2:JumpToIndex(0)
			abc = true
		end
		
		game:GetService("RunService").Stepped:Connect(function()
			pcall(function()
				MainFramePage2.CanvasSize = UDim2.new(0,0,0,UIListLayout2.AbsoluteContentSize.Y + 20)
				ScrollTab.CanvasSize = UDim2.new(0,PLL.AbsoluteContentSize.X + 20,0,0)
			end)
		end)
 
 coroutine.wrap(function()
 while wait() do
 end
 end)()

 
	 
 
 coroutine.wrap(function()
 while wait() do
 end
 end)()
	end
	
		local main = {}
		local TweenService = game:GetService("TweenService")

function main:AddButtonR(text, callback)
    if not MainFramePage2 then
        warn("MainFramePage2 is not defined")
        return
    end
    
    local Button2 = Instance.new("Frame")
    local UICorner2 = Instance.new("UICorner")
    local TextBtn2 = Instance.new("TextButton")
    local UICorner_1 = Instance.new("UICorner")
    local Black2 = Instance.new("Frame")
    local UICorner_2 = Instance.new("UICorner")
    
    Button2.Name = "Button"
    Button2.Parent = MainFramePage2
    Button2.BackgroundColor3 = _G.Color or Color3.new(1, 1, 1)
    Button2.Size = UDim2.new(0, 280, 0, 28)
    
    UICorner2.CornerRadius = UDim.new(0, 5)
    UICorner2.Parent = Button2
    
    TextBtn2.Name = "TextBtn"
    TextBtn2.Parent = Button2
    TextBtn2.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
    TextBtn2.Position = UDim2.new(0, 1, 0, 1)
    TextBtn2.Size = UDim2.new(0, 278, 0, 26)
    TextBtn2.AutoButtonColor = false
    TextBtn2.Font = Enum.Font.Code
    TextBtn2.Text = text
    TextBtn2.TextColor3 = Color3.fromRGB(225, 225, 225)
    TextBtn2.TextSize = 12
    
    UICorner_1.CornerRadius = UDim.new(0, 5)
    UICorner_1.Parent = TextBtn2
    
    Black2.Name = "Black"
    Black2.Parent = Button2
    Black2.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
    Black2.BackgroundTransparency = 1
    Black2.BorderSizePixel = 0
    Black2.Position = UDim2.new(0, 1, 0, 1)
    Black2.Size = UDim2.new(0, 280, 0, 26)
    
    UICorner_2.CornerRadius = UDim.new(0, 5)
    UICorner_2.Parent = Black2

    TextBtn2.MouseEnter:Connect(function()
        local tween = TweenService:Create(
            Black2,
            TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
            {BackgroundTransparency = 0.7}
        )
        tween:Play()
    end)
    
    TextBtn2.MouseLeave:Connect(function()
        local tween = TweenService:Create(
            Black2,
            TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
            {BackgroundTransparency = 1}
        )
        tween:Play()
    end)
    
    TextBtn2.MouseButton1Click:Connect(function()
        TextBtn2.TextSize = 0
        local tween = TweenService:Create(
            TextBtn2,
            TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
            {TextSize = 12}
        )
        tween:Play()
        if callback then
            callback()
        else
            warn("Callback function is not defined")
        end
    end)
end

function main:AddButtonL(text, callback)
    if not MainFramePage then
        warn("MainFramePage is not defined")
        return
    end

    local Button = Instance.new("Frame")
    local UICorner = Instance.new("UICorner")
    local TextBtn = Instance.new("TextButton")
    local UICorner_2 = Instance.new("UICorner")
    local Black = Instance.new("Frame")
    local UICorner_3 = Instance.new("UICorner")
    
    Button.Name = "Button"
    Button.Parent = MainFramePage
    Button.BackgroundColor3 = _G.Color or Color3.new(1, 1, 1)
    Button.Size = UDim2.new(0, 280, 0, 28)
    
    UICorner.CornerRadius = UDim.new(0, 5)
    UICorner.Parent = Button
    
    TextBtn.Name = "TextBtn"
    TextBtn.Parent = Button
    TextBtn.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
    TextBtn.Position = UDim2.new(0, 1, 0, 1)
    TextBtn.Size = UDim2.new(0, 278, 0, 26)
    TextBtn.AutoButtonColor = false
    TextBtn.Font = Enum.Font.Code
    TextBtn.Text = text
    TextBtn.TextColor3 = Color3.fromRGB(225, 225, 225)
    TextBtn.TextSize = 12
    
    UICorner_2.CornerRadius = UDim.new(0, 5)
    UICorner_2.Parent = TextBtn
    
    Black.Name = "Black"
    Black.Parent = Button
    Black.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
    Black.BackgroundTransparency = 1
    Black.BorderSizePixel = 0
    Black.Position = UDim2.new(0, 1, 0, 1)
    Black.Size = UDim2.new(0, 280, 0, 26)
    
    UICorner_3.CornerRadius = UDim.new(0, 5)
    UICorner_3.Parent = Black

    TextBtn.MouseEnter:Connect(function()
        local tween = TweenService:Create(
            Black,
            TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
            {BackgroundTransparency = 0.7}
        )
        tween:Play()
    end)
    
    TextBtn.MouseLeave:Connect(function()
        local tween = TweenService:Create(
            Black,
            TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
            {BackgroundTransparency = 1}
        )
        tween:Play()
    end)
    
    TextBtn.MouseButton1Click:Connect(function()
        TextBtn.TextSize = 0
        local tween = TweenService:Create(
            TextBtn,
            TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
            {TextSize = 12}
        )
        tween:Play()
        if callback then
            callback()
        else
            warn("Callback function is not defined")
        end
    end)
end
		function main:AddToggleL(text,config,callback)
			config = config or false
			local toggled = config
			local Toggle = Instance.new("Frame")
			local UICorner = Instance.new("UICorner")
		local Button = Instance.new("TextButton")
		local True = Instance.new("TextLabel")
			local UICorner_2 = Instance.new("UICorner")
			local Label = Instance.new("TextLabel")
			local ToggleImage = Instance.new("Frame")
			local UICorner_3 = Instance.new("UICorner")
			local Circle = Instance.new("ImageLabel")
			local UICorner_4 = Instance.new("UICorner")
local ImageLabel = Instance.new("ImageLabel")
local Space = Instance.new("TextLabel")

			Toggle.Name = "Toggle"
			Toggle.Parent = MainFramePage
			Toggle.BackgroundColor3 = _G.Color
			Toggle.Size = UDim2.new(0, 280, 0, 28)

			UICorner.CornerRadius = UDim.new(0, 5)
			UICorner.Parent = Toggle

			Button.Name = "Button"
			Button.Parent = Toggle
			Button.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
			Button.Position = UDim2.new(0, 1, 0, 1)
			Button.Size = UDim2.new(0, 278, 0, 26)
			Button.AutoButtonColor = false
			Button.Font = Enum.Font.SourceSans
			Button.Text = ""
			Button.TextColor3 = Color3.fromRGB(0, 0, 0)
			Button.TextSize = 11.000

			UICorner_2.CornerRadius = UDim.new(0, 5)
			UICorner_2.Parent = Button

			Label.Name = "Label"
			Label.Parent = Toggle
			Label.BackgroundColor3 = Color3.fromRGB(0,255,255)
			Label.BackgroundTransparency = 1.000
			Label.Position = UDim2.new(0, 1, 0, 1)
			Label.Size = UDim2.new(0, 278, 0, 26)
			Label.Font = Enum.Font.Code
			Label.Text = text
			Label.TextColor3 = Color3.fromRGB(225, 225, 225)
			Label.TextSize = 12.000
			

        ToggleImage.Name = "ToggleImage"
			ToggleImage.Parent = Toggle
			ToggleImage.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
			ToggleImage.Position = UDim2.new(0, 250, 0, 4)
			ToggleImage.Size = UDim2.new(0, 22, 0, 20)

			UICorner_3.CornerRadius = UDim.new(0, 4)
			UICorner_3.Parent = ToggleImage

			Circle.Name = "Circle"
			Circle.Parent = ToggleImage
			Circle.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
			Circle.Position = UDim2.new(0, 2, 0, 2)
			Circle.Size = UDim2.new(0, 18, 0, 16)
			
			True.Name = "True"
			True.Parent = Circle
			True.BackgroundTransparency = 1.000
			True.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			True.Position = UDim2.new(0, 0, 0, 0)
			True.Size = UDim2.new(0, 18, 0, 16)
			True.Font = Enum.Font.SourceSans
			True.Text = ""
			True.TextColor3 = Color3.fromRGB(0, 0, 0)
			True.TextSize = 16.000

			UICorner_4.CornerRadius = UDim.new(0, 0)
			UICorner_4.Parent = Circle

			Button.MouseButton1Click:Connect(function()
				if toggled == false then
					toggled = true
					True.Text = "✔"
					Circle:TweenPosition(UDim2.new(0,2,0,2),"Out","Sine",0,true)
					TweenService:Create(
						Circle,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{BackgroundColor3 = Color3.fromRGB(0, 255, 0)}
					):Play()
				else
					toggled = false
					True.Text = ""
					Circle:TweenPosition(UDim2.new(0,2,0,2),"Out","Sine",0,true)
					TweenService:Create(
						Circle,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{BackgroundColor3 = Color3.fromRGB(30, 30, 30)}
					):Play()
					
				end
				pcall(callback,toggled)
			end)

			if config == true then
				toggled = true
				True.Text = "✔"
				Circle:TweenPosition(UDim2.new(0,2,0,2),"Out","Sine",0,true)
				TweenService:Create(
					Circle,
					TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{BackgroundColor3 = Color3.fromRGB(0, 255, 0)}
				):Play()
				pcall(callback,toggled)
			end
		end
		
function main:AddToggleR(text,config,callback)
			config = config or false
			local toggledd = config
			local Togglee = Instance.new("Frame")
			local UICornerr = Instance.new("UICorner")
			local Truea =Instance.new("TextLabel")
		local Buttonn = Instance.new("TextButton")
			local UICorner_22 = Instance.new("UICorner")
			local Labell = Instance.new("TextLabel")
			local ToggleImagee = Instance.new("Frame")
			local UICorner_33 = Instance.new("UICorner")
			local Circlee = Instance.new("Frame")
			local UICorner_44 = Instance.new("UICorner")
local ImageLabell = Instance.new("ImageLabel")
local Spacee = Instance.new("TextLabel")

			Togglee.Name = "Toggle"
			Togglee.Parent = MainFramePage2
			Togglee.BackgroundColor3 = _G.Color
			Togglee.Size = UDim2.new(0, 280, 0, 28)

			UICornerr.CornerRadius = UDim.new(0, 5)
			UICornerr.Parent = Togglee

			Buttonn.Name = "Button"
			Buttonn.Parent = Togglee
			Buttonn.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
			Buttonn.Position = UDim2.new(0, 1, 0, 1)
			Buttonn.Size = UDim2.new(0, 278, 0, 26)
			Buttonn.AutoButtonColor = false
			Buttonn.Font = Enum.Font.SourceSans
			Buttonn.Text = ""
			Buttonn.TextColor3 = Color3.fromRGB(0, 0, 0)
			Buttonn.TextSize = 11.000

			UICorner_22.CornerRadius = UDim.new(0, 5)
			UICorner_22.Parent = Buttonn

			Labell.Name = "Label"
			Labell.Parent = Togglee
			Labell.BackgroundColor3 = Color3.fromRGB(51,255,255)
			Labell.BackgroundTransparency = 1.000
			Labell.Position = UDim2.new(0, 1, 0, 1)
			Labell.Size = UDim2.new(0, 278, 0, 26)
			Labell.Font = Enum.Font.Code
			Labell.Text = text
			Labell.TextColor3 = Color3.fromRGB(225, 225, 225)
			Labell.TextSize = 12.000
			



		 ToggleImagee.Name = "ToggleImage"
			ToggleImagee.Parent = Togglee
			ToggleImagee.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
			ToggleImagee.Position = UDim2.new(0, 250, 0, 5)
			ToggleImagee.Size = UDim2.new(0, 22, 0, 20)

			UICorner_33.CornerRadius = UDim.new(0, 4)
			UICorner_33.Parent = ToggleImagee

			Circlee.Name = "Circle"
			Circlee.Parent = ToggleImagee
			Circlee.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
			Circlee.Position = UDim2.new(0, 2, 0, 2)
			Circlee.Size = UDim2.new(0, 18, 0, 16)

Truea.Name = "Truea"
			Truea.Parent = Circlee
			Truea.BackgroundTransparency = 1.000
			Truea.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Truea.Position = UDim2.new(0, 0, 0, 0)
			Truea.Size = UDim2.new(0, 18, 0, 16)
			Truea.Font = Enum.Font.SourceSans
			Truea.Text = ""
			Truea.TextColor3 = Color3.fromRGB(0, 0, 0)
			Truea.TextSize = 16.000

			UICorner_44.CornerRadius = UDim.new(0, 0)
			UICorner_44.Parent = Circlee

			Buttonn.MouseButton1Click:Connect(function()
				if toggledd == false then
					toggledd = true
					Truea.Text = "✔"
					Circlee:TweenPosition(UDim2.new(0,2,0,2),"Out","Sine",0,true)
					TweenService:Create(
						Circlee,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{BackgroundColor3 = Color3.fromRGB(0, 255, 0)}
					):Play()
				else
					toggledd = false
					Truea.Text = ""
					Circlee:TweenPosition(UDim2.new(0,2,0,2),"Out","Sine",0,true)
					TweenService:Create(
						Circlee,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{BackgroundColor3 = Color3.fromRGB(30, 30, 30)}
					):Play()
				end
				pcall(callback,toggledd)
			end)

			if config == true then
				toggledd = true
				Truea.Text = "✔"
				Circlee:TweenPosition(UDim2.new(0,2,0,2),"Out","Sine",0,true)
				TweenService:Create(
					Circlee,
					TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{BackgroundColor3 = Color3.fromRGB(0, 255, 0)}
				):Play()
				pcall(callback,toggledd)
			end
		end

		

		
		function main:AddDropdownL(droptitle, list, config, callback)
local config = config or "Select First"
local dropfunc = {}
local list = list or {}
local DropToggled = false
local DropSizeFrame = Instance.new("Frame")
local Frame = Instance.new("Frame")
local UIStroke = Instance.new("UIStroke")
local DropCover = Instance.new("Frame")
local UICorner = Instance.new("UICorner")
local UICorner2 = Instance.new("UICorner")
local ImageLabel = Instance.new("ImageLabel")
local Space = Instance.new("TextLabel")
local Title = Instance.new("TextLabel")
local ImageButton = Instance.new("ImageButton")
local DropStrokeList = Instance.new("UIStroke")
local DropTextList = Instance.new("TextLabel")

-- Prop --
DropSizeFrame.Name = droptitle or "DropSizeFrame"
DropSizeFrame.Parent = MainFramePage
DropSizeFrame.BackgroundColor3 = _G.SectionColor
DropSizeFrame.BackgroundTransparency = 1.000
DropSizeFrame.Size = UDim2.new(0, 280, 0, 60)

Frame.Name = "Frame"
Frame.Parent = DropSizeFrame
Frame.BackgroundColor3 = Color3.fromRGB(30,30,30)
Frame.BorderSizePixel = 0
Frame.Position = UDim2.new(0, 3, 0, 0)
Frame.Size = UDim2.new(0, 278, 0, 60)

UIStroke.Name = "UIStroke"
UIStroke.Parent = Frame
UIStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
UIStroke.Color = Color3.fromRGB(255,255,255)
UIStroke.LineJoinMode = Enum.LineJoinMode.Round
UIStroke.Thickness = 0.7
UIStroke.Transparency = 0
UIStroke.Enabled = true
UIStroke.Archivable = true

UICorner.Parent = Frame
UICorner.CornerRadius = UDim.new(0, 3)

DropCover.Name = "DropCover"
DropCover.Parent = Frame
DropCover.BackgroundColor3 = _G.BackgroundItemColor
DropCover.BackgroundTransparency = 1.000
DropCover.BorderSizePixel = 0
DropCover.Position = UDim2.new(0, 0, 0, 0)
DropCover.Size = UDim2.new(0, 202, 0, 30)

ImageLabel.Name = "ImageLabel"
ImageLabel.Parent = DropCover
ImageLabel.BackgroundColor3 = _G.SectionColor
ImageLabel.BackgroundTransparency = 1.000
ImageLabel.BorderSizePixel = 0
ImageLabel.Position = UDim2.new(0, 5, 0, 6)
ImageLabel.Size = UDim2.new(0, 18, 0, 18)
ImageLabel.Image = "rbxassetid://8825010231"
ImageLabel.ImageColor3 = Color3.fromRGB(255,255,255)

Space.Name = "Space"
Space.Parent = DropCover
Space.BackgroundColor3 = _G.SectionColor
Space.BackgroundTransparency = 1.000
Space.Position = UDim2.new(0, 30, 0, 0)
Space.Size = UDim2.new(0, 15, 0, 30)
Space.Font = Enum.Font.Code
Space.Text = "|"
Space.TextSize = 13.000
Space.TextColor3 = Color3.fromRGB(255,255,255)
Space.TextXAlignment = Enum.TextXAlignment.Center

Title.Name = "Title"
Title.Parent = DropCover
Title.BackgroundColor3 = _G.SectionColor
Title.BackgroundTransparency = 1.000
Title.Position = UDim2.new(0, 50, 0, 0)
Title.Size = UDim2.new(0, 207, 0, 30)
Title.Font = Enum.Font.Code
Title.Text = tostring(droptitle) or "drop Title"
Title.TextColor3 = Color3.fromRGB(255,255,255)
Title.TextSize = 12.000
Title.TextXAlignment = Enum.TextXAlignment.Left

ImageButton.Name = "ImageButton"
ImageButton.Parent = DropCover
ImageButton.BackgroundColor3 = _G.WindowBackgroundColor
ImageButton.BackgroundTransparency = 1.000
ImageButton.Position = UDim2.new(0, 250, 0, 7)
ImageButton.Size = UDim2.new(0, 23, 0, 18)
ImageButton.Image = "rbxassetid://6583628103"
ImageButton.ImageColor3 = Color3.fromRGB(51,255,255)
ImageButton.Rotation = 180

DropTextList.Name = "DropTextList"
DropTextList.Parent = Frame
DropTextList.BackgroundColor3 = _G.BackgroundItemColor
DropTextList.BackgroundTransparency = 1.000
DropTextList.Position = UDim2.new(0, 3, 0, 30)
DropTextList.Size = UDim2.new(0, 278, 0, 25)
DropTextList.Font = Enum.Font.Code
DropTextList.Text = v or config or"Select First"
DropTextList.TextColor3 = Color3.fromRGB(255,255,255)
DropTextList.TextSize = 12.000
DropTextList.TextXAlignment = Enum.TextXAlignment.Center

UICorner2.Parent = DropTextList
UICorner2.CornerRadius = UDim.new(0,0)

DropStrokeList.Name = "DropStrokeList"
DropStrokeList.Parent = DropTextList
DropStrokeList.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
DropStrokeList.Color = Color3.fromRGB(255,255,255)
DropStrokeList.LineJoinMode = Enum.LineJoinMode.Round
DropStrokeList.Thickness = 0.2
DropStrokeList.Transparency = 0
DropStrokeList.Enabled = true
DropStrokeList.Archivable = true

-- Adden Local --
local DropItemScroll = Instance.new("ScrollingFrame")
local DropItemLayout = Instance.new("UIListLayout")
local DropItemStroke = Instance.new("UIStroke")

-- Adden Prop --
DropItemScroll.Name = "DropItemScroll"
DropItemScroll.Parent = Frame
DropItemScroll.BackgroundColor3 = _G.SectionColor
DropItemScroll.BackgroundTransparency = 1.000
DropItemScroll.Position = UDim2.new(0, 3, 0, 60)
DropItemScroll.Size = UDim2.new(0, 280, 0, 0)
DropItemScroll.ScrollBarThickness = 0
DropItemScroll.CanvasSize = UDim2.new(0, 0, 0, 0)

DropItemLayout.Name = "DropItemLayout"
DropItemLayout.Parent = DropItemScroll
DropItemLayout.SortOrder = Enum.SortOrder.LayoutOrder
DropItemLayout.Padding = UDim.new(0, 0)

DropItemStroke.Name = "DropItemStroke"
DropItemStroke.Parent = DropItemScroll
DropItemStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
DropItemStroke.Color = Color3.fromRGB(51,255,255)
DropItemStroke.LineJoinMode = Enum.LineJoinMode.Round
DropItemStroke.Thickness = 0
DropItemStroke.Transparency = 0
DropItemStroke.Enabled = true
DropItemStroke.Archivable = true

-- Dropdown Script--
local ItemCount = 0
local FrameSize = 0

ImageButton.MouseButton1Click:Connect(function()
 if DropToggled then
DropToggled = false
DropSizeFrame:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
Frame:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
DropItemScroll:TweenSize(UDim2.new(0, 278, 0, 0), 'InOut', 'Linear', 0.08)
game.TweenService:Create(ImageButton, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
{Rotation = 180}
):Play()
game.TweenService:Create(ImageButton, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
{ImageColor3 = Color3.fromRGB(51,255,255)}
):Play()

 else
DropToggled = true
DropSizeFrame:TweenSize(UDim2.new(0, 278, 0, 65 + FrameSize), 'InOut', 'Linear', 0.08)
Frame:TweenSize(UDim2.new(0, 278, 0, 65 + FrameSize), 'InOut', 'Linear', 0.08)
DropItemScroll:TweenSize(UDim2.new(0, 278, 0, FrameSize), 'InOut', 'Linear', 0.08)
game.TweenService:Create(ImageButton, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
{Rotation = 0}
):Play()
game.TweenService:Create(ImageButton, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
{ImageColor3 = Color3.fromRGB(51,255,255)}
):Play()
 end
end)

for i,v in next, list do
 ItemCount = ItemCount + 1
 if ItemCount == 1 then
FrameSize = 30
 elseif ItemCount == 2 then
FrameSize = 60
 elseif ItemCount == 3 then
FrameSize = 90
 elseif ItemCount >= 3 then
FrameSize = 120
 end
 
 local ItemList = Instance.new("TextButton")
 
 ItemList.Name = "ItemList"
 ItemList.Parent = DropItemScroll
 ItemList.BackgroundColor3 = Color3.fromRGB(51,255,255)
 ItemList.BackgroundTransparency = 1.000
 ItemList.Size = UDim2.new(0, 278, 0, 30)
 ItemList.AutoButtonColor = false
 ItemList.Font = Enum.Font.Code
 ItemList.TextColor3 = Color3.fromRGB(51,255,255)
 ItemList.TextSize = 12.000
 ItemList.Text = v or "None..."
 ItemList.TextXAlignment = Enum.TextXAlignment.Center

 ItemList.MouseEnter:Connect(function()
game.TweenService:Create(ItemList, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
{BackgroundTransparency = 0.8}
):Play()
 end)
 ItemList.MouseLeave:Connect(function()
game.TweenService:Create(ItemList, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
{BackgroundTransparency = 1}
):Play()
 end)
 
 ItemList.MouseButton1Click:Connect(function()
DropTextList.Text = v or "None..."
pcall(callback, v)
DropToggled = false
DropSizeFrame:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
Frame:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
DropItemScroll:TweenSize(UDim2.new(0, 278, 0), 'InOut', 'Linear', 0.08)
game.TweenService:Create(ImageButton, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
{Rotation = 180}
):Play()
game.TweenService:Create(ImageButton, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
{ImageColor3 = Color3.fromRGB(51,255,255)}
):Play()
 end)
 DropItemScroll.CanvasSize = UDim2.new(0, 0, 0, DropItemLayout.AbsoluteContentSize.Y)
end

function dropfunc:Clear()
                    for _,v  in next, DropItemScroll:GetChildren() do
                        if v:IsA("TextButton") then
                            v:Destroy()
                            FrameSize = 0
                            ItemCount = 0
                        end
                    end
                    DropTextList.Text = "Reset Succesfully..."
                    DropToggled = false
                    DropSizeFrame:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
                    Frame:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
                    DropItemScroll:TweenSize(UDim2.new(0, 278, 0), 'InOut', 'Linear', 0.08)
                    game.TweenService:Create(ImageButton, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
                        {Rotation = 180}
                        ):Play()
                    game.TweenService:Create(ImageButton, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
                        {ImageColor3 = Color3.fromRGB(255,255,255)}
                        ):Play()
                end

function dropfunc:Add(newadd)
 newadd = newadd or {}
 ItemCount = ItemCount + 1
 if ItemCount == 1 then
FrameSize = 30
 elseif ItemCount == 2 then
FrameSize = 60
 elseif ItemCount == 3 then
FrameSize = 90
 elseif ItemCount >= 3 then
FrameSize = 120
 end
 
 local ItemList = Instance.new("TextButton")
 ItemList.Name = "ItemList"
 ItemList.Parent = DropItemScroll
 ItemList.BackgroundColor3 = Color3.fromRGB(51,255,255)
 ItemList.BackgroundTransparency = 1.000
 ItemList.Size = UDim2.new(0, 278, 0, 30)
 ItemList.AutoButtonColor = false
 ItemList.Font = Enum.Font.Code
 ItemList.TextColor3 = Color3.fromRGB(51,255,255)
 ItemList.TextSize = 12.000
 ItemList.Text = newadd or "None..."
 ItemList.TextXAlignment = Enum.TextXAlignment.Center

 ItemList.MouseEnter:Connect(function()
game.TweenService:Create(ItemList, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
{BackgroundTransparency = 0.8}
):Play()
 end)
 ItemList.MouseLeave:Connect(function()
game.TweenService:Create(ItemList, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
{BackgroundTransparency = 1}
):Play()
 end)
 
 ItemList.MouseButton1Click:Connect(function()
DropTextList.Text = newadd or "None..."
pcall(callback, newadd)
DropToggled = false
DropSizeFrame:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
Frame:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
DropItemScroll:TweenSize(UDim2.new(0, 278, 0), 'InOut', 'Linear', 0.08)
game.TweenService:Create(ImageButton, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
{Rotation = 180}
):Play()
game.TweenService:Create(ImageButton, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
{ImageColor3 = Color3.fromRGB(51,255,255)}
):Play()
 end)
 DropItemScroll.CanvasSize = UDim2.new(0, 0, 0, DropItemLayout.AbsoluteContentSize.Y)
end
return dropfunc
end

	function main:AddDropdownR(droptitle, list,  config, callback1)
-- Local --
local config = config or "Select First"
local dropfunc1 = {}
local list = list or {}
local DropToggled1 = false
local DropSizeFrame1 = Instance.new("Frame")
local Frame1 = Instance.new("Frame")
local UIStroke1 = Instance.new("UIStroke")
local DropCover1 = Instance.new("Frame")
local UICorner1 = Instance.new("UICorner")
local UICorner21 = Instance.new("UICorner")
local ImageLabel1 = Instance.new("ImageLabel")
local Space1 = Instance.new("TextLabel")
local Title1 = Instance.new("TextLabel")
local ImageButton1 = Instance.new("ImageButton")
local DropStrokeList1 = Instance.new("UIStroke")
local DropTextList1 = Instance.new("TextLabel")

-- Prop --
DropSizeFrame1.Name = droptitle or "DropSizeFrame"
DropSizeFrame1.Parent = MainFramePage2
DropSizeFrame1.BackgroundColor3 = _G.SectionColor
DropSizeFrame1.BackgroundTransparency = 1.000
DropSizeFrame1.Size = UDim2.new(0, 280, 0, 60)

Frame1.Name = "Frame"
Frame1.Parent = DropSizeFrame1
Frame1.BackgroundColor3 = Color3.fromRGB(30,30,30)
Frame1.BorderSizePixel = 0
Frame1.Position = UDim2.new(0, 3, 0, 0)
Frame1.Size = UDim2.new(0, 278, 0, 60)

UIStroke1.Name = "UIStroke"
UIStroke1.Parent = Frame1
UIStroke1.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
UIStroke1.Color = Color3.fromRGB(255,255,255)
UIStroke1.LineJoinMode = Enum.LineJoinMode.Round
UIStroke1.Thickness = 0.7
UIStroke1.Transparency = 0
UIStroke1.Enabled = true
UIStroke1.Archivable = true

UICorner1.Parent = Frame1
UICorner1.CornerRadius = UDim.new(0, 3)

DropCover1.Name = "DropCover"
DropCover1.Parent = Frame1
DropCover1.BackgroundColor3 = _G.BackgroundItemColor
DropCover1.BackgroundTransparency = 1.000
DropCover1.BorderSizePixel = 0
DropCover1.Position = UDim2.new(0, 0, 0, 0)
DropCover1.Size = UDim2.new(0, 204, 0, 30)

ImageLabel1.Name = "ImageLabel"
ImageLabel1.Parent = DropCover1
ImageLabel1.BackgroundColor3 = _G.SectionColor
ImageLabel1.BackgroundTransparency = 1.000
ImageLabel1.BorderSizePixel = 0
ImageLabel1.Position = UDim2.new(0, 5, 0, 6)
ImageLabel1.Size = UDim2.new(0, 18, 0, 18)
ImageLabel1.Image = "rbxassetid://8825010231"
ImageLabel1.ImageColor3 = Color3.fromRGB(255,255,255)

Space1.Name = "Space"
Space1.Parent = DropCover1
Space1.BackgroundColor3 = _G.SectionColor
Space1.BackgroundTransparency = 1.000
Space1.Position = UDim2.new(0, 30, 0, 0)
Space1.Size = UDim2.new(0, 15, 0, 30)
Space1.Font = Enum.Font.Code
Space1.Text = "|"
Space1.TextSize = 13.000
Space1.TextColor3 = Color3.fromRGB(255,255,255)
Space1.TextXAlignment = Enum.TextXAlignment.Center

Title1.Name = "Title"
Title1.Parent = DropCover1
Title1.BackgroundColor3 = _G.SectionColor
Title1.BackgroundTransparency = 1.000
Title1.Position = UDim2.new(0, 50, 0, 0)
Title1.Size = UDim2.new(0, 278, 0, 30)
Title1.Font = Enum.Font.Code
Title1.Text = tostring(droptitle) or "drop Title"
Title1.TextColor3 = Color3.fromRGB(255,255,255)
Title1.TextSize = 12.000
Title1.TextXAlignment = Enum.TextXAlignment.Left

ImageButton1.Name = "ImageButton"
ImageButton1.Parent = DropCover1
ImageButton1.BackgroundColor3 = _G.WindowBackgroundColor
ImageButton1.BackgroundTransparency = 1.000
ImageButton1.Position = UDim2.new(0, 250, 0, 7)
ImageButton1.Size = UDim2.new(0, 23, 0, 18)
ImageButton1.Image = "rbxassetid://6583628103"
ImageButton1.ImageColor3 = Color3.fromRGB(51,255,255)
ImageButton1.Rotation = 180

DropTextList1.Name = "DropTextList"
DropTextList1.Parent = Frame1
DropTextList1.BackgroundColor3 = _G.BackgroundItemColor
DropTextList1.BackgroundTransparency = 1.000
DropTextList1.Position = UDim2.new(0, 3, 0, 30)
DropTextList1.Size = UDim2.new(0, 278, 0, 25)
DropTextList1.Font = Enum.Font.Code
DropTextList1.Text = v or config or "Select First"
DropTextList1.TextColor3 = Color3.fromRGB(255,255,255)
DropTextList1.TextSize = 12.000
DropTextList1.TextXAlignment = Enum.TextXAlignment.Center

UICorner21.Parent = DropTextList1
UICorner21.CornerRadius = UDim.new(0,0)

DropStrokeList1.Name = "DropStrokeList"
DropStrokeList1.Parent = DropTextList1
DropStrokeList1.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
DropStrokeList1.Color = Color3.fromRGB(255,255,255)
DropStrokeList1.LineJoinMode = Enum.LineJoinMode.Round
DropStrokeList1.Thickness = 0.2
DropStrokeList1.Transparency = 0
DropStrokeList1.Enabled = true
DropStrokeList1.Archivable = true

-- Adden Local --
local DropItemScroll1 = Instance.new("ScrollingFrame")
local DropItemLayout1 = Instance.new("UIListLayout")
local DropItemStroke1 = Instance.new("UIStroke")

-- Adden Prop --
DropItemScroll1.Name = "DropItemScroll"
DropItemScroll1.Parent = Frame1
DropItemScroll1.BackgroundColor3 = _G.SectionColor
DropItemScroll1.BackgroundTransparency = 1.000
DropItemScroll1.Position = UDim2.new(0, 3, 0, 60)
DropItemScroll1.Size = UDim2.new(0, 278, 0, 0)
DropItemScroll1.ScrollBarThickness = 0
DropItemScroll1.CanvasSize = UDim2.new(0, 0, 0, 0)

DropItemLayout1.Name = "DropItemLayout"
DropItemLayout1.Parent = DropItemScroll1
DropItemLayout1.SortOrder = Enum.SortOrder.LayoutOrder
DropItemLayout1.Padding = UDim.new(0, 0)

DropItemStroke1.Name = "DropItemStroke"
DropItemStroke1.Parent = DropItemScroll1
DropItemStroke1.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
DropItemStroke1.Color = Color3.fromRGB(51,255,255)
DropItemStroke1.LineJoinMode = Enum.LineJoinMode.Round
DropItemStroke1.Thickness = 0
DropItemStroke1.Transparency = 0
DropItemStroke1.Enabled = true
DropItemStroke1.Archivable = true

-- Dropdown Script--
local ItemCount1 = 0
local FrameSize1 = 0

ImageButton1.MouseButton1Click:Connect(function()
 if DropToggled1 then
DropToggled1 = false
DropSizeFrame1:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
Frame1:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
DropItemScroll1:TweenSize(UDim2.new(0, 278, 0, 0), 'InOut', 'Linear', 0.08)
game.TweenService:Create(ImageButton1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
{Rotation = 180}
):Play()
game.TweenService:Create(ImageButton1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
{ImageColor3 = Color3.fromRGB(51,255,255)}
):Play()

 else
DropToggled1 = true
DropSizeFrame1:TweenSize(UDim2.new(0, 278, 0, 65 + FrameSize1), 'InOut', 'Linear', 0.08)
Frame1:TweenSize(UDim2.new(0, 278, 0, 65 + FrameSize1), 'InOut', 'Linear', 0.08)
DropItemScroll1:TweenSize(UDim2.new(0, 278, 0, FrameSize1), 'InOut', 'Linear', 0.08)
game.TweenService:Create(ImageButton1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
{Rotation = 0}
):Play()
game.TweenService:Create(ImageButton1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
{ImageColor3 = Color3.fromRGB(51,255,255)}
):Play()
 end
end)

for i,v in next, list do
 ItemCount1 = ItemCount1 + 1
 if ItemCount1 == 1 then
FrameSize1 = 30
 elseif ItemCount1 == 2 then
FrameSize1 = 60
 elseif ItemCount1 == 3 then
FrameSize1 = 90
 elseif ItemCount1 >= 3 then
FrameSize1 = 120
 end
 
 local ItemList1 = Instance.new("TextButton")
 
 ItemList1.Name = "ItemList"
 ItemList1.Parent = DropItemScroll1
 ItemList1.BackgroundColor3 = Color3.fromRGB(51,255,255)
 ItemList1.BackgroundTransparency = 1.000
 ItemList1.Size = UDim2.new(0, 278, 0, 30)
 ItemList1.AutoButtonColor = false
 ItemList1.Font = Enum.Font.Code
 ItemList1.TextColor3 = Color3.fromRGB(51,255,255)
 ItemList1.TextSize = 12.000
 ItemList1.Text = v or "None..."
 ItemList1.TextXAlignment = Enum.TextXAlignment.Center

 ItemList1.MouseEnter:Connect(function()
game.TweenService:Create(ItemList1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
{BackgroundTransparency = 0.8}
):Play()
 end)
 ItemList1.MouseLeave:Connect(function()
game.TweenService:Create(ItemList1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
{BackgroundTransparency = 1}
):Play()
 end)
 
 ItemList1.MouseButton1Click:Connect(function()
DropTextList1.Text = v or "None..."
pcall(callback1, v)
DropToggled1 = false
DropSizeFrame1:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
Frame1:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
DropItemScroll1:TweenSize(UDim2.new(0, 278, 0), 'InOut', 'Linear', 0.08)
game.TweenService:Create(ImageButton1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
{Rotation = 180}
):Play()
game.TweenService:Create(ImageButton1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
{ImageColor3 = Color3.fromRGB(51,255,255)}
):Play()
 end)
 DropItemScroll1.CanvasSize = UDim2.new(0, 0, 0, DropItemLayout1.AbsoluteContentSize.Y)
end

               function dropfunc1:Clear()
                    for _,v  in next, DropItemScroll1:GetChildren() do
                        if v:IsA("TextButton") then
                            v:Destroy()
                        end
                    end
                    DropTextList1.Text = "Reset Succesfully"
                    DropToggled1 = false
                    DropSizeFrame1:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
                    Frame1:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
                    DropItemScroll1:TweenSize(UDim2.new(0, 278, 0), 'InOut', 'Linear', 0.08)
                    game.TweenService:Create(ImageButton1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
                        {Rotation = 180}
                        ):Play()
                    game.TweenService:Create(ImageButton1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
                        {ImageColor3 = Color3.fromRGB(255,255,255)}
                        ):Play()
                end

function dropfunc1:Add(newadd)
 newadd = newadd or {}
 ItemCount1 = ItemCount1 + 1
 if ItemCount1 == 1 then
FrameSize1= 30
 elseif ItemCount1 == 2 then
FrameSize1 = 60
 elseif ItemCount1 == 3 then
FrameSize1 = 90
 elseif ItemCount1 >= 3 then
FrameSize1 = 120
 end
 
 local ItemList1 = Instance.new("TextButton")
 ItemList1.Name = "ItemList"
 ItemList1.Parent = DropItemScroll1
 ItemList1.BackgroundColor3 = Color3.fromRGB(255,255,255)
 ItemList1.BackgroundTransparency = 1.000
 ItemList1.Size = UDim2.new(0, 278, 0, 30)
 ItemList1.AutoButtonColor = false
 ItemList1.Font = Enum.Font.Code
 ItemList1.TextColor3 = Color3.fromRGB(51,255,255)
 ItemList1.TextSize = 12.000
 ItemList1.Text = newadd or "None..."
 ItemList1.TextXAlignment = Enum.TextXAlignment.Center

 ItemList1.MouseEnter:Connect(function()
game.TweenService:Create(ItemList1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
{BackgroundTransparency = 0.8}
):Play()
 end)
 ItemList1.MouseLeave:Connect(function()
game.TweenService:Create(ItemList1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
{BackgroundTransparency = 1}
):Play()
 end)
 
 ItemList1.MouseButton1Click:Connect(function()
DropTextList1.Text = newadd or "None..."
pcall(callback1, newadd)
DropToggled1 = false
DropSizeFrame1:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
Frame1:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
DropItemScroll1:TweenSize(UDim2.new(0, 278, 0), 'InOut', 'Linear', 0.08)
game.TweenService:Create(ImageButton1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
{Rotation = 180}
):Play()
game.TweenService:Create(ImageButton1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
{ImageColor3 = Color3.fromRGB(51,255,255)}
):Play()
 end)
 DropItemScroll1.CanvasSize = UDim2.new(0, 0, 0, DropItemLayout1.AbsoluteContentSize.Y)
end
return dropfunc1
end


function main:AddSliderLeft(text,min,max,set,config,callback)
				local config = min or max or set
				local Slider = Instance.new("Frame")
				local slidercorner = Instance.new("UICorner")
				local sliderr = Instance.new("Frame")
				local sliderrcorner = Instance.new("UICorner")
				local SliderLabel = Instance.new("TextLabel")
				local HAHA = Instance.new("Frame")
				local AHEHE = Instance.new("TextButton")
				local bar = Instance.new("Frame")
				local bar1 = Instance.new("Frame")
				local bar1corner = Instance.new("UICorner")
				local barcorner = Instance.new("UICorner")
				local circlebar = Instance.new("Frame")
				local UICorner = Instance.new("UICorner")
				local slidervalue = Instance.new("Frame")
				local valuecorner = Instance.new("UICorner")
				local TextBox = Instance.new("TextBox")
				local UICorner_2 = Instance.new("UICorner")
	
				Slider.Name = "Slider"
				Slider.Parent = MainFramePage
				Slider.BackgroundColor3 = _G.Color
				Slider.BackgroundTransparency = 0
				Slider.Size = UDim2.new(0, 280, 0, 51)
	
				slidercorner.CornerRadius = UDim.new(0, 5)
				slidercorner.Name = "slidercorner"
				slidercorner.Parent = Slider
	
				sliderr.Name = "sliderr"
				sliderr.Parent = Slider
				sliderr.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
				sliderr.Position = UDim2.new(0, 1, 0, 1)
				sliderr.Size = UDim2.new(0, 278, 0, 49)
	
				sliderrcorner.CornerRadius = UDim.new(0, 5)
				sliderrcorner.Name = "sliderrcorner"
				sliderrcorner.Parent = sliderr
	
				SliderLabel.Name = "SliderLabel"
				SliderLabel.Parent = sliderr
				SliderLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				SliderLabel.BackgroundTransparency = 1.000
				SliderLabel.Position = UDim2.new(0, 15, 0, 0)
				SliderLabel.Size = UDim2.new(0, 100, 0, 26)
				SliderLabel.Font = Enum.Font.Code
				SliderLabel.Text = text
				SliderLabel.TextColor3 = Color3.fromRGB(225, 225, 225)
				SliderLabel.TextSize = 16.000
				SliderLabel.TextTransparency = 0
				SliderLabel.TextXAlignment = Enum.TextXAlignment.Left
	
				HAHA.Name = "HAHA"
				HAHA.Parent = sliderr
				HAHA.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				HAHA.BackgroundTransparency = 1.000
				HAHA.Size = UDim2.new(0, 468, 0, 29)
	
				AHEHE.Name = "AHEHE"
				AHEHE.Parent = sliderr
				AHEHE.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				AHEHE.BackgroundTransparency = 1.000
				AHEHE.Position = UDim2.new(0, 10, 0, 35)
				AHEHE.Size = UDim2.new(0, 260, 0, 5)
				AHEHE.Font = Enum.Font.Code
				AHEHE.Text = ""
				AHEHE.TextColor3 = Color3.fromRGB(0, 0, 0)
				AHEHE.TextSize = 14.000
	
				bar.Name = "bar"
				bar.Parent = AHEHE
				bar.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
				bar.Size = UDim2.new(0, 260, 0, 5)
	
				bar1.Name = "bar1"
				bar1.Parent = bar
				bar1.BackgroundColor3 = _G.Color
				bar1.BackgroundTransparency = 0
				bar1.Size = UDim2.new(set/max, 0, 0, 5)
	
				bar1corner.CornerRadius = UDim.new(0, 5)
				bar1corner.Name = "bar1corner"
				bar1corner.Parent = bar1
	
				barcorner.CornerRadius = UDim.new(0, 5)
				barcorner.Name = "barcorner"
				barcorner.Parent = bar
	
				circlebar.Name = "circlebar"
				circlebar.Parent = bar1
				circlebar.BackgroundColor3 = Color3.fromRGB(225, 225, 225)
				circlebar.Position = UDim2.new(1, -2, 0, -3)
				circlebar.Size = UDim2.new(0, 10, 0, 10)
	
				UICorner.CornerRadius = UDim.new(0, 100)
				UICorner.Parent = circlebar
	
				slidervalue.Name = "slidervalue"
				slidervalue.Parent = sliderr
				slidervalue.BackgroundColor3 = _G.Color
				slidervalue.BackgroundTransparency = 0
				slidervalue.Position = UDim2.new(0, 220, 0, 5)
				slidervalue.Size = UDim2.new(0, 50, 0, 15)
	
				valuecorner.CornerRadius = UDim.new(0, 5)
				valuecorner.Name = "valuecorner"
				valuecorner.Parent = slidervalue
	
				TextBox.Parent = slidervalue
				TextBox.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
				TextBox.Position = UDim2.new(0, 1, 0, 1)
				TextBox.Size = UDim2.new(0, 48, 0, 13)
				TextBox.Font = Enum.Font.Code
				TextBox.TextColor3 = Color3.fromRGB(225, 225, 225)
				TextBox.TextSize = 9.000
				TextBox.Text = set
				TextBox.TextTransparency = 0
	
				UICorner_2.CornerRadius = UDim.new(0, 5)
				UICorner_2.Parent = TextBox
	
				local mouse = game.Players.LocalPlayer:GetMouse()
				local uis = game:GetService("UserInputService")
	
				if Value == nil then
					Value = set
					pcall(function()
						callback(Value)
					end)
				end
				
				AHEHE.MouseButton1Down:Connect(function()
					Value = math.floor((((tonumber(max) - tonumber(min)) / 260) * bar1.AbsoluteSize.X) + tonumber(min)) or 0
					pcall(function()
						callback(Value)
					end)
					TweenService:Create(
						bar1,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 260), 0, 5)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					--bar1.Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 448), 0, 5)
					TweenService:Create(
						circlebar,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Position =  UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 260), 0, -3)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					--circlebar.Position = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 438), 0, -3)
					moveconnection = mouse.Move:Connect(function()
						TextBox.Text = Value
						Value = math.floor((((tonumber(max) - tonumber(min)) / 260) * bar1.AbsoluteSize.X) + tonumber(min))
						pcall(function()
							callback(Value)
						end)
						TweenService:Create(
							bar1,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 260), 0, 5)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						--bar1.Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 448), 0, 5)
						TweenService:Create(
							circlebar,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Position =  UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 260), 0, -3)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						--circlebar.Position = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 438), 0, -3)
					end)
					releaseconnection = uis.InputEnded:Connect(function(Mouse)
						if Mouse.UserInputType == Enum.UserInputType.MouseButton1 then
							Value = math.floor((((tonumber(max) - tonumber(min)) / 260) * bar1.AbsoluteSize.X) + tonumber(min))
							pcall(function()
								callback(Value)
							end)
							TweenService:Create(
								bar1,
								TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 260), 0, 5)} -- UDim2.new(0, 128, 0, 25)
							):Play()
							--bar1.Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 448), 0, 5)
							TweenService:Create(
								circlebar,
								TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{Position =  UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 260), 0, -3)} -- UDim2.new(0, 128, 0, 25)
							):Play()
							--circlebar.Position = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 438), 0, -3)
							moveconnection:Disconnect()
							releaseconnection:Disconnect()
						end
					end)
				end)
				releaseconnection = uis.InputEnded:Connect(function(Mouse)
					if Mouse.UserInputType == Enum.UserInputType.MouseButton1 then
						Value = math.floor((((tonumber(max) - tonumber(min)) / 260) * bar1.AbsoluteSize.X) + tonumber(min))
						TextBox.Text = Value
					end
				end)
	
				TextBox.FocusLost:Connect(function()
					if tonumber(TextBox.Text) > max then
						TextBox.Text  = max
					end
					bar1.Size = UDim2.new((TextBox.Text or 0) / max, 0, 0, 5)
					circlebar.Position = UDim2.new(1, -2, 0, -3)
					TextBox.Text = tostring(TextBox.Text and math.floor( (TextBox.Text / max) * (max - min) + min) )
					pcall(callback, TextBox.Text)
				end)
			end

function main:AddSliderRight(text,min,max,set,callback)
				local Slider = Instance.new("Frame")
				local slidercorner = Instance.new("UICorner")
				local sliderr = Instance.new("Frame")
				local sliderrcorner = Instance.new("UICorner")
				local SliderLabel = Instance.new("TextLabel")
				local HAHA = Instance.new("Frame")
				local AHEHE = Instance.new("TextButton")
				local bar = Instance.new("Frame")
				local bar1 = Instance.new("Frame")
				local bar1corner = Instance.new("UICorner")
				local barcorner = Instance.new("UICorner")
				local circlebar = Instance.new("Frame")
				local UICorner = Instance.new("UICorner")
				local slidervalue = Instance.new("Frame")
				local valuecorner = Instance.new("UICorner")
				local TextBox = Instance.new("TextBox")
				local UICorner_2 = Instance.new("UICorner")
	
				Slider.Name = "Slider"
				Slider.Parent = MainFramePage2
				Slider.BackgroundColor3 = _G.Color
				Slider.BackgroundTransparency = 0
				Slider.Size = UDim2.new(0, 280, 0, 51)
	
				slidercorner.CornerRadius = UDim.new(0, 5)
				slidercorner.Name = "slidercorner"
				slidercorner.Parent = Slider
	
				sliderr.Name = "sliderr"
				sliderr.Parent = Slider
				sliderr.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
				sliderr.Position = UDim2.new(0, 1, 0, 1)
				sliderr.Size = UDim2.new(0, 278, 0, 49)
	
				sliderrcorner.CornerRadius = UDim.new(0, 5)
				sliderrcorner.Name = "sliderrcorner"
				sliderrcorner.Parent = sliderr
	
				SliderLabel.Name = "SliderLabel"
				SliderLabel.Parent = sliderr
				SliderLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				SliderLabel.BackgroundTransparency = 1.000
				SliderLabel.Position = UDim2.new(0, 15, 0, 0)
				SliderLabel.Size = UDim2.new(0, 100, 0, 26)
				SliderLabel.Font = Enum.Font.Code
				SliderLabel.Text = text
				SliderLabel.TextColor3 = Color3.fromRGB(225, 225, 225)
				SliderLabel.TextSize = 16.000
				SliderLabel.TextTransparency = 0
				SliderLabel.TextXAlignment = Enum.TextXAlignment.Left
	
				HAHA.Name = "HAHA"
				HAHA.Parent = sliderr
				HAHA.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				HAHA.BackgroundTransparency = 1.000
				HAHA.Size = UDim2.new(0, 468, 0, 29)
	
				AHEHE.Name = "AHEHE"
				AHEHE.Parent = sliderr
				AHEHE.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				AHEHE.BackgroundTransparency = 1.000
				AHEHE.Position = UDim2.new(0, 10, 0, 35)
				AHEHE.Size = UDim2.new(0, 260, 0, 5)
				AHEHE.Font = Enum.Font.Code
				AHEHE.Text = ""
				AHEHE.TextColor3 = Color3.fromRGB(0, 0, 0)
				AHEHE.TextSize = 14.000
	
				bar.Name = "bar"
				bar.Parent = AHEHE
				bar.BackgroundColor3 = Color3.fromRGB(45,45,45)
				bar.Size = UDim2.new(0, 260, 0, 5)
	
				bar1.Name = "bar1"
				bar1.Parent = bar
				bar1.BackgroundColor3 = _G.Color
				bar1.BackgroundTransparency = 0
				bar1.Size = UDim2.new(set/max, 0, 0, 5)
	
				bar1corner.CornerRadius = UDim.new(0, 5)
				bar1corner.Name = "bar1corner"
				bar1corner.Parent = bar1
	
				barcorner.CornerRadius = UDim.new(0, 5)
				barcorner.Name = "barcorner"
				barcorner.Parent = bar
	
				circlebar.Name = "circlebar"
				circlebar.Parent = bar1
				circlebar.BackgroundColor3 = Color3.fromRGB(225, 225, 225)
				circlebar.Position = UDim2.new(1, -2, 0, -3)
				circlebar.Size = UDim2.new(0, 10, 0, 10)
	
				UICorner.CornerRadius = UDim.new(0, 100)
				UICorner.Parent = circlebar
	
				slidervalue.Name = "slidervalue"
				slidervalue.Parent = sliderr
				slidervalue.BackgroundColor3 = _G.Color
				slidervalue.BackgroundTransparency = 0
				slidervalue.Position = UDim2.new(0, 220, 0, 5)
				slidervalue.Size = UDim2.new(0, 50, 0, 15)
	
				valuecorner.CornerRadius = UDim.new(0, 5)
				valuecorner.Name = "valuecorner"
				valuecorner.Parent = slidervalue
	
				TextBox.Parent = slidervalue
				TextBox.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
				TextBox.Position = UDim2.new(0, 1, 0, 1)
				TextBox.Size = UDim2.new(0, 48, 0, 13)
				TextBox.Font = Enum.Font.Code
				TextBox.TextColor3 = Color3.fromRGB(225, 225, 225)
				TextBox.TextSize = 9.000
				TextBox.Text = set
				TextBox.TextTransparency = 0
	
				UICorner_2.CornerRadius = UDim.new(0, 5)
				UICorner_2.Parent = TextBox
	
				local mouse = game.Players.LocalPlayer:GetMouse()
				local uis = game:GetService("UserInputService")
	
				if Value == nil then
					Value = set
					pcall(function()
						callback(Value)
					end)
				end
				
				AHEHE.MouseButton1Down:Connect(function()
					Value = math.floor((((tonumber(max) - tonumber(min)) / 260) * bar1.AbsoluteSize.X) + tonumber(min)) or 0
					pcall(function()
						callback(Value)
					end)
					TweenService:Create(
						bar1,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 260), 0, 5)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					--bar1.Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 448), 0, 5)
					TweenService:Create(
						circlebar,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Position =  UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 260), 0, -3)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					--circlebar.Position = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 438), 0, -3)
					moveconnection = mouse.Move:Connect(function()
						TextBox.Text = Value
						Value = math.floor((((tonumber(max) - tonumber(min)) / 260) * bar1.AbsoluteSize.X) + tonumber(min))
						pcall(function()
							callback(Value)
						end)
						TweenService:Create(
							bar1,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 260), 0, 5)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						--bar1.Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 448), 0, 5)
						TweenService:Create(
							circlebar,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Position =  UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 260), 0, -3)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						--circlebar.Position = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 438), 0, -3)
					end)
					releaseconnection = uis.InputEnded:Connect(function(Mouse)
						if Mouse.UserInputType == Enum.UserInputType.MouseButton1 then
							Value = math.floor((((tonumber(max) - tonumber(min)) / 260) * bar1.AbsoluteSize.X) + tonumber(min))
							pcall(function()
								callback(Value)
							end)
							TweenService:Create(
								bar1,
								TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 260), 0, 5)} -- UDim2.new(0, 128, 0, 25)
							):Play()
							--bar1.Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 448), 0, 5)
							TweenService:Create(
								circlebar,
								TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{Position =  UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 260), 0, -3)} -- UDim2.new(0, 128, 0, 25)
							):Play()
							--circlebar.Position = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 438), 0, -3)
							moveconnection:Disconnect()
							releaseconnection:Disconnect()
						end
					end)
				end)
				releaseconnection = uis.InputEnded:Connect(function(Mouse)
					if Mouse.UserInputType == Enum.UserInputType.MouseButton1 then
						Value = math.floor((((tonumber(max) - tonumber(min)) / 260) * bar1.AbsoluteSize.X) + tonumber(min))
						TextBox.Text = Value
					end
				end)
	
				TextBox.FocusLost:Connect(function()
					if tonumber(TextBox.Text) > max then
						TextBox.Text  = max
					end
					bar1.Size = UDim2.new((TextBox.Text or 0) / max, 0, 0, 5)
					circlebar.Position = UDim2.new(1, -2, 0, -3)
					TextBox.Text = tostring(TextBox.Text and math.floor( (TextBox.Text / max) * (max - min) + min) )
					pcall(callback, TextBox.Text)
				end)
			end



		function main:AddTextboxLeft(text,texts,disappear,callback)
			local Textbox = Instance.new("Frame")
			local TextboxCorner = Instance.new("UICorner")
			local Textboxx = Instance.new("Frame")
			local TextboxxCorner = Instance.new("UICorner")
			local TextboxLabel = Instance.new("TextLabel")
			local txtbtn = Instance.new("TextButton")
			local RealTextbox = Instance.new("TextBox")
			local UICorner = Instance.new("UICorner")

         
			Textbox.Name = "Textbox"
			Textbox.Parent = MainFramePage
			Textbox.BackgroundColor3 = _G.Color
			Textbox.BackgroundTransparency = 0
			Textbox.Size = UDim2.new(0, 280, 0, 57)

			TextboxCorner.CornerRadius = UDim.new(0, 5)
			TextboxCorner.Name = "TextboxCorner"
			TextboxCorner.Parent = Textbox

			Textboxx.Name = "Textboxx"
			Textboxx.Parent = Textbox
			Textboxx.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
			Textboxx.Position = UDim2.new(0, 1, 0, 1)
			Textboxx.Size = UDim2.new(0, 278, 0, 55)

			TextboxxCorner.CornerRadius = UDim.new(0, 5)
			TextboxxCorner.Name = "TextboxxCorner"
			TextboxxCorner.Parent = Textboxx

		
			txtbtn.Name = "txtbtn"
			txtbtn.Parent = Textbox
			txtbtn.BackgroundColor3 = Color3.fromRGB(51,255,255)
			txtbtn.BackgroundTransparency = 1.000
			txtbtn.Position = UDim2.new(0, 1, 0, 1)
			txtbtn.Size = UDim2.new(0, 278, 0, 45)
			txtbtn.Font = Enum.Font.SourceSans
			txtbtn.Text = ""
			txtbtn.TextColor3 = Color3.fromRGB(0, 0, 0)
			txtbtn.TextSize = 14.000

TextboxLabel.Name = "TextboxLabel"
			TextboxLabel.Parent = Textbox
			TextboxLabel.BackgroundColor3 = Color3.fromRGB(51,255,255)
			TextboxLabel.BackgroundTransparency = 1.000
			TextboxLabel.Position = UDim2.new(0, 15, 0, 8)
			TextboxLabel.Text = text
			TextboxLabel.Size = UDim2.new(0, 220, 0, 12)
			TextboxLabel.Font = Enum.Font.Code
			TextboxLabel.TextColor3 = Color3.fromRGB(225, 225, 225)
			TextboxLabel.TextSize = 12.000
			TextboxLabel.TextTransparency = 0
			TextboxLabel.TextXAlignment = Enum.TextXAlignment.Left

			Textbox.Name = "Textbox"
			Textbox.Parent = MainFramePage
			Textbox.BackgroundColor3 = _G.Color
			Textbox.BackgroundTransparency = 0
			Textbox.Size = UDim2.new(0, 280, 0, 57)

			RealTextbox.Name = "RealTextbox"
			RealTextbox.Parent = Textbox
			RealTextbox.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
			RealTextbox.BackgroundTransparency = 0
			RealTextbox.Position = UDim2.new(0, 3, 0, 30)
			RealTextbox.Size = UDim2.new(0, 276, 0, 24)
			RealTextbox.Font = Enum.Font.Code
			RealTextbox.Text = texts
			RealTextbox.TextColor3 = Color3.fromRGB(255, 225, 225)
			RealTextbox.TextSize = 11.000
			RealTextbox.TextTransparency = 0

			RealTextbox.FocusLost:Connect(function()
				callback(RealTextbox.Text)
				if disappear then
					RealTextbox.Text = ""
				end
			end)

			UICorner.CornerRadius = UDim.new(0, 5)
			UICorner.Parent = RealTextbox
		end
		
		function main:AddTextboxRight(text,texts,disappear,callback)
			local Textboxx = Instance.new("Frame")
			local TextboxCornerr = Instance.new("UICorner")
			local Textboxxx = Instance.new("Frame")
			local TextboxxCornerr = Instance.new("UICorner")
			local TextboxLabell = Instance.new("TextLabel")
			local txtbtnn = Instance.new("TextButton")
			local RealTextboxx = Instance.new("TextBox")
			local UICornerr = Instance.new("UICorner")

			Textboxx.Name = "Textbox"
			Textboxx.Parent = MainFramePage2
			Textboxx.BackgroundColor3 = _G.Color
			Textboxx.BackgroundTransparency = 0
			Textboxx.Size = UDim2.new(0, 280, 0, 57)

			TextboxCornerr.CornerRadius = UDim.new(0, 5)
			TextboxCornerr.Name = "TextboxCorner"
			TextboxCornerr.Parent = Textboxx

			Textboxxx.Name = "Textboxx"
			Textboxxx.Parent = Textboxx
			Textboxxx.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
			Textboxxx.Position = UDim2.new(0, 1, 0, 1)
			Textboxxx.Size = UDim2.new(0, 278, 0, 55)

			TextboxxCornerr.CornerRadius = UDim.new(0, 5)
			TextboxxCornerr.Name = "TextboxxCorner"
			TextboxxCornerr.Parent = Textboxxx

		
			txtbtnn.Name = "txtbtn"
			txtbtnn.Parent = Textboxx
			txtbtnn.BackgroundColor3 = Color3.fromRGB(51,255,255)
			txtbtnn.BackgroundTransparency = 1.000
			txtbtnn.Position = UDim2.new(0, 1, 0, 1)
			txtbtnn.Size = UDim2.new(0, 278, 0, 45)
			txtbtnn.Font = Enum.Font.SourceSans
			txtbtnn.Text = ""
			txtbtnn.TextColor3 = Color3.fromRGB(0, 0, 0)
			txtbtnn.TextSize = 14.000

TextboxLabell.Name = "TextboxLabel"
			TextboxLabell.Parent = Textboxx
			TextboxLabell.BackgroundColor3 = Color3.fromRGB(51,255,255)
			TextboxLabell.BackgroundTransparency = 1.000
			TextboxLabell.Position = UDim2.new(0, 15, 0, 8)
			TextboxLabell.Text = text
			TextboxLabell.Size = UDim2.new(0, 278, 0, 12)
			TextboxLabell.Font = Enum.Font.Code
			TextboxLabell.TextColor3 = Color3.fromRGB(225, 225, 225)
			TextboxLabell.TextSize = 12.000
			TextboxLabell.TextTransparency = 0
			TextboxLabell.TextXAlignment = Enum.TextXAlignment.Left

			RealTextboxx.Name = "RealTextbox"
			RealTextboxx.Parent = Textboxx
			RealTextboxx.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
			RealTextboxx.BackgroundTransparency = 0
			RealTextboxx.Position = UDim2.new(0, 3, 0, 30)
			RealTextboxx.Size = UDim2.new(0, 276, 0, 24)
			RealTextboxx.Font = Enum.Font.Code
			RealTextboxx.Text = texts
			RealTextboxx.TextColor3 = Color3.fromRGB(255, 225, 225)
			RealTextboxx.TextSize = 11.000
			RealTextboxx.TextTransparency = 0

			RealTextboxx.FocusLost:Connect(function()
				callback(RealTextboxx.Text)
				if disappear then
					RealTextboxx.Text = ""
				end
			end)

			UICornerr.CornerRadius = UDim.new(0, 5)
			UICornerr.Parent = RealTextboxx
		end
		
		function main:AddLabelLeft(text)
			local Label = Instance.new("TextLabel")
			local PaddingLabel = Instance.new("UIPadding")
			local labelfunc = {}
	
			Label.Name = "Label"
			Label.Parent = MainFramePage
			Label.BackgroundColor3 = Color3.fromRGB(51,255,255)
			Label.BackgroundTransparency = 1.000
			Label.Size = UDim2.new(0, 360, 0, 20)
			Label.Font = Enum.Font.Code
			Label.TextColor3 = Color3.fromRGB(225, 225, 225)
			Label.TextSize = 14.000
			Label.Text = text
			Label.TextXAlignment = Enum.TextXAlignment.Left

			PaddingLabel.PaddingLeft = UDim.new(0,15)
			PaddingLabel.Parent = Label
			PaddingLabel.Name = "PaddingLabel"
	
			function labelfunc:Set(newtext)
			Label.Text = newtext
		end
		return labelfunc
		end

		function main:AddLabelRight(text)
			local Labell = Instance.new("TextLabel")
			local PaddingLabell = Instance.new("UIPadding")
			local labelfunc = {}
	
			Labell.Name = "Label"
			Labell.Parent = MainFramePage2
			Labell.BackgroundColor3 = Color3.fromRGB(51,255,255)
			Labell.BackgroundTransparency = 1.000
			Labell.Size = UDim2.new(0, 360, 0, 20)
			Labell.Font = Enum.Font.Code
			Labell.TextColor3 = Color3.fromRGB(225, 225, 225)
			Labell.TextSize = 14.000
			Labell.Text = text
			Labell.TextXAlignment = Enum.TextXAlignment.Left

			PaddingLabell.PaddingLeft = UDim.new(0,15)
			PaddingLabell.Parent = Labell
			PaddingLabell.Name = "PaddingLabel"
	
			function labelfunc:Set(newtext)
			Labell.Text = newtext
		end
		return labelfunc
		end


function main:Label1(text)
			local Label1 = Instance.new("TextLabel")
			local PaddingLabel1 = Instance.new("UIPadding")
			local Label1func = {}
	
			Label1.Name = "Label1"
			Label1.Parent = MainFramePage
			Label1.BackgroundColor3 = Color3.fromRGB(51,255,255)
			Label1.BackgroundTransparency = 1.000
			Label1.Size = UDim2.new(0, 360, 0, 20)
			Label1.Font = Enum.Font.Code
			Label1.TextColor3 = Color3.fromRGB(225, 225, 225)
			Label1.TextSize = 15.000
			Label1.Text = text
			Label1.TextXAlignment = Enum.TextXAlignment.Left

			PaddingLabel1.PaddingLeft = UDim.new(0,15)
			PaddingLabel1.Parent = Label1
			PaddingLabel1.Name = "PaddingLabel1"
function Label1func:Refresh(tochange)
 Label1.Text = tochange
end

return Label1func
end

		function main:AddSeperatorLeft(text)
			local Seperator = Instance.new("Frame")
			local Sep1 = Instance.new("Frame")
			local Sep2 = Instance.new("TextLabel")
			local Sep3 = Instance.new("Frame")
			
			Seperator.Name = "Seperator"
			Seperator.Parent = MainFramePage
			Seperator.BackgroundColor3 = Color3.fromRGB(51,255,255)
			Seperator.BackgroundTransparency = 1.000
			Seperator.Size = UDim2.new(0, 280, 0, 20)
			
			Sep1.Name = "Sep1"
			Sep1.Parent = Seperator
			Sep1.BackgroundColor3 = _G.Color
			Sep1.BorderSizePixel = 0
			Sep1.Position = UDim2.new(0, 0, 0, 10)
			Sep1.Size = UDim2.new(0, 20, 0, 1)
			
			Sep2.Name = "Sep2"
			Sep2.Parent = Seperator
			Sep2.BackgroundColor3 = Color3.fromRGB(51,255,255)
			Sep2.BackgroundTransparency = 1.000
			Sep2.Position = UDim2.new(0, 0.01, 0, 0)
			Sep2.Size = UDim2.new(0, 280, 0, 20)
			Sep2.Font = Enum.Font.Code
			Sep2.Text = text
			Sep2.TextColor3 = Color3.fromRGB(51,255,255)
			Sep2.TextSize = 20.000
			
			Sep3.Name = "Sep3"
			Sep3.Parent = Seperator
			Sep3.BackgroundColor3 = _G.Color
			Sep3.BorderSizePixel = 0
			Sep3.Position = UDim2.new(0, 260, 0, 10)
			Sep3.Size = UDim2.new(0, 20, 0, 1)
		end

		function main:AddSeperatorRight(text)
			local Seperator2 = Instance.new("Frame")
			local Sep4 = Instance.new("Frame")
			local Sep5 = Instance.new("TextLabel")
			local Sep6 = Instance.new("Frame")
			
			Seperator2.Name = "Seperator"
			Seperator2.Parent = MainFramePage2
			Seperator2.BackgroundColor3 = Color3.fromRGB(51,255,255)
			Seperator2.BackgroundTransparency = 1.000
			Seperator2.Size = UDim2.new(0, 280, 0, 20)
			
			Sep4.Name = "Sep1"
			Sep4.Parent = Seperator2
			Sep4.BackgroundColor3 = _G.Color
			Sep4.BorderSizePixel = 0
			Sep4.Position = UDim2.new(0, 0, 0, 10)
			Sep4.Size = UDim2.new(0, 20, 0, 1)
			
			Sep5.Name = "Sep2"
			Sep5.Parent = Seperator2
			Sep5.BackgroundColor3 = Color3.fromRGB(51,255,255)
			Sep5.BackgroundTransparency = 1.000
			Sep5.Position = UDim2.new(0, 0.01, 0, 0)
			Sep5.Size = UDim2.new(0, 280, 0, 20)
			Sep5.Font = Enum.Font.Code
			Sep5.Text = text
			Sep5.TextColor3 = Color3.fromRGB(51,255,255)
			Sep5.TextSize = 20.000
			
			Sep6.Name = "Sep3"
			Sep6.Parent = Seperator2
			Sep6.BackgroundColor3 = _G.Color
			Sep6.BorderSizePixel = 0
			Sep6.Position = UDim2.new(0, 260, 0, 10)
			Sep6.Size = UDim2.new(0, 20, 0, 1)
		end


		function main:AddLineLeft()
			local Linee = Instance.new("Frame")
			local Line = Instance.new("Frame")
			
			Linee.Name = "Linee"
			Linee.Parent = MainFramePage
			Linee.BackgroundColor3 = Color3.fromRGB(255,0,0)
			Linee.BackgroundTransparency = 1.000
			Linee.Position = UDim2.new(0, 0, 0.119999997, 0)
			Linee.Size = UDim2.new(0, 280, 0, 20)
			
			Line.Name = "Line"
			Line.Parent = Linee
			Line.BackgroundColor3 = _G.Color
			Line.BorderSizePixel = 0
			Line.Position = UDim2.new(0, 0, 0, 10)
			Line.Size = UDim2.new(0, 280, 0, 1)
		end
		
		function main:AddLineRight()
			local Lineee = Instance.new("Frame")
			local Line1 = Instance.new("Frame")
			
			Lineee.Name = "Linee"
			Lineee.Parent = MainFramePage2
			Lineee.BackgroundColor3 = Color3.fromRGB(255,0,0)
			Lineee.BackgroundTransparency = 1.000
			Lineee.Position = UDim2.new(0, 0, 0.119999997, 0)
			Lineee.Size = UDim2.new(0, 280, 0, 20)
			
			Line1.Name = "Line"
			Line1.Parent = Lineee
			Line1.BackgroundColor3 = _G.Color
			Line1.BorderSizePixel = 0
			Line1.Position = UDim2.new(0, 0, 0, 10)
			Line1.Size = UDim2.new(0, 280, 0, 1)
		end
		
		return main
	end
	return uitab
end

------------------------------------ Function -------------------------------
function Tp(Pos)
    local py = game.Players.LocalPlayer
    local Npy = py.Name
    local character = workspace:FindFirstChild(Npy) -- ค้นหาโมเดลของผู้เล่นใน workspace

    if character and character:FindFirstChild("HumanoidRootPart") then
        if typeof(Pos) == "CFrame" then
            character.HumanoidRootPart.CFrame = Pos -- หาก Pos เป็น CFrame ใช้ได้โดยตรง
        elseif typeof(Pos) == "Vector3" then
            character.HumanoidRootPart.CFrame = CFrame.new(Pos) -- หาก Pos เป็น Vector3 แปลงเป็น CFrame
        else
            warn("Invalid Pos type. Expected CFrame or Vector3.")
        end
    else
        warn("Character or HumanoidRootPart not found for player: " .. Npy)
    end
end



    function Upgrade(PartUnit)
        game:GetService("ReplicatedStorage").endpoints.client_to_server.upgrade_unit_ingame:InvokeServer(PartUnit)
    end

function SelectMapJoin(Box,Map,Act,FriendOnly,Mode)

    game:GetService("ReplicatedStorage").endpoints.client_to_server.request_lock_level:InvokeServer(Box,Map.."_"..Act.."",FriendOnly,""..Mode)
end

function PlaceUnit(CodeUnit,CFrameUnit)
    game:GetService("ReplicatedStorage").endpoints.client_to_server.spawn_unit:InvokeServer(CodeUnit, CFrame.new(CFrameUnit))
end

function SelectNext(Select)
    game:GetService("ReplicatedStorage").endpoints.client_to_server.set_game_finished_vote:InvokeServer(Select)
end
----------------------------- Ui Set
local RenUi = Update:AddWindow("RebornXer Hub","10039618734",Enum.KeyCode.RightControl)

local Main = RenUi:AddTab("Main","6026568198")
local Check = RenUi:AddTab("Check","6035190846")
local Misc = RenUi:AddTab("Misc","6034509993")
local Setting = RenUi:AddTab("","")

local S = RenUi:AddTabH("Top","14134158045")

Main:AddSeperatorLeft("Info")
Main:AddLabelLeft("Wecome To RebornXer Hub Script")
Main:AddLabelLeft("Map : Anime Adventures")
Date = os.date("%d".." ".."%B".." ".."%Y")
Main:AddLabelLeft("Day : "..Date)
Main:AddLineLeft("")

Main:AddSeperatorLeft("Join Map")

local MapList = {
    "namek",
    "aot",
    "demonslayer",
    "naruto",
    "marineford",
    "tokyo_ghoul",
    "hueco",
    "hxhant",
    "magnolia",
    "jjk",
    "clover",
    "jojo",
    "opm",
    "7ds",
    "mha",
    "dressrosa",
    "sao",
    "berserk",
    "overlord",
    "fate",
    "amegakure"
}


Main:AddDropdownL("Select Map",MapList,_G.SST.Select_Map,function(Value)
    Select_Map = Value
    _G.SST.Select_Map = Select_Map
    SS()
end)
ActList = {"1","2","3","4","5","6","Infinite"}

Main:AddDropdownL("Select Act",ActList,_G.SST.Select_Act,function(Value)
    Select_Act = Value
    _G.SST.Select_Act = Select_Act
    SS()
end)
spawn(function()
	while true do
		pcall(function()
		    if _G.SST.Select_Act == "1" then
        _G.Act_Select = "level_1"
    elseif _G.SST.Select_Act == "2" then
        _G.Act_Select = "level_2"
    elseif _G.SST.Select_Act == "3" then
        _G.Act_Select = "level_3"
    elseif _G.SST.Select_Act == "4" then
        _G.Act_Select = "level_4"
    elseif _G.SST.Select_Act == "5" then
        _G.Act_Select = "level_5"
    elseif _G.SST.Select_Act == "6" then
        _G.Act_Select = "level_6"
    elseif _G.SST.Select_Act == "Infinite" then
        _G.Act_Select = "infinite"
    end
	end)
		wait()
	end
end)


ModeList = {"Normal","Hard"}
Main:AddDropdownL("Select Mode",ModeList,_G.SST.Select_Mode,function(Value)
    Select_Mode = Value
    _G.SST.Select_Mode = Select_Mode
    SS()
end)

Main:AddToggleL("Select Friend Only",_G.SST.Select_Friend_Only,function(value)
    Select_Friend_Only = value
    _G.SST.Select_Friend_Only = Select_Friend_Only
    SS()
end)
spawn(function()
	while wait() do
		pcall(function()
		if _G.SST.Select_Friend_Only then
			_G.Fraiend_Only = "true"
			else
				_G.Fraiend_Only = "false"
				end
				end)
		end
	end)
Main:AddToggleL("Auto Join",_G.SST.Auto_Join,function(value)
    Auto_Join = value
    _G.SST.Auto_Join = Auto_Join
    SS()
end)

	spawn(function()
		while wait() do
			pcall(function()
				if _G.SST.Auto_Join then
					for i, Room in pairs(workspace._LOBBIES.Story:GetChildren()) do
						if Room:FindFirstChild("Timer") and Room.Timer.Value == -1 then
							-- ตรวจสอบค่า arguments ก่อนเรียกใช้
							local args = {
								[1] = Room.Name,
								[2] = _G.SST.Select_Map.."_".._G.Act_Select,
								[3] = true,
								[4] = _G.SST.Select_Mode
							}
							print("Arguments: ", args[1], args[2], args[3], args[4])  -- ตรวจสอบค่าก่อนเรียก
							game:GetService("ReplicatedStorage").endpoints.client_to_server.request_join_lobby:InvokeServer(Room.Name)

							game:GetService("ReplicatedStorage").endpoints.client_to_server.request_lock_level:InvokeServer(unpack(args))
							wait(2)
       game:GetService("ReplicatedStorage").endpoints.client_to_server.request_start_game:InvokeServer(Room.Name)
							
						end
					end
				end
			end)
		end
	end)


Main:AddSeperatorRight("Game")

local RunService = game:GetService("RunService")
local Players = game:GetService("Players")
local ReplicatedStorage = game:GetService("ReplicatedStorage")

if not _G.SST then
    _G.SST = {}
end

local lastCheck = 0  -- ตัวแปรเก็บเวลาล่าสุดที่เรียกฟังก์ชัน
local checkInterval = 1  -- เช็คทุกๆ 1 วินาที (ปรับค่าได้)

local function handleBackToLobby()
    local player = Players.LocalPlayer
    local resultsUI = player.PlayerGui:FindFirstChild("ResultsUI")
    
    if resultsUI and resultsUI.Enabled then
        ReplicatedStorage.endpoints.client_to_server.teleport_back_to_lobby:InvokeServer()
    end
end

local function handleReJoin()
    local player = Players.LocalPlayer
    local resultsUI = player.PlayerGui:FindFirstChild("ResultsUI")
    
    if resultsUI and resultsUI.Enabled then
        ReplicatedStorage.endpoints.client_to_server.set_game_finished_vote:InvokeServer("replay")
    end
end

-- สร้างตัวเลือก Auto Back To Lobby
Main:AddToggleR("Auto Back To Lobby", _G.SST.Auto_Back_To_Lobby or false, function(value)
    _G.SST.Auto_Back_To_Lobby = value
end)

-- สร้างตัวเลือก Auto ReJoin
Main:AddToggleR("Auto ReJoin", _G.SST.Auto_ReJoin or false, function(value)
    _G.SST.Auto_ReJoin = value
end)

-- ใช้ RunService.Heartbeat พร้อมตัวจับเวลา
RunService.Heartbeat:Connect(function()
    if tick() - lastCheck >= checkInterval then
        lastCheck = tick()  -- อัปเดตเวลาล่าสุด
        
        if _G.SST.Auto_Back_To_Lobby then
            handleBackToLobby()
        end
        if _G.SST.Auto_ReJoin then
            handleReJoin()
        end
    end
end)

Main:AddSeperatorRight("Game")
Main:AddDropdownR("Select To upgrade",{"All Unit","Cost Unit"},_G.SST.Select_To_Upgrade,function(a)
	Select_To_Upgrade = a
_G.SST.Select_To_Upgrade = Select_To_Upgrade
SS()
end)


	
Main:AddToggleR("Auto Upgrade Unit",_G.SST.Auto_Upgrade_Unit,function(a)
	Auto_Upgrade_Unit = a
	_G.SST.Auto_Upgrade_Unit = Auto_Upgrade_Unit
	SS()
end)
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local upgradeEndpoint = ReplicatedStorage.endpoints.client_to_server.upgrade_unit_ingame
local UnitsFolder = workspace._UNITS
local Player = game:GetService("Players").LocalPlayer

-- ฟังก์ชันช่วยกรองยูนิต
local function getUpgradeableUnits(filter)
    local upgradeableUnits = {}
    for _, unit in ipairs(UnitsFolder:GetChildren()) do
        if unit:IsA("Model") and unit:GetAttribute("range_stat") then
            local stats = unit:FindFirstChild("_stats")
            if stats and stats.player and stats.player.Value == Player then
                if filter == "Cost Unit" then
                    if unit.Name == "bulma" or unit.Name == "bulma:shiny" or unit.Name == "bulma:shiny:golden" or
                       unit.Name == "speedwagon" or unit.Name == "speedwagon:shiny" or unit.Name == "speedwagon:shiny:golden" or
                       unit.Name == "speedwagon:golden" then
                        table.insert(upgradeableUnits, unit)
                    end
                elseif filter == "All Unit" then
                    table.insert(upgradeableUnits, unit)
                end
            end
        end
    end
    return upgradeableUnits
end

-- ลูปหลักสำหรับอัปเกรดยูนิต
spawn(function()
    while true do
        local success, err = pcall(function()
            if _G.SST and _G.SST.Auto_Upgrade_Unit then
                local filter = _G.SST.Select_To_Upgrade
                local unitsToUpgrade = getUpgradeableUnits(filter)

                for _, unit in ipairs(unitsToUpgrade) do
                    local success, err = pcall(function()
                        upgradeEndpoint:InvokeServer(unit)
                    end)

                    if not success then
                        warn("Error invoking upgrade_unit_ingame: " .. tostring(err))
                    else
                        print("Upgraded unit: " .. unit.Name)
                    end
                end
            end
        end)

        if not success then
            warn("Error in auto-upgrade loop: " .. tostring(err))
        end

        task.wait(0.1) -- เพิ่มเวลาให้ลูปทำงานน้อยลง (ปรับได้ตามความเหมาะสม)
    end
end)



Main:AddSeperatorLeft("Farm")

Main:AddToggleL("Auto Farm Level",_G.SST.Farm_Level,function(a)
	Farm_Level = a
_G.SST.Farm_Level = Farm_Level
SS()
end)
spawn(function()
		while wait() do
			pcall(function()
				if _G.SST.Farm_Level then
					for i, Room in pairs(workspace._LOBBIES.Story:GetChildren()) do
						if Room:FindFirstChild("Timer") and Room.Timer.Value == -1 then
							-- ตรวจสอบค่า arguments ก่อนเรียกใช้
							local args = {
								[1] = Room.Name,
								[2] = "namek_level_1",
								[3] = true,
								[4] = "Hard"
							}
							game:GetService("ReplicatedStorage").endpoints.client_to_server.request_join_lobby:InvokeServer(Room.Name)

							game:GetService("ReplicatedStorage").endpoints.client_to_server.request_lock_level:InvokeServer(unpack(args))
							wait(2)
      						game:GetService("ReplicatedStorage").endpoints.client_to_server.request_start_game:InvokeServer(Room.Name)
							
						end
					end
				end
			end)
		end
	end)


	
	local unitId = "{46c72326-665b-4a1c-9bf4-24fbee7317a1}"
local replicatedStorage = game:GetService("ReplicatedStorage")
local spawnUnit = replicatedStorage.endpoints.client_to_server.spawn_unit

local spawnPositionsFarm = {
    Vector3.new(-2939.32568359375, 91.80620574951172, -704.94287109375),
    Vector3.new(-2938.983642578125, 91.80620574951172, -707.9991455078125),
    Vector3.new(-2941.4306640625, 91.80620574951172, -708.3591918945312),
    Vector3.new(-2942.264892578125, 91.80620574951172, -705.732177734375)
}

local function isCloseEnough(pos1, pos2, tolerance)
    return (pos1 - pos2).Magnitude <= tolerance
end

spawn(function()
    while wait() do
        pcall(function()
            if _G.SST.Farm_Level then
				if game:GetService("Players").LocalPlayer.PlayerGui.VoteStart.Enabled == true then
					game:GetService("ReplicatedStorage").endpoints.client_to_server.vote_start:InvokeServer()
				end
                local units = workspace._UNITS
                for _, position in ipairs(spawnPositionsFarm) do
                    local isUnitPresent = false
                    for _, unit in pairs(units:GetChildren()) do
                        if unit:FindFirstChild("HumanoidRootPart") and isCloseEnough(unit.HumanoidRootPart.Position, position, 0.1) then
                            isUnitPresent = true
                            break
                        end
                    end
                    
                    -- หากไม่มี Unit ในตำแหน่งนี้ ให้วาง Unit
                    if not isUnitPresent then
                        local cframe = CFrame.new(position) * CFrame.Angles(0, 0, 0)
                        spawnUnit:InvokeServer(unitId, cframe)
                    end
                end
            end
        end)
    end
end)

spawn(function()
    while wait() do
        pcall(function()
            if _G.SST and _G.SST.Farm_Level then -- ตรวจสอบ _G.SST และ _G.SST.Farm_Sukuna
                local units = workspace._UNITS:GetChildren()
                for i, v in pairs(units) do
                    if v:IsA("Model") and v:GetAttribute("range_stat") ~= nil then -- ตรวจสอบว่า unit เป็น Model และมี Attribute "range_stat"
                        print("Pet: " .. v.Name) -- ใช้ v.Name เพื่อพิมพ์ชื่อ Model

                        local up = {
                            [1] = v -- ใช้ Instance โดยตรง
                        }
                        -- เรียกฟังก์ชัน sell_unit_ingame
                        local success, err = pcall(function()
                            game:GetService("ReplicatedStorage").endpoints.client_to_server.upgrade_unit_ingame:InvokeServer(unpack(up))
                        end)

                        if not success then
                            warn("Error invoking sell_unit_ingame: " .. tostring(err))
                        end

                        wait(0) -- รอเล็กน้อยก่อนตรวจสอบ unit ถัดไป
                    end
                end
            end
        end)
    end
end)

Main:AddSeperatorLeft("Event")

Main:AddToggleL("Auto Feed Easter",_G.SST.Feed_Easter,function(a)
	Feed_Easter = a
_G.SST.Feed_Easter = Feed_Easter
SS()
end)

spawn(function()
	while wait() do
		pcall(function()
			if _G.SST.Feed_Easter then
				game:GetService("ReplicatedStorage").endpoints.client_to_server.feed_easter_meter:InvokeServer()
				_G.SST.Feed_Easter = false
			end
		end)
	end
end)

Main:AddToggleL("Auto Claim Easter",_G.SST.Claim_Easter,function(a)
	Claim_Easter = a
_G.SST.Claim_Easter = Claim_Easter
SS()
end)

spawn(function()
	while wait() do
		pcall(function()
			if _G.SST.Claim_Easter then
				game:GetService("ReplicatedStorage").endpoints.client_to_server.claim_easter_meter:InvokeServer()
				_G.SST.Claim_Easter = false
			end
		end)
	end
end)

Main:AddSeperatorLeft("Gem")

Main:AddToggleL("Auto Farm Gem",_G.SST.Farm_Gem,function(a)
	Farm_Gem = a
_G.SST.Farm_Gem = Farm_Gem
SS()
end)
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer

spawn(function()
    while task.wait(0.5) do -- ปรับเวลาให้ลูปทำงานไม่ถี่เกินไป
        local success, err = pcall(function()
            if _G.SST and _G.SST.Farm_Gem then
                -- ตรวจสอบ VoteStart ก่อนเรียกใช้งาน
                if LocalPlayer.PlayerGui.VoteStart and LocalPlayer.PlayerGui.VoteStart.Enabled then
                    ReplicatedStorage.endpoints.client_to_server.vote_start:InvokeServer()
                end
                
                for _, Room in ipairs(workspace._LOBBIES.Story:GetChildren()) do
                    if Room:FindFirstChild("Timer") and Room.Timer.Value == -1 then
                        -- เตรียม arguments สำหรับล็อบบี้
                        local args = {
                            Room.Name,
                            "aot_infinite",
                            true,
                            "Hard"
                        }
                        
                        -- ตรวจสอบค่าก่อนเรียกใช้งาน
                        print("Joining lobby:", args[1])
                        
                        -- Join lobby
                        ReplicatedStorage.endpoints.client_to_server.request_join_lobby:InvokeServer(Room.Name)
                        
                        -- Lock level
                        local lockSuccess, lockErr = pcall(function()
                            ReplicatedStorage.endpoints.client_to_server.request_lock_level:InvokeServer(unpack(args))
                        end)
                        
                        if not lockSuccess then
                            warn("Error locking level:", lockErr)
                        end
                        
                        -- Start game
                        task.wait(1) -- ลดเวลารอให้น้อยลง
                        local startSuccess, startErr = pcall(function()
                            ReplicatedStorage.endpoints.client_to_server.request_start_game:InvokeServer(Room.Name)
                        end)
                        
                        if not startSuccess then
                            warn("Error starting game:", startErr)
                        end
                    end
                end
            end
        end)

        if not success then
            warn("Error in Farm_Gem loop:", err)
        end
    end
end)

	Main:AddSeperatorLeft("Holiday Stars")

	Main:AddToggleL("Auto Farm HolidayStars",_G.SST.Auto_Farm_HolidayStars,function(a)
		Auto_Farm_HolidayStars = a
		_G.SST.Auto_Farm_HolidayStars = Auto_Farm_HolidayStars
		SS()
	end)
	
	spawn(function()
		while wait() do
			pcall(function()
				if _G.SST.Auto_Farm_HolidayStars then
					if game:GetService("Players").LocalPlayer.PlayerGui.VoteStart.Enabled == true then
						game:GetService("ReplicatedStorage").endpoints.client_to_server.vote_start:InvokeServer()
					end
					if workspace._EVENT_CHALLENGES.Lobbies._lobbytemplate_event3:FindFirstChild("Timer").Value == -1 then
						game:GetService("ReplicatedStorage").endpoints.client_to_server.request_join_lobby:InvokeServer("_lobbytemplate_event3")
					end
				end
			end)
		end
	end)

Main:AddSeperatorLeft("Curse Key")

Main:AddToggleL("Auto Farm Curse",_G.SST.Farm_Sukuna,function(a)
	Farm_Sukuna = a
_G.SST.Farm_Sukuna = Farm_Sukuna
SS()
end)

local unitId = "{8bf8f990-cb29-4b70-b382-da807acd100d}"
local replicatedStorage = game:GetService("ReplicatedStorage")
local spawnUnit = replicatedStorage.endpoints.client_to_server.spawn_unit

local spawnPositions = {
    Vector3.new(316.823, 125.597, -99.345),
    Vector3.new(319.000, 125.597, -96.916),
    Vector3.new(320.497, 125.597, -100.160),
    Vector3.new(319.032, 125.597, -103.319)
}

local function isCloseEnough(pos1, pos2, tolerance)
    return (pos1 - pos2).Magnitude <= tolerance
end

spawn(function()
    while wait() do
        pcall(function()
            if _G.SST.Farm_Sukuna then
				if game:GetService("Players").LocalPlayer.PlayerGui.VoteStart.Enabled == true then
					game:GetService("ReplicatedStorage").endpoints.client_to_server.vote_start:InvokeServer()
				end
                local units = workspace._UNITS
                for _, position in ipairs(spawnPositions) do
                    local isUnitPresent = false
                    for _, unit in pairs(units:GetChildren()) do
                        if unit:FindFirstChild("HumanoidRootPart") and isCloseEnough(unit.HumanoidRootPart.Position, position, 0.1) then
                            isUnitPresent = true
                            break
                        end
                    end
                    
                    -- หากไม่มี Unit ในตำแหน่งนี้ ให้วาง Unit
                    if not isUnitPresent then
                        local cframe = CFrame.new(position) * CFrame.Angles(0, 0, 0)
                        spawnUnit:InvokeServer(unitId, cframe)
                    end
                end
            end
        end)
    end
end)

spawn(function()
    while wait() do
        pcall(function()
            if _G.SST and _G.SST.Farm_Sukuna then -- ตรวจสอบ _G.SST และ _G.SST.Farm_Sukuna
                local units = workspace._UNITS:GetChildren()
                for i, v in pairs(units) do
                    if v:IsA("Model") and v:GetAttribute("range_stat") ~= nil then -- ตรวจสอบว่า unit เป็น Model และมี Attribute "range_stat"
                        print("Pet: " .. v.Name) -- ใช้ v.Name เพื่อพิมพ์ชื่อ Model

                        local up = {
                            [1] = v -- ใช้ Instance โดยตรง
                        }
                        -- เรียกฟังก์ชัน sell_unit_ingame
                        local success, err = pcall(function()
                            game:GetService("ReplicatedStorage").endpoints.client_to_server.upgrade_unit_ingame:InvokeServer(unpack(up))
                        end)

                        if not success then
                            warn("Error invoking sell_unit_ingame: " .. tostring(err))
                        end

                        wait(0) -- รอเล็กน้อยก่อนตรวจสอบ unit ถัดไป
                    end
                end
            end
        end)
    end
end)

Misc:AddSeperatorRight("Fps")
local player = game:GetService("Players").LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")
local blackScreenUI = nil

-- ฟังก์ชันสำหรับเปิด/ปิดจอดำ
local function toggleBlackScreen(enable)
    if not enable then
        -- ถ้าปิดจอดำ ให้ซ่อน UI
        if blackScreenUI then
            blackScreenUI.Enabled = false
        end
        return
    end

    -- ถ้าจอดำมีอยู่แล้ว ให้แสดง UI
    if blackScreenUI then
        blackScreenUI.Enabled = true
        return
    end

    -- สร้าง UI จอดำใหม่
    blackScreenUI = Instance.new("ScreenGui")
    blackScreenUI.Name = "Blackscreen"
    blackScreenUI.DisplayOrder = 1 -- ให้แสดงอยู่เหนือ UI อื่นๆ
    blackScreenUI.ResetOnSpawn = false -- UI จะไม่หายไปเมื่อผู้เล่นตายหรือเกิดใหม่
    blackScreenUI.IgnoreGuiInset = true -- ให้จอดำครอบคลุมพื้นที่เต็มจอ
    blackScreenUI.Parent = playerGui

    -- สร้างเฟรมสีดำ
    local uiFrame = Instance.new("Frame")
    uiFrame.BackgroundColor3 = Color3.new(0, 0, 0) -- สีดำสนิท
    uiFrame.Size = UDim2.new(1, 0, 1, 0) -- เต็มหน้าจอ
    uiFrame.Position = UDim2.new(0, 0, 0, 0) -- มุมบนซ้าย
    uiFrame.BorderSizePixel = 0 -- ไม่มีขอบ
    uiFrame.Parent = blackScreenUI
end

-- เปลี่ยนมาใช้ตัวแปรแทนการเก็บสถานะใน _G
-- เพิ่มปุ่ม toggle (สมมติว่า Misc:AddToggleR เป็นฟังก์ชันจากระบบที่ใช้งานอยู่)
Misc:AddToggleR("Black Screen",_G.SST.Black_Screen, function(value)
    Black_Screen = value
	_G.SST.Black_Screen = Black_Screen
    SS() -- ฟังก์ชันเพิ่มเติมที่คุณมีในระบบ
    if value then
        -- ปิดการแสดงผล 3D และเปิดจอดำ
        game:GetService("RunService"):Set3dRenderingEnabled(false)
        toggleBlackScreen(true)
    else
        -- เปิดการแสดงผล 3D และปิดจอดำ
        game:GetService("RunService"):Set3dRenderingEnabled(true)
        toggleBlackScreen(false)
    end
end)


Misc:AddToggleR("Boost Fps",_G.SST.Boost_Fps,function(va)
	Boost_Fps = va
 _G.SST.Boost_Fps = Boost_Fps
 SS()
end)

-- สร้าง Slider สำหรับการเลือก Frame Rate
Misc:AddSliderRight("Select Frame Rate", 0, 240, _G.SST.Select_Farme_Rate, function(a)
    Select_Farme_Rate = a -- ใช้ตัวแปร a แทนค่า Select_Farme_Rate
	_G.SST.Select_Farme_Rate = Select_Farme_Rate
    SS() -- ฟังก์ชันเพิ่มเติม
end)

-- เริ่มฟังก์ชัน spawn สำหรับการตั้งค่า FPS
spawn(function()
    while task.wait(1) do
        pcall(function()
            if type(_G.SST.Select_Farme_Rate) == "number" and _G.SST.Select_Farme_Rate > 0 then
                setfpscap(_G.SST.Select_Farme_Rate) -- ตั้งค่าความเร็วเฟรมตามค่า
            end
        end)
    end
end)


Misc:AddSeperatorLeft("Misc")
Misc:AddToggleL("Auto Rejoin [Kick]",_G.SST.Auto_Rejoin_Kick ,function(a)
	Auto_Rejoin_Kick  = a
	_G.SST.Auto_Rejoin_Kick = Auto_Rejoin_Kick
	SS()
end)
spawn(function()
	while wait() do
		if _G.SST.Auto_Rejoin_Kick then
			Auto_Rejoin_Kick = game:GetService("CoreGui").RobloxPromptGui.promptOverlay.ChildAdded:Connect(function(child)
				if child.Name == 'ErrorPrompt' and child:FindFirstChild('MessageArea') and child.MessageArea:FindFirstChild("ErrorFrame") then
					game:GetService("TeleportService"):Teleport(8304191830)
				end
			end)
		end
	end
end)


Misc:AddToggleL("Anti AFK", _G.SST.Anti_AFK, function(isEnabled)
    Anti_AFK = isEnabled
	_G.SST.Anti_AFK = Anti_AFK
    SS()
end)

task.spawn(function()
    while _G.AntiAFKEnabled and task.wait(300) do -- รันทุก 5 นาที
        pcall(function()
            local VirtualUser = game:GetService("VirtualUser")
            VirtualUser:CaptureController()
            VirtualUser:ClickButton2(Vector2.new(0, 0)) -- ส่งสัญญาณคลิกขวาจำลอง
        end)
    end
end)



	Check:AddSeperatorRight("WebHook")
Check:AddTextboxRight("WebHook Link",_G.SST.WebHook_Link,true,function(a)
	WebHook_Link = a
		_G.SST.WebHook_Link = WebHook_Link

	SS()
end)
Check:AddToggleR("Send WebHook",_G.SST.Sent_WebHook,function(a)
	Sent_WebHook = a
_G.SST.Sent_WebHook = Sent_WebHook
SS()
end)

local HttpService = game:GetService("HttpService")
local RunService = game:GetService("RunService")
local Players = game:GetService("Players")

local function sendWebhook(Name, GemRewards, XpRewards, GameTime, player)
    local url = _G.SST.WebHook_Link
    if not url or url == "" then
        warn("Invalid Webhook URL")
        return
    end

    local fields = {}

    -- Add Total field
    table.insert(fields, {
        ["name"] = "📊 Total 📊",
        ["value"] = "```Name          : " .. Name ..
                    "\nGem           : " .. player._stats.gem_amount.Value ..
                    "\nGold          : " .. player._stats.gold_amount.Value ..
                    "\nXP            : " .. player._stats.player_xp.Value ..
                    "\nHolidayStars  : " .. player._stats._resourceHolidayStars.Value .. "```"
    })

    -- Add Time field
    table.insert(fields, {
        ["name"] = "⌛ Time ⌛",
        ["value"] = "```" .. GameTime .. "```"
    })

    -- Add Rewards field if necessary
    if GemRewards ~= "+99999" or XpRewards ~= "+99999 XP" then
        table.insert(fields, {
            ["name"] = "Rewards",
            ["value"] = "```Gems: " .. GemRewards .. "   XP: " .. XpRewards .. "```"
        })
    end

    -- Construct the webhook payload
    local data = {
        ["content"] = "",
        ["embeds"] = {
            {
                ["author"] = { ["name"] = "ReBornxer Hub WebHook" },
                ["type"] = "rich",
                ["title"] = "[❄️CHRISTMAS + 💫RERELEASE + 🏆TOURNAMENT] AA",
                ["color"] = tonumber(0x13da),
                ["fields"] = fields
            }
        }
    }

    local jsonData = HttpService:JSONEncode(data)
    local headers = { ["Content-Type"] = "application/json" }

    -- Send the webhook request
    local request = http_request or request or HttpPost or syn.request
    if request then
        local response = request({
            Url = url,
            Body = jsonData,
            Method = "POST",
            Headers = headers
        })
        if response.StatusCode ~= 200 then
            warn("Failed to send webhook. Status Code: " .. response.StatusCode)
        end
    else
        warn("HTTP request function not available.")
    end
end

RunService.Heartbeat:Connect(function()
    pcall(function()
        if _G.SST.Sent_WebHook then
            local player = Players.LocalPlayer
            local resultsUI = player.PlayerGui:FindFirstChild("ResultsUI")
            
            if resultsUI and resultsUI.Enabled then
                local Name = player.Name
                local GemRewards = resultsUI.Holder.LevelRewards.ScrollingFrame.GemReward.Main.Amount.Text
                local XpRewards = resultsUI.Holder.LevelRewards.ScrollingFrame.XPReward.Main.Amount.Text
                local GameTime = resultsUI.Holder.Middle.Timer.Text

                -- Call the function to send the webhook
                sendWebhook(Name, GemRewards, XpRewards, GameTime, player)

                -- Reset the webhook flag
                _G.SST.Sent_WebHook = false
            end
        end
    end)
end)


-- เพิ่ม Separator
Check:AddSeperatorLeft("Player")

-- ชื่อผู้เล่น
local NamePlayer = game.Players.LocalPlayer.Name
Check:AddLabelLeft("Name : " .. NamePlayer)

-- เช็ค Level ของผู้เล่น
local LevelPlayer = nil
pcall(function()
    LevelPlayer = game:GetService("Players").LocalPlayer.PlayerGui.spawn_units.Lives.Main.Desc.Level.Text
end)
Check:AddLabelLeft("Level : " .. (LevelPlayer or "Loading..."))

-- เช็ค XP ของผู้เล่น
local ExpPlayer = nil
pcall(function()
    ExpPlayer = game:GetService("Players").LocalPlayer._stats.player_xp.Value
end)
Check:AddLabelLeft("Xp : " .. (ExpPlayer or "Loading..."))

-- เช็ค BattlePass Level และ Furthest Room
local BattlePassLevel = nil
local FurthestRoom = nil
pcall(function()
    BattlePassLevel = game:GetService("Players").LocalPlayer.PlayerGui.BattlePass.Main.Level.V.Text
    FurthestRoom = game:GetService("Players").LocalPlayer.PlayerGui.BattlePass.Main.FurthestRoom.V.Text
end)
Check:AddLabelLeft("BattlePassLevel : " .. (BattlePassLevel or "Loading...") .. "[" .. (FurthestRoom or "Loading...") .. "]")

-- สร้าง Label สำหรับ Gems และ Gold
local GemCheck = Check:AddLabelLeft("Gem : Loading...")
local GoldCheck = Check:AddLabelLeft("Gold : Loading...")

-- ลูปการอัปเดต Gems และ Gold
spawn(function()
    while wait(1) do -- ลดความถี่การอัปเดตเป็น 1 วินาทีเพื่อประหยัดทรัพยากร
        pcall(function()
            local GemAmount = game:GetService("Players").LocalPlayer._stats.gem_amount.Value
            local GoldAmount = game:GetService("Players").LocalPlayer._stats.gold_amount.Value
            GemCheck:Set("Gem : " .. GemAmount)
            GoldCheck:Set("Gold : " .. GoldAmount)
        end)
    end
end)


local Boosted = false -- ตัวแปรสถานะเพื่อตรวจสอบว่ารันแล้วหรือไม่
local RunService = game:GetService("RunService")

local function optimizeSettings(player)
    local settings = player:FindFirstChild("_settings")
    if settings then
        for _, property in ipairs({"disable_effects", "disable_kill_fx", "disable_other_fx", "low_quality", "low_quality_shadows", "low_quality_textures"}) do
            local setting = settings:FindFirstChild(property)
            if setting and setting:IsA("BoolValue") then
                setting.Value = true
            end
        end
    end
end

local function optimizeTerrain(terrain)
    terrain.WaterWaveSize = 0
    terrain.WaterWaveSpeed = 0
    terrain.WaterReflectance = 0
    terrain.WaterTransparency = 0
end

local function optimizeLighting(lighting)
    lighting.GlobalShadows = false
    lighting.FogEnd = 9e9
    lighting.Brightness = 0

    for _, effect in ipairs(lighting:GetChildren()) do
        if effect:IsA("BlurEffect") or effect:IsA("SunRaysEffect") 
            or effect:IsA("ColorCorrectionEffect") or effect:IsA("BloomEffect") 
            or effect:IsA("DepthOfFieldEffect") then
            effect.Enabled = false
        end
    end
end

local function optimizePartsAndEffects(descendants)
    for _, obj in ipairs(descendants) do
        pcall(function()
            if obj:IsA("Part") or obj:IsA("Union") or obj:IsA("CornerWedgePart") 
                or obj:IsA("TrussPart") or obj:IsA("MeshPart") then
                obj.Material = Enum.Material.Plastic
                obj.Reflectance = 0
                if obj:IsA("MeshPart") then
                    obj.TextureID = ""
                end
            elseif obj:IsA("Decal") or obj:IsA("Texture") then
                obj:Destroy()
            elseif obj:IsA("ParticleEmitter") or obj:IsA("Trail") then
                obj.Lifetime = NumberRange.new(0)
            elseif obj:IsA("Fire") or obj:IsA("SpotLight") or obj:IsA("Smoke") or obj:IsA("Sparkles") then
                obj.Enabled = false
            elseif obj:IsA("Sound") then
                obj.Playing = false
            end
        end)
    end
end

local function removeUnnecessaryAccessories(descendants)
    for _, obj in ipairs(descendants) do
        pcall(function()
            if obj:IsA("Accessory") or obj:IsA("Clothing") then
                obj:Destroy()
            end
        end)
    end
end

RunService.Heartbeat:Connect(function()
    if _G.SST and _G.SST.Boost_Fps and not Boosted then
        Boosted = true
        pcall(function()
            local player = game:GetService("Players").LocalPlayer
            if not player then return end

            local playerGui = player:FindFirstChild("PlayerGui")

            -- ลบ MessageGui
            if playerGui and playerGui:FindFirstChild("MessageGui") then
                pcall(function() playerGui.MessageGui:Destroy() end)
            end

            -- ปรับค่าการตั้งค่า
            optimizeSettings(player)

            -- ปรับ Terrain และ Lighting
            optimizeTerrain(workspace.Terrain)
            optimizeLighting(game.Lighting)

            -- ปรับแต่งวัตถุและเอฟเฟกต์
            local descendants = game:GetDescendants()
            optimizePartsAndEffects(descendants)
            removeUnnecessaryAccessories(descendants)

            -- ลดคุณภาพการแสดงผล
            if settings and settings().Rendering then
                settings().Rendering.QualityLevel = Enum.QualityLevel.Level01
            end
        end)
    end
end)


Update:AddNotification('Hello  '..game.Players.LocalPlayer.Name)
-- ฟังก์ชันเพื่อตรวจสอบและสร้างไฟล์ข้อมูลผู้เล่น
-- รับบริการที่ต้องใช้
local HttpService = game:GetService("HttpService")
local Players = game:GetService("Players")
local localPlayer = Players.LocalPlayer

-- กำหนดชื่อไฟล์สำหรับบันทึกข้อมูลของผู้เล่น
local fileName = "AA" .. localPlayer.Name .. ".json"

-- ฟังก์ชันสำหรับสร้างข้อมูลเริ่มต้นจาก UnitFrames
local function createInitialData()
    local data = {}

    -- เข้าถึง UnitFrames ภายใน PlayerGui ของผู้เล่น
    local unitFramesFolder = localPlayer.PlayerGui.collection.grid.List.Outer.UnitFrames
    for _, v in ipairs(unitFramesFolder:GetChildren()) do
        if v.Name == "CollectionUnitFrame" then
            -- ใช้ชื่อใน text label เป็น key และเก็บข้อมูลต่าง ๆ ลงในตาราง
            data[v.name.Text] = {
                Equipped = v.EquippedList.Equipped.Visible,
                Level = tonumber(v.Main:FindFirstChild("Level").Text) or 0,
                UUID = v._uuid.Value,
                Cost = tonumber(v.Cost.text.Text) or 0
            }
        end
    end

    return data
end

-- ฟังก์ชันเพื่อตรวจสอบว่ามีไฟล์ข้อมูลอยู่หรือไม่ ถ้าไม่มีก็ให้สร้างไฟล์ขึ้นมา
local function checkOrCreateFile()
    if not isfile(fileName) then
        local initialData = createInitialData()
        writefile(fileName, HttpService:JSONEncode(initialData))
    end
end

-- ฟังก์ชันสำหรับโหลดข้อมูลจากไฟล์ JSON ไปยัง _G.SeveST
local function loadData()
    if isfile(fileName) then
        local fileContent = readfile(fileName)
        local success, decoded = pcall(function()
            return HttpService:JSONDecode(fileContent)
        end)
        if success and type(decoded) == "table" then
            _G.SeveST = decoded
        else
            warn("ไม่สามารถถอดรหัสข้อมูลจากไฟล์ " .. fileName .. " ได้")
            _G.SeveST = {}
        end
    else
        -- ถ้าไม่มีไฟล์ ให้สร้างและโหลดข้อมูลใหม่
        checkOrCreateFile()
        loadData()
    end
end

-- ฟังก์ชันสำหรับบันทึกข้อมูลจาก _G.SeveST กลับไปยังไฟล์ JSON
local function saveData()
    if _G.SeveST then
        writefile(fileName, HttpService:JSONEncode(_G.SeveST))
    else
        warn("ไม่มีข้อมูลใน _G.SeveST ให้บันทึก")
    end
end

-- ฟังก์ชันแสดงข้อมูลของ Unit ที่บันทึกไว้
local function printData()
    if _G.SeveST then
        for name, unit in pairs(_G.SeveST) do
            print(string.format(
                "%s Uid: %s | Equipped: %s | Cost: %s | Level: %s",
                name, unit.UUID, tostring(unit.Equipped), tostring(unit.Cost), tostring(unit.Level)
            ))
        end
    else
        warn("ไม่มีข้อมูลใน _G.SeveST")
    end
end

-- ฟังก์ชันตัวอย่างการใช้งานข้อมูลจาก _G.SeveST
local function useData()
    if _G.SeveST then
        for name, unit in pairs(_G.SeveST) do
            if unit.Equipped then
                print(name .. " is equipped and ready for use.")
            else
                print(name .. " is not equipped.")
            end

            local upgradeCost = unit.Cost * unit.Level
            print("The upgrade cost for " .. name .. " is " .. upgradeCost)
        end
    else
        warn("ไม่มีข้อมูลใน _G.SeveST")
    end
end

-- ขั้นตอนการทำงานหลัก
checkOrCreateFile()   -- ตรวจสอบและสร้างไฟล์ถ้ายังไม่มี
loadData()            -- โหลดข้อมูลจากไฟล์ไปยัง _G.SeveST
printData()           -- แสดงข้อมูลที่ได้
useData()             -- เรียกใช้งานข้อมูลตามที่ต้องการ

-- หากต้องการบันทึกข้อมูลใหม่หลังจากมีการเปลี่ยนแปลงใน _G.SeveST ให้เรียกใช้ saveData()
-- saveData()
