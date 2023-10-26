  |SIP|Title|Status|Type|Category|Author|Created|
  |--:|:--:|:--:|:--:|:--:|:--|:--:|
  |6|Wallet with DRM function|Draft|Standard|Application|Yutaka Otake(@YErikOhtake)|2023-10-15|

# Simple Summary
Wallets that play content require license management and copy protection.
We would like to implement these functions using existing DRM services, Widevine & Fairplay.

DRM content protection means no/no screenshots and no playback outside the wallet.
In order to realize DRM protection of content and viewing of DRM-protected content, it is necessary to implement DRM-related functions in the Wallet.

# Implementation
In order to play DRM-protected content, the following functions should be provided
- Image
  - Existing DRM services do not support images. Therefore, image protection is implemented in native applications using OS functionality.
  - For Android, a setting called FLAG_SECURE makes screenshots impossible.
  - For iOS, the isSecureTextEntry setting can be used to effectively disable screenshots by making them completely white.
- Audio
  - Use existing DRM services: Widevine and Fairplay
- Video
  - Use existing DRM services: Widevine and Fairplay
