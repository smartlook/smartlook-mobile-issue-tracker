# Android SDK changelog

## [1.7.0] - 2020-12-02

### Added
- Automatic integrations for [Heap.io](https://heap.io/), [Amplitude](https://amplitude.com/), [Firebase Crashlytics](https://firebase.google.com/products/crashlytics), [Bugsnag](https://www.bugsnag.com/) and [Mixpanel](https://mixpanel.com/)
- Segment [Middleware](https://segment.com/docs/connections/sources/catalog/libraries/mobile/android/middleware/) implementation that can be used to propagate events from segment to Smartlook
- Adaptive recording framerate enable/disable API

### Fixed
- Various stability improvements

## [1.6.1] - 2020-10-26

### Fixed
- Fixed `Activity` reference issue

## [1.6.0] - 2020-10-12

### Added
- New robust event tracking mode implementation

### Fixed
- Json conversions stability improved
- Debug log tags are not obfuscated

### Changed
- API is now using enums instead of annotation classes, this applies for: `RenderingMode`, `RenderingModeOption`, `ViewType` and `ViewState` 
- Wireframe rendering mode improved `view.clipChildren=false` is now considered

## [1.5.3] - 2020-09-08

### Added
- Additional builder options for bridges (React, Flutter, ...)

### Fixed
- Event spamming stability issue
- Internal session handling
- **Sessions from the same visitor are correctly grouped in Dashboard**

## [1.5.2] - 2020-07-22

### Fixed
- Identify methods can be called outside UI thread

## [1.5.1] - 2020-07-15

### Fixed
- Crashlytics handling

## [1.5.0] - 2020-07-09

### Added
- New API for identification and user properties
- Added `IntegrationListener` that can be used to obtain dashboard session and visitor URL
- New `getDashboardVisitorUrl` method used to obtain dashboard visitor URL
- Session can be now restarted using `resetSession` method
- New visitor can be created using `resetSession` method with `resetUser` option set to TRUE

### Fixed
- Crashes tied to orientation changes
- Identify now fully supports UTF-8

### Changed
- All `setup` and `setupAndStart` methods (appart from the basic variants with `apiKey` parameter only) are now deprecated
- Method `getDashboardSessionUrl` has new option `withCurrentTimestamp` 
- All SDK threads are now named

## [1.4.2] - 2020-04-16

### Added
- Smartlook setup Builder
- Log listener API
- Added various event tracking modes
- WebView whitelisting

### Fixed
- **Smartlook.trackCustomEvent()** fixed -> all custom events are being handled correctly
- Custom events send to the SDK on application start are now being tracked
- All API constants (like `RenderingMode`, `LogAspect`, etc.) are now visible

### Changed
- Offline cache has strict rules now, so the SDK does not occupy large amount of device memory

## [1.4.0] - 2020-03-11

### Added
- Wireframe rendering mode
- TabItem selector identification
- OkHttp network interceptor

### Fixed
- Orientation detection problems
- WebView recording stability issues

### Changed
- Improved image downscaling == better video quality
- Smartlook API doesnt have obfuscated parameter names
- Improved selector detection
- Removed **deprecated** API methods from versions under 1.0.0

## [1.1.5] - 2019-09-17

### Fixed
- Referrer detection now stable
- Tracking of focus gain event

### Added
- Detection of ANR implemented
- New custom timed event

### Changed
- Optimized video size and bitrate so the recordings are smaller than 0,5 MB per minute

## [1.1.2] - 2019-08-20

### Fixed
- User identification now works consistently regardless of when it gets called

## [1.1.1] - 2019-08-19

### Added
- Added ability to adjust view name for "click" events
- Prepared SDK for mobile uploads

### Fixed
- Json parsing issues

## [1.1.0] - 2019-08-07

### Added
- Custom navigation events
- Added ability to not record sensitive elements in WebViews
- Automatic hiding of input elements on WebViews

### Fixed
- Fixed some minor stability issues
- Adaptive framerate is allowed only on native/React SDKs
- Fixed some FragmentDialog recording issues

## [1.0.1] - 2019-07-24

### Fixed
- Fixed some minor stability issues
- Resolved OkHttp v3 and v4 incompability issues

## [1.0.0] - 2019-07-18

### Added
- Adaptive framerate (SDK does not capture new video frames when application idle)
- View/class blacklist and whitelist for marking views as (non) sensitive
- Sensitive mode

### Changed
- API rewriten and unified with iOS API
- Timed event has event properties

### Deprecated
- Most of original API methods were deprecated

### Fixed
- Significant stability improvement
- Fixed keyboard detection
- Recording is not randomly stopping on activity change or orientation change
- Resolved OkHttp v3 and v4 incpomatibility crash
- A variety of minnor issue were fixed

## [0.9.0.2.5.7-beta] - 2019-05-23
### Changed
- New isRecording() method - you can now check if SDK is running or not
- Improved capture logic and selectors detection
- Fix of several minor issues


## [0.9.0.2.5.3-beta] - 2019-04-11
### Changed
- Possibility to use initPassive method and controll recording via start/pause methods
- Fix of cached sessions -> sometimes we created two visitors for single user
- Better lifecycle handling of the activities
- Fix of stability issues for some Huawei/Honor models


## [0.9.0.2.3.9-beta] - 2019-03-26
### Changed
- Possibility to set desired FPS in init methods
- Possibility to init SDK in the middle of the app lifecycle
- Automatic detection of activity/fragment/dialog lifecycle + duration metrics
- Fix of session length
- Better detection that keyboard is active
- Alpha functionality for form analytics -> You can now see which input was somehow problematic for the user to fill in
- Fix of several stability issues


## [0.9.0.2.1.9-beta] - 2019-02-25
### Changed
- Enhanced selector detection
- Fixed display resolution metrics
- Better functionality of pause/start methods
- Fix of several stability issues


## [0.9.0.2.1.4-beta] - 2019-01-14
### Changed
- Better detection of selectors
- Better handling of orientation events
- Minor non-critical bugfixes


## [0.9.0.2.0.8-beta] - 2019-01-14
### Changed
- Overall performance improvements
- Better handling of app's lifecycle
- Several bugfixes


## [0.9.0.2.0.2-beta] - 2019-01-08
### Changed
- Better click detection
- Several bugfixes


## [0.9.0.2.0.0-beta] - 2018-12-19
### Changed
- Multitouch detection
- Keyboard event -> shown in dashboard
- Experimental recording of native maps and MapBox
- Improvement of offline recordings
- Several bugfixes


## [0.9.0.1.8.1-beta] - 2018-11-30
### Changed
- Fixed `ArrayIndexOutOfBoundsException` bug described in issue #8.


## [0.9.0.1.7.7-beta] - 2018-11-22
### Changed
- Improved click detection
- Bug fix: https://github.com/smartlook/smartlook-android-sdk/issues/8
