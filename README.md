# PhotosCore


- Package: `com.zijian.photoscore`
- Version: `1.0.0-14.12`
- Supported systems: iOS `16.0-16.5.1`
- Architectures: `arm64`, `arm64e`
- Injection target: `com.apple.mobileslideshow` / `MobileSlideShow`

## General Controls

This is a plugin designed to enhance the system's photo app.

- **Enable PhotosCore**: Enables or disables all PhotosCore runtime features. The state is read when the Photos process starts, preventing hooks from being installed or removed while Photos is running. A restart confirmation is shown after changing this setting.
- **Show Function Descriptions**: Shows or hides the explanatory text displayed below PhotosCore options. Changes take effect after the requested process restart.
- **Restore Default Settings**: Restores feature options and the native thumbnail mode. It does not change the master enable state or the Show Function Descriptions preference.

## Photo Viewing and Album Navigation

- **Photos Bottom Bar**: Independently shows or hides the native Photos bottom bar.
- **Fullscreen Photos**: Centers an opened photo in the full available display area so the sidebar does not cover the image. This option also keeps the current zoom level when the enlarged photo is tapped once.
- **Sort by Name**: Adds custom name-based sorting to the album sorting menu available from the upper-right corner of an album.
- **Open Albums at the Bottom**: Opens an album at its newest/bottom position instead of starting at the top.
- **Long-Press Albums Shortcut**: Long-pressing the bottom Albums tab jumps directly to the Albums page.

## Thumbnail Layouts

PhotosCore can replace the native `1 / 3 / 5 / 15 / 33`-column zoom sequence with a denser and more configurable thumbnail system.

- **Native Thumbnails**: Uses the original Photos layouts without modification.
- **1-9 Thumbnail Preset**: Provides a ready-made sequence from 1 through 9 columns.
- **Custom Mode**: Provides full control over thumbnail zoom levels and column counts.
- Configure between **5 and 10 zoom levels**.
- Configure each level from **1 to 100 columns**.
- Use `-1` for the native final high-density layout or `-2` for the native second-to-last high-density layout.
- Configure a **0-100 spacing threshold**; layouts above the selected column count use zero spacing.
- Optionally use the native Photos high-density layout engine for the final two custom levels.
- Custom values are stored independently for each selected zoom-level count.

## Search Customization

Each Photos search section can be shown, hidden, and reordered:

- Moments
- People
- Places
- Categories
- Recent Searches

## Album Section Customization

- Independently show or hide **People**.
- Independently show or hide **Places**.
- When both are hidden, the complete People & Places section is removed rather than leaving an empty heading.

## Sidebar Customization

The following sidebar destinations can be independently shown or hidden:

- Library
- For You
- People
- Places
- Favorites
- Recents
- Search

The following sidebar groups can be shown, hidden, and reordered:

- More Items
- Media Types
- Shared Albums
- My Albums

## Experimental Features

These options are grouped under **Test Features** because they are still experimental and may be less stable than the main feature set.

- **Landscape Double-Page Photos**: Displays two photos side by side while the device is in landscape orientation.
- **Photos Dark Mode**: Forces the Photos app to use a dark appearance.
- **Smart Albums**: Adds advanced, rule-based album creation and management using the native Photos search index.

### Smart Album Capabilities

- Create a custom-named system album from native Photos **Saved from App** search results.
- Bind one or multiple source apps to a Smart Album.
- View and manage bound sources, including source item counts and thumbnails.
- Manually synchronize each bound source and optionally synchronize when its native search result is opened.
- Choose **Add New Items Only** or **Keep Consistent with Search Results** synchronization.
- Consistency mode only removes rule-managed items that no longer match; it does not delete photos or videos from the library and preserves manually added album items.
- View the target album directly from the rule detail page.
- Inspect target-album status, system item count, recorded rule item count, missing items, stale records, and the last synchronization time.
- Restore missing items, repair inconsistent records, remove extra album items on demand, and repair stale records.
- Add or detach sources without deleting media from the Photos library.
- Sort Smart Albums manually or alphabetically.
- Long-press a Smart Album to rename it.
- Delete a Smart Album rule and its target system album without deleting the contained photos or videos from the library.

## Runtime and Safety Notes

- The tweak filter targets only the Apple Photos process; it is not globally injected into unrelated apps or system processes.
- Preference changes that affect hook installation use a Photos/SpringBoard restart flow to avoid changing hooks in a live Photos process.
- Smart Album cleanup operations modify album membership only. They do not delete the underlying photos or videos from the photo library.

---


