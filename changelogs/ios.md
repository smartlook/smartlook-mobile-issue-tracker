# iOS SDK changelog

## [1.5.0] - 2020-10-5

### Fixed
- there are some reported bugs that cannot reproduced by us. This release attempts to fix them nevertherless:
 - https://github.com/smartlook/smartlook-mobile-issue-tracker/issues/8
 - https://github.com/smartlook/smartlook-mobile-issue-tracker/issues/5

### Added
- event tracking modes
- rage click detection
- added networking dev tool to iOS

### Changed
- removed some long deprecated methods

## [1.4.1] - 2020-07-07

### Fixed
- messed up focus events
- ocassional crashes in SLInternalSDKProperties when initializing the SDK

## [1.4.0] - 2020-06-24
### Added 
- integration points for other SDKs: session URL with timestamp, visitor page https://smartlook.github.io/docs/sdk/ios/#dashboard-urls

### Fixed
- a significant memory leak

### Changed
- performace improvements
- video quality improvements

## [1.3.1] - 2020-04-29
### Fixed
- an issue when Smartlook blocked answer from `UICollectionViewDelegate` `collectionView:shouldSelectItemAtIndexPath:` method

## [1.3.0] - 2020-04-22
### Fixed
- memory issues in apps with a lot of background activities
### Added
- Event tracking modes
- `noRecording` rendering mode
- `resetSessionAndUser` to explicitelly start new session and optionally reset the current user
### Deprecated
- `fullScreenSensitive` and `analyticsOnlyMode`: they shud be subsititued by a suitable combination of rendering mode and events tracking mode

## [1.2.9] - 2020-04-07
### Fixed
- fixed an error that blocked analytics events

## [1.2.8] - 2020-03-16
### Added
- Analytics-Only recording: does not record screen and does not visualise user interactions https://smartlook.github.io/docs/sdk/ios/#analytics-only-mode
- Rendering Mode BETA: to further protect user's privacy, new recording modes were added to record the screen in the form of a wireframe scheme https://smartlook.github.io/docs/sdk/ios/#rendering-mode-beta

### Changed
- some refactorings, optimizations

### Fixed
- various small and niche bugs

## [1.2.7] - 2019-12-18
### Changed
- removed all traces of `UIWebView` from SDK. `UIWebView` is deprecated and app that use it will soon not allowed in App Store. 
- removing `UIWebView` from SDK causes that **`UIWebView` instances are not overlayed in recordings**. If you want all instances of `UIWebView` overlayed to protect potentially sensitive data, add the following line just after Smartlook setup.

```swift
// Swift
Smartlook.registerBlacklisted(object: UIWebView.self)
// OBJ-C
[Smartlook registerBlacklistedObject:UIWebView.class];
```

## [1.2.6] - 2019-12-02
### Changed
- removed calls to UIWebView methods to avoid App Store warnings. 
- this causes that **in whitelisted UIWebView, sensitive fields are no longer overlayed**. In embedded web views, sensitive fileds are overlayed only in WKWebView from now.

### Added
- ability to whitelist sensitive fields in whitelisted WKWebViews. In order to do that, flag the whitelisted HTML elements with `smartlook-show` CSS class.

## [1.2.5] - 2019-11-11
### Changed
- SDK is build using Xcode 10 again to avoid `___isPlatformVersionAtLeast` undefined symbol issue.

## [1.2.4] - 2019-11-09
### Fixed
- crashing when app presents `UIAlertController` *not* using the standard `UIViewController.present(_:animated:completion:)` method

## [1.2.3] - 2019-10-25
### Fixed
- crashing when app uses `UIAlertController` with `nil` action handler

## [1.2.2] - 2019-10-23
### Added
- `UIAlertController` navigation events and actions recorded
-  in whitelisted instances of `UIWebView` or `WKWebView`, the sensitive data inside them are overlayed

## [1.2.1] - 2019-09-23
### Fixed
- bug when Smartlook crashed on iOS 10.x when some kinds of views (e.g., `UIAlertController`) were used in the app
- bug when Smartlook crashed when the app started w/out network connection
### Added
- support for custom timed events

## [1.2.0] - 2019-09-09
### Added
- support for custom navigation events
### Changed
- improved recording when there are Maps, SpriteKit, SceneKit or Metal views in UIKit app
### Fixed
- bug when `isRecording` returned `true` before `Smartlook.setup()`
- various smaller issues

## [1.1.0] - 2019-07-23
### Changed
- new much consistent version of API, the legacy API marked as deprecated, see documentation for details
- better snapshot handlings to improve CPU and battery efficiency
### Fixed
- various small errors

## [1.0.0] - 2019-05-21
### Added 
- Crashlytics support: URL of the latest recording made by Smartlook during or before the crash is added to crashreports
- Timed events: custom events can record their duration
- Form analytics: the length of editign focus to individual UI elements is explicitly recorded
- Pause/Resume recording, init Smartlook w/out to start recording later
- Optional framerate parameter in Smartlook initialization
### Fixed
- crashes in some complex scenarios where delegate methods to e.g., UITableView are implemented with inheritance hierarchy

## [0.1.12] - 2019-03-25
### Fixed
- Optimized sensitive views overlays with respect to the device rotation and CPU load.

## [0.1.11] - 2019-03-4
### Added
- Supporting selector event on all `UIControl` instances, including `UIDatePicker`, `UISegmentedControl`, `UISlider`, `UIStepper` and `UISwitch`
- `UIView` has two new properties for direct setting of their *sensitivity* handling: `slSensitive` (boolean flag) and `slOverlay` (overlay colour)
  - these properties are also accessible in Xcode Interface Builder

### Fixed
- Location of accessed UITabBarItems
- More accurate overlay of sensitive views

## [0.1.10] - 2019-01-29
### Changes
- Sensitive input views (UITextField, UITextView) are hidden by default now, i.e., overlay is opt-out, not opt-in now
### Fixed
- UserAgent properly set for Smartlook communication
- Fixed snapshots generating when app switches keyWindow


## [0.1.9] - 2019-01-15
### Added
- Multitouch events
- Keyboard show/hide events
### Fixed
- Removed conflicting Crashlytics framework
- Some further minor bug fixes and tweaks
