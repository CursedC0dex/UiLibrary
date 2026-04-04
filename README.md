Cursed Library

Loader

local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/CursedC0dex/UiLibrary/refs/heads/main/source.lua"))()

Main UI

local Window = Library.CreateLib {
	name = "Cursed UI Library"
}


Tab

local Tab = Window:NewTab({
	name = "Tab",
	icon = "rbxassetid://6764432408"
})


Button

local Button = Tab:NewButton({
	name = "Button", 
	callback = function()
		print("hi") 
end})


Labels

local Label = Tab:NewLabel({
	message = "Label", 
})


local Info = Tab:NewInfo({	
	message = "Info Label",
})


local Warn = Tab:NewWarning({	
	message = "Warning Label",
})


Slider

local Slider = Tab:NewSlider({
	title = "Slider",
	min = 0,
	max = 100,
	callback = function(value)
		game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = value 
end})


Toggle

local Toggle = Tab:NewToggle({
	title = "Toggle",
	callback = function(state)
		if state then
			print("On")
		else
			print("off")
		end
	end,
})


DropDown

local DropDown = Tab:NewDropDown({
	title = "DropDown",
	callback = function(v)
		game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = v
	end,
})

DropDown:Add("WS 50", 50)

DropDown:Add("WS 100", 100)

DropDown:Add("WS 10", 10)

DropDown:Add("WS 30", 30)


TextBox

local TextBox = Tab:NewTextBox({
	title = "TextBox",
	placeholder = "...",
	callback = function(text)
		game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = text
	end
})


KeyBind

local KeyBind = Tab:NewKeyBind({
	title = "KeyBind",
	defaultKey = "F",
	defaultEnabled = true,
	callback = function(key, isEnabled)
		if isEnabled then
			print("Key " .. key .. " pressed!")
		end
	end
})
