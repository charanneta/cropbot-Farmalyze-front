# Farmalyse - CropBot AI 🌾

An intelligent Flutter mobile application that provides AI-powered crop disease detection and agricultural insights. Farmalyse leverages computer vision and machine learning to help farmers identify crop diseases, access real-time news, and get location-based agricultural information.

---

## 📋 Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Project Structure](#project-structure)
- [Usage](#usage)
- [API Integration](#api-integration)
- [Supported Platforms](#supported-platforms)
- [Contributing](#contributing)

---

## ✨ Features

- **AI-Powered Disease Detection**: Upload or capture crop images to identify diseases using machine learning
- **Real-time Agricultural News**: Stay updated with the latest agricultural insights and news
- **Voice Input Support**: Use speech-to-text for hands-free interaction
- **Text Translation**: Multi-language support with automatic translation
- **Geolocation Services**: Access location-based agricultural information
- **Text-to-Speech**: Listen to results and news in your preferred language
- **Offline Support**: Core features work offline with cached data
- **Dark Mode**: Beautiful dark theme for comfortable nighttime usage
- **Cross-Platform**: Available on Android, iOS, web, Windows, macOS, and Linux

---

## 🛠 Tech Stack

### Framework & Language

- **Flutter 3.8.1+** - UI framework
- **Dart** - Programming language

### Key Dependencies

- **image_picker** (^1.0.4) - Image capture and selection
- **http** (^1.5.0) - API communication
- **speech_to_text** (^7.3.0) - Voice input
- **flutter_tts** (^3.8.5) - Text-to-speech output
- **flutter_sound** (^9.28.0) - Audio recording
- **geolocator** (^10.1.0) - Geolocation services
- **translator** (^1.0.0) - Multi-language translation
- **google_fonts** (6.3.2) - Typography
- **lottie** (^3.3.2) - Animations
- **share_plus** (^12.0.1) - Share functionality
- **url_launcher** (^6.3.2) - Launch external URLs
- **permission_handler** (^11.0.0) - Permission management
- **flutter_dotenv** (^5.2.1) - Environment configuration

### Development Tools

- **flutter_launcher_icons** - App icon generation
- **flutter_native_splash** - Splash screen generation
- **flutter_lints** - Code quality and linting

---

## 📦 Prerequisites

Before you begin, ensure you have installed:

- **Flutter SDK** (3.8.1 or higher) - [Installation Guide](https://flutter.dev/docs/get-started/install)
- **Dart SDK** (included with Flutter)
- **Android SDK** (for Android development)
  - Android Studio or Android Command-line Tools
  - Minimum API Level: 21
- **Xcode** (for iOS development, macOS only)
- **Git** - Version control

### System Requirements

- **RAM**: Minimum 4GB (8GB recommended)
- **Storage**: At least 5GB free space
- **Internet**: Required for API communication and feature downloads

---

## 🚀 Installation

### 1. Clone the Repository

```bash
git clone <repository-url>
cd cropbot_ai
```

### 2. Install Dependencies

```bash
flutter pub get
```

### 3. Generate App Icons and Splash Screen

```bash
flutter pub run flutter_launcher_icons:main
flutter pub run flutter_native_splash:create
```

### 4. Platform-Specific Setup

#### For Android

```bash
cd android
./gradlew build
```

#### For iOS

```bash
cd ios
pod install
```

---

## ⚙️ Configuration

### Environment Setup

Create a `.env` file in the project root:

```env
API_BASE_URL=https://farmalyse-backend.onrender.com/
```

### API Configuration

The app automatically configures the API base URL in `main.dart`:

- **Emulator**: `http://10.0.2.2:8000`
- **Physical Device**: `https://farmalyse-backend.onrender.com/` (or NGROK URL)
- **Local Network**: `http://<YOUR_IP>:8000` (e.g., `http://192.168.43.1:8000`)

### Permissions

The app requires the following permissions:

**Android** (`android/app/src/main/AndroidManifest.xml`):

- Camera
- Storage Read/Write
- Microphone (for speech-to-text)
- Location (GPS)

**iOS** (`ios/Runner/Info.plist`):

- Camera usage description
- Microphone usage description
- Location usage description
- Photo library usage description

---

## 📁 Project Structure

```
lib/
├── main.dart                 # App entry point, theme configuration
├── screens/
│   ├── prediction_screen.dart   # Main crop disease detection UI
│   └── news_screen.dart         # Agricultural news feed
├── pages/
│   └── home_page.dart           # Home page navigation
├── services/
│   └── api_service.dart         # Backend API communication
├── utils/                       # Utility functions and helpers
└── widgets/                     # Reusable UI components

assets/
├── images/                  # App images and graphics
├── icons/                   # App icons and branding
├── animations/
│   └── plant_loading.json   # Lottie animations
├── fonts/                   # Custom fonts (Manrope)
└── vosk-model-small-en-in-0.4/  # Offline speech recognition model
```

---

## 🎯 Usage

### Running the App

#### Development Mode

```bash
flutter run
```

#### Specific Platform

```bash
flutter run -d android      # Android device/emulator
flutter run -d ios          # iOS device/simulator
flutter run -d web          # Web browser
flutter run -d windows      # Windows
flutter run -d macos        # macOS
flutter run -d linux        # Linux
```

#### Release Build

```bash
flutter build apk           # Android APK
flutter build ios           # iOS app
flutter build web           # Web deployment
flutter build windows       # Windows executable
flutter build macos         # macOS app bundle
flutter build linux         # Linux executable
```

### Key Features Usage

1. **Disease Detection**:

   - Tap camera icon to capture or select an image
   - AI model analyzes the image
   - View disease diagnosis and recommendations

2. **Voice Input**:

   - Activate voice input during prediction
   - Speak to search or input text
   - Results displayed with text-to-speech

3. **News Feed**:

   - Browse latest agricultural news
   - Read full articles
   - Share news with others

4. **Translation**:
   - Results automatically translated to your language
   - Configurable language preferences

---

## 🔌 API Integration

The app communicates with the **Farmalyse Backend** API for:

- **Image Analysis**: Sends crop images for disease detection
- **News Feed**: Fetches agricultural news and updates
- **Location Data**: Processes geolocation for localized recommendations

### Base URL Configuration

Update the base URL in `main.dart` for your backend server:

```dart
String baseUrl = 'https://your-api-url.com';
ApiService.setBaseUrl(baseUrl);
```

---

## 📱 Supported Platforms

| Platform | Status       | Min Version          |
| -------- | ------------ | -------------------- |
| Android  | ✅ Supported | API 21 (Android 5.0) |
| iOS      | ✅ Supported | iOS 11.0+            |
| Web      | ✅ Supported | Modern browsers      |
| Windows  | ✅ Supported | Windows 10+          |
| macOS    | ✅ Supported | macOS 10.11+         |
| Linux    | ✅ Supported | Ubuntu 16.04+        |

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

## 📞 Support & Contact

For support, issues, or questions:

- **Email**: [Your Contact Email]
- **Issues**: [GitHub Issues](../../issues)
- **Documentation**: [Flutter Docs](https://flutter.dev/docs)

---

## 🙏 Acknowledgments

- Flutter team for the amazing framework
- Contributors and community members
- Agricultural AI research community

---

**Made with ❤️ for farmers and agricultural innovators**
