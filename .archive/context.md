# Shattered Pixel Dungeon Development Status

## Project Overview
Shattered Pixel Dungeon is an open-source roguelike RPG with pixel art graphics. It's a fork of the original Pixel Dungeon by Watabou, featuring enhanced gameplay, new content, and improved mechanics. The game is available on multiple platforms including Android (primary focus) and desktop (Windows, Mac, Linux).

## Current Development Status (As of June 6, 2025)
- **Repository:** Successfully cloned from https://github.com/00-Evan/shattered-pixel-dungeon.git
- **Environment Configuration:** 
  - Platform: Windows
  - JDK: Java 17.0.12
  - Gradle: 8.10.2
  - Android SDK: Configured in local.properties (C:\Users\Administrator\AppData\Local\Android\Sdk)

## Build Status
- **Android Build:** ✅ Successful (APK generated at android/build/outputs/apk/debug/android-debug.apk)
- **Module Builds:** All modules built successfully (core, android, desktop, services, SPD-classes, etc.)
- **Current Focus:** Android platform development and testing

## Project Structure
- **core:** Main game logic, mechanics, and assets
- **android:** Android-specific implementation
- **desktop:** Desktop-specific implementation
- **SPD-classes:** Custom classes for the game
- **services:** Updates and news services
- **ios:** iOS-specific implementation

## Technology Stack
- **Framework:** LibGDX (1.12.1)
- **Language:** Java (Java 8 compatibility)
- **Build System:** Gradle 8.10.2
- **Android Configuration:**
  - Compile SDK: 34
  - Min SDK: 14
  - Target SDK: 34
  - Application ID: com.shatteredpixel.shatteredpixeldungeon
  - Version: 3.0.2 (Code: 833)

## Next Steps
1. Configure Android device/emulator for testing
2. Deploy and test the APK on device/emulator
3. Verify game features work properly on Android
4. Explore codebase for potential modifications/enhancements

## Memory Bank Status
Memory Bank system initialized and configured with task tracking, context documentation, and project information.

Setting Up Shattered Pixel Dungeon in Cursor IDE
Overview
This wiki entry summarizes the process of setting up the Shattered Pixel Dungeon project for development in the Cursor IDE by cloning the GitHub repository, configuring the development environment, and resolving a Gradle build error related to the Android SDK. The conversation occurred on June 2, 2025, and addresses setup for a Java-based, LibGDX project targeting desktop and Android platforms.
Prerequisites

Git: For cloning the repository. Install from git-scm.com and verify with git --version.
Java Development Kit (JDK): JDK 17 or later, available from Adoptium or Oracle. Set JAVA_HOME environment variable.
Android Studio (optional for Android): For Android SDK and emulator, downloadable from developer.android.com.
Cursor IDE: A VS Code-based IDE with AI features, available from cursor.com.
Gradle: Included as a wrapper in the project, but can be installed separately for manual builds.

Steps to Set Up Shattered Pixel Dungeon
1. Cloning the Repository

In Cursor IDE:
Open the Source Control view (Ctrl+Shift+G).
Select Clone Repository and enter https://github.com/00-Evan/shattered-pixel-dungeon.git.
Choose a local directory (e.g., D:\Projects\shattered-pixel-dungeon).


Via Terminal:git clone https://github.com/00-Evan/shattered-pixel-dungeon.git
cd shattered-pixel-dungeon
cursor .



2. Opening the Project

In Cursor IDE, go to File > Open Folder and select the cloned shattered-pixel-dungeon directory.
Cursor loads the Gradle-based project structure.

3. Configuring Java Environment

Install Java Extensions:
In the Extensions view (Ctrl+Shift+X), install the Java Extension Pack by Microsoft or Language Support for Java™ by Red Hat.


Set JDK:
Configure java.home in Cursor settings to point to JDK 17 (e.g., C:\Program Files\Java\jdk-17).
Verify by opening a .java file (e.g., core/src/main/java/com/shatteredpixel/shatteredpixeldungeon/ShatteredPixelDungeon.java) and checking for code completion.



4. Setting Up Gradle

The project uses Gradle 8.10.2 (per gradle-wrapper.properties).
Sync Gradle:
In Cursor, run Gradle: Refresh Gradle Project from the Command Palette (Ctrl+Shift+P).
Or, in terminal:./gradlew build




Dependencies (e.g., LibGDX) are downloaded automatically during the first sync.

5. Run Configurations

Desktop:
In Run and Debug (Ctrl+Shift+D), create a Java configuration:
Main Class: com.shatteredpixel.shatteredpixeldungeon.desktop.DesktopLauncher.
Module: desktop.
Working Directory: <project-root>/desktop.


Run or debug using the green play icon.


Android (optional):
Requires Android SDK setup (see below).
Configure the android module with main class com.shatteredpixel.shatteredpixeldungeon.ShatteredPixelDungeon.



6. Building the Project

Full Build:./gradlew build


Outputs: desktop/build/libs/ for desktop, android/build/outputs/apk/debug/ for Android.


Desktop-Only Build:./gradlew desktop:build


Run desktop version:./gradlew desktop:run



7. Resolving Gradle Build Error

Error Encountered:
Running ./gradlew build in D:\Projects\shattered-pixel-dungeon\shattered-pixel-dungeon failed with:Could not determine the dependencies of task ':android:compileDebugJavaWithJavac'.
> SDK location not found. Define a valid SDK location with an ANDROID_HOME environment variable or by setting the sdk.dir path in your project's local properties file at 'D:\Projects\shattered-pixel-dungeon\shattered-pixel-dungeon\local.properties'.


Caused by missing Android SDK configuration for the android module.


Solution:
Install Android Studio: Download from developer.android.com and install Android SDK (e.g., API 33 or 34).
Set ANDROID_HOME:
On Windows:
Open Environment Variables via "Edit the system environment variables."
Add ANDROID_HOME with value C:\Users\<YourUsername>\AppData\Local\Android\Sdk.
Verify: echo $Env:ANDROID_HOME in PowerShell.




Create local.properties (alternative):
In the project root, create local.properties with:sdk.dir=C:\\Users\\<YourUsername>\\AppData\\Local\\Android\\Sdk




Retry Build:./gradlew build


Desktop-Only Alternative:
If Android is not needed, build only the desktop module:./gradlew desktop:build






Verification:
User confirmed setting ANDROID_HOME, resolving the SDK issue.
Refresh Gradle in Cursor (Gradle: Refresh Gradle Project) to ensure proper configuration.



8. Leveraging Cursor IDE Features

AI Assistance:
Use Cursor's AI for code completion, refactoring, or error fixing (e.g., Ctrl+Shift+A or right-click).
Optionally, create a .cursor/settings.json for project-specific AI settings:{
  "language": "java",
  "project_type": "libgdx",
  "preferred_style": "Google Java Style"
}




Git Integration:
Use the Source Control view to commit and push changes:git add .
git commit -m "Changes made"
git push origin main





Troubleshooting

Gradle Sync Issues:
Clear cache: ./gradlew cleanBuildCache.
Use --stacktrace --info for detailed logs.


Java Issues:
Verify JAVA_HOME and JDK path in Cursor settings.


Android Issues:
Ensure Android SDK includes required build tools and API levels.
Check android/build.gradle for compatible compileSdkVersion.



Project Structure

Core: core/src/main/java/com/shatteredpixel/shatteredpixeldungeon/ (main game logic).
Desktop: desktop/src/main/java/ (desktop-specific code).
Android: android/src/main/java/ (Android-specific code).
Docs: Refer to getting-started-desktop.md and getting-started-android.md.

Sources

GitHub Repository: 00-Evan/shattered-pixel-dungeon
Gradle Documentation: docs.gradle.org
Android Studio: developer.android.com
Community: r/PixelDungeon
Cursor IDE insights from X posts on project setup.

Notes

Focus on the desktop module for simpler setup if Android development is not required.
Use Cursor's AI features to streamline coding and debugging.
For further issues, consult the project's GitHub issues or community forums.

