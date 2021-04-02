# Optimized Minecraft Server Start Script

## start.sh
The following script has been put together by a few people other than myself and published for
people like me to steal and keep tucked away. Below is the startup script I use for running
a [PaperMC](https://papermc.io/) server.
```shell
#!/bin/bash

SERVER="paper.jar"
MEMORY="6G"

java -Xms${MEMORY} -Xmx${MEMORY} -XX:+UseG1GC -XX:+ParallelRefProcEnabled -XX:MaxGCPauseMillis=200 \
  -XX:+UnlockExperimentalVMOptions -XX:+DisableExplicitGC -XX:-OmitStackTraceInFastThrow \
  -XX:+AlwaysPreTouch  -XX:G1NewSizePercent=30 -XX:G1MaxNewSizePercent=40 \
  -XX:G1HeapRegionSize=8M -XX:G1ReservePercent=20 -XX:G1HeapWastePercent=5 \ 
  -XX:G1MixedGCCountTarget=8 -XX:InitiatingHeapOccupancyPercent=15 \
  -XX:G1MixedGCLiveThresholdPercent=90 -XX:G1RSetUpdatingPauseTimePercent=5 \
  -XX:SurvivorRatio=32 -XX:MaxTenuringThreshold=1 -Dusing.aikars.flags=true \
  -Daikars.new.flags=true -jar ${SERVER} nogui
```

## restart.py
This script is a Python program that keeps starting the Minecraft server in a loop.
This allows the server to restart even if an OP accidentally runs `/stop`. This is
in no way "bulletproof", but it helps is a few scenarios.

```python
#!/usr/bin/env python3

import os, time, sys

while True:
    try:
        os.system("./start.sh")
        print("Restarting in 3...")
        print("Press Control-C to abort")
        time.sleep(1)
        print("2...")
        time.sleep(1)
        print("1...")
        time.sleep(1)
    except KeyboardInterrupt:
        break
    except:
        pass

print("Aborted!")
```