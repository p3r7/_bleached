# _bleached

norns lib for integration w/ bleached

automatically retrieves a plugged bleached configuration at init (via sysex) and bind a callback to slider changes.

## example usage

```lua
bleached = include("lib/bleached")

function init()
  bleached.init(bleached_cc_callback)
end

function bleached_cc_callback(midi_msg)
  local row = bleached.cc_to_row(midi_msg.cc)
  local pot = bleached.cc_to_row_pot(midi_msg.cc)
  local v = midi_msg.val

  print("pot "..row.."."..pot.." just got its value changed to "..v)
end
```
