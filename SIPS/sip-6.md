  |SIP|Title|Status|Type|Category|Author|Created|
  |--:|:--:|:--:|:--:|:--:|:--|:--:|
  |6|Wallet with DRM function|Review|Standard|Application|Yutaka Otake(@YErikOhtake)|2023-10-15|

# Simple Summary
Application that play NFT content require license management and content protection.

Content protection means no/no screenshots and no playback outside the application.

We will use our existing DRM services, Widevine and Fairplay, to accomplish these functions.

With Widevine and Fairplay, almost any end user can use it.

# Implementation
- Image
  - Widevine and Fairplay do not support images. Therefore, image protection is implemented in native applications using OS functionality.
  - For Android, a setting called FLAG_SECURE makes screenshots impossible.
  - For iOS, the isSecureTextEntry setting can be used to effectively disable screenshots by making them completely white.
- Audio
  - Use Widevine and Fairplay
- Video
  - Use Widevine and Fairplay
