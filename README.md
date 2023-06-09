# qb-armyjob
Army Job for QB-Core Framework

## Dependencies
- [qb-core](https://github.com/qbcore-framework/qb-core)
- [qb-management](https://github.com/qbcore-framework/qb-management) (Replaces qb-bossmenu) - For the boss/gang menu
- [qb-garages](https://github.com/qbcore-framework/qb-garages) - For the vehicle spawner
- [qb-menu](https://github.com/qbcore-framework/qb-menu) - For the vehicle menus
- [qb-input](https://github.com/qbcore-framework/qb-input) - For accessing evidence stashes


## Installation
### Manual
- Download the script and put it in the `[qb]` directory.
- Add the following code to your server.cfg/resouces.cfg
```
ensure qb-core
ensure qb-armyjob
ensure qb-management  
```
# qb-management/client/cl_config.lua

```
['army'] = {
        { coords = vec3(-2346.23, 3269.55, 32.81), length = 1, width = 1, heading = 330, minZ = 29.61, maxZ = 33.61 },
    },
```

Add this to 
# qb-core/shared/jobs.lua 
```
    ['army'] = {
		label = 'United States Armed Forces',
		defaultDuty = false,
		offDutyPay = false,
		grades = {
            ['0'] = {
                name = 'Private',
                payment = 900
            },
			['1'] = {
                name = 'Private First Class',
                payment = 1150
            },
			['2'] = {
                name = 'Corporal',
                payment = 1400
            },
			['3'] = {
                name = 'Sergeant',
                payment = 1750
            },
			['4'] = {
                name = 'Staff Sergeant',
                payment = 2000
            },
            ['5'] = {
                name = 'First Sergeant',
                payment = 2250
            },
            ['6'] = {
                name = 'Command Sergeant Major',
                payment = 2250
            },
            ['7'] = {
                name = 'Sergeant Major of the Army',
                payment = 2250
            },
            ['8'] = {
                name = 'First and Second Lieutenant',
                isboss = true,
                payment = 2900
            },
            ['9'] = {
                name = 'Colonel',
                isboss = true,
                payment = 3300
            },
            ['10'] = {
                name = 'Major General',
                isboss = true,
                payment = 3550
            },
            ['11'] = {
                name = 'Lieutenant General',
                isboss = true,
                payment = 3700
            },
            ['12'] = {
                name = 'General',
                isboss = true,
                payment = 3700
            },
        },
	},
```
### Commands
- /spikestrip - Places spike strip on ground.
- /pobject [pion/barier/schotten/tent/light/delete] - Places or deletes an object on/from ground.
- /cuff - Cuffs/Uncuffs nearby player
- /escort - Escorts nearby plyer.
- /callsign [text] - Sets the player a callsign on database.
- /clearcasings - Clears nearby bullet casings.
- /jail [id] [time] - Sends a player to the jail.
- /unjail [id] - Takes the player out of jail.
- /clearblood - Clears nearby blood drops.
- /seizecash - Seizes nearby player's cash. (Puts in money bag)
- /sc - Puts soft cuff on nearby player.
- /cam [cam] - Shows the selected security cam display.
- /flagplate [plate] [reason] - Flags the vehicle.
- /unflagplate [plate] - Removes the flag of a vehicle.
- /plateinfo [plate] - Displays if a vehicle is marked or not.
- /depot [price] - Depots nearby vehicle. Player can take it after paying the cost.
- /impound - Impounds nearby vehicle permanently.
- /paytow [id] - Makes payment to the tow driver.
- /paylawyer [id] - Makes payment to the lawyer.
- /radar - Toggles the police radar.

## Features
- Classical requirements like on duty/off duty, clothing, vehicle, stash etc.
- Citizen ID based armory (Whitelisted)
- Fingerprint test
- Evidence locker (stash)
- Whitelisted vehicles
- Speed radars across the map
- Stormram
- Impounding player vehicle (permanent / for an amount of money)
- Integrated jail system
- Bullet casings
- GSR
- Blood drop
- Evidence bag & Money bag
- Police radar
- Handcuff as an item (Can used via command too. Check Commands section.)
- Emergency services can see each other on map
- /911 [message] - Sends a report to emergency services.
- /911r [id] - Used to respond the emergency alerts.
- /911a [message] - Sends an anonymous report to emergency services (gives no location).
- /anklet - Places anklet (tracking device) on nearby player.
- /removeanklet [citizenid] - Removes the anklet from player.
- /ebutton - Used to respond an emergency alert.
- /takedrivinglicense - Takes the driving license from nearby player.
- /takedna [id] - Takes a DNA sample from the player.
