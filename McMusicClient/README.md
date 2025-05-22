# Get Game Data Mod (Minecraft Client Mod)
## Result
### Terminal Output
![image](https://github.com/novel2430/MyImage/blob/main/MCMUSIC-001.png?raw=true)
### File Output
```json
{
        "Index":4,
        "Biome":{
                "Plains":100.0
        },
        "Time":{
                "Night":100.0
        },
        "Climate":{
                "Clear":100.0
        },
        "Temperature":{
                "Not Cold":100.0
        },
        "Health":{
                "Full":100.0
        },
        "Hunger":{
                "Full":100.0
        },
        "Status":{
                "Not Touching Water":100.0,
                "Not On Fire":100.0
        },
        "Motion":{
                "Sprinting":27.093596059113302,
                "Not Sprinting":72.9064039408867,
                "Not Sneaking":100.0
        },
        "Placing":{
                "On Ground":100.0,
                "Not On Rail":100.0,
                "Not In Lava":100.0
        },
        "Monster":{
                "zoglin":0.0,
                "vex":0.0,
                "sum":0.1625615763546798,
                "skelton":0.0,
                "piglin":0.0,
                "blaze":0.0,
                "endermite":0.0,
                "silverfish":0.0,
                "zombie":0.1625615763546798,
                "warden":0.0,
                "giant":0.0,
                "guardian":0.0,
                "wither":0.0,
                "spider":0.0,
                "patrik":0.0,
                "creeper":0.0,
                "enderman":0.0
        },
        "Attacked":{
                "Not Attacked":100.0
        },
        "BiomePredict":{
                "River":41.37931034482759
        }
}
```
## Requirement
- Jdk >= 17
## Runing
- Windows
```
./gradlew.bat runClient
```
- Mac / Linux
```
./gradlew runClient
```
## Proxy
If you are not using **Clash**, you should modify the `gradle.properties`  
delete line 20 to line 23
```
# Done to increase the memory available to gradle.
org.gradle.jvmargs=-Xmx1G
org.gradle.parallel=true

# Fabric Properties
# check these on https://fabricmc.net/develop
minecraft_version=1.20.1
yarn_mappings=1.20.1+build.10
loader_version=0.15.3

# Mod Properties
mod_version=1.0.0
maven_group=com.novel
archives_base_name=outputdata

# Dependencies
fabric_version=0.91.0+1.20.1

# Proxy <- Delete Here
systemProp.http.proxyHost=127.0.0.1
systemProp.http.proxyPort=7890
systemProp.https.proxyHost=127.0.0.1
systemProp.https.proxyPort=7890
```
## Setting
you can change how long (Second) between each output, and some other settings
### Step
1. if directory `run` not exist, create directory `run`
2. copy file `outputDataConfig.json` in `run`, and it will be `run/outputDataConfig.json`
3. modify `run/outputDataConfig.json` file
### Key Meaning
| Key | Meaning |
|---|---|
| PauseSecond | how long between each output |
| SavePath | where to save ouput files (DO NOT put "/" at the path end! Path "." means directory `run`) |
| SaveToDisk | Do save to disk or not |
| Debug | need or not to print thread log |
| URL | Data Transfer Server URL |
| PlayerName | Player Name |
| DetectSize | Size of detecting monster |
| BiomePredictDirectionAlpha | Weight for player facing direction. Higher value prioritizes biomes in front of the player |
| BiomePredictDistanceBeta | Penalty for biome distance. Higher value reduces the score of faraway biomes |
| BiomePredictDetectSize | Scan radius (in blocks) to detect nearby biomes |
| BiomePredictSampleRate | Sampling interval (in blocks). Smaller values increase accuracy but cost more performance |
| BiomePredictTickInterval | Tick interval to update biome prediction. Lower values update more frequently |
### File Content
```json
{
  "PauseSecond": 10.0,
  "SavePath": ".", 
  "SaveToDisk": true,
  "Debug": true,
  "URL": "http://127.0.0.1:44349",
  "PlayerName": "novel2430",
  "DetectSize": 20,
  "BiomePredictDirectionAlpha": 1.0,
  "BiomePredictDistanceBeta": 1.0,
  "BiomePredictDetectSize": 40,
  "BiomePredictSampleRate": 2,
  "BiomePredictTickInterval": 20 
}
```
