# Image packs

<img width="945" height="1285" alt="thumbs_grid_clean" src="https://github.com/user-attachments/assets/538708e8-f02e-447c-9a89-3a3ae12f9889" />

Each pack is a folder `images/<Pack>/<width>x<height>/` with one PNG per voice-assistant state:

`idle.png`, `listening.png`, `thinking.png`, `replying.png`, `loading.png`, `error.png`, `mute.png`, `playing.png`, `timer_finished.png`

Device YAMLs pick a pack with the `imagemodel` substitution and build the URLs from `imagewidth` and `imageheight`:

```yaml
imagemodel: "Dobby"
imagewidth: "240"
imageheight: "240"
idle_illustration_file: https://github.com/davidru85/xiaozhi-esphome/raw/main/images/${imagemodel}/${imagewidth}x${imageheight}/idle.png
```

The pack must exist **at your display's resolution**, and the name is **case-sensitive** (`Vader`, not `vader`). Images are downloaded from GitHub at compile time, so a new pack only works after it has been pushed.

## Available packs

| Pack | Resolutions | Notes |
|---|---|---|
| `AlbertQuackmore` | 240x240, 240x320, 360x360, 480x480 |  |
| `Alfred` | 172x172, 240x240, 240x320, 360x360, 400x600, 466x466, 480x480, 600x600, 640x172 |  |
| `Alita` | 240x240, 240x320, 320x480, 360x360, 410x502, 480x480 |  |
| `Astrobot` | 240x240, 240x320, 360x360 |  |
| `Buzz` | 240x240, 240x320, 360x360, 480x480 |  |
| `Casita` | 240x240, 240x320, 360x360 |  |
| `Cybergirl` | 240x240, 240x320, 360x360, 480x480 |  |
| `Dobby` | 240x240 | Added in this fork |
| `Dory` | 240x240, 240x320, 360x360, 480x480, 720x720 |  |
| `Dwight` | 240x240 | Added in this fork |
| `EVE` | 240x240, 240x320, 360x360, 480x480 |  |
| `Eyes` | 128x64, 240x240, 240x320, 360x360, 480x480 |  |
| `Eyes2` | 128x64, 240x240, 240x320, 360x360, 410x502, 480x480 |  |
| `Girl1` | 240x240, 240x320, 360x360 |  |
| `GLaDOS` | 240x240, 240x320, 360x360, 480x480, 720x720 |  |
| `Guy1` | 240x240, 240x320, 360x360 |  |
| `Guy2` | 240x240, 240x320, 360x360 |  |
| `Gwen` | 172x172, 240x240, 240x296, 240x320, 284x240, 320x240, 320x480, 360x360, 400x600, 410x502, 466x466, 480x320, 480x480, 480x800, 600x600, 640x172, 720x720, 800x480, 1024x600 |  |
| `Gwen_Black` | 240x240, 360x360, 466x466, 480x480, 720x720 |  |
| `HA-character` | 240x240, 240x320, 320x480, 360x360, 410x502, 480x480 |  |
| `ha-girl` | 240x240, 240x320, 320x480, 360x360, 410x502, 480x480 |  |
| `Hacker` | 240x240, 240x320, 360x360, 480x480, 720x720 |  |
| `Harley` | 240x240, 240x320, 360x360, 480x480 |  |
| `Jarvis` | 240x240, 240x320, 360x360, 480x480, 640x172 |  |
| `Luffy` | 240x240, 240x320, 360x360, 400x600, 480x480, 600x600, 720x720, 800x480 |  |
| `Mario` | 240x240, 240x320, 360x360, 480x480 |  |
| `Max` | 240x240, 240x320, 360x360 |  |
| `Prime` | 240x240, 240x320, 360x360, 480x480, 720x720 |  |
| `Robochibi` | 240x240, 240x320, 360x360 |  |
| `Robocop` | 240x240, 240x320, 360x360 |  |
| `Robot` | 240x240, 240x320 |  |
| `Robotgirl` | 240x240, 240x320, 360x360 |  |
| `Salem` | 172x172, 240x240, 240x320, 320x480, 360x360, 410x502, 480x480, 640x172, 720x720 |  |
| `Sarah` | 172x172, 172x640, 240x240, 240x320, 320x480, 360x360, 480x480, 640x172, 720x720 |  |
| `Shaun` | 240x240, 240x320, 360x360, 480x480, 720x720 |  |
| `Vader` | 240x240 | Added in this fork |

`Other/` holds clock backgrounds and the no-Wi-Fi / no-HA error screens, and `Mute/` holds shared mute icons; they are not selectable as `imagemodel`.

## Adding a new pack

1. Create `images/<Pack>/<width>x<height>/` with the 9 PNGs listed above, at exactly that size.
2. Add `<Pack>` to the `imagemodel` options comment in the device YAMLs under `devices/`.
3. Add it to the table above.
4. Commit and push, then set `imagemodel: "<Pack>"` on the device and install.
