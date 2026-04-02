local players = game:GetService("Players")
local tweenService = game:GetService("TweenService")
local runService = game:GetService("RunService")
local CoreGui = game:GetService("CoreGui")
local uis = game:GetService("UserInputService")
local UserInputService = game:GetService("UserInputService")

-- vars
local lp = players.LocalPlayer
local mouse = lp:GetMouse()
local viewport = workspace.CurrentCamera.ViewportSize
local tweenInfo = TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut)



local kavo = {}

function kavo:validate(defaults, options)
	for i, v in pairs(defaults) do
		if options[i] == nil then
			options[i] = v
		end
	end
	return options
end

function kavo:tween(object, goal, callback)
	local tween = tweenService:Create(object, tweenInfo, goal)
	tween.Completed:Connect(callback or function() end)
	tween:Play()
end

function kavo:CreateLib(options)
	options = kavo:validate({
		name =  "UI Library Test"
	}, options or {})

	local GUI = {
		CurrentTab = nil
	}
	
		-- Main Frame
	do
		-- StarterGui.MyLibrary
		GUI["1"] = Instance.new("ScreenGui", game:GetService("Players").LocalPlayer:WaitForChild("PlayerGui"));
		GUI["1"]["IgnoreGuiInset"] = true;
		GUI["1"]["Enabled"] = true;
		GUI["1"]["ScreenInsets"] = Enum.ScreenInsets.DeviceSafeInsets;
		GUI["1"]["Name"] = [[MyLibrary]];

		-- StarterGui.MyLibrary.Main
		GUI["2"] = Instance.new("Frame", GUI["1"]);
		GUI["2"]["BorderSizePixel"] = 0;
		GUI["2"]["BackgroundColor3"] = Color3.fromRGB(43, 43, 43);
		GUI["2"]["AnchorPoint"] = Vector2.new(0.5, 0.5);
		GUI["2"]["ClipsDescendants"] = true;
		GUI["2"]["Size"] = UDim2.new(0, 350, 0, 250);
		GUI["2"]["Position"] = UDim2.new(0.5, 0, 0.5, 0);
		GUI["2"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
		GUI["2"]["Name"] = [[Main]];
		GUI["2"]["ClipsDescendants"] = false

		-- StarterGui.MyLibrary.Main.UICorner
		GUI["3"] = Instance.new("UICorner", GUI["2"]);

		-- StarterGui.MyLibrary.Main.DropShadowHolder
		GUI["4"] = Instance.new("Frame", GUI["2"]);
		GUI["4"]["ZIndex"] = 0;
		GUI["4"]["BorderSizePixel"] = 0;
		GUI["4"]["Size"] = UDim2.new(1, 0, 1, 0);
		GUI["4"]["Name"] = [[DropShadowHolder]];
		GUI["4"]["BackgroundTransparency"] = 1;

		-- StarterGui.MyLibrary.Main.DropShadowHolder.DropShadow
		GUI["5"] = Instance.new("ImageLabel", GUI["4"]);
		GUI["5"]["ZIndex"] = 0;
		GUI["5"]["BorderSizePixel"] = 0;
		GUI["5"]["SliceCenter"] = Rect.new(49, 49, 450, 450);
		GUI["5"]["ScaleType"] = Enum.ScaleType.Slice;
		GUI["5"]["ImageTransparency"] = 0.5;
		GUI["5"]["ImageColor3"] = Color3.fromRGB(0, 0, 0);
		GUI["5"]["AnchorPoint"] = Vector2.new(0.5, 0.5);
		GUI["5"]["Image"] = [[rbxassetid://6014261993]];
		GUI["5"]["Size"] = UDim2.new(1, 47, 1, 47);
		GUI["5"]["BackgroundTransparency"] = 1;
		GUI["5"]["Name"] = [[DropShadow]];
		GUI["5"]["Position"] = UDim2.new(0.5, 0, 0.5, 0);

		-- StarterGui.MyLibrary.Main.TopBar
		GUI["6"] = Instance.new("Frame", GUI["2"]);
		GUI["6"]["ZIndex"] = 3;
		GUI["6"]["BorderSizePixel"] = 0;
		GUI["6"]["BackgroundColor3"] = Color3.fromRGB(31, 31, 31);
		GUI["6"]["Size"] = UDim2.new(1, 0, 0, 30);
		GUI["6"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
		GUI["6"]["Name"] = [[TopBar]];

		-- Dragging Topbar
		do 
			local dragging = false
			local dragStart
			local startPos

			-- Start drag when clicking on TopBar
			GUI["6"].InputBegan:Connect(function(input)
				if input.UserInputType == Enum.UserInputType.MouseButton1 then
					dragging = true
					dragStart = input.Position
					startPos = GUI["2"].Position
				end
			end)

			-- End drag when releasing mouse button anywhere
			GUI["6"].InputEnded:Connect(function(input)
				if input.UserInputType == Enum.UserInputType.MouseButton1 then
					dragging = false
				end
			end)

			-- Track mouse movement globally using UserInputService
			uis.InputChanged:Connect(function(input)
				if input.UserInputType == Enum.UserInputType.MouseMovement and dragging then
					local delta = input.Position - dragStart
					GUI["2"].Position = UDim2.new(
						startPos.X.Scale, 
						startPos.X.Offset + delta.X,
						startPos.Y.Scale, 
						startPos.Y.Offset + delta.Y
					)
				end
			end)

			-- Optional: Also end drag if mouse leaves the screen
			uis.InputEnded:Connect(function(input, gpe)
				if input.UserInputType == Enum.UserInputType.MouseButton1 then
					dragging = false
				end
			end)
		end

		-- StarterGui.MyLibrary.Main.TopBar.UICorner
		GUI["7"] = Instance.new("UICorner", GUI["6"]);

		-- StarterGui.MyLibrary.Main.TopBar.Extension
		GUI["8"] = Instance.new("Frame", GUI["6"]);
		GUI["8"]["ZIndex"] = 3;
		GUI["8"]["BorderSizePixel"] = 0;
		GUI["8"]["BackgroundColor3"] = Color3.fromRGB(31, 31, 31);
		GUI["8"]["AnchorPoint"] = Vector2.new(0.5, 1);
		GUI["8"]["Size"] = UDim2.new(1, 0, 0.5, 0);
		GUI["8"]["Position"] = UDim2.new(0.5, 0, 1, 0);
		GUI["8"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
		GUI["8"]["Name"] = [[Extension]];

		-- StarterGui.MyLibrary.Main.TopBar.Title
		GUI["9"] = Instance.new("TextLabel", GUI["6"]);
		GUI["9"]["ZIndex"] = 3;
		GUI["9"]["BorderSizePixel"] = 0;
		GUI["9"]["TextSize"] = 14;
		GUI["9"]["TextXAlignment"] = Enum.TextXAlignment.Left;
		GUI["9"]["BackgroundColor3"] = Color3.fromRGB(255, 255, 255);
		GUI["9"]["FontFace"] = Font.new([[rbxasset://fonts/families/Ubuntu.json]], Enum.FontWeight.Regular, Enum.FontStyle.Normal);
		GUI["9"]["TextColor3"] = Color3.fromRGB(255, 255, 255);
		GUI["9"]["BackgroundTransparency"] = 1;
		GUI["9"]["Size"] = UDim2.new(0.5, 0, 1, 0);
		GUI["9"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
		GUI["9"]["Text"] = options.name;
		GUI["9"]["Name"] = [[Title]];

		-- StarterGui.MyLibrary.Main.TopBar.Title.UIPadding
		GUI["a"] = Instance.new("UIPadding", GUI["9"]);
		GUI["a"]["PaddingLeft"] = UDim.new(0, 8);

		-- StarterGui.MyLibrary.Main.TopBar.ExitBtn
		GUI["b"] = Instance.new("ImageLabel", GUI["6"]);
		GUI["b"]["ZIndex"] = 3;
		GUI["b"]["AnchorPoint"] = Vector2.new(1, 0.5);
		GUI["b"]["Image"] = [[rbxassetid://8445470984]];
		GUI["b"]["ImageRectSize"] = Vector2.new(96, 96);
		GUI["b"]["Size"] = UDim2.new(0, 22, 0, 22);
		GUI["b"]["BackgroundTransparency"] = 1;
		GUI["b"]["ImageRectOffset"] = Vector2.new(304, 304);
		GUI["b"]["Name"] = [[ExitBtn]];
		GUI["b"]["Position"] = UDim2.new(1, -4, 0.5, 0);
		GUI["b"].InputBegan:Connect(function(input)
			if input.UserInputType == Enum.UserInputType.MouseButton1 then
				GUI["1"]:Destroy()  -- This destroys the entire ScreenGui
			end
		end)

		-- StarterGui.MyLibrary.Main.TopBar.ExitBtn.UIAspectRatioConstraint
		GUI["c"] = Instance.new("UIAspectRatioConstraint", GUI["b"]);
		GUI["c"]["DominantAxis"] = Enum.DominantAxis.Height;

		-- StarterGui.MyLibrary.Main.TopBar.Line
		GUI["d"] = Instance.new("Frame", GUI["6"]);
		GUI["d"]["ZIndex"] = 3;
		GUI["d"]["BorderSizePixel"] = 0;
		GUI["d"]["BackgroundColor3"] = Color3.fromRGB(81, 81, 81);
		GUI["d"]["AnchorPoint"] = Vector2.new(0, 1);
		GUI["d"]["Size"] = UDim2.new(1, 0, 0, 1);
		GUI["d"]["Position"] = UDim2.new(0, 0, 1, 0);
		GUI["d"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
		GUI["d"]["Name"] = [[Line]];

		-- StarterGui.MyLibrary.Main.TopBar.MinBtn
		GUI["e"] = Instance.new("ImageLabel", GUI["6"]);
		GUI["e"]["ZIndex"] = 3;
		GUI["e"]["AnchorPoint"] = Vector2.new(1, 0.5);
		GUI["e"]["Image"] = [[rbxassetid://91077096614618]];
		GUI["e"]["ImageRectSize"] = Vector2.new(90, 90);
		GUI["e"]["Size"] = UDim2.new(0, 22, 0, 22);
		GUI["e"]["BackgroundTransparency"] = 1;
		GUI["e"]["Name"] = [[MinBtn]];
		GUI["e"]["Position"] = UDim2.new(1, -28, 0.5, 0);
		
		local isMinimized = false
		local originalSize = GUI["2"].Size
		local minimizedSize = UDim2.new(0, 200, 0, 30)
		
		GUI["e"].InputBegan:Connect(function(input)
			if input.UserInputType == Enum.UserInputType.MouseButton1 then
				isMinimized = not isMinimized

				if isMinimized then
					-- Minimize: shrink to title bar only
					kavo:tween(GUI["2"], {Size = minimizedSize})
					-- Hide content and navigation
					GUI["20"].Visible = false  -- Content container
					GUI["10"].Visible = false  -- Navigation sidebar
					GUI["4"].Visible = false
				else
					-- Restore: back to original size
					kavo:tween(GUI["2"], {Size = originalSize})
					-- Show content and navigation
					GUI["20"].Visible = true
					GUI["10"].Visible = true
					GUI["4"].Visible = true
				end
			end
		end)

		-- StarterGui.MyLibrary.Main.TopBar.MinBtn.UIAspectRatioConstraint
		GUI["f"] = Instance.new("UIAspectRatioConstraint", GUI["e"]);
		GUI["f"]["DominantAxis"] = Enum.DominantAxis.Height;

		-- StarterGui.MyLibrary.Main.ContentContainer
		GUI["20"] = Instance.new("Frame", GUI["2"]);
		GUI["20"]["BorderSizePixel"] = 0;
		GUI["20"]["BackgroundColor3"] = Color3.fromRGB(255, 255, 255);
		GUI["20"]["AnchorPoint"] = Vector2.new(1, 0);
		GUI["20"]["Size"] = UDim2.new(1, -135, 1, -40);
		GUI["20"]["Position"] = UDim2.new(1, -5, 0, 35);
		GUI["20"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
		GUI["20"]["Name"] = [[ContentContainer]];
		GUI["20"]["BackgroundTransparency"] = 1;
	end
	
	
		-- Navigation
	do
		-- StarterGui.MyLibrary.Main.Navigation
		GUI["10"] = Instance.new("Frame", GUI["2"]);
		GUI["10"]["BorderSizePixel"] = 0;
		GUI["10"]["BackgroundColor3"] = Color3.fromRGB(53, 53, 53);
		GUI["10"]["Size"] = UDim2.new(0, 125, 1, -30);
		GUI["10"]["Position"] = UDim2.new(0, 0, 0, 30);
		GUI["10"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
		GUI["10"]["Name"] = [[Navigation]];

		-- StarterGui.MyLibrary.Main.Navigation.UICorner
		GUI["11"] = Instance.new("UICorner", GUI["10"]);

		-- StarterGui.MyLibrary.Main.Navigation.Hide
		GUI["12"] = Instance.new("Frame", GUI["10"]);
		GUI["12"]["BorderSizePixel"] = 0;
		GUI["12"]["BackgroundColor3"] = Color3.fromRGB(53, 53, 53);
		GUI["12"]["Size"] = UDim2.new(1, 0, 0, 10);
		GUI["12"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
		GUI["12"]["Name"] = [[Hide]];

		-- StarterGui.MyLibrary.Main.Navigation.Hide2
		GUI["13"] = Instance.new("Frame", GUI["10"]);
		GUI["13"]["BorderSizePixel"] = 0;
		GUI["13"]["BackgroundColor3"] = Color3.fromRGB(53, 53, 53);
		GUI["13"]["AnchorPoint"] = Vector2.new(1, 0);
		GUI["13"]["Size"] = UDim2.new(0, 10, 1, 0);
		GUI["13"]["Position"] = UDim2.new(1, 0, 0, 0);
		GUI["13"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
		GUI["13"]["Name"] = [[Hide2]];

		-- StarterGui.MyLibrary.Main.Navigation.ButtonHolder
		GUI["14"] = Instance.new("Frame", GUI["10"]);
		GUI["14"]["BorderSizePixel"] = 0;
		GUI["14"]["BackgroundColor3"] = Color3.fromRGB(255, 255, 255);
		GUI["14"]["Size"] = UDim2.new(1, 0, 1, 0);
		GUI["14"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
		GUI["14"]["Name"] = [[ButtonHolder]];
		GUI["14"]["BackgroundTransparency"] = 1;

		-- StarterGui.MyLibrary.Main.Navigation.ButtonHolder.UIPadding
		GUI["15"] = Instance.new("UIPadding", GUI["14"]);
		GUI["15"]["PaddingTop"] = UDim.new(0, 5);
		GUI["15"]["PaddingBottom"] = UDim.new(0, 5);

		-- StarterGui.MyLibrary.Main.Navigation.ButtonHolder.UIListLayout
		GUI["16"] = Instance.new("UIListLayout", GUI["14"]);
		GUI["16"]["Padding"] = UDim.new(0, 5);
		GUI["16"]["SortOrder"] = Enum.SortOrder.LayoutOrder;

		-- StarterGui.MyLibrary.Main.Navigation.Line
		GUI["1d"] = Instance.new("Frame", GUI["10"]);
		GUI["1d"]["BorderSizePixel"] = 0;
		GUI["1d"]["BackgroundColor3"] = Color3.fromRGB(81, 81, 81);
		GUI["1d"]["AnchorPoint"] = Vector2.new(1, 0);
		GUI["1d"]["Size"] = UDim2.new(0, 1, 1, 0);
		GUI["1d"]["Position"] = UDim2.new(1, 0, 0, 0);
		GUI["1d"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
		GUI["1d"]["Name"] = [[Line]];
	end
	
	function GUI:NewTab(options)
		options = kavo:validate({
			name =  "Preview Tab",
			icon = "rbxassetid://6764432408"
		}, options or {})

		local Tab = {
			Hover = false,
			Active = false
		}
		
			-- Render
		do
			-- StarterGui.MyLibrary.Main.Navigation.ButtonHolder.Inactive
			Tab["1a"] = Instance.new("TextLabel", GUI["14"]);
			Tab["1a"]["BorderSizePixel"] = 0;
			Tab["1a"]["TextSize"] = 14;
			Tab["1a"]["TextXAlignment"] = Enum.TextXAlignment.Left;
			Tab["1a"]["BackgroundColor3"] = Color3.fromRGB(151, 151, 151);
			Tab["1a"]["FontFace"] = Font.new([[rbxasset://fonts/families/Ubuntu.json]], Enum.FontWeight.Regular, Enum.FontStyle.Normal);
			Tab["1a"]["TextColor3"] = Color3.fromRGB(151, 151, 151);
			Tab["1a"]["BackgroundTransparency"] = 1;
			Tab["1a"]["Size"] = UDim2.new(1, 0, 0, 25);
			Tab["1a"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
			Tab["1a"]["Text"] = options.name;
			Tab["1a"]["Name"] = [[Inactive]];
			
			-- StarterGui.MyLibrary.Main.Navigation.ButtonHolder.Inactive.UIPadding
			Tab["1b"] = Instance.new("UIPadding", Tab["1a"]);
			Tab["1b"]["PaddingLeft"] = UDim.new(0, 26);

			-- StarterGui.MyLibrary.Main.Navigation.ButtonHolder.Inactive.Icon
			Tab["1c"] = Instance.new("ImageLabel", Tab["1a"]);
			Tab["1c"]["BorderSizePixel"] = 0;
			Tab["1c"]["ImageColor3"] = Color3.fromRGB(151, 151, 151);
			Tab["1c"]["AnchorPoint"] = Vector2.new(0, 0.5);
			Tab["1c"]["Image"] = [[rbxassetid://6764432408]];
			Tab["1c"]["ImageRectSize"] = Vector2.new(50, 50);
			Tab["1c"]["Size"] = UDim2.new(0, 20, 0, 20);
			Tab["1c"]["BackgroundTransparency"] = 1;
			Tab["1c"]["ImageRectOffset"] = Vector2.new(150, 800);
			Tab["1c"]["Name"] = [[Icon]];
			Tab["1c"]["Position"] = UDim2.new(0, -22, 0.5, 0);
			
			-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab
			Tab["1f"] = Instance.new("ScrollingFrame", GUI["20"]);
			Tab["1f"]["BorderSizePixel"] = 0;
			Tab["1f"]["CanvasPosition"] = Vector2.new(0, 100);
			Tab["1f"]["Name"] = [[HomeTab]];
			Tab["1f"]["BackgroundColor3"] = Color3.fromRGB(255, 255, 255);
			Tab["1f"]["Selectable"] = false;
			Tab["1f"]["Size"] = UDim2.new(1, 0, 1, 0);
			Tab["1f"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
			Tab["1f"]["ScrollBarThickness"] = 0;
			Tab["1f"]["BackgroundTransparency"] = 1;
			Tab["1f"].Visible = false
			
			-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.UIPadding
			Tab["26"] = Instance.new("UIPadding", Tab["1f"]);
			Tab["26"]["PaddingTop"] = UDim.new(0, 1);
			Tab["26"]["PaddingRight"] = UDim.new(0, 1);
			Tab["26"]["PaddingLeft"] = UDim.new(0, 1);
			Tab["26"]["PaddingBottom"] = UDim.new(0, 1);

			-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.UIListLayout
			Tab["27"] = Instance.new("UIListLayout", Tab["1f"]);
			Tab["27"]["Padding"] = UDim.new(0, 5);
			Tab["27"]["SortOrder"] = Enum.SortOrder.LayoutOrder;
			
			local function updateCanvasSize()
				local contentHeight = Tab["27"].AbsoluteContentSize.Y + 5
				Tab["1f"].CanvasSize = UDim2.new(0, 0, 0, contentHeight)
			end
			
			-- Connect to layout changes
			Tab["27"]:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(updateCanvasSize)
			-- Also update when children are added/removed
			Tab["1f"].ChildAdded:Connect(updateCanvasSize)
			Tab["1f"].ChildRemoved:Connect(updateCanvasSize)
			
			task.wait() -- Wait one frame for layout to calculate
			updateCanvasSize()
		end
		
			-- Methods
		function Tab:Activate()
			if not Tab.Active then
				if GUI.CurrentTab ~= nil then
					GUI.CurrentTab:Deactivate()
				end

				Tab.Active = true
				kavo:tween(Tab["1a"], {BackgroundTransparency = 0.9})
				kavo:tween(Tab["1a"], {TextColor3 = Color3.fromRGB(255,255,255)})
				kavo:tween(Tab["1c"], {ImageColor3 = Color3.fromRGB(255,255,255)})

				-- ✅ Show this tab's content
				Tab["1f"].Visible = true

				GUI.CurrentTab = Tab
			end
		end
		
		function Tab:Deactivate()
			if Tab.Active then
				Tab.Active = false
				Tab.Hover = false
				kavo:tween(Tab["1a"], {BackgroundTransparency = 1})
				kavo:tween(Tab["1a"], {TextColor3 = Color3.fromRGB(150,150,150)})
				kavo:tween(Tab["1c"], {ImageColor3 = Color3.fromRGB(150, 150, 150)})

				-- ✅ Hide this tab's content
				Tab["1f"].Visible = false
			end
		end
		
			--Logic
		do
			Tab["1a"].MouseEnter:Connect(function()
				Tab.Hover = true

				if not Tab.Active then
					kavo:tween(Tab["1a"], {TextColor3 = Color3.fromRGB(255,255,255)})
					kavo:tween(Tab["1c"], {ImageColor3 = Color3.fromRGB(255,255,255)})
				end
			end)
			
			Tab["1a"].MouseLeave:Connect(function()
				Tab.Hover = false

				if not Tab.Active then
					kavo:tween(Tab["1a"], {TextColor3 = Color3.fromRGB(150,150,150)})
					kavo:tween(Tab["1c"], {ImageColor3 = Color3.fromRGB(150, 150, 150)})
				end
			end)
			
			uis.InputBegan:Connect(function(input, gpe)
				if gpe then return end

				if input.UserInputType == Enum.UserInputType.MouseButton1 then
					if Tab.Hover then
						Tab:Activate()
					end
				end
			end)
			
			if GUI.CurrentTab == nil then
				Tab:Activate()
			end
		end
		
		
		function Tab:NewButton(options)
			options = kavo:validate({
				name =  "Preview Buton",
				callback = function() end
			}, options or {})

			local Button = {
				Hover = false,
				MouseDown = false
			}
			
				-- Render
			do
				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Button
				Button["20"] = Instance.new("Frame", Tab["1f"]);
				Button["20"]["BorderSizePixel"] = 0;
				Button["20"]["BackgroundColor3"] = Color3.fromRGB(31, 31, 31);
				Button["20"]["Size"] = UDim2.new(1, 0, 0, 30);
				Button["20"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				Button["20"]["Name"] = [[Button]];

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Button.UICorner
				Button["21"] = Instance.new("UICorner", Button["20"]);
				Button["21"]["CornerRadius"] = UDim.new(0, 6);

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Button.UIStroke
				Button["22"] = Instance.new("UIStroke", Button["20"]);
				Button["22"]["Color"] = Color3.fromRGB(81, 81, 81);
				Button["22"]["ApplyStrokeMode"] = Enum.ApplyStrokeMode.Border;

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Button.Title
				Button["23"] = Instance.new("TextLabel", Button["20"]);
				Button["23"]["BorderSizePixel"] = 0;
				Button["23"]["TextSize"] = 14;
				Button["23"]["TextXAlignment"] = Enum.TextXAlignment.Left;
				Button["23"]["BackgroundColor3"] = Color3.fromRGB(255, 255, 255);
				Button["23"]["FontFace"] = Font.new([[rbxasset://fonts/families/Ubuntu.json]], Enum.FontWeight.Regular, Enum.FontStyle.Normal);
				Button["23"]["TextColor3"] = Color3.fromRGB(255, 255, 255);
				Button["23"]["BackgroundTransparency"] = 1;
				Button["23"]["Size"] = UDim2.new(1, -20, 1, 0);
				Button["23"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				Button["23"]["Text"] = options.name;
				Button["23"]["Name"] = [[Title]];

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Button.UIPadding
				Button["24"] = Instance.new("UIPadding", Button["20"]);
				Button["24"]["PaddingTop"] = UDim.new(0, 5);
				Button["24"]["PaddingRight"] = UDim.new(0, 5);
				Button["24"]["PaddingLeft"] = UDim.new(0, 5);
				Button["24"]["PaddingBottom"] = UDim.new(0, 5);

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Button.Icon
				Button["25"] = Instance.new("ImageLabel", Button["20"]);
				Button["25"]["AnchorPoint"] = Vector2.new(1, 0.5);
				Button["25"]["Image"] = [[rbxassetid://6764432293]];
				Button["25"]["ImageRectSize"] = Vector2.new(100, 100);
				Button["25"]["Size"] = UDim2.new(0, 22, 0, 22);
				Button["25"]["BackgroundTransparency"] = 1;
				Button["25"]["ImageRectOffset"] = Vector2.new(400, 0);
				Button["25"]["Name"] = [[Icon]];
				Button["25"]["Position"] = UDim2.new(1, 0, 0.5, 0);
			end
			
				-- Methods
			function Button:SetCallBack(fn)
				options.callback = fn
			end
			
				-- Logic
			do
				Button["20"].MouseEnter:Connect(function()
					Button.Hover = true

					kavo:tween(Button["22"], {Color = Color3.fromRGB(61,61,61)})

				end)
				
				Button["20"].MouseLeave:Connect(function()
					Button.Hover = false

					if not Button.MouseDown then
						kavo:tween(Button["22"], {Color = Color3.fromRGB(81,81,81)})
					end
				end)
				
				uis.InputBegan:Connect(function(input, gpe)
					if gpe then return end

					if input.UserInputType == Enum.UserInputType.MouseButton1 and Button.Hover then
						Button.MouseDown = true
						kavo:tween(Button["20"], {BackgroundColor3 = Color3.fromRGB(51,51,51)})
						kavo:tween(Button["22"], {Color = Color3.fromRGB(81,81,81)})
						options.callback()
					end
				end)
				
				uis.InputEnded:Connect(function(input, gpe)
					if gpe then return end

					if input.UserInputType == Enum.UserInputType.MouseButton1 then
						Button.MouseDown = false

						if Button.Hover then
							-- Hover state	
							kavo:tween(Button["20"], {BackgroundColor3 = Color3.fromRGB(31,31,31)})
							kavo:tween(Button["22"], {Color = Color3.fromRGB(101,101,101)})
						else
							-- Reset
							kavo:tween(Button["20"], {BackgroundColor3 = Color3.fromRGB(31,31,31)})
							kavo:tween(Button["22"], {Color = Color3.fromRGB(81,81,81)})

						end
					end
				end)
			end
			
			return Button
		end
		
		function Tab:NewLabel(options)
			options = kavo:validate({
				message = "Preview Label",
				icon = ""
			}, options or {})
			local Label = {}
			
				-- Render
			do
				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Label
				Label["34"] = Instance.new("Frame", Tab["1f"]);
				Label["34"]["BorderSizePixel"] = 0;
				Label["34"]["BackgroundColor3"] = Color3.fromRGB(31, 31, 31);
				Label["34"]["Size"] = UDim2.new(1, 0, 0, 25);
				Label["34"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				Label["34"]["Name"] = [[Label]];


				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Label.UICorner
				Label["35"] = Instance.new("UICorner", Label["34"]);
				Label["35"]["CornerRadius"] = UDim.new(0, 6);


				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Label.UIStroke
				Label["36"] = Instance.new("UIStroke", Label["34"]);
				Label["36"]["Color"] = Color3.fromRGB(81, 81, 81);
				Label["36"]["ApplyStrokeMode"] = Enum.ApplyStrokeMode.Border;


				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Label.Title
				Label["37"] = Instance.new("TextLabel", Label["34"]);
				Label["37"]["BorderSizePixel"] = 0;
				Label["37"]["TextSize"] = 14;
				Label["37"]["TextXAlignment"] = Enum.TextXAlignment.Left;
				Label["37"]["BackgroundColor3"] = Color3.fromRGB(255, 255, 255);
				Label["37"]["FontFace"] = Font.new([[rbxasset://fonts/families/Ubuntu.json]], Enum.FontWeight.Regular, Enum.FontStyle.Normal);
				Label["37"]["TextColor3"] = Color3.fromRGB(255, 255, 255);
				Label["37"]["BackgroundTransparency"] = 1;
				Label["37"]["Size"] = UDim2.new(1, -20, 1, 0);
				Label["37"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				Label["37"]["Name"] = [[Title]];
				Label["37"]["Text"] = options.message;
				Label["37"]["Position"] = UDim2.new(0, 20, 0, 0);


				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Label.UIPadding
				Label["3a"] = Instance.new("UIPadding", Label["34"]);
				Label["3a"]["PaddingTop"] = UDim.new(0, 5);
				Label["3a"]["PaddingRight"] = UDim.new(0, 5);
				Label["3a"]["PaddingLeft"] = UDim.new(0, 5);
				Label["3a"]["PaddingBottom"] = UDim.new(0, 6);


				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Label.Icon
				Label["39"] = Instance.new("ImageLabel", Label["34"]);
				Label["39"]["ImageColor3"] = Color3.fromRGB(76, 76, 76);
				Label["39"]["AnchorPoint"] = Vector2.new(0, 0.5);
				Label["39"]["Image"] = [[rbxassetid://8445470984]];
				Label["39"]["ImageRectSize"] = Vector2.new(96, 96);
				Label["39"]["Size"] = UDim2.new(0, 18, 0, 18);
				Label["39"]["BackgroundTransparency"] = 1;
				Label["39"]["ImageRectOffset"] = Vector2.new(804, 304);
				Label["39"]["Name"] = [[Icon]];
				Label["39"]["Position"] = UDim2.new(0, -2, 0.5, 0);
			end
			
			return Label
		end
		
		function Tab:NewInfo(options)
			options = kavo:validate({
				message = "Preview Info",
				icon = "rbxassetid://8445471499"
			}, options or {})
			local Info = {}
			
				-- Render
			do
				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Info
				Info["2e"] = Instance.new("Frame", Tab["1f"]);
				Info["2e"]["BorderSizePixel"] = 0;
				Info["2e"]["BackgroundColor3"] = Color3.fromRGB(4, 64, 89);
				Info["2e"]["Size"] = UDim2.new(1, 0, 0, 25);
				Info["2e"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				Info["2e"]["Name"] = [[Info]];


				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Info.UICorner
				Info["2f"] = Instance.new("UICorner", Info["2e"]);
				Info["2f"]["CornerRadius"] = UDim.new(0, 6);


				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Info.UIStroke
				Info["30"] = Instance.new("UIStroke", Info["2e"]);
				Info["30"]["Color"] = Color3.fromRGB(9, 126, 181);
				Info["30"]["ApplyStrokeMode"] = Enum.ApplyStrokeMode.Border;


				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Info.Title
				Info["31"] = Instance.new("TextLabel", Info["2e"]);
				Info["31"]["BorderSizePixel"] = 0;
				Info["31"]["TextSize"] = 14;
				Info["31"]["TextXAlignment"] = Enum.TextXAlignment.Left;
				Info["31"]["BackgroundColor3"] = Color3.fromRGB(255, 255, 255);
				Info["31"]["FontFace"] = Font.new([[rbxasset://fonts/families/Ubuntu.json]], Enum.FontWeight.Regular, Enum.FontStyle.Normal);
				Info["31"]["TextColor3"] = Color3.fromRGB(255, 255, 255);
				Info["31"]["BackgroundTransparency"] = 1;
				Info["31"]["Size"] = UDim2.new(1, -20, 1, 0);
				Info["31"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				Info["31"]["Text"] = options.message;
				Info["31"]["Name"] = [[Title]];
				Info["31"]["Position"] = UDim2.new(0, 20, 0, 0);


				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Info.UIPadding
				Info["32"] = Instance.new("UIPadding", Info["2e"]);
				Info["32"]["PaddingTop"] = UDim.new(0, 5);
				Info["32"]["PaddingRight"] = UDim.new(0, 5);
				Info["32"]["PaddingLeft"] = UDim.new(0, 5);
				Info["32"]["PaddingBottom"] = UDim.new(0, 6);


				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Info.Icon
				Info["33"] = Instance.new("ImageLabel", Info["2e"]);
				Info["33"]["ImageColor3"] = Color3.fromRGB(9, 126, 181);
				Info["33"]["AnchorPoint"] = Vector2.new(0, 0.5);
				Info["33"]["Image"] = [[rbxassetid://8445471499]];
				Info["33"]["ImageRectSize"] = Vector2.new(96, 96);
				Info["33"]["Size"] = UDim2.new(0, 20, 0, 20);
				Info["33"]["BackgroundTransparency"] = 1;
				Info["33"]["ImageRectOffset"] = Vector2.new(304, 104);
				Info["33"]["Name"] = [[Icon]];
				Info["33"]["Position"] = UDim2.new(0, -3, 0.5, 0);
			end
			
			return Info
		end
		
		function Tab:NewWarning(options)
			options = kavo:validate({
				message = "Preview Warning",
				icon = "rbxassetid://6764432408"
			}, options or {})
			local Warning = {}
			
				-- Render
			do
				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Warning
				Warning["28"] = Instance.new("Frame", Tab["1f"]);
				Warning["28"]["BorderSizePixel"] = 0;
				Warning["28"]["BackgroundColor3"] = Color3.fromRGB(56, 66, 0);
				Warning["28"]["Size"] = UDim2.new(1, 0, 0, 25);
				Warning["28"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				Warning["28"]["Name"] = [[Warning]];


				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Warning.UICorner
				Warning["29"] = Instance.new("UICorner", Warning["28"]);
				Warning["29"]["CornerRadius"] = UDim.new(0, 6);


				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Warning.UIStroke
				Warning["2a"] = Instance.new("UIStroke", Warning["28"]);
				Warning["2a"]["Color"] = Color3.fromRGB(128, 132, 7);
				Warning["2a"]["ApplyStrokeMode"] = Enum.ApplyStrokeMode.Border;


				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Warning.Title
				Warning["2b"] = Instance.new("TextLabel", Warning["28"]);
				Warning["2b"]["BorderSizePixel"] = 0;
				Warning["2b"]["TextSize"] = 14;
				Warning["2b"]["TextXAlignment"] = Enum.TextXAlignment.Left;
				Warning["2b"]["BackgroundColor3"] = Color3.fromRGB(255, 255, 255);
				Warning["2b"]["FontFace"] = Font.new([[rbxasset://fonts/families/Ubuntu.json]], Enum.FontWeight.Regular, Enum.FontStyle.Normal);
				Warning["2b"]["TextColor3"] = Color3.fromRGB(255, 255, 255);
				Warning["2b"]["BackgroundTransparency"] = 1;
				Warning["2b"]["Size"] = UDim2.new(1, -20, 1, 0);
				Warning["2b"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				Warning["2b"]["Text"] = options.message;
				Warning["2b"]["Name"] = [[Title]];
				Warning["2b"]["Position"] = UDim2.new(0, 20, 0, 0);


				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Warning.UIPadding
				Warning["2c"] = Instance.new("UIPadding", Warning["28"]);
				Warning["2c"]["PaddingTop"] = UDim.new(0, 5);
				Warning["2c"]["PaddingRight"] = UDim.new(0, 5);
				Warning["2c"]["PaddingLeft"] = UDim.new(0, 5);
				Warning["2c"]["PaddingBottom"] = UDim.new(0, 6);


				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Warning.Icon
				Warning["2d"] = Instance.new("ImageLabel", Warning["28"]);
				Warning["2d"]["BackgroundColor3"] = Color3.fromRGB(127, 127, 0);
				Warning["2d"]["ImageColor3"] = Color3.fromRGB(212, 205, 0);
				Warning["2d"]["AnchorPoint"] = Vector2.new(0, 0.5);
				Warning["2d"]["Image"] = [[rbxassetid://6764432408]];
				Warning["2d"]["ImageRectSize"] = Vector2.new(50, 50);
				Warning["2d"]["Size"] = UDim2.new(0, 22, 0, 22);
				Warning["2d"]["BackgroundTransparency"] = 1;
				Warning["2d"]["ImageRectOffset"] = Vector2.new(0, 900);
				Warning["2d"]["Name"] = [[Icon]];
				Warning["2d"]["Position"] = UDim2.new(0, -3, 0.5, 0);
			end
			
			return Warning
		end
		
		function Tab:NewSlider(options)
			options = kavo:validate({
				title = "Preview Slider",
				min = 0,
				max = 100,
				callback = function(v) end

			}, options or {})
			local Slider = {
				MouseDown = false,
				Hover = false,
				Connection = nil 
			}

			-- Render
			do
				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Slider
				Slider["3a"] = Instance.new("Frame", Tab["1f"]);
				Slider["3a"]["BorderSizePixel"] = 0;
				Slider["3a"]["BackgroundColor3"] = Color3.fromRGB(31, 31, 31);
				Slider["3a"]["Size"] = UDim2.new(1, 0, 0, 40);
				Slider["3a"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				Slider["3a"]["Name"] = [[Slider]];

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Slider.UICorner
				Slider["3b"] = Instance.new("UICorner", Slider["3a"]);
				Slider["3b"]["CornerRadius"] = UDim.new(0, 6);

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Slider.UIStroke
				Slider["3c"] = Instance.new("UIStroke", Slider["3a"]);
				Slider["3c"]["Color"] = Color3.fromRGB(81, 81, 81);
				Slider["3c"]["ApplyStrokeMode"] = Enum.ApplyStrokeMode.Border;

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Slider.Title
				Slider["3f"] = Instance.new("TextLabel", Slider["3a"]);
				Slider["3f"]["BorderSizePixel"] = 0;
				Slider["3f"]["TextSize"] = 14;
				Slider["3f"]["TextXAlignment"] = Enum.TextXAlignment.Left;
				Slider["3f"]["BackgroundColor3"] = Color3.fromRGB(255, 255, 255);
				Slider["3f"]["FontFace"] = Font.new([[rbxasset://fonts/families/Ubuntu.json]], Enum.FontWeight.Regular, Enum.FontStyle.Normal);
				Slider["3f"]["TextColor3"] = Color3.fromRGB(255, 255, 255);
				Slider["3f"]["BackgroundTransparency"] = 1;
				Slider["3f"]["Size"] = UDim2.new(1, -25, 1, -12);
				Slider["3f"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				Slider["3f"]["Text"] = options.title;
				Slider["3f"]["Name"] = [[Title]];

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Slider.UIPadding
				Slider["42"] = Instance.new("UIPadding", Slider["3a"]);
				Slider["42"]["PaddingTop"] = UDim.new(0, 5);
				Slider["42"]["PaddingRight"] = UDim.new(0, 5);
				Slider["42"]["PaddingLeft"] = UDim.new(0, 5);
				Slider["42"]["PaddingBottom"] = UDim.new(0, 5);

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Slider.Value
				Slider["3f"] = Instance.new("TextLabel", Slider["3a"]);
				Slider["3f"]["BorderSizePixel"] = 0;
				Slider["3f"]["TextSize"] = 14;
				Slider["3f"]["TextXAlignment"] = Enum.TextXAlignment.Right;
				Slider["3f"]["BackgroundColor3"] = Color3.fromRGB(255, 255, 255);
				Slider["3f"]["FontFace"] = Font.new([[rbxasset://fonts/families/Ubuntu.json]], Enum.FontWeight.Regular, Enum.FontStyle.Normal);
				Slider["3f"]["TextColor3"] = Color3.fromRGB(255, 255, 255);
				Slider["3f"]["BackgroundTransparency"] = 1;
				Slider["3f"]["AnchorPoint"] = Vector2.new(1, 0);
				Slider["3f"]["Size"] = UDim2.new(0, 22, 0, 18);
				Slider["3f"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				Slider["3f"]["Text"] = [[100]];
				Slider["3f"]["Name"] = [[Value]];
				Slider["3f"]["Position"] = UDim2.new(1, 0, 0, 0);

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Slider.SliderBack
				Slider["42"] = Instance.new("Frame", Slider["3a"]);
				Slider["42"]["BorderSizePixel"] = 0;
				Slider["42"]["BackgroundColor3"] = Color3.fromRGB(6, 6, 6);
				Slider["42"]["AnchorPoint"] = Vector2.new(0, 1);
				Slider["42"]["Size"] = UDim2.new(1, 0, 0, 5);
				Slider["42"]["Position"] = UDim2.new(0, 0, 1, 0);
				Slider["42"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				Slider["42"]["Name"] = [[SliderBack]];

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Slider.SliderBack.UICorner
				Slider["43"] = Instance.new("UICorner", Slider["42"]);


				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Slider.SliderBack.UIStroke
				Slider["44"] = Instance.new("UIStroke", Slider["42"]);
				Slider["44"]["Color"] = Color3.fromRGB(76, 76, 76);

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Slider.SliderBack.Draggable
				Slider["4z"] = Instance.new("Frame", Slider["42"]);
				Slider["4z"]["BorderSizePixel"] = 0;
				Slider["4z"]["BackgroundColor3"] = Color3.fromRGB(51, 51, 51);
				Slider["4z"]["Size"] = UDim2.new(0.5, 0, 1, 0);
				Slider["4z"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				Slider["4z"]["Name"] = [[Draggable]];

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.Slider.SliderBack.Draggable.UICorner
				Slider["44"] = Instance.new("UICorner", Slider["43"]);
			end

			-- Methods
			function Slider:SetValue(v)
				if v == nil then
					local percentage = math.clamp((mouse.X - Slider["42"].AbsolutePosition.X) / Slider["42"].AbsoluteSize.X, 0, 1)
					local value = math.round(((options.max - options.min) * percentage) + options.min)

					Slider["3f"].Text = tostring(value)
					Slider["4z"].Size = UDim2.fromScale(percentage, 1)
				else
					Slider["3f"].Text = tostring(v)
					Slider["4z"].Size = UDim2.fromScale(((v - options.min) / (options.max - options.min)), 1)
				end
				options.callback(Slider:GetValue())
			end

			function Slider:GetValue()
				return tonumber(Slider["3f"].Text)
			end

			-- Logic
			do
				Slider["3a"].MouseEnter:Connect(function()
					Slider.Hover = true

					kavo:tween(Slider["3c"], {Color = Color3.fromRGB(61,61,61)})
					kavo:tween(Slider["42"], {BackgroundColor3  = Color3.fromRGB(41,41,41)})
					--kavo:tween(Slider["41"], {BackgroundColor3 = Color3.fromRGB(82,82,82)})

				end)

				Slider["3a"].MouseLeave:Connect(function()
					Slider.Hover = false

					if not Slider.MouseDown then
						kavo:tween(Slider["3c"], {Color = Color3.fromRGB(81,81,81)})
						kavo:tween(Slider["42"], {BackgroundColor3  = Color3.fromRGB(61,61,61)})
						--kavo:tween(Slider["41"], {BackgroundColor3 = Color3.fromRGB(82,82,82)})
					end
				end)

				uis.InputBegan:Connect(function(input, gpe)
					if gpe then return end

					if input.UserInputType == Enum.UserInputType.MouseButton1 and Slider.Hover then
						Slider.MouseDown = true
						kavo:tween(Slider["3a"], {BackgroundColor3 = Color3.fromRGB(51,51,51)})
						kavo:tween(Slider["3c"], {Color = Color3.fromRGB(81,81,81)})
						kavo:tween(Slider["42"], {BackgroundColor3  = Color3.fromRGB(101,101,101)})
						--kavo:tween(Slider["41"], {BackgroundColor3 = Color3.fromRGB(51,51,51)})

						if not Slider.Connection then
							Slider.Connection = runService.RenderStepped:Connect(function()
								Slider:SetValue()
							end)
						end
					end
				end)

				uis.InputEnded:Connect(function(input, gpe)
					if gpe then return end

					if input.UserInputType == Enum.UserInputType.MouseButton1 then
						Slider.MouseDown = false

						if Slider.Hover then
							-- Hover state	
							kavo:tween(Slider["3a"], {BackgroundColor3 = Color3.fromRGB(31,31,31)})
							kavo:tween(Slider["3c"], {Color = Color3.fromRGB(102,102,102)})
							kavo:tween(Slider["42"], {BackgroundColor3  = Color3.fromRGB(82,82,82)})
							--kavo:tween(Slider["41"], {BackgroundColor3 = Color3.fromRGB(102,102,102)})

						else
							-- Reset
							kavo:tween(Slider["3a"], {BackgroundColor3 = Color3.fromRGB(31,31,31)})
							kavo:tween(Slider["3c"], {Color = Color3.fromRGB(81,81,81)})
							kavo:tween(Slider["42"], {BackgroundColor3  = Color3.fromRGB(61,61,61)})
							--kavo:tween(Slider["41"], {BackgroundColor3 = Color3.fromRGB(31,31,31)})

						end
						if Slider.Connection then Slider.Connection:Disconnect() end
						Slider.Connection = nil
					end
				end)
			end

			return Slider
		end
		
		function Tab:NewToggle(options)
			options = kavo:validate({
				title = "Preview Toggle",
				callback = function() end
			}, options or {})

			local Toggle = {
				Hover = false,
				MouseDown = false,
				State = false
			}
			
				-- Render
			do
				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.ToggleInActive
				Toggle["56"] = Instance.new("Frame", Tab["1f"]);
				Toggle["56"]["BorderSizePixel"] = 0;
				Toggle["56"]["BackgroundColor3"] = Color3.fromRGB(31, 31, 31);
				Toggle["56"]["Size"] = UDim2.new(1, 0, 0, 30);
				Toggle["56"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				Toggle["56"]["Name"] = [[ToggleInActive]];

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.ToggleInActive.UICorner
				Toggle["57"] = Instance.new("UICorner", Toggle["56"]);
				Toggle["57"]["CornerRadius"] = UDim.new(0, 6);

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.ToggleInActive.UIStroke
				Toggle["58"] = Instance.new("UIStroke", Toggle["56"]);
				Toggle["58"]["Color"] = Color3.fromRGB(81, 81, 81);
				Toggle["58"]["ApplyStrokeMode"] = Enum.ApplyStrokeMode.Border;

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.ToggleInActive.Title
				Toggle["59"] = Instance.new("TextLabel", Toggle["56"]);
				Toggle["59"]["BorderSizePixel"] = 0;
				Toggle["59"]["TextSize"] = 14;
				Toggle["59"]["TextXAlignment"] = Enum.TextXAlignment.Left;
				Toggle["59"]["BackgroundColor3"] = Color3.fromRGB(255, 255, 255);
				Toggle["59"]["FontFace"] = Font.new([[rbxasset://fonts/families/Ubuntu.json]], Enum.FontWeight.Regular, Enum.FontStyle.Normal);
				Toggle["59"]["TextColor3"] = Color3.fromRGB(255, 255, 255);
				Toggle["59"]["BackgroundTransparency"] = 1;
				Toggle["59"]["Size"] = UDim2.new(1, -20, 1, 0);
				Toggle["59"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				Toggle["59"]["Text"] = [[Toggle]];
				Toggle["59"]["Name"] = [[Title]];

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.ToggleInActive.UIPadding
				Toggle["5a"] = Instance.new("UIPadding", Toggle["56"]);
				Toggle["5a"]["PaddingTop"] = UDim.new(0, 5);
				Toggle["5a"]["PaddingRight"] = UDim.new(0, 5);
				Toggle["5a"]["PaddingLeft"] = UDim.new(0, 5);
				Toggle["5a"]["PaddingBottom"] = UDim.new(0, 5);

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.ToggleInActive.CheckmarkHolder
				Toggle["5b"] = Instance.new("Frame", Toggle["56"]);
				Toggle["5b"]["BorderSizePixel"] = 0;
				Toggle["5b"]["BackgroundColor3"] = Color3.fromRGB(51, 51, 51);
				Toggle["5b"]["AnchorPoint"] = Vector2.new(1, 0.5);
				Toggle["5b"]["Size"] = UDim2.new(0, 17, 0, 17);
				Toggle["5b"]["Position"] = UDim2.new(1, -3, 0.5, 0);
				Toggle["5b"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				Toggle["5b"]["Name"] = [[CheckmarkHolder]];

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.ToggleInActive.CheckmarkHolder.UICorner
				Toggle["5c"] = Instance.new("UICorner", Toggle["5b"]);
				Toggle["5c"]["CornerRadius"] = UDim.new(0, 4);

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.ToggleInActive.CheckmarkHolder.UIStroke
				Toggle["5d"] = Instance.new("UIStroke", Toggle["5b"]);
				Toggle["5d"]["Color"] = Color3.fromRGB(81, 81, 81);

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.ToggleInActive.CheckmarkHolder.Checkmark
				Toggle["5e"] = Instance.new("ImageLabel", Toggle["5b"]);
				Toggle["5e"]["AnchorPoint"] = Vector2.new(0.5, 0.5);
				Toggle["5e"]["Image"] = [[rbxassetid://6764432408]];
				Toggle["5e"]["ImageRectSize"] = Vector2.new(50, 50);
				Toggle["5e"]["Size"] = UDim2.new(0, 16, 0, 16);
				Toggle["5e"]["Visible"] = false;
				Toggle["5e"]["BackgroundTransparency"] = 1;
				Toggle["5e"]["ImageRectOffset"] = Vector2.new(200, 700);
				Toggle["5e"]["Name"] = [[Checkmark]];
				Toggle["5e"]["Position"] = UDim2.new(0.5, 0, 0.5, 0);
			end
			
			-- Methods
			function Toggle:Toggle(b)
				if b == nil then
					Toggle.State = not Toggle.State
				else
					Toggle.State = b
				end

				if Toggle.State then
					kavo:tween(Toggle["5b"], {BackgroundColor3 = Color3.fromRGB(9, 141, 0)})
					kavo:tween(Toggle["5e"], {ImageTransparency = 0})
					kavo:tween(Toggle["5d"], {Color = Color3.fromRGB(14, 213, 0)})
				else
					kavo:tween(Toggle["5b"], {BackgroundColor3 = Color3.fromRGB(50, 50, 50)})
					kavo:tween(Toggle["5e"], {ImageTransparency = 1})
					kavo:tween(Toggle["5d"], {Color = Color3.fromRGB(81, 81, 81)})
				end

				options.callback(Toggle.State)
			end
			
			-- Logic
			do
				Toggle["56"].MouseEnter:Connect(function()
					Toggle.Hover = true

					kavo:tween(Toggle["58"], {Color = Color3.fromRGB(61,61,61)})

				end)

				Toggle["56"].MouseLeave:Connect(function()
					Toggle.Hover = false

					if not Toggle.MouseDown then
						kavo:tween(Toggle["58"], {Color = Color3.fromRGB(81,81,81)})
					end
				end)

				uis.InputBegan:Connect(function(input, gpe)
					if gpe then return end

					if input.UserInputType == Enum.UserInputType.MouseButton1 and Toggle.Hover then
						Toggle.MouseDown = true
						kavo:tween(Toggle["56"], {BackgroundColor3 = Color3.fromRGB(51,51,51)})
						kavo:tween(Toggle["58"], {Color = Color3.fromRGB(81, 81, 81)})
						Toggle:Toggle()
					end
				end)

				uis.InputEnded:Connect(function(input, gpe)
					if gpe then return end

					if input.UserInputType == Enum.UserInputType.MouseButton1 then
						Toggle.MouseDown = false

						if Toggle.Hover then
							kavo:tween(Toggle["56"], {BackgroundColor3 = Color3.fromRGB(31, 31, 31)})
							kavo:tween(Toggle["58"], {Color = Color3.fromRGB(101,101,101)})
						else
							kavo:tween(Toggle["56"], {BackgroundColor3 = Color3.fromRGB(31, 31, 31)})
							kavo:tween(Toggle["58"], {Color = Color3.fromRGB(81,81,81)})
						end
					end
				end)
			end
			
			return Toggle
		end
		
		function Tab:NewDropDown(options)
			options = kavo:validate({
				title = "Preview DropDown",
				callback = function(v) end,
				items = {}
			}, options or {})

			local DropDown = {
				Items = {}, -- Start with empty table
				Open = false,
				MouseDown = false,
				Hover = false
			}
			
				-- Render
			do
				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.DropDown
				DropDown["45"] = Instance.new("Frame", Tab["1f"]);
				DropDown["45"]["BorderSizePixel"] = 0;
				DropDown["45"]["BackgroundColor3"] = Color3.fromRGB(31, 31, 31);
				DropDown["45"]["ClipsDescendants"] = true;
				DropDown["45"]["Size"] = UDim2.new(1, 0, 0, 30);
				DropDown["45"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				DropDown["45"]["Name"] = [[DropDown]];
				
				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.DropDown.UICorner
				DropDown["46"] = Instance.new("UICorner", DropDown["45"]);
				DropDown["46"]["CornerRadius"] = UDim.new(0, 6);
				
				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.DropDown.UIStroke
				DropDown["47"] = Instance.new("UIStroke", DropDown["45"]);
				DropDown["47"]["Color"] = Color3.fromRGB(81, 81, 81);
				DropDown["47"]["ApplyStrokeMode"] = Enum.ApplyStrokeMode.Border;


				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.DropDown.Title
				DropDown["48"] = Instance.new("TextLabel", DropDown["45"]);
				DropDown["48"]["BorderSizePixel"] = 0;
				DropDown["48"]["TextSize"] = 14;
				DropDown["48"]["TextXAlignment"] = Enum.TextXAlignment.Left;
				DropDown["48"]["BackgroundColor3"] = Color3.fromRGB(255, 255, 255);
				DropDown["48"]["FontFace"] = Font.new([[rbxasset://fonts/families/Ubuntu.json]], Enum.FontWeight.Regular, Enum.FontStyle.Normal);
				DropDown["48"]["TextColor3"] = Color3.fromRGB(255, 255, 255);
				DropDown["48"]["BackgroundTransparency"] = 1;
				DropDown["48"]["Size"] = UDim2.new(1, -20, 0, 20);
				DropDown["48"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				DropDown["48"]["Text"] = options.title;
				DropDown["48"]["Name"] = [[Title]];
				
				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.DropDown.UIPadding
				DropDown["49"] = Instance.new("UIPadding", DropDown["45"]);
				DropDown["49"]["PaddingTop"] = UDim.new(0, 5);
				DropDown["49"]["PaddingRight"] = UDim.new(0, 5);
				DropDown["49"]["PaddingLeft"] = UDim.new(0, 5);
				DropDown["49"]["PaddingBottom"] = UDim.new(0, 5);
				
				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.DropDown.Icon
				DropDown["4a"] = Instance.new("ImageLabel", DropDown["45"]);
				DropDown["4a"]["AnchorPoint"] = Vector2.new(1, 0);
				DropDown["4a"]["Image"] = [[rbxassetid://6764432408]];
				DropDown["4a"]["ImageRectSize"] = Vector2.new(50, 50);
				DropDown["4a"]["Size"] = UDim2.new(0, 20, 0, 20);
				DropDown["4a"]["BackgroundTransparency"] = 1;
				DropDown["4a"]["ImageRectOffset"] = Vector2.new(150, 0);
				DropDown["4a"]["Name"] = [[Icon]];
				DropDown["4a"]["Position"] = UDim2.new(1, 0, 0, 0);
				
				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.DropDown.OptionHolder
				DropDown["4b"] = Instance.new("Frame", DropDown["45"]);
				DropDown["4b"]["Visible"] = false;
				DropDown["4b"]["BorderSizePixel"] = 0;
				DropDown["4b"]["BackgroundColor3"] = Color3.fromRGB(255, 255, 255);
				DropDown["4b"]["Size"] = UDim2.new(1, 0, 1, -24);
				DropDown["4b"]["Position"] = UDim2.new(0, 0, 0, 26);
				DropDown["4b"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				DropDown["4b"]["Name"] = [[OptionHolder]];
				DropDown["4b"]["BackgroundTransparency"] = 1;
				
				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.DropDown.OptionHolder.UIListLayout
				DropDown["4c"] = Instance.new("UIListLayout", DropDown["4b"]);
				DropDown["4c"]["Padding"] = UDim.new(0, 4);
				DropDown["4c"]["SortOrder"] = Enum.SortOrder.LayoutOrder;
				
					-- Methdos
				function DropDown:Add(id, value)
					if DropDown.Items[id] ~= nil then
						return
					end
					
					-- Create the entry in Items table
					DropDown.Items[id] = {
						value = value,
						instance = {},
						Hover = false,
						MouseDown = false
					}
					
					-- Get a reference to the item
					local item = DropDown.Items[id]
					
					-- Create the option TextLabel
					item.instance["4d"] = Instance.new("TextLabel", DropDown["4b"]);
					item.instance["4d"]["BorderSizePixel"] = 0;
					item.instance["4d"]["TextSize"] = 14;
					item.instance["4d"]["BackgroundColor3"] = Color3.fromRGB(51, 51, 51);
					item.instance["4d"]["FontFace"] = Font.new([[rbxasset://fonts/families/Ubuntu.json]], Enum.FontWeight.Regular, Enum.FontStyle.Normal);
					item.instance["4d"]["TextColor3"] = Color3.fromRGB(185, 185, 185);
					item.instance["4d"]["Size"] = UDim2.new(1, 0, 0, 16);
					item.instance["4d"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
					item.instance["4d"]["Text"] = id;
					item.instance["4d"]["Name"] = [[InactiveOption]];
					
					-- UIStroke
					item.instance["4e"] = Instance.new("UIStroke", item.instance["4d"]);
					item.instance["4e"]["Color"] = Color3.fromRGB(81, 81, 81);
					item.instance["4e"]["ApplyStrokeMode"] = Enum.ApplyStrokeMode.Border;
					
					-- UICorner
					item.instance["4f"] = Instance.new("UICorner", item.instance["4d"]);
					item.instance["4f"]["CornerRadius"] = UDim.new(0, 2);
					
					-- Mouse Enter
					item.instance["4d"].MouseEnter:Connect(function()
						item.Hover = true
						kavo:tween(item.instance["4e"], {Color = Color3.fromRGB(61,61,61)})
					end)
					
					-- Mouse Leave
					item.instance["4d"].MouseLeave:Connect(function()
						item.Hover = false
						if not item.MouseDown then
							kavo:tween(item.instance["4e"], {Color = Color3.fromRGB(81,81,81)})
						end
					end)
					
					-- Mouse Click (using InputBegan since it's a TextLabel)
					item.instance["4d"].InputBegan:Connect(function(input, gpe)
						if gpe then return end
						if input.UserInputType == Enum.UserInputType.MouseButton1 and item.Hover then
							item.MouseDown = true
							kavo:tween(item.instance["4d"], {BackgroundColor3 = Color3.fromRGB(51,51,51)})
							kavo:tween(item.instance["4e"], {Color = Color3.fromRGB(81,81,81)})

							-- Call the callback with the value
							options.callback(value)

							-- Update DropDown title to show selected option
							DropDown["48"].Text = id

							-- Close the DropDown
							DropDown.Open = false
							DropDown:Toggle()
						end
					end)
					
					-- Mouse Release
					uis.InputEnded:Connect(function(input, gpe)
						if gpe then return end
						if input.UserInputType == Enum.UserInputType.MouseButton1 then
							item.MouseDown = false
							if item.Hover then
								kavo:tween(item.instance["4d"], {BackgroundColor3 = Color3.fromRGB(31,31,31)})
								kavo:tween(item.instance["4e"], {Color = Color3.fromRGB(101,101,101)})
							else
								kavo:tween(item.instance["4d"], {BackgroundColor3 = Color3.fromRGB(31,31,31)})
								kavo:tween(item.instance["4e"], {Color = Color3.fromRGB(81,81,81)})
							end
						end
					end)
				end
				
				function DropDown:Remove(id)
					if self.Items[id] and self.Items[id].instance["4d"] then
						self.Items[id].instance["4d"]:Destroy()
						self.Items[id] = nil
					end
				end
				
				function DropDown:Clear()
					for id, item in pairs(self.Items) do
						if item.instance["4d"] then
							item.instance["4d"]:Destroy()
						end
					end
					self.Items = {} -- Update size after clearing (will set to 0)
				end
				
				function DropDown:Toggle()
					if DropDown.Open then
						kavo:tween(DropDown["45"], {Size = UDim2.new(1, 0, 0, 30)}, function()
							DropDown["4b"].Visible = false
						end)
					else
						local count = 0
						for i, v in pairs(DropDown.Items) do
							if v ~= nil then
								count += 1
							end
						end
						DropDown["4b"].Visible = true
						kavo:tween(DropDown["45"], {Size = UDim2.new(1, 0, 0, 30 + (count * 20) + 4)})
					end	
					DropDown.Open = not DropDown.Open
					DropDown["4b"].Visible = DropDown.Open
				end
				
				-- Logic
				do
					DropDown["45"].MouseEnter:Connect(function()
						DropDown.Hover = true

						kavo:tween(DropDown["47"], {Color = Color3.fromRGB(61,61,61)})

					end)

					DropDown["45"].MouseLeave:Connect(function()
						DropDown.Hover = false

						if not DropDown.MouseDown then
							kavo:tween(DropDown["47"], {Color = Color3.fromRGB(81,81,81)})
						end
					end)

					uis.InputBegan:Connect(function(input, gpe)
						if gpe then return end

						if input.UserInputType == Enum.UserInputType.MouseButton1 and DropDown.Hover then
							DropDown.MouseDown = true
							kavo:tween(DropDown["45"], {BackgroundColor3 = Color3.fromRGB(51,51,51)})
							kavo:tween(DropDown["47"], {Color = Color3.fromRGB(81,81,81)})
							DropDown:Toggle()
						end
					end)

					uis.InputEnded:Connect(function(input, gpe)
						if gpe then return end

						if input.UserInputType == Enum.UserInputType.MouseButton1 then
							DropDown.MouseDown = false

							if DropDown.Hover then
								-- Hover state	
								kavo:tween(DropDown["45"], {BackgroundColor3 = Color3.fromRGB(31,31,31)})
								kavo:tween(DropDown["47"], {Color = Color3.fromRGB(101,101,101)})
							else
								-- Reset
								kavo:tween(DropDown["45"], {BackgroundColor3 = Color3.fromRGB(31,31,31)})
								kavo:tween(DropDown["47"], {Color = Color3.fromRGB(81,81,81)})

							end
						end
					end)
				end
			end
			
			 return DropDown
		end
		
		function Tab:NewTextBox(options)
			options = kavo:validate({
				title = "Preview TextBox",
				placeholder = "...",
				callback = function(text) end
			}, options or {})

			local TextBox = {}

			-- Render
			do
				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.TextBox
				TextBox["68"] = Instance.new("Frame", Tab["1f"]);
				TextBox["68"]["BorderSizePixel"] = 0;
				TextBox["68"]["BackgroundColor3"] = Color3.fromRGB(31, 31, 31);
				TextBox["68"]["Size"] = UDim2.new(1, 0, 0, 30);
				TextBox["68"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				TextBox["68"]["Name"] = [[TextBox]];


				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.TextBox.UICorner
				TextBox["69"] = Instance.new("UICorner", TextBox["68"]);
				TextBox["69"]["CornerRadius"] = UDim.new(0, 6);


				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.TextBox.UIStroke
				TextBox["6a"] = Instance.new("UIStroke", TextBox["68"]);
				TextBox["6a"]["Color"] = Color3.fromRGB(81, 81, 81);
				TextBox["6a"]["ApplyStrokeMode"] = Enum.ApplyStrokeMode.Border;


				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.TextBox.Title
				TextBox["6b"] = Instance.new("TextLabel", TextBox["68"]);
				TextBox["6b"]["BorderSizePixel"] = 0;
				TextBox["6b"]["TextSize"] = 14;
				TextBox["6b"]["TextXAlignment"] = Enum.TextXAlignment.Left;
				TextBox["6b"]["BackgroundColor3"] = Color3.fromRGB(255, 255, 255);
				TextBox["6b"]["FontFace"] = Font.new([[rbxasset://fonts/families/Ubuntu.json]], Enum.FontWeight.Regular, Enum.FontStyle.Normal);
				TextBox["6b"]["TextColor3"] = Color3.fromRGB(255, 255, 255);
				TextBox["6b"]["BackgroundTransparency"] = 1;
				TextBox["6b"]["Size"] = UDim2.new(1, -60, 1, 0);
				TextBox["6b"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				TextBox["6b"]["Text"] = [[TextBox]];
				TextBox["6b"]["Name"] = [[Title]];


				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.TextBox.UIPadding
				TextBox["6c"] = Instance.new("UIPadding", TextBox["68"]);
				TextBox["6c"]["PaddingTop"] = UDim.new(0, 5);
				TextBox["6c"]["PaddingRight"] = UDim.new(0, 5);
				TextBox["6c"]["PaddingLeft"] = UDim.new(0, 5);
				TextBox["6c"]["PaddingBottom"] = UDim.new(0, 5);


				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.TextBox.Write
				TextBox["6d"] = Instance.new("TextBox", TextBox["68"]);
				TextBox["6d"]["Active"] = false;
				TextBox["6d"]["Name"] = [[Write]];
				TextBox["6d"]["PlaceholderColor3"] = Color3.fromRGB(0, 0, 0);
				TextBox["6d"]["BorderSizePixel"] = 0;
				TextBox["6d"]["TextSize"] = 14;
				TextBox["6d"]["TextColor3"] = Color3.fromRGB(255, 255, 255);
				TextBox["6d"]["BackgroundColor3"] = Color3.fromRGB(51, 51, 51);
				TextBox["6d"]["FontFace"] = Font.new([[rbxasset://fonts/families/Ubuntu.json]], Enum.FontWeight.Regular, Enum.FontStyle.Normal);
				TextBox["6d"]["Selectable"] = false;
				TextBox["6d"]["AnchorPoint"] = Vector2.new(1, 0.5);
				TextBox["6d"]["Size"] = UDim2.new(0, 70, 0, 17);
				TextBox["6d"]["Position"] = UDim2.new(1, -3, 0.5, 0);
				TextBox["6d"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				TextBox["6d"]["Text"] = [[...]];
				TextBox["6d"]["TextXAlignment"] = Enum.TextXAlignment.Center;
				TextBox["6d"]["TextScaled"] = true


				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.TextBox.Write.UICorner
				TextBox["6e"] = Instance.new("UICorner", TextBox["6d"]);
				TextBox["6e"]["CornerRadius"] = UDim.new(0, 4);


				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.TextBox.Write.UIStroke
				TextBox["6f"] = Instance.new("UIStroke", TextBox["6d"]);
				TextBox["6f"]["Color"] = Color3.fromRGB(81, 81, 81);
				TextBox["6f"]["ApplyStrokeMode"] = Enum.ApplyStrokeMode.Border;
			end

			-- Functionality (from our previous discussion)
			local shouldClear = false

			-- When user finishes typing (presses Enter)
			TextBox["6d"].FocusLost:Connect(function(enterPressed)
				if enterPressed and TextBox["6d"].Text ~= "" then
					local enteredText = TextBox["6d"].Text
					options.callback(enteredText)
					shouldClear = true
				end
			end)

			-- When user clicks back into the textbox
			TextBox["6d"].Focused:Connect(function()
				if shouldClear then
					TextBox["6d"].Text = ""
					shouldClear = false
				end
			end)

			-- Hover effect on the container (optional)
			local hoverConnection = nil
			TextBox["68"].MouseEnter:Connect(function()
				kavo:tween(TextBox["6a"], {Color = Color3.fromRGB(101,101,101)})
			end)

			TextBox["68"].MouseLeave:Connect(function()
				kavo:tween(TextBox["6a"], {Color = Color3.fromRGB(81,81,81)})
			end)

			-- Return methods for external control
			local TextBoxMethods = {}

			function TextBoxMethods:SetText(text)
				TextBox["6d"].Text = text
			end

			function TextBoxMethods:GetText()
				return TextBox["6d"].Text
			end

			function TextBoxMethods:Clear()
				TextBox["6d"].Text = ""
			end

			function TextBoxMethods:SetPlaceholder(text)
				TextBox["6d"].PlaceholderText = text
			end

			return TextBoxMethods
		end
		
		function Tab:NewKeyBind(options)
			options = kavo:validate({
				title = "Preview Keybind",
				defaultKey = "None",
				defaultEnabled = true,
				callback = function(key, isEnabled) end
			}, options or {})

			local KeyBind = {
				State = options.defaultEnabled,
				CurrentKey = options.defaultKey,
				IsListening = false,
				Connection = nil
			}

			-- Render
			do
				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.KeyBind
				KeyBind["70"] = Instance.new("Frame", Tab["1f"]);
				KeyBind["70"]["BorderSizePixel"] = 0;
				KeyBind["70"]["BackgroundColor3"] = Color3.fromRGB(31, 31, 31);
				KeyBind["70"]["Size"] = UDim2.new(1, 0, 0, 30);
				KeyBind["70"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				KeyBind["70"]["Name"] = [[KeyBind]];

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.KeyBind.UICorner
				KeyBind["71"] = Instance.new("UICorner", KeyBind["70"]);
				KeyBind["71"]["CornerRadius"] = UDim.new(0, 6);

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.KeyBind.UIStroke
				KeyBind["72"] = Instance.new("UIStroke", KeyBind["70"]);
				KeyBind["72"]["Color"] = Color3.fromRGB(81, 81, 81);
				KeyBind["72"]["ApplyStrokeMode"] = Enum.ApplyStrokeMode.Border;

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.KeyBind.Title
				KeyBind["73"] = Instance.new("TextLabel", KeyBind["70"]);
				KeyBind["73"]["BorderSizePixel"] = 0;
				KeyBind["73"]["TextSize"] = 14;
				KeyBind["73"]["TextXAlignment"] = Enum.TextXAlignment.Left;
				KeyBind["73"]["BackgroundColor3"] = Color3.fromRGB(255, 255, 255);
				KeyBind["73"]["FontFace"] = Font.new([[rbxasset://fonts/families/Ubuntu.json]], Enum.FontWeight.Regular, Enum.FontStyle.Normal);
				KeyBind["73"]["TextColor3"] = Color3.fromRGB(255, 255, 255);
				KeyBind["73"]["BackgroundTransparency"] = 1;
				KeyBind["73"]["Size"] = UDim2.new(1, -60, 1, 0);
				KeyBind["73"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				KeyBind["73"]["Text"] = options.title;
				KeyBind["73"]["Name"] = [[Title]];

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.KeyBind.UIPadding
				KeyBind["74"] = Instance.new("UIPadding", KeyBind["70"]);
				KeyBind["74"]["PaddingTop"] = UDim.new(0, 5);
				KeyBind["74"]["PaddingRight"] = UDim.new(0, 5);
				KeyBind["74"]["PaddingLeft"] = UDim.new(0, 5);
				KeyBind["74"]["PaddingBottom"] = UDim.new(0, 5);

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.KeyBind.KeyWrite
				KeyBind["75"] = Instance.new("TextButton", KeyBind["70"]);
				KeyBind["75"]["TextWrapped"] = true;
				KeyBind["75"]["Active"] = false;
				KeyBind["75"]["BorderSizePixel"] = 0;
				KeyBind["75"]["TextSize"] = 14;
				KeyBind["75"]["TextColor3"] = Color3.fromRGB(255, 255, 255);
				KeyBind["75"]["BackgroundColor3"] = Color3.fromRGB(51, 51, 51);
				KeyBind["75"]["FontFace"] = Font.new([[rbxasset://fonts/families/Ubuntu.json]], Enum.FontWeight.Regular, Enum.FontStyle.Normal);
				KeyBind["75"]["Selectable"] = false;
				KeyBind["75"]["AnchorPoint"] = Vector2.new(1, 0.5);
				KeyBind["75"]["Size"] = UDim2.new(0, 35, 0, 17);
				KeyBind["75"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				KeyBind["75"]["Text"] = KeyBind.CurrentKey;
				KeyBind["75"]["Name"] = [[KeyWrite]];
				KeyBind["75"]["Position"] = UDim2.new(1, -3, 0.5, 0);

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.KeyBind.KeyWrite.UICorner
				KeyBind["76"] = Instance.new("UICorner", KeyBind["75"]);
				KeyBind["76"]["CornerRadius"] = UDim.new(0, 4);

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.KeyBind.KeyWrite.UIStroke
				KeyBind["77"] = Instance.new("UIStroke", KeyBind["75"]);
				KeyBind["77"]["Color"] = Color3.fromRGB(81, 81, 81);
				KeyBind["77"]["ApplyStrokeMode"] = Enum.ApplyStrokeMode.Border;

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.KeyBind.SwitchBtn
				KeyBind["78"] = Instance.new("TextButton", KeyBind["70"]);
				KeyBind["78"]["TextWrapped"] = true;
				KeyBind["78"]["Active"] = false;
				KeyBind["78"]["BorderSizePixel"] = 0;
				KeyBind["78"]["TextSize"] = 14;
				KeyBind["78"]["TextColor3"] = Color3.fromRGB(255, 255, 255);
				KeyBind["78"]["BackgroundColor3"] = KeyBind.State and Color3.fromRGB(9, 141, 0) or Color3.fromRGB(51, 51, 51);
				KeyBind["78"]["FontFace"] = Font.new([[rbxasset://fonts/families/Ubuntu.json]], Enum.FontWeight.Regular, Enum.FontStyle.Normal);
				KeyBind["78"]["Selectable"] = false;
				KeyBind["78"]["AnchorPoint"] = Vector2.new(1, 0.5);
				KeyBind["78"]["Size"] = UDim2.new(0, 20, 0, 15);
				KeyBind["78"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				KeyBind["78"]["Text"] = KeyBind.State and "✓" or "✗";
				KeyBind["78"]["Name"] = [[SwitchBtn]];
				KeyBind["78"]["Position"] = UDim2.new(1, -46, 0.5, 0);

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.KeyBind.SwitchBtn.UICorner
				KeyBind["79"] = Instance.new("UICorner", KeyBind["78"]);
				KeyBind["79"]["CornerRadius"] = UDim.new(0, 4);

				-- StarterGui.MyLibrary.Main.ContentContainer.HomeTab.KeyBind.SwitchBtn.UIStroke
				KeyBind["7a"] = Instance.new("UIStroke", KeyBind["78"]);
				KeyBind["7a"]["Color"] = KeyBind.State and Color3.fromRGB(14, 213, 0) or Color3.fromRGB(81, 81, 81);
				KeyBind["7a"]["ApplyStrokeMode"] = Enum.ApplyStrokeMode.Border;

				-- Listening Indicator (hidden by default)
				KeyBind["7b"] = Instance.new("TextButton", KeyBind["70"]);
				KeyBind["7b"]["TextWrapped"] = true;
				KeyBind["7b"]["Active"] = false;
				KeyBind["7b"]["BorderSizePixel"] = 0;
				KeyBind["7b"]["TextSize"] = 14;
				KeyBind["7b"]["TextColor3"] = Color3.fromRGB(255, 255, 0);
				KeyBind["7b"]["BackgroundColor3"] = Color3.fromRGB(51, 51, 51);
				KeyBind["7b"]["FontFace"] = Font.new([[rbxasset://fonts/families/Ubuntu.json]], Enum.FontWeight.Regular, Enum.FontStyle.Normal);
				KeyBind["7b"]["Selectable"] = false;
				KeyBind["7b"]["AnchorPoint"] = Vector2.new(1, 0.5);
				KeyBind["7b"]["Size"] = UDim2.new(0, 35, 0, 17);
				KeyBind["7b"]["BorderColor3"] = Color3.fromRGB(0, 0, 0);
				KeyBind["7b"]["Text"] = [[...]];
				KeyBind["7b"]["Visible"] = false;
				KeyBind["7b"]["Name"] = [[ListeningIndicator]];
				KeyBind["7b"]["Position"] = UDim2.new(1, -3, 0.5, 0);

				-- Listening Indicator Corner
				KeyBind["7c"] = Instance.new("UICorner", KeyBind["7b"]);
				KeyBind["7c"]["CornerRadius"] = UDim.new(0, 4);

				-- Listening Indicator Stroke
				KeyBind["7d"] = Instance.new("UIStroke", KeyBind["7b"]);
				KeyBind["7d"]["Color"] = Color3.fromRGB(81, 81, 81);
			end

			-- ========== FUNCTIONALITY (No changes to render above) ==========

			-- Helper function to convert InputType to readable string
			local function getKeyName(input)
				if input.UserInputType == Enum.UserInputType.Keyboard then
					return input.KeyCode.Name
				elseif input.UserInputType == Enum.UserInputType.MouseButton1 then
					return "LeftMouse"
				elseif input.UserInputType == Enum.UserInputType.MouseButton2 then
					return "RightMouse"
				elseif input.UserInputType == Enum.UserInputType.MouseButton3 then
					return "MiddleMouse"
				else
					return input.UserInputType.Name
				end
			end

			-- Function to update switch button appearance
			local function updateSwitchButton()
				if KeyBind.State then
					kavo:tween(KeyBind["78"], {BackgroundColor3 = Color3.fromRGB(9, 141, 0)})
					kavo:tween(KeyBind["7a"], {Color = Color3.fromRGB(14, 213, 0)})
					KeyBind["78"].Text = "✓"
				else
					kavo:tween(KeyBind["78"], {BackgroundColor3 = Color3.fromRGB(51, 51, 51)})
					kavo:tween(KeyBind["7a"], {Color = Color3.fromRGB(81, 81, 81)})
					KeyBind["78"].Text = ""
				end
			end

			-- Function to start listening for a key
			local function startListening()
				KeyBind.IsListening = true
				KeyBind["75"].Visible = false
				KeyBind["7b"].Visible = true

				local connection
				connection = uis.InputBegan:Connect(function(input, gpe)
					if gpe then return end
					if not KeyBind.IsListening then return end

					local keyName = getKeyName(input)
					KeyBind.CurrentKey = keyName
					KeyBind["75"].Text = keyName

					KeyBind.IsListening = false
					KeyBind["75"].Visible = true
					KeyBind["7b"].Visible = false
					connection:Disconnect()

					options.callback(KeyBind.CurrentKey, KeyBind.State)
				end)
			end

			-- Key button click to start binding
			KeyBind["75"].MouseButton1Click:Connect(function()
				startListening()
			end)

			-- Main keybind detection (when the bound key is pressed)
			local function updateKeyConnection()
				if KeyBind.Connection then
					KeyBind.Connection:Disconnect()
					KeyBind.Connection = nil
				end

				if KeyBind.State and KeyBind.CurrentKey ~= "None" then
					KeyBind.Connection = uis.InputBegan:Connect(function(input, gpe)
						if gpe then return end
						local keyName = getKeyName(input)
						if keyName == KeyBind.CurrentKey then
							options.callback(KeyBind.CurrentKey, KeyBind.State)
						end
					end)
				end
			end
			
			-- Switch button click to enable/disable
			KeyBind["78"].MouseButton1Click:Connect(function()
				KeyBind.State = not KeyBind.State
				updateSwitchButton()

				updateKeyConnection()
			end)

			-- Hover effects
			KeyBind["70"].MouseEnter:Connect(function()
				kavo:tween(KeyBind["72"], {Color = Color3.fromRGB(101,101,101)})
			end)

			KeyBind["70"].MouseLeave:Connect(function()
				kavo:tween(KeyBind["72"], {Color = Color3.fromRGB(81,81,81)})
			end)

			KeyBind["75"].MouseEnter:Connect(function()
				kavo:tween(KeyBind["77"], {Color = Color3.fromRGB(101,101,101)})
			end)

			KeyBind["75"].MouseLeave:Connect(function()
				kavo:tween(KeyBind["77"], {Color = Color3.fromRGB(81,81,81)})
			end)

			KeyBind["78"].MouseEnter:Connect(function()
				kavo:tween(KeyBind["7a"], {Color = Color3.fromRGB(101,101,101)})
			end)

			KeyBind["78"].MouseLeave:Connect(function()
				if KeyBind.State then
					kavo:tween(KeyBind["7a"], {Color = Color3.fromRGB(14, 213, 0)})
				else
					kavo:tween(KeyBind["7a"], {Color = Color3.fromRGB(81,81,81)})
				end
			end)

			-- Initialize
			updateSwitchButton()
			updateKeyConnection()

			-- Return methods
			local KeyBindMethods = {}

			function KeyBindMethods:GetKey()
				return KeyBind.CurrentKey
			end

			function KeyBindMethods:SetKey(key)
				KeyBind.CurrentKey = key
				KeyBind["75"].Text = key
				updateKeyConnection()
			end

			function KeyBindMethods:GetState()
				return KeyBind.State
			end

			function KeyBindMethods:SetState(state)
				KeyBind.State = state
				updateSwitchButton()
				updateKeyConnection()
			end

			return KeyBindMethods
		end
		
		return Tab
	end
	
	return GUI
end
