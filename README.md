# 🥗 NutriTrack - Android Nutrition & Calorie Tracker App

NutriTrack is a modern, full-featured personal health, nutrition, calorie, and water intake tracker app built natively for Android using **Jetpack Compose**, **Kotlin**, and **Room Database (SQLite)** following modern **Material 3 (M3)** design principles.

---

## 🌟 Key Features

- **5 Dedicated Meal Categories:**
  - 🌅 **Breakfast** (Custom calorie goals, e.g. 500 kcal)
  - ☀️ **Lunch** (Custom calorie goals, e.g. 650 kcal)
  - 🌆 **Evening** (Custom calorie goals, e.g. 400 kcal)
  - 🌙 **Dinner** (Custom calorie goals, e.g. 650 kcal)
  - 🥜 **Extra / Snacks** (Custom calorie goals, e.g. 250 kcal)
- **⚡ Instant Food Logging:**
  - Quick-add popular healthy food items (Oats, Eggs, Rice & Dal, Paneer/Chicken, Sattu, Salads, Fruits).
  - Custom food entry with item name, serving size, unit (g, ml, bowl, piece, plate), and exact calorie count.
  - Delete items with automatic recalculation.
- **💧 Smart Hydration Tracking:**
  - Dynamic water intake logging (100ml, 250ml, 500ml quick add & custom input).
  - Daily progress ring tracking toward your target (e.g., 3000 ml).
  - Timestamped hydration log history.
- **📅 Date-Wise History & Calendar:**
  - Seamless day-by-day navigation strip (Previous Day, Today, Next Day).
  - Monthly interactive calendar view with calorie target compliance status.
  - Complete data isolation per day with automatic carry-over of target goals.
- **📊 Analytics & Visual Insights:**
  - Interactive calorie breakdown and weekly trend charts.
  - Water vs. calorie intake correlation comparisons.
  - Personalized nutrition health score and daily motivational insights.
- **👤 User Profile & Custom Targets:**
  - Individual goal customization: Daily Calorie Target, Daily Water Target, and per-meal calorie budgets.
  - Weight tracking and BMI calculator.
  - Dark Mode and Light Mode support with smooth theme transitions.
- **🔒 Local-First SQLite Persistence:**
  - Fast, fully offline, and secure data storage using Android Room Database.
  - Multi-user authentication & profile isolation support.

---

## 🛠️ Architecture & Tech Stack

| Component | Technology |
|---|---|
| **Language** | Kotlin 100% |
| **UI Framework** | Jetpack Compose (Declarative Android UI) |
| **Design System** | Material Design 3 (M3) |
| **Database** | Android Room Database (SQLite) + KSP |
| **Architecture** | Clean MVVM (Model - View - ViewModel) + Repository Pattern |
| **Async & Reactive** | Kotlin Coroutines & `StateFlow` |
| **Local Preferences** | Android DataStore / Encrypted Shared Preferences |
| **Build System** | Gradle (Kotlin DSL - `build.gradle.kts`) |
| **Minimum SDK** | Android 8.0 (API Level 26) |
| **Target SDK** | Android 14 / 15 (API Level 34+) |

---

## 📂 Project Structure

```text
app/src/main/java/com/example/
├── MainActivity.kt                  # App Entry Point & Screen Orchestration
├── data/                            # Database Entities, DAOs, Database & Repository
│   ├── UserEntity.kt                # User Profile & Meal Target Settings
│   ├── MealItemEntity.kt            # Meal items logged by date & category
│   ├── WaterEntryEntity.kt          # Water entries logged with timestamps
│   ├── DailyRecordEntity.kt         # Daily summary records
│   ├── NutriTrackDao.kt             # Room Database Queries (Flow-based)
│   ├── NutriTrackDatabase.kt        # Room Database Definition
│   ├── NutriTrackRepository.kt      # Clean Repository Layer
│   └── SessionManager.kt            # User session & auth state
├── model/                           # Domain Enums & Models
│   └── NutriModels.kt               # MealType (Breakfast, Lunch, Evening, Dinner, Extra)
├── ui/
│   ├── NutriTrackViewModel.kt       # ViewModel handling business logic & StateFlow
│   ├── components/                  # Reusable Jetpack Compose Components
│   │   ├── NutriTrackHeader.kt      # Top bar with Date picker & PRO branding
│   │   ├── NutriTrackNavBar.kt      # Bottom Navigation Bar
│   │   ├── MealCard.kt              # Expandable 5-meal cards with progress bars
│   │   ├── AddFoodBottomSheet.kt    # Quick & custom food logging bottom sheet
│   │   ├── CalorieOverviewCard.kt   # Daily progress summary ring
│   │   ├── WaterOverviewCard.kt     # Hydration tracker card
│   │   ├── InteractiveCharts.kt     # Weekly & monthly analytics charts
│   │   └── MonthlyCalendarView.kt   # Calendar for date-based records
│   ├── screens/                     # Main App Screens
│   │   ├── DashboardScreen.kt       # Main Dashboard view
│   │   ├── DailyLogScreen.kt        # Daily meals & log breakdown
│   │   ├── AnalyticsScreen.kt       # Charts and trend analysis
│   │   ├── WaterScreen.kt           # Detailed hydration logger
│   │   ├── HistoryScreen.kt         # Past days and calendar logs
│   │   ├── ProfileScreen.kt         # User profile and custom targets
│   │   └── AuthScreens.kt           # Login and Registration screens
│   └── theme/                       # Design System Colors, Typography & Shapes
│       ├── Color.kt
│       ├── Theme.kt
│       └── Type.kt
└── util/
    └── DateUtils.kt                 # Date formatting & calendar utilities
```

---

## 🚀 How to Run the Project Locally

1. **Clone the repository:**
   ```bash
   git clone https://github.com/YOUR_USERNAME/NutriTrack.git
   cd NutriTrack
   ```

2. **Open in Android Studio:**
   - Launch **Android Studio** (Ladybug, Koala, Hedgehog, or newer).
   - Select **Open an Existing Project** and choose the cloned `NutriTrack` folder.
   - Wait for Gradle to finish syncing dependencies.

3. **Run on Device or Emulator:**
   - Connect an Android device (with USB Debugging enabled) or start an Android Emulator.
   - Click the green **Run (▶️)** button in Android Studio or press `Shift + F10`.

---

## 🧪 Testing

Run JVM unit and Robolectric tests:
```bash
./gradlew testDebugUnitTest
```

---

## 📄 License
This project is open-source under the [MIT License](LICENSE).
