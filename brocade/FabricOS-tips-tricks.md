# FabricOS Tips and Tricks

Brocade FabricOS is the software that runs on Brocade's FC switches. In order to configure zoning, IP addresses, or
run diagnostics, you must log in to the switch either over SSH or serial cable. Below are some useful commands and their
usages.

## Zone Configuration
`cfgcreate "cfgName", "member[; member...]"` - Creates a configuration with the provided members  
`cfgenable "cfgName"` - Enables a defined configuration  
`cfgdisable` - Disables the effective configuration  
`cfgclear` - Clears all defined configurations  
`cfgsave` - Saves the defined configurations  
`cfgshow` - Shows the current defined and effective configurations  

## Alias Configuration
`alicreate "aliName", "member[; member...]"` - Creates an alias for the provided members  
`aliadd "aliName", "member[; member...]"` - Adds members to an existing alias  
`aliremove "aliName", "member[; member...]"` - Removes members from an existing alias  
`alidelete "aliName"` - Deletes an alias  
`alishow` - Show current aliases  

## IP Configuration
`ipaddrset` - Sets the IP address  
`ipaddrshow` - Shows the IP address  

## Troubleshooting
`fabricshow` - Shows the switches in the fabric  
`switchshow` - Shows the switch and port information  
`sensorshow` - Shows sensor information  
`errshow` - Shows errors one at a time  