![Supports i386 Architecture][i386-shield] ![Supports amd64 Architecture][amd64-shield] ![Supports armhf Architecture][armhf-shield] ![Supports armv7 Architecture][armv7-shield] ![Supports aarch64 Architecture][aarch64-shield] 

# 📻 Squeezelite player standalone 📻

## 📄 Description
Runs the [Squeezelite](https://github.com/ralph-irving/squeezelite) player as standalone on home assistant. \
Squeezelite requires a [Squeezebox server](https://mysqueezebox.com/download) running in the network. This plugin does **not** install Squeezebox server! 

From version 1.35 archs x86/x64, armv6/7 and ARM64 (aarch64) is supported. Squeezelite-executable for all architetures is included in the add-on. \
**X86/x64 and ARM64 is verified working** \
Note that ARM64 (or aarch64) requires glibc 2.29 which is not available at apt, but installed during addon installation.

I would love to hear from RPi1 or RPi2 users is the armv7 version works for you.
Mail me at lars@werner.no

## 💵 Support me:  
  You can thank me for developing any of my projects by buy me a cup of coffee.☕ \
  ![](https://github.com/large/raw/master/assets/imgs/paypal_logo.jpg) [**PayPal**](https://paypal.me/mrlarswerner)

## 🏷 Install
1. Add this url to your hass.io addons repos (Supervisor -> Add-on store -> three dots upper right): \
`https://github.com/large/hassio-addons`
2. Update addons list .
3. Install Squeezelite.

## 🧰 How to use
1. Install add-on.
2. Update the config with your own name and output
3. Check add-on logs for possible outputs and supported parameters.

## 🔧 Config parameters

**Note**: _Remember to restart the add-on when the configuration is changed._

Default config and these are required to be set:
```yaml
name: Home Assistant Squeezelite
output: default 
clientmac: '0A:0B:0C:0D:0E:0F' 
```
### Option: `name`
Displayname for the player (only English Ascii chars are supported)

### Option: `output`
Audio output (where you want the music to play). Please check the log after startup for a list of possible outputs \

### Option: `clientmac`
A "dummy mac" to make the player unique. \
There should not be 2 players in a squeezeserver with equial mac, that mess things up. 

### Option (optional): `server`
Host or IP to link this squeezelite player. If not set autodiscover will be used and join the first server it sees. \

### Option (optional): `log_level`
Only "debug" is valid  here (only used during development) 

## 🧷 Urls
[Add-on link](https://github.com/large/hassio-addons/tree/master/squeezelite)
[Squeezelite](https://github.com/ralph-irving/squeezelite)
[Squeezebox server](https://mysqueezebox.com/download)

## 👪 Credits
Developed by [Lars Werner](https://github.com/large)

## 🎓 License
   [Apache License 2.0](https://github.com/large/hassio-addons/blob/master/squeezelite/LICENSE.md)
   Copyright 2020 Lars Werner (large)

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.

[amd64-shield]: https://img.shields.io/badge/amd64-yes-green.svg
[i386-shield]: https://img.shields.io/badge/i386-yes-green.svg
[armhf-shield]: https://img.shields.io/badge/armhf-yes-green.svg
[armv7-shield]: https://img.shields.io/badge/armv7-yes-green.svg
[aarch64-shield]: https://img.shields.io/badge/aarch64-yes-green.svg
