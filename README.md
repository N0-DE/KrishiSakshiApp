# 📱 Krishi Sakhi - Android App Wrapper

This repository contains the native Android WebView wrapper for the **Krishi Sakhi** web application. It bridges the gap between modern web technologies and native Android hardware capabilities to deliver a seamless mobile experience for farmers.

## ✨ Features

- **🌐 WebView Encapsulation:** Serves the compiled React frontend directly from local Android assets (`file:///android_asset/www/index.html`) for offline-first fast loading.
- **📷 Native Camera Integration:** Bypasses standard Android 11+ intent resolution limitations by implementing a custom `WebChromeClient.onShowFileChooser` with `FileProvider`, allowing direct access to the native device camera.
- **✉️ Native SMS Interception:** Intercepts `sms:`, `tel:`, and `mailto:` URIs inside the WebView and safely dispatches them as native Android `ACTION_VIEW` intents to trigger the device's default messaging and telephony apps.
- **🔐 Permission Handling:** Automatically manages required hardware permissions (Camera, Storage) from within the web context.

## 🚀 Getting Started

### Prerequisites
- Android Studio (Iguana or later recommended)
- Android SDK Platform-Tools
- Gradle 8.x

### Build & Install

1. Clone the repository:
   ```bash
   git clone https://github.com/N0-DE/KrishiSakshiApp.git
   ```

2. Open the project in **Android Studio**.

3. To update the web bundle:
   - Build the frontend project (`krishisakhi`) using `npm run build`.
   - Copy the contents of the `dist/` directory into `app/src/main/assets/www/`.

4. Build and deploy:
   - Connect your Android device via ADB.
   - Click **Run 'app'** in Android Studio, or use the command line:
     ```bash
     ./gradlew assembleDebug
     adb install app/build/outputs/apk/debug/app-debug.apk
     ```

## 📄 License
This project is licensed under the MIT License.
