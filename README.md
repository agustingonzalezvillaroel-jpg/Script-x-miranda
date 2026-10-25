-- Script Hub

local SCRIPT_NAME = "Script Hub"

loadstring(game:HttpGet(
    "https://raw.githubusercontent.com/miirandahub/loader/refs/heads/main/antiafk"
))()

task.wait(1)

loadstring(game:HttpGet(
    "https://api.luarmor.net/files/v4/loaders/6b07a458832f08b2314f706f14723212.lua"
))()

task.wait(3)

-- Busca interfaces cargadas y cambia el nombre
-- de las ventanas que tengan un título identificable.
for _, gui in ipairs(game:GetService("CoreGui"):GetChildren()) do
    if gui:IsA("ScreenGui") then
        for _, obj in ipairs(gui:GetDescendants()) do
            if obj:IsA("TextLabel") and obj.Visible then
                if string.find(string.lower(obj.Text), "hub") then
                    obj.Text = SCRIPT_NAME
                end
            end
        end
    end
end
