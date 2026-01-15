# Aosp_SystemUI

We are customising AOSP SystemUI similar to Pixel in Portrait mode.

## Overview

This project contains the Android System UI from AOSP (Android Open Source Project) adapted for Android Studio development. The codebase is based on Android 14 and has been configured to be buildable as a standalone Android Studio project.

## Project Structure

- **src/** - Main source code directory containing Java/Kotlin files
- **res/**, **res-keyguard/**, **res-product/** - Resource directories for UI assets, layouts, and configurations
- **libs/** - Required Android framework JARs and SystemUI libraries
- **iconloaderlib/** - Icon loading library module
- **plugin_core/** - Plugin core module for SystemUI plugins
- **SettingsLib/** - Settings library with multiple submodules
- **WifiTrackerLib/** - WiFi tracking library module
- **Filter/** - Filter module
- **shared/** - Shared components
- **plugin/** - Plugin implementations
- **AndroidManifest.xml** - Application manifest with system permissions
- **proguard.flags** - ProGuard configuration for code obfuscation
- **platform.keystore** - Keystore for signing the application with platform signature

## Prerequisites

- **Android Studio Narwhal (2025.1.2) or later** recommended
  - Also compatible with Android Studio Iguana (2023.2.1) or later
- **JDK 17 or later** (JDK 21 recommended for latest Android Studio versions)
- **Android SDK with API level 34** (Android 14) or later
- **Build Tools version 34.0.0**
- Internet connection for downloading Gradle dependencies

## Setup Instructions

1. **Clone the repository:**
   ```bash
   git clone https://github.com/SharksJio/Aosp_SystemUI.git
   cd Aosp_SystemUI
   ```

2. **Open in Android Studio:**
   - Launch Android Studio
   - Select "Open an Existing Project"
   - Navigate to the cloned directory and select it
   - Wait for Gradle sync to complete (this may take several minutes on first run)
   - Android Studio will automatically download required dependencies

3. **Configure SDK:**
   - Ensure Android SDK API level 30 is installed
   - Set Build Tools version to 30.0.3 in SDK Manager if needed

## Building the Project

### Using Android Studio

1. Open the project in Android Studio
2. Wait for Gradle sync to complete
3. Select **Build > Make Project** from the menu
4. The APK will be generated in `build/outputs/apk/`

### Using Command Line

```bash
# Build debug APK
./gradlew assembleDebug

# Build release APK
./gradlew assembleRelease

# Clean build
./gradlew clean build
```

## Configuration

The project uses the following key configurations:

- **Application ID:** `com.android.systemui`
- **Min SDK:** 29 (Android 10)
- **Target SDK:** 34 (Android 14)
- **Compile SDK:** 34 (Android 14)
- **Build Tools:** 34.0.0
- **Gradle:** 8.7
- **Android Gradle Plugin:** 8.5.2
- **Kotlin:** 1.9.24
- **Java:** 11 (source/target compatibility)

## Dependencies

The project includes:

- AndroidX libraries (AppCompat, RecyclerView, ViewPager2, etc.)
- Kotlin standard library and coroutines
- Dagger 2 for dependency injection
- Android framework JARs (framework.jar, core-all.jar)
- SystemUI specific libraries (SystemUIPluginLib, SystemUISharedLib, WindowManager-Shell)

## Signing Configuration

The project is configured to use the `platform.keystore` with:
- **Store Password:** 123456
- **Key Alias:** platform
- **Key Password:** 123456

**Note:** This is for development purposes. For production, use a secure keystore.

## Modules

The project consists of several modules:

- **iconloaderlib** - Icon loading and manipulation
- **plugin_core** - Core plugin functionality
- **SettingsLib** - Multiple sub-libraries for settings UI:
  - Tile, AdaptiveIcon, RestrictedLockUtils, HelpUtils
  - ActionButtonsPreference, EntityHeaderWidgets, BarChartPreference
  - And more...
- **WifiTrackerLib** - WiFi tracking and management
- **Filter** - Content filtering utilities

## Development Notes

- The project uses Gradle 6.5
- Kotlin version 1.4.0
- Dagger version 2.19
- All modules are configured to disable BuildConfig generation
- Lint checks are disabled for release builds

## References

This project structure is inspired by:
- [siren-ocean/SystemUI](https://github.com/siren-ocean/SystemUI) - Reference implementation for Android Studio compatibility
- AOSP frameworks/base/packages/SystemUI - Original source code

## License

See [LICENSE](LICENSE) file for details.

## Contributing

This is a customization project for AOSP SystemUI. Contributions should maintain compatibility with Android 14 baseline.
