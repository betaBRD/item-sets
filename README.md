# item-sets
-- User-Globals.lua
state.TravelMode = M(false, true)

function global_on_load()
      send_command('bind !@= gs c cycle TravelMode')
      send_command('bind !^end oi index <t>')
      send_command('bind !^sysrq oi parse server.asura <t>')
      send_command('bind !^insert oi parse server.global <t>')
  end
function global_on_unload()
      send_command('unbind !@=')
      send_command('unbind !^end')
      send_command('unbind !^sysrq')
      send_command('unbind !^insert')
  end
  
function define_global_sets()
      gear.nxc = "Nexus Cape"
  end

function user_status_change(newStatus, oldStatus, eventArgs)
      if state.TravelMode.value == true then
            equip({back = gear.nxc})
            disable('back')
         else
            enable('back')
      end
 end

