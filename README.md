# 🎖️ BFT Calculator

## Know Your Basic Fitness Test Requirement for GAF

An application for calculating and tracking Basic Fitness Test (BFT) requirements for the Ghana Armed Forces (GAF). Get your pass mark requirements based on age and gender, or calculate your BFT percentage and performance level.

## 📥 Download the App

The latest release is available on GitHub Releases.

- Release page: [TrialApps](https://github.com/jackbalo/bft_calculator_with_chart/releases/tag/TrialApps)
- Android APK (arm64-v8a): [Download](https://github.com/jackbalo/bft_calculator_with_chart/releases/download/TrialApps/app-arm64-v8a-release.apk)
- Android APK (armeabi-v7a): [Download](https://github.com/jackbalo/bft_calculator_with_chart/releases/download/TrialApps/app-armeabi-v7a-release.apk)
- Android APK (x86_64): [Download](https://github.com/jackbalo/bft_calculator_with_chart/releases/download/TrialApps/app-x86_64-release.apk)
- Windows executable: [Download](https://github.com/jackbalo/bft_calculator_with_chart/releases/download/TrialApps/BFTCalculator.exe)

> These binaries are published as GitHub Release assets, so users can click directly to download the latest APK or EXE without cloning the repository.

## 📸 Screenshots

Screenshots coming soon - showing the main input page, pass mark requirements, and percentage calculator results.

---

## ✨ Features

### 1. **Pass Mark Checker**

- Enter your age and gender to instantly see your BFT pass mark requirements
- Supports ages 18-60 with specific age categories
- View minimum scores for:
  - Push-ups (2-minute test)
  - Sit-ups (2-minute test)
  - 3.2 km running time
- Different standards for male and female candidates

### 2. **BFT Percentage Calculator**

- Input your actual performance scores
- Automatically calculate your percentage for each exercise
- Get an average BFT percentage score
- Visual progress indicators showing performance level:
  - 🟢 Green (80%+): Excellent
  - 🔵 Blue (60-79%): Good
  - 🟠 Orange (<60%): Needs improvement

## 🚀 Getting Started

### Prerequisites

Before you begin, ensure you have the following installed:

- **Flutter SDK**: Version ^3.12.2 or higher
  - [Install Flutter](https://flutter.dev/docs/get-started/install)
- **Dart SDK**: ^3.12.2 (included with Flutter)
- **Git**: For version control
- **Platform-specific requirements**:
  - **Android**: Android SDK 36+ (API level 36+), Android Gradle Plugin 8.0+
  - **iOS**: Xcode 14.0+ (macOS 12.0+)
  - **Windows**: Windows 10+ with Visual Studio Build Tools

### Clone the Repository

```bash
git clone https://github.com/jackbalo/bft_calculator_with_chart.git
cd bft_calculator_with_chart
```

### Install Dependencies

```bash
flutter pub get
```

### Run the App

```bash
# Run on default device/emulator
flutter run

# Run on specific device
flutter run -d <device-id>

# Run in release mode
flutter run --release
```

---

## 📦 Dependencies

The project uses the following key dependencies:

- **flutter**: Core Flutter framework with Material Design 3 support
- **google_fonts** (^8.2.1): Beautiful custom fonts (using Poppins font family)
- **flutter_lints** (^6.0.0): Dart code linting rules (dev dependency)
- **flutter_launcher_icons** (^0.13.1): Custom app icon configuration (dev dependency)

All dependencies are defined in `pubspec.yaml`.

---

## 📖 How to Use

### Step 1: Enter Your Information

1. Launch the app
2. Select your **Gender** (Male or Female) from the dropdown
3. Enter your **Age** (must be between 18 and 60)
4. Tap the **Proceed** button

### Step 2: Choose an Action

Once your information is validated, you'll see two options:

#### Option A: **Check BFT Pass Mark** ✓

- View the minimum scores required to pass at 60% (passmark)
- Displays your age category and requirements for:
  - Push-ups count
  - Sit-ups count
  - 3.2 km running time
- Helps you understand what you need to achieve to pass

#### Option B: **Calculate BFT Percentage** 📊

- Enter your actual performance scores:
  - Push-ups completed (count)
  - Sit-ups completed (count)
  - Running time (minutes, supports decimals like 15.5)
- Tap **Calculate** to see your results
- Results include:
  - Individual percentage for each exercise
  - Overall average BFT percentage
  - Visual progress bars for easy interpretation

### Step 3: View Results

- See color-coded percentages (Green > Blue > Orange)
- Navigate back to check different scores or start over with a new user

---

## 🏋️ BFT Scoring System

The BFT percentage calculation follows this logic:

### Passing Mark (60%)

- **60% baseline**: This is the minimum score to "pass" the BFT test
- For each exercise, the pass mark represents 60% achievement

### Scoring Formula

#### Push-ups & Sit-ups

```Percentage = 60 + (Your Score - Pass Mark Score)
Capped at: 0% minimum, 100% maximum
```

**Example:**

- Pass mark push-ups: 42
- Your push-ups: 50
- Your percentage: 60 + (50 - 42) = **68%**

#### Running (3.2 km)

```Percentage = 60 + (Seconds Saved / 60) × 10
```

**Example:**

- Pass mark time: 15:54 (954 seconds)
- Your time: 14:54 (894 seconds)
- Seconds saved: 60 seconds
- Your percentage: 60 + (60 / 60) × 10 = **70%**

### Final Score

```Average Percentage = (Push-ups % + Sit-ups % + Running %) / 3
```

---

## 🏗️ Project Structure

```
lib/
├── main.dart                          # Application entry point
├── config/
│   └── theme.dart                     # Material Design 3 theme configuration
├── constants/
│   ├── app_constants.dart             # Colors, spacing, radius, strings
│   └── bft_standards.dart             # BFT pass mark standards by age/gender
├── models/
│   └── bft_user_data.dart             # User data transfer object
├── screens/
│   ├── input_page.dart                # Gender/age input screen
│   ├── pass_mark_detail_page.dart     # Options menu (check or calculate)
│   ├── check_pass_mark_page.dart      # Display pass mark requirements
│   └── bft_calculator_page.dart       # Main calculator screen
├── utils/
│   └── bft_calculator_utils.dart      # Calculation and validation logic
└── widgets/
    ├── result_row.dart                # Reusable label-value display
    └── percentage_row.dart            # Reusable percentage display with progress bar

assets/
├── gaf.png                            # GAF logo (launcher icon)
├── gaf2.jpg                           # GAF background
├── gaf3.jpg                           # GAF background
├── t1.jpg                             # Background - sit-ups exercise
├── t2.jpg                             # Background - push-ups form
├── t3.jpg                             # Background - general BFT
├── t4.jpg                             # Background - outdoor setting
├── t5.jpg                             # Background - running activity
└── t5.jpg                             # Background - running activity

pubspec.yaml                           # Project configuration and dependencies
```

### Key Data Models

#### `BftUserData`

Stores user information across pages:

- `age`: User's age (18-60)
- `gender`: User's gender (male/female)
- `ageCategory`: Age range category (e.g., "18-21")
- `pushupsMark`: Pass mark for push-ups
- `situpsMark`: Pass mark for sit-ups
- `runTimeMark`: Pass mark for 3.2 km run (format: "MM:SS")

---

## 📊 BFT Standards

### Male Standards by Age Category

| Age Range | Pushups | Sit-ups | 3.2 km Run |
|-----------|---------|---------|-----------|
| 18-21     | 42      | 52      | 15:54     |
| 22-26     | 40      | 47      | 16:36     |
| 27-31     | 38      | 42      | 17:18     |
| 32-36     | 33      | 38      | 18:00     |
| 37-41     | 32      | 33      | 18:42     |
| 42-46     | 26      | 29      | 19:06     |
| 47-51     | 22      | 27      | 19:36     |
| 52-56     | 16      | 26      | 20:00     |

### Female Standards by Age Category

| Age Range | Pushups | Sit-ups | 3.2 km Run |
|-----------|---------|---------|-----------|
| 18-21     | 18      | 50      | 18:54     |
| 22-26     | 16      | 45      | 19:36     |
| 27-31     | 15      | 40      | 19:42     |
| 32-36     | 14      | 35      | 22:36     |
| 37-41     | 13      | 30      | 23:36     |
| 42-46     | 12      | 27      | 24:00     |
| 47-51     | 10      | 24      | 24:30     |
| 52-56     | 9       | 22      | 25:00     |

---

## 🎨 App Configuration

### Theme Colors (GAF Branding)

- **Military Red**: `#B71C1C` (Primary action color)
- **Gold**: `#D4A017` (Accent color)
- **Navy**: `#1A3A52` (Secondary color)
- **Green**: `#4CAF50` (Success indicator)
- **Background**: `#F5F5F5` (Light neutral)
- **Surface**: `#FFFFFF` (White)

### Typography

- **Font Family**: Poppins (via Google Fonts)
- **Material Design**: Version 3 enabled
- **Input Decoration**: Rounded corners (14px radius)
- **Text Styling**: Custom weights (600, 700) for hierarchy

### Visual Elements

- **Left-aligned AppBar titles** for consistent visual hierarchy
- **56px minimum button height** for accessibility
- **Semi-transparent dark overlays** on background images (55% opacity)
- **Color-coded progress indicators** (Green ≥80%, Blue ≥60%, Orange <60%)

---

## 🛠️ Platform-Specific Build Instructions

### Android

#### Prerequisites

- Android SDK 36+ (API level 36+)
- Android Gradle Plugin 8.0+
- Gradle 8.0+

#### Configuration in `pubspec.yaml`

```yaml
flutter_launcher_icons:
  android: "launcher_icon"
  image_path: "assets/gaf.png"
  min_sdk_android: 36
```

#### Build & Deploy

```bash
# Generate launcher icon
flutter pub run flutter_launcher_icons

# Build APK (debug)
flutter build apk --debug

# Build APK (release)
flutter build apk --release

# Build App Bundle (for Google Play)
flutter build appbundle --release
```

**Output locations:**

- APK: `build/app/outputs/flutter-apk/app-release.apk`
- App Bundle: `build/app/outputs/bundle/release/app-release.aab`

### iOS

#### Prerequisites

- Xcode 14.0 or higher
- macOS 12.0 or higher
- iOS 11.0 or higher deployment target

#### Build & Deploy

```bash
# Generate launcher icon for iOS
flutter pub run flutter_launcher_icons

# Build iOS app (debug)
flutter build ios --debug

# Build iOS app (release)
flutter build ios --release

# Build for App Store
flutter build ipa --release
```

**Output location:** `build/ios/iphoneos/Runner.app`

### Windows

#### Prerequisites

- Windows 10 or higher
- Visual Studio with C++ build tools
- CMake 3.10+

#### Build & Deploy

```bash
# Enable Windows desktop development
flutter config --enable-windows-desktop

# Build Windows app (debug)
flutter build windows --debug

# Build Windows app (release)
flutter build windows --release
```

**Output location:** `build/windows/runner/Release/`

---

## 🔧 Development

### Running Tests

```bash
# Run all tests
flutter test

# Run tests with coverage
flutter test --coverage
```

### Generate App Icons

```bash
flutter pub run flutter_launcher_icons
```

The app uses `assets/gaf.png` as the source icon for all platforms.

---

## 🚀 Future Enhancements

Potential features for future versions:

- [ ] User profile and score history tracking
- [ ] Progress graphs and trend analysis
- [ ] Notifications and reminders for training
- [ ] Integration with fitness tracking devices
- [ ] Multi-language support (English, Twi, Hausa, etc.)
- [ ] Dark mode theme support
- [ ] Share results functionality
- [ ] Offline scoring database
- [ ] Training plan recommendations based on scores
- [ ] Social sharing and leaderboards

---

## 📄 License

This project is licensed under the **MIT License** - see below for details.

```text
MIT License

Copyright (c) 2024 BFT Calculator Contributors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 📞 Support & Feedback

For issues, bug reports, or feature requests, please open an issue on the project repository.

---

## 🙏 Acknowledgments

- **Ghana Armed Forces (GAF)**: For BFT standards and specifications
- **Flutter Team**: For the excellent Flutter framework
- **Google Fonts**: For the Poppins font family
- **Material Design**: For design guidelines and components

---

**Version**: 0.1.0+1  
**Last Updated**: August 2024  
**Flutter SDK**: ^3.12.2
