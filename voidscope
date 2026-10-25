local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()

character.ChildAdded:Connect(function(tool)
    if tool:IsA("Tool") and (tool.Name:lower():find("gun") or tool.Name:lower():find("sheriff")) then
        -- รอให้โมเดลปืนโหลดครบ
        task.wait(0.1)
        for _, part in ipairs(tool:GetDescendants()) do
            if part:IsA("BasePart") then
                -- ปรับตัวปืนให้เป็นโทนสีขาวดำ
                if math.random(1, 2) == 1 then
                    part.Color = Color3.fromRGB(240, 240, 240) -- สีขาว
                    part.Material = Enum.Material.SmoothPlastic
                else
                    part.Color = Color3.fromRGB(20, 20, 20)   -- สีดำ
                    part.Material = Enum.Material.Metal
                end
            elseif part:IsA("Trail") or part:IsA("Beam") then
                -- เปลี่ยนสีเส้นกระสุน/เอฟเฟกต์การยิงให้เป็นสีขาว
                part.Color = ColorSequence.new(Color3.fromRGB(255, 255, 255))
            elseif part:IsA("ParticleEmitter") then
                -- เปลี่ยนสีประกายไฟ/เอฟเฟกต์ปืนให้เป็นสีขาวเทา
                part.Color = ColorSequence.new(Color3.fromRGB(200, 200, 200))
            end
        end
    end
end)
