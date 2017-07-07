<img src="https://raw.githubusercontent.com/kfarr/streetmix3d/master/assets/streetmix3d-banner.jpg" />

# 🛣️ streetmix3d
Streetmix.net mixed with A-Frame for visualization of streetscapes

### Demo in your browser now: https://kfarr.github.io/streetmix3d/

### How to make your own Streetmix3D street:
* First, use <a href="https://streetmix.net">Streetmix.net</a> to create a street design. (Streetmix is a tool that lets you design, remix, and share your neighborhood street. <a href="https://github.com/streetmix/streetmix/blob/master/README.md#about">More information about Streetmix here</a>.)
* Then, save a Streetmix street using a Twitter account so that you have a unique URL for your street that looks something like this: `https://streetmix.net/kfarr/3/my-awesome-street-name`
* Load https://kfarr.github.io/streetmix3d/, paste in your street URL, and press the magic green button.
* See instant changes to your work: Switch back to a Streetmix.net tab, make changes to your street, then reload the Streetmix3D page to see the edits applied.
* "Walk" around the scene or use VR: Use the <code>W A S D</code> keys to move around the 3D scene. You can even use a VR headset to see a 1:1 scale virtual view of your street with a <a href="https://webvr.rocks">WebVR compatible headset.</a>

<img src="https://raw.githubusercontent.com/kfarr/streetmix3d/master/assets/streetmix3d.gif" />

### Segment Support

| [Streetmix Segment](https://github.com/streetmix/streetmix/blob/master/assets/scripts/segments/info.js)              | Supported? | Supported Variants  | Unsupported Variants |
| ---------------------------- | --------- | ------ | ----- |
| sidewalk            | Yes - Full        |        | no pedestrian 3d models, density levels unsupported, uses empty sidewalk for all variants |
| sidewalk-tree       | no        |   | 3d object - palm 2 and 3   |
| sidewalk-bench      | no        |      | 3d object - bench 1, 2 and 3|
| sidewalk-bike-rack  | no        |     | 3d model needed |
| sidewalk-wayfinding | no        | | 3d model needed     |
| sidewalk-lamp       | no        | | 3d object - street light 1 and 2     |
| parklet             | no        | | 3d model needed     |
| divider             | Yes - Partial   | `divider-type`: striped-buffer, bollard | only 1 texture (double yellow lines) does not match streetmix (dashed white lines), some 3d models needed for variants       |
| parking-lane        | Yes - Partial  |       | `parking-lane-direction` and `parking-lane-orientation` unsupported - "ticks" on both sides of lane |
| bike-lane           | Yes - Partial  | `direction`: inbound, outbound | `bike-asphalt` not supported, only green color   |
| drive-lane          | Yes - Full      | `direction`: inbound, outbound \| `car-type`: sharrow | `car-type`: car, truck - No 3D car or truck models supported yet.        |
| turn-lane           | Yes - Full        | `direction`: inbound, outbound \| `turn-lane-orientation`: left, left-straight, right, right-straight, both, shared, straight       | Note: there appears to be a bug with Streetmix.net rendering of `turn-lane-orientation` variant in street cross section for `inbound` - it appears to be inverted from the street's json database value. Presumably users have simply adjusted the arrows until they found a configuration that looked correct so the database value may not represent user intention for these segments. |
| bus-lane            | Yes - Partial        | `direction`: inbound, outbound       | `bus-asphalt` not supported default always red |
| light-rail          | Yes - Partial        | `direction`: inbound, outbound       | `public-transit-asphalt` not supported default always red |
| streetcar           | Yes - Partial        | `direction`: inbound, outbound       | `public-transit-asphalt` not supported default always red |
| transit-shelter     | no        | | 3d object bus stop     |
| train               | no        |        |  This does not appear to be enabled in Streetmix UI. Is this intended to be mixed mode or unpaved grade separated tracks? |

### Model Credits
* Voxel street segments created by Kieran Farr, MIT License same as project repo
* Some 3D models created by vencreations, https://www.cgtrader.com/vencreations, ["Royalty Free" License](https://www.cgtrader.com/pages/terms-and-conditions#royalty-free-license)
