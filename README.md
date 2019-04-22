# MMM-Volume
Volume controller module is for Seeed Respeaker 2-mic voice card on MagicMirror. This modules is forked from eouia/MMM-Volume. So if you plan to install the full version of the Volume controller module, please go to https://github.com/eouia/MMM-Volume

## Screenshot
![Screenshot](https://github.com/xuepgao/MMM-Volume/blob/master/mmm-volume.png)

## Install
```sh
cd ~/MagicMirror/modules
git clone https://github.com/xuepgao/MMM-Volume.git
```

## Configuration

### Simple
```js
{
  module: "MMM-Volume",
  position: "top_left", // It is meaningless. but you should set.
  config: {
    usePresetScript: "SPEAKER"(or "PLAYBACK"), 
    // "SPEAKER" is for Seeed Respeaker 2-mic JST Speaker Connectors.
    // "PLAYBACK" is for Seeed Respeaker 2-mic 3.5mm Audio Jack.
    volumeOnStart: 80,   // The suitable volume of Seeed Respeaker 2-mic is about 80%.
  }
},
```




## Usage

### By `Notification`

|notification | payload | description
|---|---|---|
|VOLUME_GET | - | Getting current volume
|VOLUME_SET | 0 - 100 | Setting Volume to `number`. 0 is mute and 100 is maximum
|VOLUME_UP | upDownScale=Number | Volume up by `upDownScale`
|VOLUME_DOWN | upDownScale=NUMBER | Volume down by `upDownScale`
|VOLUME_STORE | `null` or `0-100` | Storing current volume and setting the volume to `number`.<br/> If payload be `null`, volume will not be changed. (just stored)
|VOLUME_RESTORE | faded=true or false; upDownScale=NUMBER | Setting volume with stored previously

If volume is changed or `VOLUME_GET` is called, the current volume as result will be notified by `CURRENT_VOLUME` notification with `payload=0-100`.



### By `MMM-TelegramBot`
|command | description
|--- |---
|`/vol` | Getting Current Volume
|`/vol NUMBER` | Setting Volume to `NUMBER`(0-100)


## Styling
See `MMM-Volume.css`


## Notice
Not fully tested on RPI. I'm waiting your bug report.
