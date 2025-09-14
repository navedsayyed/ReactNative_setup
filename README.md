# 🚀 React Native Setup Guide (Windows)

This guide explains how to set up **React Native** on **Windows** step by step.

---

## 1️⃣ Install Node.js
- Download Node.js (LTS version) → [https://nodejs.org](https://nodejs.org)

Verify installation:
```bash
node -v
npm -v
2️⃣ Install Java Development Kit (JDK)
Download JDK 17 (LTS) → https://adoptium.net/

Verify installation:

bash
Copy code
java -version
3️⃣ Install Android Studio
Download → https://developer.android.com/studio

During setup, install:

✅ Android SDK

✅ Android SDK Platform

✅ Android Virtual Device (AVD)

⚠️ Important: SDK path must not contain spaces

✅ Example: C:\Android\Sdk

❌ Avoid: C:\Users\Naved Sayyed\AppData\Local\Android\Sdk

4️⃣ Install SDK Platforms
In Android Studio → Settings → SDK Manager → SDK Platforms tab, check:

✅ Android 16 (API Level 36) → Target/Compile SDK

✅ Android 5.0 (API Level 21) → Minimum supported

5️⃣ Install SDK Tools
In SDK Manager → SDK Tools tab, enable Show Package Details, then select:

✅ Android SDK Platform-Tools

✅ Android Emulator

✅ Android SDK Build-Tools → 35.0.0 and 36.0.0

✅ NDK (Side by Side) → 27.1.12297006

✅ Android Emulator Hypervisor Driver

6️⃣ Setup Environment Variables
Open System Properties → Advanced → Environment Variables

Add in User Variables (Top Section)
ini
Copy code
JAVA_HOME = C:\Program Files\Java\jdk-17
ANDROID_HOME = C:\Android\Sdk
Path → Add:

perl
Copy code
%ANDROID_HOME%\platform-tools
%ANDROID_HOME%\emulator
%ANDROID_HOME%\cmdline-tools\bin
Add the Same in System Variables (Bottom Section)
ini
Copy code
JAVA_HOME = C:\Program Files\Java\jdk-17
ANDROID_HOME = C:\Android\Sdk
Path → Add the same three lines.

Verify
bash
Copy code
echo %JAVA_HOME%
echo %ANDROID_HOME%
adb --version
7️⃣ Create and Run React Native Project
Step 1: Remove Old CLI
bash
Copy code
npm uninstall -g react-native-cli @react-native-community/cli
Step 2: Create New Project
Open terminal in C:\ and run:

bash
Copy code
npx @react-native-community/cli@latest init AwesomeProject
This creates your project in:

makefile
Copy code
C:\AwesomeProject
Step 3: Start Metro Bundler
bash
Copy code
cd C:\AwesomeProject
npm start
(Keep this terminal open)

Step 4: Run App on Android
Open a new terminal in the same folder:

bash
Copy code
npm run android
✅ Summary
Node.js → LTS

JDK → 17

SDK Platforms → API 21 (min) & API 36 (target)

SDK Build-Tools → 35.0.0 & 36.0.0

NDK (Side by Side) → 27.1.12297006

Environment Variables → Add in both User and System

Project Commands:
bash
Copy code
npm uninstall -g react-native-cli @react-native-community/cli
npx @react-native-community/cli@latest init AwesomeProject
cd C:\AwesomeProject
npm start         # Terminal 1
npm run android   # Terminal 2
🎉 Done! You now have a fully working React Native environment on Windows.

yaml
Copy code

---
