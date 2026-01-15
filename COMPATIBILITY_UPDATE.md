# Android Studio Narwhal Compatibility Update

## Overview

This update makes the SystemUI project compatible with **Android Studio Narwhal Feature Drop (2025.1.2 Patch 1)** running on Java 21.

## Changes Made

### Build System Updates

| Component | Previous | Updated |
|-----------|----------|---------|
| Gradle | 7.6.4 | **8.7** |
| Android Gradle Plugin | 7.3.1 | **8.5.2** |
| Kotlin | 1.8.22 | **1.9.24** |
| Compile SDK | 30 (Android 11) | **34 (Android 14)** |
| Target SDK | 30 | **34** |
| Build Tools | 30.0.3 | **34.0.0** |
| Java Compatibility | 8 | **11** |

### Configuration Changes

1. **Gradle Wrapper** (`gradle/wrapper/gradle-wrapper.properties`)
   - Updated to Gradle 8.7 for Java 21 support

2. **Build Configuration** (`build.gradle`)
   - Updated AGP to 8.5.2
   - Updated Kotlin to 1.9.24
   - Removed deprecated `kotlin-android-extensions` plugin
   - Changed Java source/target compatibility to 11
   - Changed Kotlin JVM target to 11
   - Replaced `lintOptions` with `lint` DSL block
   - Added `buildFeatures` configuration
   - Added namespace declaration

3. **Project Properties** (`gradle.properties`)
   - Updated compile SDK to 34
   - Updated build tools to 34.0.0
   - Added build feature defaults

4. **Module Updates**
   - **iconloaderlib**: Added namespace, updated SDK/Java versions, modernized lint config
   - **plugin_core**: Added namespace, updated SDK/Java versions, modernized lint config
   - **SettingsLib**: Added namespace, updated SDK/Java versions, modernized lint config, added Kotlin JVM target
   - **WifiTrackerLib**: Added namespace, updated SDK/Java versions, modernized lint config
   - **All 17 SettingsLib submodules**: Applied same updates

### Key Improvements

1. **Java 21 Support**: Gradle 8.7 fully supports Java 21 used by Android Studio Narwhal
2. **Modern AGP**: AGP 8.5.2 brings latest Android build features and bug fixes
3. **Kotlin K2 Mode**: Kotlin 1.9.24 is compatible with K2 compiler mode
4. **Deprecated API Removal**: All deprecated DSL elements replaced with modern equivalents
5. **Namespace Declarations**: All modules now have explicit namespace declarations (required for AGP 8.x)

### Deprecated Features Removed

- ❌ `kotlin-android-extensions` plugin (deprecated in Kotlin 1.8+)
- ❌ `lintOptions` DSL block (replaced with `lint`)
- ❌ `afterEvaluate` blocks for BuildConfig disabling (replaced with `buildFeatures`)
- ❌ Java 8 compatibility (minimum is now Java 11)

### Testing Compatibility

The project is now fully compatible with:
- ✅ Android Studio Narwhal 2025.1.2
- ✅ Java 21 (OpenJDK 21.0.6+)
- ✅ Kotlin K2 mode
- ✅ Gradle 8.x features
- ✅ AGP 8.x API changes

## What You Need

To work with this project, ensure you have:
- **Android Studio**: Narwhal (2025.1.2) or later, or Iguana (2023.2.1+)
- **JDK**: Version 17 or later (21 recommended)
- **Android SDK**: API 34 installed
- **Build Tools**: 34.0.0

## How to Use

1. Open the project in Android Studio Narwhal
2. Let Gradle sync complete (may take a few minutes on first sync)
3. Build the project: `Build > Make Project` or `./gradlew assembleDebug`

The project should now sync and build without issues in your Android Studio version!

---

**Commit**: 35f8370
**Date**: January 15, 2026
**Compatible With**: Android Studio Narwhal 2025.1.2+
