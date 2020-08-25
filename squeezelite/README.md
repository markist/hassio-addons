# 🥧 Squeezelite player standalone 🥧

## 📄 Description
Runs the [Squeezelite](https://github.com/ralph-irving/squeezelite) player as standalone on home assistant. \
Note that the player only works on x86/x64 systems (Like a NUC or normal PCs, not Raspberrys etc) since my scripting skills are limited. \
Plugin rely on compiled version from [here](https://sourceforge.net/projects/lmsclients/files/squeezelite/linux/)

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

## Config parameters
Following parameters are available and must be set: \
```name```: Displayname for the player (only english ascii supported) \
```output```: Audio output (where you want the music to play). Please check the log after startup for a list of possible outputs \
```clientmac```: A "dummy mac" to make the player unique. There should not be 2 players in a squeezeserver with equial mac, that mess things up. 

Optional: \
```server```: Host or IP to link this squeezelite player. If not set autodiscover will be used and join the first server it sees. \
```log_level```: Only debug is available here (only used during development) 

Default config is: \
```name```: Home Assistant Squeezelite \
```output```: default \
```clientmac```: '0A:0B:0C:0D:0E:0F' 

## 🧷 Urls
[Add-on link](https://github.com/large/hassio-addons/tree/master/squeezelite)

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
