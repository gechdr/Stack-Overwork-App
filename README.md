# 🔥 Stack Overwork

<div align="center">

![Android](https://img.shields.io/badge/Android-3DDC84?logo=android&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-1.9.0-7F52FF?logo=kotlin&logoColor=white)
![SDK](https://img.shields.io/badge/SDK-34-brightgreen)
![Room](https://img.shields.io/badge/Room-2.6.1-blue)
![License](https://img.shields.io/badge/license-MIT-green.svg)

**A Stack Overflow-inspired Q&A Android application built with Kotlin and Room Database**

[Features](#-features) • [Screenshots](#-screenshots) • [Installation](#-installation) • [Architecture](#-architecture) • [Contributing](#-contributing)

</div>

---

## 📖 Overview

Stack Overwork is a native Android application that replicates the core functionality of Stack Overflow. Users can register, login, ask questions, browse questions from other users, and provide answers. All data is stored locally using Room Database, making it work completely offline.

Built with modern Android development practices including Kotlin Coroutines, View Binding, Data Binding, and Material Design components.

## ✨ Features

### 🔐 Authentication
- **User Registration** - Create new accounts with username, password, name, and phone number
- **User Login** - Secure login with username and password validation
- **Session Management** - User sessions persist across activities

### ❓ Questions
- **Ask Questions** - Post questions with:
  - Title
  - Detailed description
  - Effort/What you've tried
  - Tags (exactly 2 required, no duplicates)
  - Automatic date stamping
- **Browse Questions** - View all questions in a scrollable list
- **Search Questions** - Real-time search filtering by question content
- **Question Details** - View full question information including all answers

### 💬 Answers
- **Post Answers** - Respond to any question
- **View Answers** - See all answers for a question
- **Answer Count** - Track the number of answers per question

### 👤 User Profile
- **View Profile** - See your display name and question count
- **My Questions** - Browse only your own questions
- **Search My Questions** - Filter through your questions

### 🎨 UI/UX
- **Material Design** - Modern, clean interface following Material Design guidelines
- **Dark Mode Support** - Theme support for dark mode
- **Responsive Layout** - Adapts to different screen sizes
- **Tag Display** - Visual tag chips for question categorization

## 📱 Screenshots

| Login | Register | Home |
|:---:|:---:|:---:|
| ![Login](screenshots/login.png) | ![Register](screenshots/register.png) | ![Home](screenshots/home.png) |

| Ask Question | Question Detail | Profile |
|:---:|:---:|:---:|
| ![Ask](screenshots/ask.png) | ![Detail](screenshots/detail.png) | ![Profile](screenshots/profile.png) |

> **Note**: Add your own screenshots to the `screenshots/` folder

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| [Kotlin](https://kotlinlang.org/) | Primary programming language |
| [Room Database](https://developer.android.com/training/data-storage/room) | Local SQLite database abstraction |
| [Coroutines](https://kotlinlang.org/docs/coroutines-overview.html) | Asynchronous programming |
| [View Binding](https://developer.android.com/topic/libraries/view-binding) | Type-safe view access |
| [Data Binding](https://developer.android.com/topic/libraries/data-binding) | Declarative UI binding |
| [Material Components](https://material.io/develop/android) | UI components and theming |
| [RecyclerView](https://developer.android.com/guide/topics/ui/layout/recyclerview) | Efficient list display |
| [ConstraintLayout](https://developer.android.com/training/constraint-layout) | Flexible UI layouts |

## 📋 Requirements

- **Android Studio**: Hedgehog (2023.1.1) or later
- **Minimum SDK**: API 34 (Android 14)
- **Target SDK**: API 34
- **JDK**: 1.8+
- **Gradle**: 8.3.0

## 🚀 Installation

### Clone the Repository

```bash
git clone https://github.com/yourusername/Stack-Overwork-App.git
cd Stack-Overwork-App
```

### Open in Android Studio

1. Launch **Android Studio**
2. Select **File > Open**
3. Navigate to the cloned repository
4. Click **OK** and wait for Gradle sync

### Build and Run

```bash
# Build the project
./gradlew build

# Install on connected device/emulator
./gradlew installDebug
```

Or simply click the **Run** button (▶️) in Android Studio.

## 📁 Project Structure

```
Stack-Overwork-App/
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/example/tugasm7_6958/
│   │   │   │   ├── Activities/
│   │   │   │   │   ├── LoginActivity.kt       # User login
│   │   │   │   │   ├── RegisterActivity.kt    # User registration
│   │   │   │   │   ├── HomeActivity.kt        # Main question feed
│   │   │   │   │   ├── AskActivity.kt         # Post new question
│   │   │   │   │   ├── DetailActivity.kt      # Question details & answers
│   │   │   │   │   └── ProfileActivity.kt     # User profile
│   │   │   │   │
│   │   │   │   ├── Database/
│   │   │   │   │   ├── AppDatabase.kt         # Room database configuration
│   │   │   │   │   ├── UserDao.kt             # User data access
│   │   │   │   │   ├── QuestionDao.kt         # Question data access
│   │   │   │   │   └── AnswerDao.kt           # Answer data access
│   │   │   │   │
│   │   │   │   ├── Entities/
│   │   │   │   │   ├── UserEntity.kt          # User data model
│   │   │   │   │   ├── QuestionEntity.kt      # Question data model
│   │   │   │   │   └── AnswerEntity.kt        # Answer data model
│   │   │   │   │
│   │   │   │   └── Adapters/
│   │   │   │       ├── QuestionAdapter.kt     # Question list adapter
│   │   │   │       └── AnswerAdapter.kt       # Answer list adapter
│   │   │   │
│   │   │   ├── res/
│   │   │   │   ├── layout/                    # XML layout files
│   │   │   │   ├── drawable/                  # Icons and shapes
│   │   │   │   ├── menu/                      # Navigation menus
│   │   │   │   ├── values/                    # Colors, strings, themes
│   │   │   │   └── mipmap/                    # App icons
│   │   │   │
│   │   │   └── AndroidManifest.xml
│   │   │
│   │   └── test/                              # Unit tests
│   │
│   └── build.gradle.kts                       # App-level build config
│
├── gradle/
│   ├── libs.versions.toml                     # Dependency versions
│   └── wrapper/
│
├── build.gradle.kts                           # Project-level build config
├── settings.gradle.kts
└── README.md
```

## 🏗️ Architecture

### Database Schema

```
┌─────────────────────────────────────────────────────────────┐
│                         USERS                                │
├─────────────────────────────────────────────────────────────┤
│ username (PK) │ password │ name │ phoneNumber               │
└─────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────┐
│                       QUESTIONS                              │
├─────────────────────────────────────────────────────────────┤
│ id (PK) │ title │ detail │ effort │ tags │ owner │ date │   │
│         │       │        │        │      │       │      │   │
│         │       │        │        │      │       │answers│   │
└─────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────┐
│                        ANSWERS                               │
├─────────────────────────────────────────────────────────────┤
│ id (PK) │ idQuestion (FK) │ answer │ owner                   │
└─────────────────────────────────────────────────────────────┘
```

### App Flow

```
┌─────────────┐     ┌──────────────┐     ┌─────────────┐
│   Login     │────▶│    Home      │────▶│   Detail    │
│  Activity   │     │   Activity   │     │  Activity   │
└─────────────┘     └──────────────┘     └─────────────┘
      │                    │                    │
      ▼                    ▼                    ▼
┌─────────────┐     ┌──────────────┐     Post Answer
│  Register   │     │     Ask      │
│  Activity   │     │   Activity   │
└─────────────┘     └──────────────┘
                           │
                           ▼
                    ┌──────────────┐
                    │   Profile    │
                    │   Activity   │
                    └──────────────┘
```

## 📝 Data Models

### UserEntity
```kotlin
data class UserEntity(
    val username: String,      // Primary Key
    var password: String,
    val name: String,
    val phoneNumber: String
)
```

### QuestionEntity
```kotlin
data class QuestionEntity(
    val id: Int,              // Primary Key (auto-generated)
    val title: String,
    val detail: String,
    val effort: String,
    val tags: String,         // Comma-separated tags
    val owner: String,        // Username of author
    val date: String,         // DD-MM-YYYY format
    val answers: Int = 0      // Answer count
)
```

### AnswerEntity
```kotlin
data class AnswerEntity(
    val id: Int,              // Primary Key (auto-generated)
    val idQuestion: Int,      // Foreign Key to Question
    val answer: String,
    val owner: String         // Username of answerer
)
```

## 🔧 Configuration

### Changing Minimum SDK

Edit `app/build.gradle.kts`:

```kotlin
android {
    defaultConfig {
        minSdk = 24  // Change from 34 to support older devices
    }
}
```

### Customizing Theme

Edit `app/src/main/res/values/themes.xml`:

```xml
<style name="Theme.TugasM7_6958" parent="Theme.MaterialComponents.DayNight.DarkActionBar">
    <item name="colorPrimary">@color/your_primary_color</item>
    <item name="colorPrimaryVariant">@color/your_primary_variant</item>
    <item name="colorOnPrimary">@color/white</item>
</style>
```

## 🧪 Testing

### Run Unit Tests

```bash
./gradlew test
```

### Run Instrumented Tests

```bash
./gradlew connectedAndroidTest
```

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/AmazingFeature`)
3. **Commit** your changes (`git commit -m 'Add AmazingFeature'`)
4. **Push** to the branch (`git push origin feature/AmazingFeature`)
5. **Open** a Pull Request

### Development Guidelines

- Follow Kotlin coding conventions
- Use meaningful commit messages
- Add comments for complex logic
- Update README for new features
- Write tests for new functionality

### Feature Ideas

- [ ] Vote/Like system for questions and answers
- [ ] Accept answer functionality
- [ ] User reputation system
- [ ] Image attachments for questions
- [ ] Markdown support in questions/answers
- [ ] Push notifications for answers
- [ ] Share question functionality
- [ ] Bookmark questions
- [ ] Comment on answers
- [ ] Edit/Delete own questions and answers
- [ ] Firebase integration for cloud sync
- [ ] Social login (Google, GitHub)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2024

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software...
```

## 🙏 Acknowledgments

- [Stack Overflow](https://stackoverflow.com/) - Inspiration for the app concept
- [Android Developers](https://developer.android.com/) - Official documentation
- [Material Design](https://material.io/) - Design guidelines
- [Kotlin](https://kotlinlang.org/) - Programming language

## 📞 Contact

- **GitHub**: [@gechdr](https://github.com/gechdr)

---

<div align="center">

**Built using Kotlin**

</div>
