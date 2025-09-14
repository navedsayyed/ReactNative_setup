bash
adb --version
bash
bash
<div align="center">

# 🚀 React Native Setup Guide (Windows)

</div>

---

> **Follow this step-by-step guide to set up a modern React Native development environment on Windows.**

---

## 1️⃣ Install Node.js

- Download the **LTS version** from [nodejs.org](https://nodejs.org)
- After installation, verify in a new terminal:

```powershell
node -v
npm -v
```

---

## 2️⃣ Install Java Development Kit (JDK)

- Download **JDK 17 (LTS)** from [Adoptium](https://adoptium.net/)
- After installation, verify:

```powershell
java -version
```

---

## 3️⃣ Install Android Studio

- Download from [developer.android.com/studio](https://developer.android.com/studio)
- During setup, ensure you install:
	- [x] **Android SDK**
	- [x] **Android SDK Platform**
	- [x] **Android Virtual Device (AVD)**

> ⚠️ **Important:** SDK path must **not** contain spaces!  
> ✅ Example: `C:\Android\Sdk`  
> ❌ Avoid: `C:\Users\Naved Sayyed\AppData\Local\Android\Sdk`

---

## 4️⃣ Install SDK Platforms

- In Android Studio: `Settings` → `SDK Manager` → `SDK Platforms` tab
- Check:
	- [x] **Android 16 (API Level 36)** (Target/Compile SDK)
	- [x] **Android 5.0 (API Level 21)** (Minimum supported)

---

## 5️⃣ Install SDK Tools

- In `SDK Manager` → `SDK Tools` tab
- Enable **Show Package Details**
- Select:
	- [x] **Android SDK Platform-Tools**
	- [x] **Android Emulator**
	- [x] **Android SDK Build-Tools** → `35.0.0` and `36.0.0`
	- [x] **NDK (Side by Side)** → `27.1.12297006`
	- [x] **Android Emulator Hypervisor Driver**

---

## 6️⃣ Setup Environment Variables

- Open: `System Properties` → `Advanced` → `Environment Variables`

### Add in **User Variables** (Top Section)

| Variable      | Value                              |
|--------------|-------------------------------------|
| JAVA_HOME    | C:\Program Files\Java\jdk-17       |
| ANDROID_HOME | C:\Android\Sdk                     |

Add to **Path**:

```
%ANDROID_HOME%\platform-tools
%ANDROID_HOME%\emulator
%ANDROID_HOME%\cmdline-tools\bin
```

### Add the same in **System Variables** (Bottom Section)

| Variable      | Value                              |
|--------------|-------------------------------------|
| JAVA_HOME    | C:\Program Files\Java\jdk-17       |
| ANDROID_HOME | C:\Android\Sdk                     |

Add to **Path** (same three lines as above).

#### Verify:

```powershell
echo %JAVA_HOME%
echo %ANDROID_HOME%
adb --version
```

---

## 7️⃣ Create and Run React Native Project

### Step 1: Remove Old CLI

```powershell
npm uninstall -g react-native-cli @react-native-community/cli
```

### Step 2: Create New Project

Open terminal in **C:\** and run:

```powershell
npx @react-native-community/cli@latest init AwesomeProject
```

This creates your project in:

```
C:\AwesomeProject
```

### Step 3: Start Metro Bundler

```powershell
cd C:\AwesomeProject
npm start
```

_(Keep this terminal open)_

### Step 4: Run App on Android

Open a **new terminal** in the same folder:

```powershell
npm run android
```

---

## ✅ Summary Table

| Component                | Version / Setting                |
|--------------------------|----------------------------------|
| Node.js                  | LTS                              |
| JDK                      | 17                               |
| SDK Platforms            | API 21 (min), API 36 (target)    |
| SDK Build-Tools          | 35.0.0, 36.0.0                   |
| NDK (Side by Side)       | 27.1.12297006                    |
| Environment Variables    | Add in both User & System        |

**Project Commands:**

```powershell
npm uninstall -g react-native-cli @react-native-community/cli
npx @react-native-community/cli@latest init AwesomeProject
cd C:\AwesomeProject
npm start         # Terminal 1
npm run android   # Terminal 2
```

---

<div align="center">

🎉 **Done! You now have a fully working React Native environment on Windows.**

</div>
