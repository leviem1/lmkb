# Logging into the NetApp Console

I want to start by saying that this will be very vague as I don't know which model NetApp
device I have, or even the exact name of the console that I will be explaining how to get
into. This is only informational as it took me a long time to figure this out.

1. Power on the NetApp device, wait for it to finish booting
2. Press the BREAK key (`<crtl> + <fn> + B` on my PC)
3. Press the escape key to open the console
4. Log in using the following credentials: `shellUsr` / `wy3oo&w4`

**BEWARE:** After that, you can run commands like `sysWipe` to restore the system. Management through
the appliance manager program is preferred.

## Resetting configuration
Here are some helpful commands for resetting the NetApp configuration.

Reset the SYMbol password
```bash
clearSYMbolPassword
```

Reset the storage configuration
```bash
clearStorageArray configuration all
setStorageArray resetConfiguration=true
```

Reset the device configuration
```bash
sysWipe
```

## Setting an IP address
```bash
netCfgShow
netCfgSet
```
