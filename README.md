# Midnight - Documentation

Simple, clean, and premium UI library for Roblox. This version includes built-in mobile support, dynamic title coloring for "midnight", and a customizable watermark.

### 🚀 Quick Load
```lua
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/jujuuufx/MidnightUI/refs/heads/main/ui.lua"))()
```

---

### 🪟 The Window
This is your main setup. You can customize the title, logo size, and even add a watermark right here.

```lua
local Window = Library:Window({
    Name = "midnight - The Bronx 🐍", -- "night" will automatically be colored blue!
    Version = "v2.1",
    Logo = "yourassetID",
    LogoSize = 35, -- Bigger logo? Set it here (Default is 22)
    Watermark = "yourwatermark", -- Optional watermark text
    FadeSpeed = 0.25
})
```

---

### 📑 Pages & Sections
Once you have a window, you need to add pages (tabs) and sections (containers).

```lua
-- Create a Tab
local Home = Window:Page({
    Name = "Home",
    Icon = "rbxassetid://123456789"
})

-- Create a Section (Side 1 is Left, Side 2 is Right)
local Combat = Home:Section({
    Name = "Combat Features",
    Side = 1 
})
```

---

### ⚙️ UI Elements
Add these inside any section.

#### Toggles
```lua
Combat:Toggle({
    Name = "Auto Kill",
    Default = false,
    Callback = function(v)
        print("Toggled:", v)
    end
})
```

#### Dropdowns
```lua
Combat:Dropdown({
    Name = "Select Target",
    Items = {"Closest", "Lowest HP", "Random"},
    Callback = function(v)
        print("Targeting:", v)
    end
})

-- Refresh options later:
-- myDropdown:Refresh({"New Item 1", "New Item 2"})
```

#### Sliders
```lua
Combat:Slider({
    Name = "WalkSpeed",
    Min = 16,
    Max = 100,
    Default = 16,
    Callback = function(v)
        game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = v
    end
})
```

---

### 📱 Mobile Support
If a user is on mobile, a **floating toggle button** will automatically appear (using your Logo ID). They can drag it around and tap it to hide/show the UI. You don't need to code anything for this to work.

### 🎨 Theme & Colors
The library uses a default "midnight" theme. If you want to change the Accent color globally, look for `Themes["Preset"]` in the script. The current accent is a nice light blue (`#108BDD`).

---
*Created for the community. Enjoy using Pulse!*
