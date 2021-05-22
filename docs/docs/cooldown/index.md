# A simple solution to cooldowns
Cooldown is my personal way of managing cooldowns of any type. It avoids using wait or any sort of yielding to provide performant results. On top of that, it uses a key based system for managing individual cooldowns under the main Cooldown class.

!!! note ""
	[The code for Cooldown can be found here.](https://github.com/Crystalflxme/Cooldown/blob/main/src/Cooldown.lua)

# Example

This is an example of how to utilize Cooldown:
```lua
local Players = game:GetService("Players")
local cooldown = Cooldown.new(5) -- Create a new cooldown of 5 seconds

part.Touched:Connect(function(hit)
	local player = Players:GetPlayerFromCharacter(hit.Parent)
	if not player then
		return
	end
	
	cooldown:DoTask(player, function(onCooldown, timeLeft)
		if onCooldown then
			timeLeft = math.floor(timeLeft * 10) / 10 -- Format the time
			print("There are", timeLeft, "second(s) left!")
		else
			print("Activated!")
		end
	end)
end)
```
This will print "Activated!" whenever you touch "part" only every 5 seconds.