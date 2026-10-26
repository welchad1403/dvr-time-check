# DVR Time Check — Change Log

**Status: BETA.** Not yet approved for case use. Version 1.0.0 will be the first official release.

Version numbers use MAJOR.MINOR.PATCH:
- **MAJOR** — 0 while in beta; 1 at official release; goes up after that when how results are calculated or documented changes
- **MINOR** — new features
- **PATCH** — bug fixes

The version in use shows in the app header and at the bottom of every downloaded result image.

---

## v0.5.0-beta — 2026-10-26
### Added
- **Open camera**: in-app camera (one step). The phone clock is recorded at the exact instant the shutter is tapped, to the millisecond, and used as actual time. A live clock shows in the camera view.
- The app writes EXIF metadata into the captured photo: DateTimeOriginal, sub-seconds, time zone, device, and the app version (Software field), so Photos shows the correct date taken.
- Photo metadata panel for in-app captures: capture method, shutter time, time zone, device, image size, SHA-256, EXIF written.
- **Save result** and **Save photo** open the share sheet; on iPhone tap **Save Image** to put it in the Photos library. Falls back to a download where sharing isn't available.
### Changed
- Removed the old **Take photo** button (Safari stripped its metadata). **Choose photo** and **From Files** remain for existing photos.
### Notes
- Actual time for in-app captures comes from the phone's network-synced clock at the shutter tap, recorded by this app (not by the iPhone Camera app).

## v0.4.0-beta — 2026-10-26
### Added
- **Choose from Files (keeps metadata)** button. On iPhone, Safari strips metadata from photos taken or chosen through the photo library; photos opened from the Files app keep their original EXIF date-taken time.
- Version number shown in the app header and printed on each downloaded result image.
- This change log.
### Changed
- DVR and actual time boxes are now plain text in `MM/DD/YYYY HH:MM:SS` format (12-hour with AM/PM also accepted). iPhone's built-in time picker hid the seconds.
### Fixed
- Auto-read now corrects a leading zero misread as 8, 6 or 9 in the DVR date (e.g. "88/31/2026" → 08/31/2026).

## v0.3.0-beta — 2026-10-26
### Added
- Reads EXIF metadata from HEIC/HEIF (iPhone), PNG and WebP photos, not only JPEG.
- **File type** line in the photo metadata.

## v0.2.0-beta — 2026-10-25
### Added
- Offset shown as separate days, hours, minutes and seconds.
- **Photo metadata** panel: file name, size, SHA-256 hash, camera make/model, software, EXIF date taken (with sub-seconds), EXIF time zone, EXIF digitized, file last modified, time photo was received, and which source was used for actual time.
- Photo metadata printed on the downloaded result image.
- **Save original photo** button: saves the photo byte-for-byte unchanged so its hash and metadata can be verified later.

## v0.1.0-beta — 2026-10-25
### Added
- One-screen app: photo of DVR screen, DVR time, actual time and offset.
- Automatic reading of the DVR's on-screen time (on-phone text recognition), with manual correction.
- Actual time taken from the photo's EXIF date, falling back to the file timestamp, then the phone clock.
- Download of the result as an image.
- Hosted on GitHub Pages so it runs on iPhone and Android.
