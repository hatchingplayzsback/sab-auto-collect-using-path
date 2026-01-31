local gui = Instance.new("ScreenGui")
gui.Parent = game.CoreGui
gui.Name = "PathMacro"
gui.Enabled = true
local tweenService = game:GetService("TweenService")
local uis = game:GetService("UserInputService")
local mainFrame = Instance.new("Frame")
mainFrame.Parent = gui
mainFrame.Size = UDim2.new(0, 350, 0, 250)
mainFrame.Position = UDim2.new(0.5, -175, 0.5, -125)
mainFrame.BackgroundColor3 = Color3.new(0, 0, 0)
mainFrame.BorderSizePixel = 0
mainFrame.Active = true
mainFrame.Draggable = true
mainFrame.Visible = false
local corner = Instance.new("UICorner")
corner.CornerRadius = UDim.new(0, 8)
corner.Parent = mainFrame
local tabFrame = Instance.new("Frame")
tabFrame.Parent = mainFrame
tabFrame.Size = UDim2.new(0.3, 0, 1, 0)
tabFrame.BackgroundColor3 = Color3.new(0.05, 0.05, 0.05)
tabFrame.BorderSizePixel = 0
local tabCorner = Instance.new("UICorner")
tabCorner.CornerRadius = UDim.new(0, 8)
tabCorner.Parent = tabFrame
local tabButtons = {}
local contentFrames = {}
local currentTab = nil
local function createTab(name, position)
  local button = Instance.new("TextButton")
  button.Parent = tabFrame
  button.Size = UDim2.new(1, 0, 0, 35)
  button.Position = UDim2.new(0, 0, 0, (position-1)*35)
  button.Text = name
  button.BackgroundColor3 = Color3.new(0.1, 0.1, 0.1)
  button.TextColor3 = Color3.new(1, 1, 1)
  button.BorderSizePixel = 0
  button.Font = Enum.Font.GothamBold
  button.TextSize = 16
  local buttonCorner = Instance.new("UICorner")
  buttonCorner.CornerRadius = UDim.new(0, 4)
  buttonCorner.Parent = button
  local content = Instance.new("Frame")
  content.Parent = mainFrame
  content.Size = UDim2.new(0.7, 0, 1, 0)
  content.Position = UDim2.new(0.3, 0, 0, 0)
  content.BackgroundColor3 = Color3.new(0, 0, 0)
  content.BackgroundTransparency = 0.05
  content.Visible = false
  local contentCorner = Instance.new("UICorner")
  contentCorner.CornerRadius = UDim.new(0, 8)
  contentCorner.Parent = content
  button.MouseButton1Click:Connect(function()
    if currentTab then
      contentFrames[currentTab].Visible = false
      tweenService:Create(tabButtons[currentTab], TweenInfo.new(0.2), {BackgroundColor3 = Color3.new(0.1, 0.1, 0.1)}):Play()
    end
    content.Visible = true
    tweenService:Create(button, TweenInfo.new(0.2), {BackgroundColor3 = Color3.new(0.2, 0.2, 0.2)}):Play()
    tweenService:Create(content, TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {BackgroundTransparency = 0}):Play()
    currentTab = name
  end)
  tabButtons[name] = button
  contentFrames[name] = content
end
createTab("Main", 1)
createTab("Pos Info", 2)
createTab("Visual", 3)
createTab("Settings", 4)
-- Main Tab
local addPosButton = Instance.new("TextButton")
addPosButton.Parent = contentFrames["Main"]
addPosButton.Size = UDim2.new(0.8, 0, 0, 35)
addPosButton.Position = UDim2.new(0.1, 0, 0.1, 0)
addPosButton.Text = "Add Position"
addPosButton.BackgroundColor3 = Color3.new(0.1, 0.1, 0.1)
addPosButton.TextColor3 = Color3.new(1, 1, 1)
addPosButton.BorderSizePixel = 0
addPosButton.Font = Enum.Font.Gotham
addPosButton.TextSize = 14
local addCorner = Instance.new("UICorner")
addCorner.CornerRadius = UDim.new(0, 4)
addCorner.Parent = addPosButton
local toggleButton = Instance.new("TextButton")
toggleButton.Parent = contentFrames["Main"]
toggleButton.Size = UDim2.new(0.8, 0, 0, 35)
toggleButton.Position = UDim2.new(0.1, 0, 0.3, 0)
toggleButton.Text = "Toggle: Off"
toggleButton.BackgroundColor3 = Color3.new(0.1, 0.1, 0.1)
toggleButton.TextColor3 = Color3.new(1, 1, 1)
toggleButton.BorderSizePixel = 0
toggleButton.Font = Enum.Font.Gotham
toggleButton.TextSize = 14
local toggleCorner = Instance.new("UICorner")
toggleCorner.CornerRadius = UDim.new(0, 4)
toggleCorner.Parent = toggleButton
local posCountLabel = Instance.new("TextLabel")
posCountLabel.Parent = contentFrames["Main"]
posCountLabel.Size = UDim2.new(0.8, 0, 0, 35)
posCountLabel.Position = UDim2.new(0.1, 0, 0.5, 0)
posCountLabel.Text = "Positions: 0"
posCountLabel.BackgroundColor3 = Color3.new(0.05, 0.05, 0.05)
posCountLabel.TextColor3 = Color3.new(1, 1, 1)
posCountLabel.BorderSizePixel = 0
posCountLabel.Font = Enum.Font.Gotham
posCountLabel.TextSize = 14
local countCorner = Instance.new("UICorner")
countCorner.CornerRadius = UDim.new(0, 4)
countCorner.Parent = posCountLabel
-- Pos Info Tab
local resetPosButton = Instance.new("TextButton")
resetPosButton.Parent = contentFrames["Pos Info"]
resetPosButton.Size = UDim2.new(0.8, 0, 0, 35)
resetPosButton.Position = UDim2.new(0.1, 0, 0, 5)
resetPosButton.Text = "Reset Positions"
resetPosButton.BackgroundColor3 = Color3.new(0.1, 0.1, 0.1)
resetPosButton.TextColor3 = Color3.new(1, 0, 0)
resetPosButton.BorderSizePixel = 0
resetPosButton.Font = Enum.Font.Gotham
resetPosButton.TextSize = 14
local resetCorner = Instance.new("UICorner")
resetCorner.CornerRadius = UDim.new(0, 4)
resetCorner.Parent = resetPosButton
local posScroll = Instance.new("ScrollingFrame")
posScroll.Parent = contentFrames["Pos Info"]
posScroll.Size = UDim2.new(1, 0, 1, -45)
posScroll.Position = UDim2.new(0, 0, 0, 45)
posScroll.BackgroundTransparency = 1
posScroll.ScrollBarThickness = 6
posScroll.ScrollBarImageColor3 = Color3.new(0.3, 0.3, 0.3)
local posListUI = Instance.new("UIListLayout")
posListUI.Parent = posScroll
posListUI.SortOrder = Enum.SortOrder.LayoutOrder
posListUI.Padding = UDim.new(0, 5)
-- Visual Tab
local espToggle = Instance.new("TextButton")
espToggle.Parent = contentFrames["Visual"]
espToggle.Size = UDim2.new(0.8, 0, 0, 35)
espToggle.Position = UDim2.new(0.1, 0, 0.1, 0)
espToggle.Text = "Player ESP: Off"
espToggle.BackgroundColor3 = Color3.new(0.1, 0.1, 0.1)
espToggle.TextColor3 = Color3.new(1, 1, 1)
espToggle.BorderSizePixel = 0
espToggle.Font = Enum.Font.Gotham
espToggle.TextSize = 14
local espCorner = Instance.new("UICorner")
espCorner.CornerRadius = UDim.new(0, 4)
espCorner.Parent = espToggle
local tracerToggle = Instance.new("TextButton")
tracerToggle.Parent = contentFrames["Visual"]
tracerToggle.Size = UDim2.new(0.8, 0, 0, 35)
tracerToggle.Position = UDim2.new(0.1, 0, 0.3, 0)
tracerToggle.Text = "Tracers: Off"
tracerToggle.BackgroundColor3 = Color3.new(0.1, 0.1, 0.1)
tracerToggle.TextColor3 = Color3.new(1, 1, 1)
tracerToggle.BorderSizePixel = 0
tracerToggle.Font = Enum.Font.Gotham
tracerToggle.TextSize = 14
local tracerCorner = Instance.new("UICorner")
tracerCorner.CornerRadius = UDim.new(0, 4)
tracerCorner.Parent = tracerToggle
local posEspToggle = Instance.new("TextButton")
posEspToggle.Parent = contentFrames["Visual"]
posEspToggle.Size = UDim2.new(0.8, 0, 0, 35)
posEspToggle.Position = UDim2.new(0.1, 0, 0.5, 0)
posEspToggle.Text = "Pos ESP: Off"
posEspToggle.BackgroundColor3 = Color3.new(0.1, 0.1, 0.1)
posEspToggle.TextColor3 = Color3.new(1, 1, 1)
posEspToggle.BorderSizePixel = 0
posEspToggle.Font = Enum.Font.Gotham
posEspToggle.TextSize = 14
local posEspCorner = Instance.new("UICorner")
posEspCorner.CornerRadius = UDim.new(0, 4)
posEspCorner.Parent = posEspToggle
-- Settings Tab
local keybindLabel = Instance.new("TextLabel")
keybindLabel.Parent = contentFrames["Settings"]
keybindLabel.Size = UDim2.new(0.4, 0, 0, 35)
keybindLabel.Position = UDim2.new(0.1, 0, 0.1, 0)
keybindLabel.Text = "Keybind:"
keybindLabel.BackgroundColor3 = Color3.new(0.05, 0.05, 0.05)
keybindLabel.TextColor3 = Color3.new(1, 1, 1)
keybindLabel.BorderSizePixel = 0
keybindLabel.Font = Enum.Font.Gotham
keybindLabel.TextSize = 14
local keyLabelCorner = Instance.new("UICorner")
keyLabelCorner.CornerRadius = UDim.new(0, 4)
keyLabelCorner.Parent = keybindLabel
local keybindButton = Instance.new("TextButton")
keybindButton.Parent = contentFrames["Settings"]
keybindButton.Size = UDim2.new(0.4, 0, 0, 35)
keybindButton.Position = UDim2.new(0.5, 0, 0.1, 0)
keybindButton.Text = "Insert"
keybindButton.BackgroundColor3 = Color3.new(0.1, 0.1, 0.1)
keybindButton.TextColor3 = Color3.new(1, 1, 1)
keybindButton.BorderSizePixel = 0
keybindButton.Font = Enum.Font.Gotham
keybindButton.TextSize = 14
local keyButtonCorner = Instance.new("UICorner")
keyButtonCorner.CornerRadius = UDim.new(0, 4)
keyButtonCorner.Parent = keybindButton
local unloadButton = Instance.new("TextButton")
unloadButton.Parent = contentFrames["Settings"]
unloadButton.Size = UDim2.new(0.8, 0, 0, 35)
unloadButton.Position = UDim2.new(0.1, 0, 0.3, 0)
unloadButton.Text = "Unload Script"
unloadButton.BackgroundColor3 = Color3.new(0.1, 0.1, 0.1)
unloadButton.TextColor3 = Color3.new(1, 0, 0)
unloadButton.BorderSizePixel = 0
unloadButton.Font = Enum.Font.Gotham
unloadButton.TextSize = 14
local unloadCorner = Instance.new("UICorner")
unloadCorner.CornerRadius = UDim.new(0, 4)
unloadCorner.Parent = unloadButton
-- Script Logic
local positions = {}
local running = false
local walkSpeed = 16
local espEnabled = false
local tracersEnabled = false
local posEspEnabled = false
local keybind = Enum.KeyCode.Insert
local player = game.Players.LocalPlayer
local char = player.Character or player.CharacterAdded:Wait()
local hum = char:WaitForChild("Humanoid")
local pathfinding = game:GetService("PathfindingService")
local runService = game:GetService("RunService")
player.CharacterAdded:Connect(function(newChar)
  char = newChar
  hum = newChar:WaitForChild("Humanoid")
end)
local pathParams = {
  AgentRadius = 2,
  AgentHeight = 5,
  AgentCanJump = true,
  AgentCanClimb = true,
  WaypointSpacing = 3,
  Costs = {
    Border = math.huge,
    Water = math.huge,
    Lava = math.huge
  }
}
local espDrawings = {}
local tracerDrawings = {}
local posDrawings = {}
local function updatePosCount()
  posCountLabel.Text = "Positions: " .. #positions
end
local function refreshPosList()
  for _, child in ipairs(posScroll:GetChildren()) do
    if child:IsA("Frame") then
      child:Destroy()
    end
  end
  for i, pos in ipairs(positions) do
    local posFrame = Instance.new("Frame")
    posFrame.Parent = posScroll
    posFrame.Size = UDim2.new(1, 0, 0, 25)
    posFrame.BackgroundTransparency = 1
    local coordLabel = Instance.new("TextLabel")
    coordLabel.Parent = posFrame
    coordLabel.Size = UDim2.new(0.7, 0, 1, 0)
    coordLabel.Text = "Pos " .. i .. ": " .. math.floor(pos.X) .. ", " .. math.floor(pos.Y) .. ", " .. math.floor(pos.Z)
    coordLabel.BackgroundTransparency = 1
    coordLabel.TextColor3 = Color3.new(1, 1, 1)
    coordLabel.Font = Enum.Font.Gotham
    coordLabel.TextSize = 12
    local deleteButton = Instance.new("TextButton")
    deleteButton.Parent = posFrame
    deleteButton.Size = UDim2.new(0.3, 0, 1, 0)
    deleteButton.Position = UDim2.new(0.7, 0, 0, 0)
    deleteButton.Text = "Delete"
    deleteButton.BackgroundColor3 = Color3.new(0.1, 0.1, 0.1)
    deleteButton.TextColor3 = Color3.new(1, 0, 0)
    deleteButton.BorderSizePixel = 0
    deleteButton.Font = Enum.Font.Gotham
    deleteButton.TextSize = 12
    local delCorner = Instance.new("UICorner")
    delCorner.CornerRadius = UDim.new(0, 4)
    delCorner.Parent = deleteButton
    deleteButton.MouseButton1Click:Connect(function()
      table.remove(positions, i)
      refreshPosList()
      updatePosCount()
      updatePosDrawings()
    end)
  end
  posScroll.CanvasSize = UDim2.new(0, 0, 0, posListUI.AbsoluteContentSize.Y)
end
local function updatePosDrawings()
  for _, drawing in pairs(posDrawings) do
    drawing:Remove()
  end
  posDrawings = {}
  if not posEspEnabled then return end
  for i, pos in ipairs(positions) do
    local circle = Drawing.new("Circle")
    circle.Radius = 10
    circle.Thickness = 2
    circle.Color = Color3.new(0, 1, 0)
    circle.Filled = false
    circle.Visible = false
    posDrawings[i] = circle
    local text = Drawing.new("Text")
    text.Text = "Pos " .. i
    text.Size = 16
    text.Color = Color3.new(1, 1, 1)
    text.Outline = true
    text.Visible = false
    posDrawings["text" .. i] = text
  end
end
addPosButton.MouseButton1Click:Connect(function()
  if char then
    table.insert(positions, char.HumanoidRootPart.Position)
    updatePosCount()
    refreshPosList()
    updatePosDrawings()
  end
end)
resetPosButton.MouseButton1Click:Connect(function()
  positions = {}
  updatePosCount()
  refreshPosList()
  updatePosDrawings()
end)
toggleButton.MouseButton1Click:Connect(function()
  running = not running
  toggleButton.Text = "Toggle: " .. (running and "On" or "Off")
  if not running then
    if hum then
      hum:MoveTo(char.HumanoidRootPart.Position)
    end
  end
end)
espToggle.MouseButton1Click:Connect(function()
  espEnabled = not espEnabled
  espToggle.Text = "Player ESP: " .. (espEnabled and "On" or "Off")
end)
tracerToggle.MouseButton1Click:Connect(function()
  tracersEnabled = not tracersEnabled
  tracerToggle.Text = "Tracers: " .. (tracersEnabled and "On" or "Off")
end)
posEspToggle.MouseButton1Click:Connect(function()
  posEspEnabled = not posEspEnabled
  posEspToggle.Text = "Pos ESP: " .. (posEspEnabled and "On" or "Off")
  updatePosDrawings()
end)
local binding = false
keybindButton.MouseButton1Click:Connect(function()
  binding = true
  keybindButton.Text = "Press Key..."
end)
uis.InputBegan:Connect(function(input, processed)
  if binding and input.UserInputType == Enum.UserInputType.Keyboard then
    keybind = input.KeyCode
    keybindButton.Text = input.KeyCode.Name
    binding = false
  elseif not processed and input.KeyCode == keybind then
    mainFrame.Visible = not mainFrame.Visible
    if mainFrame.Visible then
      tweenService:Create(mainFrame, TweenInfo.new(0.3, Enum.EasingStyle.Quad), {BackgroundTransparency = 0}):Play()
    else
      tweenService:Create(mainFrame, TweenInfo.new(0.3, Enum.EasingStyle.Quad), {BackgroundTransparency = 1}):Play()
    end
  end
end)
unloadButton.MouseButton1Click:Connect(function()
  gui:Destroy()
  for _, drawing in pairs(espDrawings) do drawing:Remove() end
  for _, drawing in pairs(tracerDrawings) do drawing:Remove() end
  for _, drawing in pairs(posDrawings) do drawing:Remove() end
end)
local function isObstacleJumpable(position, direction)
  local rayLow = Ray.new(position + Vector3.new(0, 1, 0), direction.Unit * 3)
  local hitLow, hitPosLow = workspace:FindPartOnRayWithIgnoreList(rayLow, {char})
  local rayHigh = Ray.new(position + Vector3.new(0, 4, 0), direction.Unit * 3)
  local hitHigh, _ = workspace:FindPartOnRayWithIgnoreList(rayHigh, {char})
  if hitLow and not hitHigh then
    local height = (hitPosLow.Y - position.Y)
    if height > 0 and height < hum.JumpPower / 10 then  -- Adjust based on jump power
      return true
    end
  end
  return false
end
local function moveAlongPath(start, goal)
  if hum and start and goal then
    hum.WalkSpeed = walkSpeed
    local path = pathfinding:CreatePath(pathParams)
    path:ComputeAsync(start, goal)
    if path.Status == Enum.PathStatus.Success then
      local waypoints = path:GetWaypoints()
      local blockedConn
      blockedConn = path.Blocked:Connect(function(blockedWaypointIndex)
        if blockedWaypointIndex >= 1 then
          blockedConn:Disconnect()
          moveAlongPath(char.HumanoidRootPart.Position, goal)
        end
      end)
      for i, waypoint in ipairs(waypoints) do
        if not running then break end
        local direction = (waypoint.Position - char.HumanoidRootPart.Position)
        if isObstacleJumpable(char.HumanoidRootPart.Position, direction) then
          hum:ChangeState(Enum.HumanoidStateType.Jumping)
        elseif waypoint.Action == Enum.PathWaypointAction.Jump then
          hum:ChangeState(Enum.HumanoidStateType.Jumping)
        end
        local reached = false
        while not reached and running do
          hum:MoveTo(waypoint.Position)
          local timeout = tick() + 10
          while tick() < timeout and running do
            if (char.HumanoidRootPart.Position - waypoint.Position).Magnitude < 4 then
              reached = true
              break
            end
            wait(0.1)
          end
          if not reached then
            blockedConn:Disconnect()
            moveAlongPath(char.HumanoidRootPart.Position, goal)
            return
          end
        end
        if not running then break end
      end
      blockedConn:Disconnect()
    end
  end
end
spawn(function()
  while true do
    if running and #positions > 0 then
      for i, pos in ipairs(positions) do
        if not running then break end
        moveAlongPath(char.HumanoidRootPart.Position, pos)
      end
    end
    wait(0.1)
  end
end)
local function createESP(player)
  if player == game.Players.LocalPlayer or not player.Character then return end
  local char = player.Character
  local box = Drawing.new("Square")
  box.Thickness = 1
  box.Color = Color3.new(1, 0, 0)
  box.Filled = false
  espDrawings[player] = box
  local name = Drawing.new("Text")
  name.Size = 14
  name.Color = Color3.new(1, 1, 1)
  name.Outline = true
  espDrawings[player.Name .. "_name"] = name
  local tracer = Drawing.new("Line")
  tracer.Thickness = 1
  tracer.Color = Color3.new(0, 1, 0)
  tracerDrawings[player] = tracer
end
game.Players.PlayerAdded:Connect(function(plr)
  createESP(plr)
end)
for _, plr in ipairs(game.Players:GetPlayers()) do
  createESP(plr)
end
runService.RenderStepped:Connect(function()
  for plr, drawing in pairs(espDrawings) do
    if typeof(plr) == "Instance" and plr.Character and plr.Character:FindFirstChild("HumanoidRootPart") and plr.Character.Humanoid.Health > 0 then
      local root = plr.Character.HumanoidRootPart
      local cam = workspace.CurrentCamera
      local vec, onScreen = cam:WorldToViewportPoint(root.Position)
      if onScreen and espEnabled then
        local size = (cam:WorldToViewportPoint(root.Position - Vector3.new(2, 3, 0)).Y - cam:WorldToViewportPoint(root.Position + Vector3.new(2, 5, 0)).Y) / 2
        drawing.Size = Vector2.new(size * 1.5, size * 2.5)
        drawing.Position = Vector2.new(vec.X - drawing.Size.X / 2, vec.Y - drawing.Size.Y / 2)
        drawing.Visible = true
      else
        drawing.Visible = false
      end
    else
      drawing.Visible = false
    end
  end
  for plr, name in pairs(espDrawings) do
    if typeof(plr) == "string" and string.find(plr, "_name") then
      local actualPlr = game.Players:FindFirstChild(plr:gsub("_name", ""))
      if actualPlr and actualPlr.Character and actualPlr.Character:FindFirstChild("HumanoidRootPart") and actualPlr.Character.Humanoid.Health > 0 then
        local root = actualPlr.Character.HumanoidRootPart
        local cam = workspace.CurrentCamera
        local vec, onScreen = cam:WorldToViewportPoint(root.Position + Vector3.new(0, 3, 0))
        if onScreen and espEnabled then
          name.Text = actualPlr.Name
          name.Position = Vector2.new(vec.X, vec.Y)
          name.Visible = true
        else
          name.Visible = false
        end
      else
        name.Visible = false
      end
    end
  end
  for plr, tracer in pairs(tracerDrawings) do
    if plr.Character and plr.Character:FindFirstChild("HumanoidRootPart") and plr.Character.Humanoid.Health > 0 then
      local root = plr.Character.HumanoidRootPart
      local cam = workspace.CurrentCamera
      local vec, onScreen = cam:WorldToViewportPoint(root.Position)
      if onScreen and tracersEnabled then
        tracer.From = Vector2.new(cam.ViewportSize.X / 2, cam.ViewportSize.Y)
        tracer.To = Vector2.new(vec.X, vec.Y)
        tracer.Visible = true
      else
        tracer.Visible = false
      end
    else
      tracer.Visible = false
    end
  end
  if posEspEnabled then
    for i, pos in ipairs(positions) do
      local circle = posDrawings[i]
      local text = posDrawings["text" .. i]
      if circle and text then
        local cam = workspace.CurrentCamera
        local vec, onScreen = cam:WorldToViewportPoint(pos)
        if onScreen then
          circle.Position = Vector2.new(vec.X, vec.Y)
          circle.Visible = true
          text.Position = Vector2.new(vec.X, vec.Y - 20)
          text.Visible = true
        else
          circle.Visible = false
          text.Visible = false
        end
      end
    end
  end
end)
-- Open Main tab by default
contentFrames["Main"].Visible = true
tweenService:Create(tabButtons["Main"], TweenInfo.new(0.2), {BackgroundColor3 = Color3.new(0.2, 0.2, 0.2)}):Play()
tweenService:Create(contentFrames["Main"], TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {BackgroundTransparency = 0}):Play()
currentTab = "Main"
mainFrame.Visible = true
updatePosCount()
refreshPosList()
updatePosDrawings()
