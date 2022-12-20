# QbusToEsx Converting Qbus Scripts to ESX, Non-stop Updating.
# Discord : www.discord.gg/mdtyazilim
--------------------------------------------------------------------------------------------------
Qbus Foundation and ESX foundation.
 ```lua
QBCore = nil 

Citizen.CreateThread(function()
	while QBCore == nil do
		TriggerEvent('QBCore:GetObject', function(obj) QBCore = obj end)
		Citizen.Wait(30) -- Seconds Wait
	end
end)
```
The bottom one is for the new ones -- the top one is for the old version, try both if it doesn't work...
```lua
local QBCore = exports['qb-core']:GetCoreObject()
```

# QBUSCORE ON TOP

# BOTTOM ESX
```lua
ESX = nil

Citizen.CreateThread(function()
  while ESX == nil do
    TriggerEvent('esx:getSharedObject', function(obj) ESX = obj end)
    Citizen.Wait(30)-- Seconds Wait
  end
end)
```

--------------------------------------------------------------------------------------------------

Gentlemen This section was not added.
Meaning:
The Player Login Part is Needed When Entering the Buttonhole Game, so it is the Server File.
This event is triggered when the player connects to the server
```lua
RegisterNetEvent('QBCore:Client:OnPlayerLoaded')
AddEventHandler('QBCore:Client:OnPlayerLoaded',
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
RegisterNetEvent('esx:playerLoaded')
AddEventHandler('esx:playerLoaded',
```

--------------------------------------------------------------------------------------------------

Server File, Job Section is the Profession Section.
```lua
RegisterNetEvent('QBCore:Client:OnJobUptade')
AddEventHandler('QBCore:Client:OnJobUptade', 
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
RegisterNetEvent('esx:setJob')
AddEventHandler('esx:setJob',
```

--------------------------------------------------------------------------------------------------

You can check here.
https://esx-framework.github.io/es_extended/common/events/onplayerdeath/#example-client-side-usage
```lua
RegisterNetEvent('QBCore:Client:OnPlayerUnload')
AddEventHandler('QBCore:Client:OnPlayerUnload',
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
RegisterNetEvent('esx:onPlayerDeath')
AddEventHandler('esx:onPlayerDeath',
```

--------------------------------------------------------------------------------------------------

Gentlemen This section was not added.
Description:
This function gets the nearest player client ID and the distance to the player.
```lua
QBCore.Functions.GetClosestPlayer()
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
ESX.Game.GetClosestPlayer()
```

--------------------------------------------------------------------------------------------------

Adding 3D text, Cilent File. Örnek : https://media.discordapp.net/attachments/623207764314816562/812096508786507806/resim_1.png
```lua
QBCore.Functions.DrawText3D(1, 1, 1, 1, 'Example')
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
DrawText3D(1, 1, 1, 1, 'Example') -- (you need to open the function below.)
ESX.Game.Utils.DrawText3D(1, 1, 1, 1, 'Example') -- ESX doesn't need this function, it already exists.
```

--------------------------------------------------------------------------------------------------

Menu Open Close Menus in ESX & QBCore Examples : https://prnt.sc/u4f7s5
```lua
QBCore.UI.Menu.Open
QBCore.UI.Menu.CloseAll() -- (you need to install menu default script)
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
ESX.UI.Menu.Open
ESX.UI.Menu.CloseAll()
```

--------------------------------------------------------------------------------------------------

Notification Scripts Example : https://dosya.turkmmo.com/2020/09/36521_efa54848705a4069cbedfc2770e50cf1.png
```lua
TriggerClientEvent("QBCore:Notify", "Text/Text", "success", 2500)

-- top server -- bottom client

QBCore.Functions.Notify("Text/Print.", "error")
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
TriggerEvent('Notification', "Text/Text.")

-- top server -- bottom client

ESX.ShowHelpNotification('Text/Text.')
```

--------------------------------------------------------------------------------------------------

Enventer Item Section.
```lua
xPlayer.Functions.GetItemByName 
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
xPlayer.getInventoryItem
```
--------------------------------------------------------------------------------------------------

```lua
xPlayer.PlayerData.name 
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
xPlayer.getName()
```

--------------------------------------------------------------------------------------------------

Job Start code.
```lua
RegisterNetEvent('QBCore:Client:OnJobUpdate')
AddEventHandler('QBCore:Client:OnJobUpdate', function(job)
    PlayerData.job = job
end)
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
RegisterNetEvent('esx:setJob')
AddEventHandler('esx:setJob', function(job)
    PlayerData.job = job
end)
```

--------------------------------------------------------------------------------------------------

Give Money Get Money Part
```lua
Player.Functions.AddMoney('bank', amount, "Bank depost") -- bank
Player.Functions.RemoveMoney('cash', amount, "Bank deposit") -- the money on top
```
# QBUSCORE ON TOP


# BOTTOM ESX
```lua
xPlayer.removeAccountMoney('bank', amount) --money removal
xPlayer.addMoney(amount) -- add money
```

--------------------------------------------------------------------------------------------------

Money Part Data.
```lua
Player.PlayerData.money["bank"]
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
xPlayer.getAccount('bank').money
```

--------------------------------------------------------------------------------------------------

```lua
QBCore.Functions.IsSpawnPointClear()
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
ESX.Game.IsSpawnPointClear()
```

--------------------------------------------------------------------------------------------------

```lua
QBCore.Functions.SetVehicleProperties()
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
ESX.Game.SetVehicleProperties()
```

--------------------------------------------------------------------------------------------------

Inventory Item Deletion Section.
```lua
xPlayer.Functions.RemoveItem 
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
xPlayer.removeInventoryItem 
```

--------------------------------------------------------------------------------------------------

Inventory Item Addition Section.
```lua
xPlayer.Functions.AddItem
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
xPlayer.addInventoryItem
```

--------------------------------------------------------------------------------------------------

It's like the Id of a character.
```lua
QBCore.Functions.GetPlayer(src)
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
ESX.GetPlayerFromId(src)
```


--------------------------------------------------------------------------------------------------

It attracts all the players.
```lua
QBCore.Functions.GetPlayers(src)
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
ESX.GetPlayers(src)
```

--------------------------------------------------------------------------------------------------

```lua
QBCore.Functions.GetPlayerByCitizenId(src)
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
ESX.GetPlayerFromIdentifier(src)
```

--------------------------------------------------------------------------------------------------

This function truncates a text by removing all trailing white spaces. It is often used when disinfecting `GetVehicleNumberPlateText()` natives.
#Example
```lua
QBCore.Functions.MathTrim(GetVehicleNumberPlateText(vehicle))
````
#standard
```lua
QBCore.Functions.MathTrim 
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
ESX.Math.Trim(value)
```

--------------------------------------------------------------------------------------------------

Nill this will be updated as soon as it is known
# EXAMPLE
```lua
QBCore.Functions.MathRound(GetVehicleBodyHealth(vehicle), 1),
```
#standard
```lua
QBCore.Functions.MathRound()
```
# QBUSCORE ON TOP

# BOTTOM ESX
# EXAMPLE
```lua
local value - 5.444

print ('value:' .. value) - 5.444 -- returns
print ('deger rounded:' ... ESX.Math.Round(deger)) -- Returns 5
print ('deger rounded:' ... ESX.Math.Round(deger, 1)) -- Returns 5.4
```
#standard
```lua
ESX.Math.Round(value, numberNumberDigits)
```

--------------------------------------------------------------------------------------------------

Car Spawn Part Location Etc.
```lua
QBCore.Functions.SpawnVehicle()
QBCore.Functions.DeleteVehicle()
QBCore.Functions.GetVehicleProperties()
QBCore.Functions.GetClosestVehicle()
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
ESX.Game.SpawnVehicle()
ESX.Game.DeleteVehicle()
ESX.Game.GetVehicleProperties()
ESX.Game.GetClosestVehicle()
```
--(If you have ESX.Game, almost everything is in the same form as QBCore.Functions.)


--------------------------------------------------------------------------------------------------

`qb-core/client/functions.lua`
put it in qb-core in client functions.lua. on a blank line
```lua
function QBCore.Functions.RequestNamedPtfxAsset(assetName, cb)
	if not HasNamedPtfxAssetLoaded(assetName) then
		RequestNamedPtfxAsset(assetName)

		while not HasNamedPtfxAssetLoaded(assetName) do
			Citizen.Wait(1)
		end
	end

	if cb ~= nil then
		cb()
	end
end
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
function ESX.Streaming.RequestNamedPtfxAsset(assetName, cb)
	if not HasNamedPtfxAssetLoaded(assetName) then
		RequestNamedPtfxAsset(assetName)

		while not HasNamedPtfxAssetLoaded(assetName) do
			Citizen.Wait(1)
		end
	end

	if cb ~= nil then
		cb()
	end
end
```


--------------------------------------------------------------------------------------------------

`qb-core/client/functions.lua`
bunu qb-core de client functions.lua. atın bir boş satıra
```lua
function QBCore.Functions.DeleteObject(object)
	SetEntityAsMissionEntity(object, false, true)
	DeleteObject(object)
end
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
function ESX.Game.DeleteObject(object)
	SetEntityAsMissionEntity(object, false, true)
	DeleteObject(object)
end
```

--------------------------------------------------------------------------------------------------

`qb-core/server/functions.lua`
bunu qb-core de server functions.lua. atın bir boş satıra
```lua
function QBCore.Functions.GetItemLabel(item)
	if QBCore.UseableItems[item] ~= nil then
		return QBCore.UseableItems[item].label
	end
end
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
function ESX.GetItemLabel(item)
	if ESX.Items[item] then
		return ESX.Items[item].label
	end
end
```

--------------------------------------------------------------------------------------------------

Oyuncu Kendi Karakterin.
```lua
QBCore.Functions.GetPlayerData()
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
ESX.GetPlayerData()
```

--------------------------------------------------------------------------------------------------

İtem Oluşturma.
```lua
QBCore.Functions.CreateUseableItem()
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
ESX.RegisterUsableItem()
```

--------------------------------------------------------------------------------------------------

Banka Para Kaldırma.
```lua
Player.Functions.RemoveMoney()
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
xPlayer.removeMoney(money)
```

--------------------------------------------------------------------------------------------------

Dosya'lar İle Alakalı.
```lua
QBCore.Functions.CreateCallback()
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
ESX.RegisterServerCallback()
```

--------------------------------------------------------------------------------------------------

Dosya'lar İle Alakalı.
```lua
QBCore.Functions.TriggerCallback()
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
ESX.TriggerServerCallback()
```

--------------------------------------------------------------------------------------------------

qb'de cid esx'de identifier kullanılıyor olayı çözmeniz için ufak bir kod bloğu bıraktım.
```lua
QBCore.Functions.CreateCallback('system:fetchStatus', function(source, cb)
    local Player = QBCore.Functions.GetPlayer(source)

     if Player then
           exports['ghmattimysql']:execute('SELECT skills FROM players WHERE citizenid = @citizenid', {
               ['@citizenid'] = Player.PlayerData.citizenid
          }, function(status)
              if status ~= nil then
                   cb(json.decode(status))
              else
                   cb(nil)
              end
          end)
     else
          cb()
     end
end)
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
ESX.RegisterServerCallback("system:fetchStatus", function(source, cb)
    local src = source
    local user = ESX.GetPlayerFromId(src)


    local fetch = [[
         SELECT
              skills
         FROM
              users
         WHERE
              identifier = @identifier
    ]]

    MySQL.Async.fetchScalar(fetch, {
         ["@identifier"] = user.identifier

    }, function(status)

         if status ~= nil then
              cb(json.decode(status))
         else
              cb(nil)
         end

    end)
end)
```

--------------------------------------------------------------------------------------------------

```lua
QBCore.Shared.Items
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
ESX.GetItems()
```
--------------------------------------------------------------------------------------------------

Sql bağlama kısmı
```lua
QBCore.Functions.ExecuteSql()
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
ESX.ExecuteSql() --(ghmattimysql)
MySQL.Async.execute()
```

--------------------------------------------------------------------------------------------------


RegisterCommand - yani chat komut kısmı.
```lua
QBCore.Commands.Add()
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
RegisterCommand 
```
-- (RegisterCommand qbcore'da da çalışır.)

--------------------------------------------------------------------------------------------------

Karakter Kısmı Dır Data Sına Bağlama.
```lua
local Player = QBCore.Functions.GetPlayer(source)
['@citizenid'] = Player.PlayerData.citizenid -- çekme Player
```
# QBUSCORE ON TOP

# BOTTOM ESX
```lua
local user = ESX.GetPlayerFromId(src)
["@identifier"] = user.identifier -- çekme user
```

--------------------------------------------------------------------------------------------------

```lua
QBCore.Shared.Trim()
QBCore.Shared.GroupDigits()
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
ESX.Math.Trim()
ESX.Math.GroupDigits()
```

--------------------------------------------------------------------------------------------------

```lua
QBCore.Functions.GetClosestObject()
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
ESX.Game.GetClosestObject()
```

--------------------------------------------------------------------------------------------------

```lua
QBCore.Functions.GetVehicleInDirection()
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
ESX.Game.GetVehicleInDirection()
```

--------------------------------------------------------------------------------------------------

```lua
QBCore.Functions.GetPeds()
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
ESX.Game.GetPeds()
```

--------------------------------------------------------------------------------------------------

```lua
QBCore.Functions.GetObjects()
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
ESX.Game.GetObjects()
```

--------------------------------------------------------------------------------------------------

```lua
QBCore.Functions.GetClosestPed()
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
ESX.Game.GetClosestPed()
```

--------------------------------------------------------------------------------------------------

```lua
QBCore.Functions.SpawnObject()
```
# ÜSTEKİ QBUSCORE

# ALTAKİ ESX
```lua
ESX.Game.SpawnObject()
```

--------------------------------------------------------------------------------------------------
