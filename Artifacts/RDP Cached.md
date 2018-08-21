#RDP Cached Bitmap

The RDP caching mechanism reduces the amount of data that needs to be sent to an RDP client. It does this by caching those parts of the screen that haven't changed since the display was last refreshed.

Cache-files store raw bitmaps in the form of tiles. The size of each tile can vary, but a common size is 64 x 64 pixels.

**Location:**

- %localappdata%\Microsoft\Terminal Server Client\Cache

**Tools:**

- RDP Cached Bitmap Extractor - https://www.guidancesoftware.com/app/RDP-Cached-Bitmap-Extractor
- bmc-tools - https://github.com/ANSSI-FR/bmc-tools
