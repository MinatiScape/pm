# CipherOS PocketMode

An intelligent pocket detection system for Android that preserves battery life by monitoring proximity and light sensors only when the device is locked.

## Overview

CipherOS PocketMode is a battery-efficient implementation of pocket mode functionality. Unlike traditional pocket mode implementations that continuously monitor sensors, this system activates sensor monitoring only when the device is in lockscreen state, significantly reducing battery consumption and optimizing deep sleep performance.

## Features

- Smart sensor activation only during lockscreen
- Battery-efficient pocket detection
- Prevents accidental wake-ups and touches
- Optimized for deep sleep mode
- Minimal battery impact
- Supports multiple languages (English, German, Spanish, Vietnamese, Hindi)

## How It Works

The system monitors proximity and light sensors exclusively when your device is locked. When the device is placed in a pocket and the proximity sensor detects coverage, the screen remains off to prevent accidental wake-ups. This approach ensures:

1. Extended battery life through selective sensor monitoring
2. Prevention of accidental screen activations in pockets or bags
3. Optimized deep sleep functionality for better standby time
4. Intelligent recalibration after sensor state changes

If the screen remains off after removing the device from your pocket, wait a few seconds for the sensors to recalibrate and normalize their readings.

## Installation

### For ROM Developers

Add the following lines to your device tree source in `device.mk`:

```makefile
PRODUCT_PACKAGES += \
    PocketMode

PRODUCT_COPY_FILES += \
    $(LOCAL_PATH)/pocket/privapp-permissions-pocketmode.xml:$(TARGET_COPY_OUT_PRODUCT)/etc/permissions/privapp-permissions-pocketmode.xml
```

Alternatively you can also include `pocket_mode.mk`.

## Credits

This project is based on the original [Battery-Friendly PocketMode](https://github.com/maytinhdibo/battery-friendly-pocketmode) by Tran Manh Cuong (maytinhdibo). Since the original repository is no longer actively maintained, this fork continues development and maintenance to provide ongoing support for modern Android versions and custom ROMs.

### Original Author
- **Tran Manh Cuong** ([@maytinhdibo](https://github.com/maytinhdibo))
- Original Repository: https://github.com/maytinhdibo/battery-friendly-pocketmode

## License

This project is licensed under the MIT License, maintaining the same license as the original project.

```
MIT License

Copyright (c) 2021 Tran Manh Cuong <maytinhdibo>
Copyright (c) 2026 CipherOS

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## Contributing

Contributions are welcome. Please submit pull requests or open issues for bugs, feature requests, or improvements.

## Support

For issues, questions, or feature requests, please use the GitHub issue tracker.
