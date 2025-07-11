# This project based on the original work by [Keinta15](https://github.com/Keinta15/Magisk-iOS-Emoji)
# Root-iOS-Emoji
Systemlessly replaces the Android emoji font with iOS Emoji.

## Installation
1. Download the latest release from the [Releases page](https://github.com/IslamAlorabI/Root-iOS-Emoji/releases).
2. Open the [ Magisk / KernelSU (Official) / APatch / KernelSU Next (Unofficial) ]
3. Go to **Modules** → **Install from storage** and select the downloaded ZIP file.
4. Reboot your device.
5. Enjoy iOS emojis system-wide and Apps!

## Compatibility
- **Magisk Version**: Requires Magisk v24.0 or higher.
- **Android Version**: Tested on Android 10 and above. May work on older versions, but not guaranteed.
- **Devices**: Works on most devices. Check the [Tested on](#tested-on) section for more details.

## Screenshots
<table>
  <tr>
    <td><img src="https://github.com/IslamAlorabI/Root-iOS-Emoji/blob/main/Screenshots/Root_iOS_Emoji_Gboard.png" width="300" height="225"></td>
    <td><img src="https://github.com/IslamAlorabI/Root-iOS-Emoji/blob/main/Screenshots/Root_iOS_Emoji_Messanger.png" width="300" height="225"></td>
  </tr>
  <tr>
    <td><img src="https://github.com/IslamAlorabI/Root-iOS-Emoji/blob/main/Screenshots/Root_iOS_Emoji_Instagram.png" width="300" height="225"></td>
    <td><img src="https://github.com/IslamAlorabI/Root-iOS-Emoji/blob/main/Screenshots/Root_iOS_Emoji_Facebook.png" width="300" height="225"></td>
  </tr>
</table>

*Example of iOS emojis displayed on an Android device.*

## Changelog
### v18.4
- Added 18.4 Emojis ([Unicode 16.0](https://emojipedia.org/unicode-16.0)). Thanks to [samuelngs/apple-emoji-linux](https://github.com/samuelngs/apple-emoji-linux) for the source.
- Added action.sh for user convenience
- Updated log function to display messages properly when running the action

### v17.4.7
- **Facebook Lite/Messenger Lite Support**  
  Added emoji replacement compatibility for:
  - Facebook Lite (`com.facebook.lite`)
  - Messenger Lite (`com.facebook.mlite`)
- **`display_name()` function**  
 Added function to display app names instead of package name `com.facebook.katana`

- **Case-Insensitive Font Detection**  
  Modified `replace_emoji_fonts()` in `service.sh` to use:  
  `find -iname "*emoji*.ttf"` instead of case-sensitive matching
- **Cache Clearing Lag**  
  Rewrote `clear_cache()` to eliminate delays caused by recursive `find` in `/data`  
  *New implementation uses direct path targeting for faster cleanup*

### v17.4.6
- Updated `META-INF` (see [3e9dd3b](https://github.com/Keinta15/Magisk-iOS-Emoji/commit/3e9dd3ba0d13f43f70bf299d4c727ffe3152c6b6)).  
- Restructured `customize.sh` code (see [16ef755](https://github.com/Keinta15/Magisk-iOS-Emoji/commit/16ef7553211f7de5e5f1791f6609c92de4c6c7de)), making it easier to update.  
- Added `service.sh` (see [e7ae407](https://github.com/Keinta15/Magisk-iOS-Emoji/commit/e7ae4077bf17e2b9e2c28b6aac75db1f7be11003)), eliminating the need for troubleshooting steps. Instead, simply restart your device.  

### v17.4.1
- Added Magisk 27005+ Support (see [b8339eb](https://github.com/Keinta15/Magisk-iOS-Emoji/commit/b8339eb2a38d0876d2c8d640329e517816ced6ce), thanks to [E85Addict](https://github.com/E85Addict)).
- Added OverlayFS Support (see [b9e6e0f](https://github.com/Keinta15/Magisk-iOS-Emoji/commit/b9e6e0f374759c70dccd78c8791e4bb9d37b75a9), thanks to [reddxae](https://github.com/reddxae)).
- Moved away from `install.sh` as recommended in the [Magisk Docs](https://github.com/topjohnwu/Magisk/blob/master/docs/guides.md) and switched to `customize.sh` (see [bc52d16](https://github.com/Keinta15/Magisk-iOS-Emoji/commit/bc52d16186e6d53398f7b7c552c4251fd5e15a4b)).

### v17.4
- Added 17.4 Emojis.
- Added a process to clear Gboard cache.

### v16.4
- Added 16.4 Emojis.
- Fixed a typo.

<details>
<summary>Click to view prior changelogs</summary>

### v15.4.6
- Added Android 12 Support.
- Fixed a typo in the extraction process.
- Added Android 13 Support.

### v15.4.5
- Removed the method to replace Google Keyboard emojis as it was conflicting with other apps' settings.

### v15.4.4
- Forgot to add the XML file to the module.
- Fixed a typo.

### v15.4.3
- Merged the normal module and the Samsung module into one.
- Fixed an incorrect directory path in the install file.
- Added compatibility for other devices like LG and HTC.

### v15.4.2
- Added a method to potentially completely replace Google Keyboard Emojis.
- Tested `updater.json` directly from the Magisk Manager.

### v15.4.1
- Added `updater.json` for the ability to update directly from the Magisk Manager.
- Cleaned up the code slightly.

### v15.4
- Added 15.4 Emojis.

### v14.6
- Added 14.6 Emojis.
- Added a method to replace Facebook and Facebook Messenger app emojis.

### v14.2
- Added 14.2 Emojis.
- Fixed a naming error on Samsung devices.
</details>

## Changelog for Emojis
- [18.4 New Emojis](https://blog.emojipedia.org/apple-ios-18-4-emoji-changelog/)
- [17.4 New Emojis](https://blog.emojipedia.org/ios-17-4-emoji-changelog/)
- [16.4 New Emojis](https://blog.emojipedia.org/ios-16-4-emoji-changelog/)
- [15.4 New Emojis](https://blog.emojipedia.org/ios-15-4-emoji-changelog/)
- [14.6 New Emojis](https://blog.emojipedia.org/ios-14-6-emoji-changelog/)
- [14.2 New Emojis](https://blog.emojipedia.org/ios-14-2-emoji-changelog/)

## FAQ
### Q: Why aren't the emojis changing after installation?
A: Ensure that the module is enabled in Magisk and reboot your device. If the issue persists, clear the cache of your keyboard app (e.g., Gboard).

### Q: Does this work with third-party keyboards?
A: Yes, the module replaces the system emoji font, so it should work with any keyboard that uses system emojis.

### Q: Can I use this alongside other Magisk modules?
A: Yes, but conflicts may arise if another module modifies the system font. Disable conflicting modules if issues occur.

## Tested On
- OnePlus 11 (Android 14, 15)
- OnePlus 8T (Android 13)
- OnePlus 6
- Pixel 7 Pro (Android 15, 16)
- [Reported working by users](https://github.com/Keinta15/Magisk-iOS-Emoji/issues?q=is%3Aissue+is%3Aclosed+label%3A%22reported+working%22)

## Troubleshooting
If the emoji files are replaced, reboot your phone.

## Contributing
Contributions are welcome! If you'd like to contribute, please:
1. Fork the repository.
2. Create a new branch for your changes.
3. Submit a pull request with a detailed description of your changes.

Please ensure your code includes relevant documentation.

## License
This project is licensed under the [MIT License](https://github.com/IslamAlorabI/Root-iOS-Emoji/blob/main/LICENSE). Feel free to use, modify, and distribute it as per the license terms.
